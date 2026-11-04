# Performance API Method Map

This page turns Ozon `performance API` into a compact method-family map for skill use.

## 1. Query family

Use this family when the user wants to know what campaigns exist, what state they are in, or which subset matches a filter.

- Typical shape: list / search / filter / paginate
- Example entry: `ListCampaigns`
- What to capture:
  - filter dimensions
  - pagination
  - sorting
  - state fields
  - whether the result is full or partial

## 2. Action family

Use this family when the user wants to change campaign configuration or status.

- Typical shape: activate / pause / edit / add / remove / close
- Example entry: `ActivateCampaign`
- Officially confirmed campaign actions:
  - change campaign budget
  - change auto-increase budget percentage
  - change bid
  - change bid strategy
  - add products
  - remove products
  - close campaign

What to capture:

- request vs accepted vs completed
- whether the action is synchronous or asynchronous
- what state changes are considered final

## 3. Result family

Use this family when the user wants the outcome of a campaign action or the final state after an edit.

- execution time
- returned status
- final effect
- whether the change has actually taken effect

## 4. Audit / history family

Use this family when the user asks what changed, when it changed, who changed it, or whether the current state should be trusted over history.

- change history
- current state vs historical state
- effective time
- actor / source of change

## Skill reading order

When a user asks about `performance API`, answer in this order:

1. identify the family
2. separate query vs action vs result vs audit
3. keep campaign state separate from campaign history
4. only then discuss automation or project integration

