# application-creator

An opinionated skill and agent pack for taking a React application from product idea to verified release. It follows the same separation of concerns as [PlayableIntelligence/game-creator](https://github.com/playableintelligence/game-creator): a coordinating workflow, small task-focused skills, specialist agents, and quality gates after code-changing steps.

## Install

Install with a compatible skills client:

```bash
npx skills add <owner>/application-creator
```

Or load this repository as a local Codex plugin.

## Main workflows

| Skill | Purpose |
| --- | --- |
| `application-creator` | Multi-session product workflow from discovery through release |
| `quick-react-app` | Focused one-session prototype or small application |
| `add-react-feature` | Add a bounded feature to an existing React application |
| `improve-react-app` | Audit and implement the highest-impact improvements |
| `design-react-app` | Improve visual design, responsiveness, and interaction quality |
| `qa-react-app` | Add or run the appropriate automated tests |
| `review-react-app` | Read-only code, architecture, performance, and accessibility review |
| `deploy-react-app` | Prepare and publish a verified production build |

`react-request-router` is the always-on entry point for React work. It selects one primary workflow and loads only the reference skills needed for that request.

Reference skills loaded by the workflows:

- `react-architecture` — feature boundaries, routing, data flow, state, errors, and performance.
- `react-ui-system` — tokens, reusable components, responsive layouts, accessibility, and interaction states.
- `react-qa` — Vitest, Testing Library, MSW, Playwright, axe, and pragmatic test strategy.

## Agents

| Agent | Responsibility | Preloaded skills |
| --- | --- | --- |
| `application-creator` | End-to-end implementation with verification gates | Orchestrates the skill set |
| `react-reviewer` | Read-only architecture and quality review | `react-architecture`, `react-ui-system` |
| `react-qa-runner` | Diagnose failures, fix causes, and rerun tests | `react-qa`, `react-architecture` |
| `react-deployer` | Preflight, deploy, and post-deploy validation | `deploy-react-app`, `react-qa` |

## Default technical stance

- Respect the existing stack. For new browser-only applications, prefer React + TypeScript + Vite unless requirements point to a framework such as Next.js or Remix.
- Organize by product feature, not by file type alone.
- Keep server state, URL state, shared client state, and local component state distinct.
- Treat loading, empty, error, success, unauthorized, and offline states as first-class UI states.
- Use automated checks proportionally: typecheck, lint, focused tests, production build, runtime smoke, accessibility, and visual review.
- Never deploy without explicit user authorization.

## Repository layout

```text
.codex-plugin/plugin.json
.claude-plugin/plugin.json
agents/
skills/
```

The skill pack is intentionally template-light. It uses the official scaffolder for the chosen React framework so dependency versions and configuration stay current.

## Making Codex route every request

Codex sees skill metadata and loads full instructions when a request matches. Every skill in this package explicitly allows implicit invocation, and `react-request-router` has broad React-task metadata so it is considered first.

For deterministic repository-level behavior, keep an `AGENTS.md` at the root of each React project. The `application-creator` workflow creates one from `skills/application-creator/references/react-project-agents.md`. This makes routing apply to every future request made while Codex works in that repository.

The top-level `agents/` directory remains for hosts that support declarative agent definitions. Codex does not depend on it: equivalent behavior lives in the routable skills, as recommended for OpenAI plugin compatibility.
