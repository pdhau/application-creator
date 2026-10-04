---
name: react-architecture
description: Design or review scalable React application architecture, including feature boundaries, routing, data access, state ownership, forms, errors, and performance. Use for architectural decisions and implementation guidance in React projects. Do not use as a reason to rewrite a working codebase into one fixed pattern.
---

# React Architecture

Prefer the simplest architecture that makes product changes safe. Existing project conventions and explicit user choices take priority.

## Organize by product feature

Use feature boundaries for substantial applications:

```text
src/
  app/          composition, providers, routes
  features/     user-facing capabilities
  entities/     shared domain concepts when genuinely cross-feature
  shared/       generic UI, utilities, configuration
```

A feature may own components, hooks, schemas, API adapters, tests, and types. Avoid a global `components/`, `hooks/`, or `utils/` dumping ground. Small applications can remain flat until real boundaries emerge.

## State ownership

Classify state before selecting a tool:

- URL state: navigation, shareable filters, pagination, selected resources.
- Server state: remote data, cache, request lifecycle, synchronization.
- Form state: draft values, validation, submission state.
- Shared client state: authenticated user, theme, local workflow state.
- Local UI state: disclosure, focus, a component's temporary interaction.

Keep state at the narrowest owner. Do not mirror server or URL state into a global client store without a demonstrated need. Prefer derived values over synchronized duplicate state.

## Boundaries and dependencies

- Keep network and storage details behind adapters that return domain-shaped data.
- Validate untrusted data at boundaries when incorrect shape would cause user-facing failure.
- Prevent feature-to-feature imports that create hidden coupling; move a genuinely shared concept deliberately.
- Keep components focused on rendering and interaction. Put reusable domain orchestration in hooks or services only after reuse or complexity appears.
- Avoid effects for values that can be calculated during render or actions that belong in event handlers.

## Routing and data

- Make route-level ownership explicit and split code at meaningful route or feature boundaries.
- Treat deep links, refreshes, not-found behavior, and authorization as part of route design.
- Put request cancellation, retries, cache policy, and mutation invalidation near the data layer.
- Model loading, empty, error, stale, success, and unauthorized states intentionally.
- Use optimistic updates only when rollback and conflict behavior are defined.

## Forms

- Use semantic controls and native browser behavior before custom abstractions.
- Distinguish client validation from authoritative server validation.
- Preserve user input after recoverable errors.
- Prevent duplicate submission and expose pending state accessibly.
- Focus or summarize invalid fields without trapping keyboard users.

## Errors and observability

- Use route or feature error boundaries where one failure should not blank the whole app.
- Show actionable user messages and retain diagnostic context for logs.
- Do not log secrets, tokens, or sensitive form data.
- Define recovery: retry, edit input, reauthenticate, navigate away, or contact support.

## Performance

Measure before adding memoization. First check request waterfalls, bundle weight, excessive renders, large lists, expensive calculations, image delivery, and blocking third-party scripts. Prefer architectural fixes such as colocated data loading, route splitting, virtualization, and stable state ownership.

## Review checklist

- Dependencies point inward toward stable shared contracts rather than sideways between features.
- State has one authoritative owner.
- Async states and recovery paths are represented.
- Effects have external synchronization responsibilities and cleanup.
- Public feature APIs are narrow.
- Tests cover observable behavior at the cheapest reliable layer.
- Security decisions are enforced by the server, never only hidden in React UI.
