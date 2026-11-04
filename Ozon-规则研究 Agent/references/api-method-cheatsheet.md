# Ozon API Method Cheatsheet

Fast answer layer for Ozon API pages.

## 1) Query / list

Use when the page asks what exists or what matches a filter.

Typical signals: list, get, search, catalog, table, current state.

Keep: filters, pagination, sorting, scope, current state dimensions.

## 2) Action / mutation

Use when the page changes something.

Typical signals: activate, pause, edit, update, add, remove, close, delete, change budget, change bid, change strategy.

Keep: request vs accepted vs completed, sync vs async, final effective state.

## 3) Result / settlement

Use when the page is about the output.

Typical signals: execution result, generated document, report, settlement, reconciliation.

Keep: output status, document version, effective date, business completion.

## 4) Audit / history

Use when the page describes what changed over time.

Typical signals: history, version, log, change record, effective time, source.

Keep: historical vs current state, version, actor, effective timestamp.

## 5) Async / acceptance

Use when the API accepts now and finishes later.

Typical signals: accepted, pending, processing, later completion, polling.

Keep: accepted does not mean effective, follow-up status, timeout, retry.

## One-line answer

Classify the page by family first, then entity, then state transition, then final vs accepted result.
