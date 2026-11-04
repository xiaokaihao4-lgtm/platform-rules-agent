# Ozon API Method Map

This page is the compact site-level map of Ozon API methods.
It works together with `api-connection-patterns.md`.

## Families

- Query / list
  - list campaigns
  - list goods
  - list orders
  - list balances / documents
  - list returns / claims / reviews
  - list performance entities

- Action / mutation
  - activate / pause
  - edit / update
  - add / remove
  - close / delete
  - change budget / bid / strategy
  - change campaign configuration

- Result / settlement
  - execution status
  - final effect
  - report / document generation
  - settlement / reconciliation result
  - delivery / accounting / document outcome

- Audit / history
  - change history
  - version history
  - current state vs historical state
  - actor / source / effective time
  - configuration history

- Async / acceptance
  - accepted
  - pending
  - completed later
  - background update
  - delayed effect

## Reading order

1. identify the method family
2. identify the entity scope
3. identify the state transition
4. identify whether the result is final or only accepted
5. only then discuss project integration
