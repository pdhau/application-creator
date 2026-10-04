---
name: add-react-feature
description: Add a bounded feature to an existing React application while following its architecture, design system, and tests. Use when the user describes a specific capability, route, form, integration, or workflow to implement. Do not use for visual-only polish or an open-ended audit.
---

# Add React Feature

Implement the requested outcome without silently expanding scope or replacing working conventions.

## 1. Discover the change surface

Read repository guidance, the package manifest, relevant routes, feature modules, shared UI, data adapters, and nearby tests. Trace the existing user journey and identify the smallest coherent vertical slice.

Write down or infer checkable acceptance criteria, including permissions and negative states. If a backend contract is unavailable, keep fixtures behind the same boundary the real integration will use.

## 2. Design before editing

Decide:

- route and navigation impact;
- data source, schema, cache, mutation, and invalidation behavior;
- state owner and URL representation;
- component reuse versus a feature-local component;
- loading, empty, error, success, unauthorized, and offline behavior;
- accessibility, responsive behavior, and analytics implications.

Load `react-architecture` for cross-feature or state decisions and `react-ui-system` for new shared interaction patterns.

## 3. Implement a vertical slice

Start with the boundary types or contract, then data behavior, then UI. Preserve existing inputs after recoverable errors, prevent duplicate actions, and make pending state clear. Keep authorization enforcement on the server boundary even if the UI also hides unavailable actions.

Avoid broad refactors unless they are required for the feature. If one is required, separate the enabling refactor from behavior changes so each is verifiable.

## 4. Verify

Add or update tests at the cheapest reliable layers. Prefer behavior visible to the user over implementation details. Run focused tests first, then the project's typecheck, lint, production build, and affected end-to-end journey. When UI changed, inspect mobile and desktop layouts and perform a keyboard/accessibility pass.

Never loosen an assertion simply because new code fails it. Fix the implementation or, when the requirement intentionally changed, update the test with an explicit reason.

## 5. Hand off

Summarize the user-visible behavior, key implementation decisions, files or areas changed, verification results, and any dependency on unfinished backend, content, credentials, or product decisions.
