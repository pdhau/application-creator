# Application Creator routing

Apply these instructions to every user request in this repository.

## Route every request

For any request concerning a React application, first use `react-request-router`. Select exactly one primary workflow skill unless the request genuinely spans independent workflows:

- new or substantial multi-session application: `application-creator`
- small prototype or proof of concept: `quick-react-app`
- bounded feature or bug fix: `add-react-feature`
- open-ended improvement request: `improve-react-app`
- visual, responsive, or interaction work: `design-react-app`
- testing or regression work: `qa-react-app`
- read-only review: `review-react-app`
- explicit publishing request: `deploy-react-app`

Load reference skills only when their knowledge is needed:

- `react-architecture` for boundaries, state, data, routing, or performance decisions
- `react-ui-system` for shared UI, accessibility, responsive layout, or design tokens
- `react-qa` for test strategy and failure diagnosis

The Markdown files under `agents/` are compatibility definitions for hosts that support declarative agents. Codex must use their equivalent skills instead: `application-creator`, `review-react-app`, `qa-react-app`, and `deploy-react-app`.

## Working rules

- Follow explicit user instructions over this router.
- Preserve the existing stack and repository conventions.
- Do not load every skill. Progressive disclosure is required: router, one primary skill, then only relevant references.
- Complete implementation and proportionate verification when the user asks to build or change something.
- Keep review requests read-only unless fixes are explicitly requested.
- Never deploy or perform another external mutation without explicit user authorization.
