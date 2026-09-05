# 🧠 WB 后台访问行为规范（2026-08-22 全团队执行）

> **为什么这份规范存在**：曾出现两个问题——①多个任务抢同一浏览器 profile 互相锁死；②脚本删锁文件导致用户反复重新登录。本文档是根因分析 + 统一行为标准，**所有 WB 相关 Agent 必须遵守**。

---

## 一、根因分析：为什么有的 Agent 做得好，有的做不好

### ✅ 做得好的（WB 规则研究 Agent）——做对了什么

1. **读规则用 curl，不碰浏览器**：`curl -sL URL -o 文件` 直接抓取，零浏览器、零 profile、零冲突
2. **需要登录时才开浏览器**：拉后台数据才用 Playwright，且一次只开一个
3. **正常 `context.close()` 收尾**：让登录态写回磁盘，绝不 kill -9
4. **绝不删锁文件**：脚本里根本没有 cleanProfileLocks 这类函数
5. **开任务前先查占用**：`ps aux | grep wb_chrome_profile`，有残留就等，不硬闯

### ❌ 做得不好的（其他脚本）——错在哪里

1. **脚本里残留 `cleanProfileLocks()`**：这个函数删除 SingletonLock/SingletonCookie 锁文件 → **删锁 = 登录态记录丢失 = 用户被迫重新登录**（这是"老是让我重新登录"的代码级根因）
2. **并发抢同一 profile**：两个脚本同时 `launchPersistentContext` 同一个 profile → 互相锁死 → 都打不开
3. **报错就强杀进程**：遇到占用就用 kill/pkill，杀完登录态没写回磁盘 → 下次要重新登录

### 🔑 核心区别一句话

> **做得好 = 不碰浏览器就能不碰；必须碰时只用一个、正常关、绝不删锁。**
> **做不好 = 动不动就开浏览器、一遇冲突就删锁/杀进程。**

---

## 二、统一行为标准（全部 Agent 遵守）

### 1. 能不开浏览器就不开

| 任务类型 | 正确方式 | 错误方式 |
|---------|---------|---------|
| 读平台规则/帮助中心 | `curl` 直接抓取 | 开 Playwright 抓 |
| 查本地知识库 | `read_file` / `search_files` | 开浏览器 |
| 只有拉后台数据 | Playwright + profile | — |

### 2. 必须开浏览器时（铁律）

```javascript
// ✅ 正确写法
const context = await chromium.launchPersistentContext(USER_DATA_DIR, {
  executablePath: CHROME_BIN,
  headless: false,        // 必须非无头（headless 不加载登录 cookie）
  args: ["--no-sandbox"],
});
// ... 操作 ...
await context.close();    // 正常关闭，登录态写回磁盘

// ❌ 绝对禁止
// await fs.unlinkSync(SingletonLock)   ← 删锁 = 退登
// process.kill(pid)                    ← 强杀 = 丢登录态
```

### 3. 并发冲突处理（重要！）

```
报错 "正在现有的浏览器会话中打开" 或 "Target page...closed"
↓
根因：另一个任务正占用该 profile
↓
正确做法：
  1. ps aux | grep wb_chrome_profile 找到占用进程
  2. 如果那个任务还有用 → 等它结束
  3. 如果确认是残留 → kill -TERM（温和退出，让它写回登录态）
  4. 绝不 kill -9、绝不删锁文件
```

### 4. 登录态维护

- 登录态约 1 个月过期 → **每周开一次 WB 后台保活**
- 过期后只能用户手动重登（手机号+验证码）
- 借用户浏览器是最后手段，用完提醒用户保活

---

## 三、检查清单（每个脚本提交前自查）

```
□ 脚本里没有 cleanProfileLocks / unlinkSync(Singleton*) 
□ 没有 kill -9 / pkill / osascript quit Chrome
□ 用了 headless: false（需要登录态时）
□ 有 context.close() 正常收尾
□ 启动前检查了 profile 是否被占用
□ 能 curl 解决的绝不开浏览器
```

## 四、一句话总结

**你负责思考和执行，浏览器是共享资源——能不开就不开，开了只用一个、正常关、绝不删锁。**
