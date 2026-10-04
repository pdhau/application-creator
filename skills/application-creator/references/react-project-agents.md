# React project AGENTS.md template

Create this file as `AGENTS.md` at the root of a React application scaffolded by Application Creator. Adapt commands and conventions to the actual project; remove sections that do not apply.

```markdown
# React application instructions

Use `react-request-router` for every React application request, then load exactly one primary workflow skill and only the relevant reference skills.

## Workflow routing

- substantial creation or multi-session work: `application-creator`
- quick prototype: `quick-react-app`
- feature or bug fix: `add-react-feature`
- broad improvement: `improve-react-app`
- visual/UX work: `design-react-app`
- tests and regressions: `qa-react-app`
- read-only review: `review-react-app`
- explicit deployment: `deploy-react-app`

Use `react-architecture`, `react-ui-system`, and `react-qa` only when their subject is active.

## Project commands

- Install: `<project install command>`
- Develop: `<project dev command>`
- Typecheck: `<project typecheck command>`
- Lint: `<project lint command>`
- Test: `<project test command>`
- Build: `<project build command>`
- E2E: `<project e2e command or not configured>`

## Project conventions

- Preserve the existing package manager, framework, styling system, and feature boundaries.
- Model loading, empty, error, success, and unauthorized states where applicable.
- Keep secrets out of source and client bundles.
- Add or update focused tests for changed behavior.
- Run proportionate checks and fix failures caused by the requested change.
- Review requests are read-only unless fixes are requested.
- Deployment always requires explicit authorization.
```
