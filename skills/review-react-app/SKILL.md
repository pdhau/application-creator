---
name: review-react-app
description: Perform a read-only review of a React application for correctness, architecture, state and data flow, accessibility, performance, security boundaries, and test confidence. Use for code review, architecture review, or release-readiness assessment. Do not modify files unless the user separately asks for fixes.
---

# Review React App

Load `react-architecture`; load `react-ui-system` or `react-qa` only when needed by the review scope.

## Review process

1. Read repository instructions, package scripts, framework and TypeScript configuration.
2. Map routes, providers, features, shared modules, data adapters, and tests.
3. Trace the most important user journeys through UI, state, network, and error handling.
4. Run non-mutating checks that provide evidence, such as typecheck, lint, tests, and build, when practical.
5. Inspect rendered behavior only when the app can be run safely; include mobile, keyboard, and accessibility checks for UI findings.

## Priorities

Prioritize defects that cause incorrect behavior, data loss, security or privacy exposure, inaccessible journeys, production failures, or maintainability hazards with a concrete failure mode. Do not fill the report with stylistic preferences.

Common React review targets include stale closures, effect races and missing cleanup, duplicated sources of truth, unsafe optimistic updates, cache invalidation errors, route authorization assumptions, unhandled async states, uncontrolled/controlled form mistakes, unstable list identity, unnecessary rerender cascades, bundle waterfalls, and brittle tests.

## Output

List findings in descending severity. Each actionable finding must include a concise title, why it matters, the exact file and line, a realistic trigger, and a recommended direction. Distinguish confirmed defects from risks or suggestions.

After findings, include the checks run and their results, then a short architecture and test-coverage assessment. If no actionable findings exist, say so and name any verification gaps.
