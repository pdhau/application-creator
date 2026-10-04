---
name: react-qa
description: Design and implement pragmatic React testing across unit, component, integration, end-to-end, accessibility, visual, and performance layers. Use when choosing test strategy, writing tests, debugging failures, or building QA infrastructure. This is the reference skill; use qa-react-app for an end-user testing workflow.
---

# React Qa

Build confidence around user behavior with the cheapest test layer that can reliably detect the failure.

## Layer selection

- Unit: pure domain logic, parsers, formatters, reducers, policy functions.
- Component: rendering and interaction with realistic props and accessible queries.
- Integration: a feature with routing, providers, forms, and mocked network boundaries.
- End-to-end: a small set of critical journeys in a real browser.
- Accessibility: automated rules plus keyboard and semantic inspection.
- Visual: deterministic states whose layout or styling is contractually important.
- Performance: measured budgets or regressions, not arbitrary timers in normal unit tests.

Do not duplicate the same assertion at every layer. End-to-end tests should prove journeys, not every branch.

## Testing principles

- Query by role, accessible name, label, and visible text before test IDs.
- Assert observable behavior, not component internals or hook call counts.
- Mock at external boundaries. Prefer MSW-style network interception over mocking a data hook's implementation.
- Control time, randomness, and generated IDs when determinism matters.
- Test errors, empty data, pending requests, permissions, retries, and cancellation where they affect users.
- Keep fixtures small, named, and representative of edge cases.
- Never update a snapshot until the visual change has been inspected and accepted.

## Failure diagnosis

Classify a failure as product bug, stale test, infrastructure/configuration problem, flaky timing, environment mismatch, or intentional requirement change. Reproduce narrowly, inspect the relevant source and contract, then fix the cause. Do not add sleeps, broad retries, or weaker assertions to mask uncertainty.

## Recommended gate

Use the scripts and tools already in the project. A healthy change gate commonly includes typecheck, lint, focused tests, production build, critical browser smoke, accessibility checks, and visual inspection for UI changes.

Keep CI artifacts useful: traces, screenshots, videos, coverage reports, and concise failure logs. Treat flaky tests as failures in the test system and either repair or quarantine them with ownership and a follow-up date.
