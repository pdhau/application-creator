---
name: application-creator
description: Plan, scaffold, build, and iterate on substantial React applications across multiple sessions. Use for new product ideas, end-to-end React application work, roadmap planning, or ongoing work in a React project. Do not use for a tiny prototype when quick-react-app is sufficient or for a narrowly specified change that add-react-feature covers.
---

# Application Creator

Guide a React product from intent to verified release while preserving the user's product decisions and the conventions of an existing codebase.

## Route the request

- For a new substantial product, use the lifecycle below.
- For a one-session prototype with a narrow happy path, use `quick-react-app`.
- For a bounded change in an existing app, use `add-react-feature`.
- For an open-ended quality pass, use `improve-react-app`.
- For read-only analysis, use `review-react-app`.

Load `react-architecture`, `react-ui-system`, or `react-qa` only when that part of the work is active.

## Lifecycle

### 1. Recover or define product intent

In an existing project, first read the package manifest, repository guidance, current documentation, routes, and feature structure. Prefer existing decisions over this skill's defaults.

For a new project, resolve only decisions that materially alter the implementation:

- target users and primary job;
- the smallest end-to-end journey that proves value;
- required routes and data sources;
- authentication, roles, persistence, and external integrations;
- responsive targets, accessibility needs, and deployment constraints.

Do not manufacture backend contracts, credentials, brand assets, or legal copy. Use explicit adapters or realistic fixtures where the real dependency is unavailable.

For work expected to span sessions, create the lean project memory described in [references/project-memory.md](references/project-memory.md). Keep it proportional; a small app does not need ceremonial documentation.

### 2. Choose the stack from requirements

Respect the user's framework choice and the existing project. For a new client-rendered web app with no contrary requirements, prefer React, TypeScript, and the current official Vite React scaffolder. Choose a React framework when server rendering, server routes, streaming, or framework-native data loading materially helps.

Verify current setup commands in official documentation before scaffolding because versions and defaults change. Use the official scaffolder instead of hand-writing package and bundler configuration.

Record consequential choices, including why alternatives were rejected. Do not add libraries merely to match a preferred stack.

### 3. Plan vertical slices

Define a thin shell and one complete user journey before broad feature coverage. Each slice should include:

- user-visible acceptance criteria;
- route and component impact;
- data contract and ownership;
- loading, empty, error, success, and permission states;
- accessibility and responsive behavior;
- focused verification.

Keep unrelated requests in the backlog rather than partially implementing all of them.

### 4. Scaffold and establish foundations

After the target directory and stack are known:

1. Run the official scaffolder and install only justified dependencies.
2. Confirm development and production commands work.
3. Establish route boundaries, app providers, styling approach, and test harness.
4. Add an error boundary and not-found behavior where the stack supports them.
5. Create an `.env.example` with variable names only; never place secrets in source.
6. Create a project-root `AGENTS.md` from [references/react-project-agents.md](references/react-project-agents.md), filling in the real commands and local conventions.
7. Implement a thin application shell and one working route before extracting abstractions.

Do not replace a project's architecture, package manager, or styling system unless the user requested that migration.

### 5. Implement in small verified slices

For each slice:

1. Make acceptance criteria executable where practical.
2. Model domain types and boundary validation.
3. Implement data access behind a clear boundary.
4. Build accessible UI states and interactions.
5. Keep state at the narrowest responsible owner.
6. Verify the slice before starting the next one.
7. Update project memory with decisions, completed work, and remaining risk.

Use `add-react-feature` for the detailed change workflow and `react-architecture` for architecture decisions.

### 6. Quality gate

After every meaningful code-changing slice, run the checks the project supports, normally in this order:

1. typecheck;
2. lint or static analysis;
3. focused unit/component tests;
4. production build;
5. runtime or end-to-end smoke for affected journeys;
6. accessibility checks for affected UI;
7. visual inspection at representative mobile and desktop widths when appearance changed.

Do not weaken assertions or hide errors to obtain a green result. Retry fixes up to three focused rounds; then report the remaining blocker with evidence.

### 7. Release readiness

Before calling the application ready, confirm:

- primary journeys and negative states work;
- no secrets or private data are bundled;
- deep links and refreshes resolve correctly;
- error and not-found states are useful;
- keyboard navigation, labels, focus, and contrast are acceptable;
- responsive layouts do not overflow at supported widths;
- monitoring, analytics, privacy, and deployment settings match the user's requirements;
- the production build is reproducible.

Use `deploy-react-app` only when the user asks to publish or deploy.

## Completion report

Lead with the working outcome. Summarize important decisions, changed areas, checks performed and their results, known limitations, and the exact next user-visible verification step.
