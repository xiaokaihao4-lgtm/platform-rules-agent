# Ozon University — Codex Skill

Ozon 卖家大学知识库的中文蒸馏版本，覆盖 Ozon 电商平台完整经营领域。

## 设计目标

为 Codex/Claude Code 等 AI 编程助手提供结构化的 Ozon 领域知识，使其能够：
- 回答 Ozon 经营问题（FBO、商品、财务、推广、售后等）
- 评估项目实现是否符合 Ozon 规则和 API 行为
- 在实现 Ozon 相关功能时提供准确的领域上下文

## 知识范围

| 领域 | 文件 | 说明 |
|------|------|------|
| 商品与内容 | `references/products.md` | 商品卡、媒体、变体、合并、迁移 |
| FBO 履约 | `references/fbo.md` | 供应、入仓、库存、订单 |
| 财务 | `references/finance.md` | 费用、账单、对账、税务 |
| 推广 | `references/growth.md` | 搜索、促销、分析、获客 |
| 售后 | `references/after-sales.md` | 退货、评价、客服、评级 |
| 合规 | `references/compliance.md` | 合同、规则、质量控制 |
| 课程与媒体 | `references/courses-media.md` | 官方课程、视频、直播入口 |
| 更新 | `references/updates.md` | 官方公告与规则变更追踪 |
| Seller API | `references/seller-api.md` | API 端点、权限、分页、限流 |
| 项目匹配 | `references/project-fit.md` | 对 ozon-workbench 的产品建议 |
| 覆盖状态 | `references/coverage.md` | 蒸馏完成度与维护方式 |
| 官方索引 | `references/official-index.md` | 官方栏目、课程、视频完整账本 |
| 运营清单 | `references/operations-checklist.md` | 卖家运营检查清单 |

## 使用方式

### Codex

将本仓库放到 `~/.codex/skills/ozon-university/`，Codex 会自动加载 `SKILL.md` 和 `agents/openai.yaml`。

### Claude Code

在 `CLAUDE.md` 中引用：

```markdown
@.codex/skills/ozon-university/SKILL.md
```

### 手动查阅

直接阅读 `references/` 下的 Markdown 文件，按业务领域查找。

## 项目定位

- **FBO only**：只覆盖 Ozon 仓发货模式，不建设 FBS/rFBS/跨境操作能力
- **中文蒸馏**：俄文原文规则的结构化中文提炼，保留官方 URL 和版本时间戳
- **持续维护**：费率、API、合同等动态内容需在使用前实时核对官方来源

## 来源

- [Ozon Seller API 文档](https://docs.ozon.ru/api/seller/)
- [Ozon 卖家知识库](https://seller-edu.ozon.ru/)
- [Ozon 官方 YouTube 频道](https://www.youtube.com/@OzonPartners)

## 许可

知识蒸馏内容，来源为 Ozon 官方公开文档。使用时请遵守 Ozon 的服务条款。
