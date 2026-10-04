---
name: improve-react-app
description: Audit an existing React application and implement the highest-impact improvements to UX, accessibility, reliability, performance, maintainability, or testing. Use for requests such as improve, polish, clean up, speed up, or fix this app. Do not use for a read-only review or a clearly specified feature.
---

# Improve React App

Improve outcomes, not merely scores or abstractions.

## Audit

Map the package scripts, route tree, feature boundaries, shared UI, data layer, state ownership, error handling, and tests. Run available static checks and a production build. Inspect the primary journeys at representative mobile and desktop widths when the app can run.

Score each relevant area from 1 to 5 with evidence:

- product journey and feedback;
- visual hierarchy and responsive behavior;
- accessibility and keyboard use;
- reliability and error recovery;
- data flow and state ownership;
- maintainability and boundaries;
- performance and bundle/network behavior;
- automated test confidence;
- security and privacy at client boundaries.

Do not infer quality from file names alone. Cite concrete routes, components, measurements, failures, or missing states.

## Prioritize

Rank improvements by user impact, risk reduction, confidence, and effort. If the user asked to implement improvements, choose a coherent top set that fits the request; pause only when the choice would materially change product behavior or requires new authorization.

Avoid aesthetic churn, speculative rewrites, dependency replacement, or memoization without evidence.

## Implement and verify

Make small, reviewable changes. Preserve public behavior unless a change explicitly improves it. Add regression coverage for fixed failures. After each coherent group, run focused checks; finish with typecheck, lint, tests, build, runtime smoke, accessibility, and visual inspection as applicable.

Report before/after evidence where measurable, remaining risks, and the next highest-impact improvement not taken.
