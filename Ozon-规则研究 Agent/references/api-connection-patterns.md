# Ozon API Connection Patterns

This page is the reusable connection-pattern layer for Ozon API content.

## 1. Discover first

If the page is about finding what exists, what state it is in, or what subset matches a filter, treat it as discovery.

- list / search / filter / paginate
- read-only by default
- use to establish the current state before any mutation

## 2. Mutate second

If the page changes campaign, goods, documents, or configuration state, treat it as a mutation pattern.

- activate / pause / edit / add / remove / close
- request vs accepted vs completed
- final effective state matters more than request success

## 3. Record the outcome

If the API returns a result, a report, a document, or a settlement-like object, treat it as an outcome pattern.

- execution result
- generated document
- settlement / reconciliation output
- effective date and version should be preserved

## 4. Preserve history

If the page describes what changed and when, treat it as history / audit.

- change history
- version history
- current state vs historical state
- source and effective time

## 5. Separate acceptance from completion

If the API accepts a request but finishes later, do not treat acceptance as completion.

- accepted
- pending
- completed later
- poll or follow up if needed

## 6. Prefer stable state boundaries

For skill use, the safest boundary is:

1. current state
2. state transition
3. final outcome
4. history / audit

This keeps the skill from repeating page-level instructions and helps answer all Ozon API pages with the same model.

