---
name: ozon-university
description: Ozon seller university knowledge for Ozon marketplace FBO operations, product content, finance, promotion, after-sales, training media, updates, and Seller API. Use when answering Ozon business questions, checking project fit, or relating current work to Ozon rules/API; verify current fees, contracts, interface versions, and dynamic rules against official sources before concluding.
---

# Ozon University

Use this skill as the domain guide for Ozon questions and for evaluating whether `ozon-workbench` matches Ozon rules and API behavior.

## Core workflow

1. Identify the business area.
2. Read only the most relevant reference files.
3. Prefer the chapter conclusion first, then the evidence.
4. If the question involves current fees, contracts, interface versions, or any dynamic rule, verify the official source and capture the verification date.
5. Keep facts, versioned rules, and project recommendations separate.

## Chapter selection

- Ozon API cheatsheet: `references/api-method-cheatsheet.md`
- Ozon API method quick lookup: `references/api-method-cheatsheet.md`
- Ozon API connection patterns: `references/api-connection-patterns.md`
- Ozon API method map: `references/api-method-map.md`
- Performance API method map: `references/performance-api-method-map.md`
- Performance API and campaign actions: `references/performance-api.md`
- Product and content project summary: `../Desktop/ozon-workbench/ozon-workbench/docs/ozon-university/03-商品与内容运营-项目版.md`
- FBO fulfillment project summary: `../Desktop/ozon-workbench/ozon-workbench/docs/ozon-university/04-FBO履约与供应-项目版.md`
- Finance project summary: `../Desktop/ozon-workbench/ozon-workbench/docs/ozon-university/05-财务费用与对账-项目版.md`
- Growth project summary: `../Desktop/ozon-workbench/ozon-workbench/docs/ozon-university/06-推广增长与分析-项目版.md`
- After-sales project summary: `../Desktop/ozon-workbench/ozon-workbench/docs/ozon-university/07-售后评价与风控-项目版.md`
- Updates project summary: `../Desktop/ozon-workbench/ozon-workbench/docs/ozon-university/09-更新摘要与动态规则-项目版.md`
- Seller API project summary: `../Desktop/ozon-workbench/ozon-workbench/docs/ozon-university/10-Seller API-项目版.md`
- Performance API project summary: `../Desktop/ozon-workbench/ozon-workbench/docs/ozon-university/11-Performance API-项目版.md`
- Product and content: `references/products.md`
- FBO fulfillment and supply: `references/fbo.md`
- Finance, fees, and reconciliation: `references/finance.md`
- Growth, promotion, and analytics: `references/growth.md`
- After-sales, reviews, and risk: `references/after-sales.md`
- Training media and course/video/live entry points: `references/courses-media.md`
- News, updates, and changing rules: `references/updates.md`
- Seller API and contract constraints: `references/seller-api.md`
- Project fit and implementation implications: `references/project-fit.md`
- Coverage, completeness, and update status: `references/coverage.md`
- Operational checklist: `references/operations-checklist.md`
- Official index and course coverage: `references/official-index.md`

## Project posture

- Treat FBO as the only fulfillment mode for `ozon-workbench`.
- Do not recommend building FBS, rFBS, or FBP operational capabilities into the project.
- Separate facts, official version changes, and project advice.
- Preserve source URLs, effective dates, version notes, and verification timestamps for any dynamic rule.
- Mark any uncertain rule clearly as uncertain; do not guess.

## Seller API questions

1. Read `references/seller-api.md`.
2. Verify method path, HTTP method, permissions, pagination, time boundaries, response shape, and deprecation/contract changes.
3. Distinguish success, async acceptance, partial data, and business completion.
4. Provide rate limits, pagination, time windows, and contract-test suggestions when relevant.

## Project-fit review

1. Read `references/project-fit.md` and the relevant business reference.
2. Check code, data model, sync flows, and page behavior.
3. Answer in the format: official requirement / current state / gap or risk / priority / recommended verification.
4. Prioritize reliable data and the FBO closed loop over raw endpoint count.

## Rules

- Use official sources for current fees, contracts, interface versions, and changing rules.
- Keep historical announcements as history unless the current official page confirms otherwise.
- Avoid mixing promotional language with verified operating rules.
- Prefer read-only evidence and versioned conclusions before any automation recommendation.
