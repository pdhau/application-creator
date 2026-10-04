---
name: react-request-router
description: Route every request about creating, changing, testing, reviewing, improving, designing, or deploying a React application to the correct Application Creator workflow. Use for any React application task before loading a more specific skill.
---

# React Request Router

Classify the request and load the smallest useful instruction set. Do not perform the full task from this router.

## Choose one primary workflow

| User intent | Primary skill |
| --- | --- |
| Create a substantial app, plan a product, or continue multi-session work | `application-creator` |
| Create a quick prototype, demo, or narrow proof of concept | `quick-react-app` |
| Add a specified feature, fix a bug, or change bounded behavior | `add-react-feature` |
| Audit and implement broad improvements | `improve-react-app` |
| Improve visual design, UX, responsiveness, or accessibility | `design-react-app` |
| Add tests, run QA, or diagnose regressions | `qa-react-app` |
| Review without making changes | `review-react-app` |
| Publish or configure hosting after explicit authorization | `deploy-react-app` |

If several intents are present, choose the workflow that owns the requested outcome and load supporting reference skills as needed. Do not run every workflow sequentially by default.

## Load reference skills selectively

- `react-architecture`: architecture, feature boundaries, state ownership, routing, data flow, errors, or performance.
- `react-ui-system`: shared components, tokens, responsive behavior, interactions, or accessibility.
- `react-qa`: test strategy, infrastructure, browser checks, failure classification, or quality gates.

## Specialist-agent mapping

Some plugin hosts recognize the compatibility definitions under `agents/`. In Codex, use these skill equivalents:

- application creator agent -> `application-creator`
- React reviewer agent -> `review-react-app`
- React QA runner agent -> `qa-react-app` plus `react-qa`
- React deployer agent -> `deploy-react-app`

Delegation is optional and depends on the host. The selected skill remains authoritative even when work is delegated.

## Boundary

Do not activate for non-React tasks merely because this plugin is installed. Explicit user instructions override routing defaults. Never infer deployment authorization from a request to build, test, or review.
