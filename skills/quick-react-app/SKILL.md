---
name: quick-react-app
description: Rapidly create a focused React prototype or small application with one primary journey and pragmatic verification. Use when the user asks for a quick prototype, proof of concept, demo, or small app. Do not use for a production system that needs extensive discovery, migrations, or multi-session milestones.
---

# Quick React App

Turn a clear idea into a runnable application without introducing avoidable product or architecture overhead.

## Workflow

1. Extract the primary user, job, input, output, and success state from the request. Ask only about missing choices that would materially change the result.
2. If starting fresh, verify and use the current official scaffolder. Default to React + TypeScript + Vite for a browser-only prototype unless requirements indicate another React framework.
3. Implement one complete happy path first. Use realistic local fixtures behind a replaceable data adapter when a real backend is out of scope.
4. Include loading, empty, error, and success states for the primary journey.
5. Make the layout responsive and keyboard-operable. Use semantic HTML and visible focus.
6. Add only tests that protect the core behavior: focused unit/component tests and one smoke journey when practical.
7. Run typecheck, lint, tests, and production build if the project exposes them. Inspect the working UI at mobile and desktop widths.

## Constraints

- Reuse the project's dependencies and patterns when adding the prototype inside an existing codebase.
- Do not add authentication, a database, analytics, a state library, or a design-system dependency unless the prompt requires it.
- Do not claim production readiness. Clearly identify fixtures, missing persistence, security assumptions, and integration seams.
- Never deploy unless the user explicitly asks.

Report the runnable outcome, how to start it, what was verified, and what would need to change before production use.
