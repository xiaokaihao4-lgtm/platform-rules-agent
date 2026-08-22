# 🌐 电商平台规则研究 Agent（总仓库）

> **多平台电商运营能力包** — 每个平台一个子项目，丢给 AI Agent 即可获得对应平台的完整运营知识。

## 📦 已收录平台

| 子项目 | 平台 | 内容 | 状态 |
|--------|------|------|:---:|
| `WB-规则研究 Agent/` | **Wildberries（WB）** | 平台规则 + 广告方法论 + 诊断 SOP + 运营手册 | ✅ 完整 |
| `Ozon-规则研究 Agent/` | **Ozon（欧众）** | 待研究 | ⏳ 规划中 |

> 后续可扩展：Yandex Market、AliExpress Russia 等。

## 🚀 使用方式

**给 Agent 用：** 把对应子项目文件夹（或其 README 链接）丢给你用的 AI Agent，它会读取 `AGENTS.md` 获得全部能力。

```bash
# 例：让 Agent 获得 WB 平台能力
# 告诉你的 Agent："读取这个仓库的 WB-规则研究 Agent/AGENTS.md"
```

**给人用：** 直接进入对应子项目浏览即可。

## 📁 结构

```
platform-rules-agent/
├── README.md                  ← 本文件（总入口）
├── WB-规则研究 Agent/         ← WB 平台能力包
│   ├── AGENTS.md              ← WB Agent 入口
│   ├── README.md
│   ├── 知识库/                ← 18 份中文规则
│   └── knowledge-base/        ← 原始抓取 JSON
└── Ozon-规则研究 Agent/       ← （规划中）
    └── README.md
```

## ⚠️ 免责

各平台规则随时更新，重大决策以平台官方最新文档为准。更新截止 2026-08。
