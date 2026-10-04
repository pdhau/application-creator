# Lean project memory

Use this structure for work that will span sessions or involve several independent features. Adapt existing project documentation instead of creating duplicates.

```text
docs/
  PRODUCT.md
  ARCHITECTURE.md
  STATE.md
  BACKLOG.md
  decisions/
  milestones/
```

## PRODUCT.md

Keep the target users, problem, non-goals, primary journeys, success measures, and product constraints. Product behavior belongs here; implementation detail does not.

## ARCHITECTURE.md

Record the stack, route map, feature boundaries, data sources, authentication model, state ownership, styling system, testing layers, and deployment target.

## STATE.md

Make this the short session handoff:

- current milestone and status;
- what was completed;
- verification results;
- known failures or risks;
- next concrete step.

Keep it concise enough to read at every session start.

## BACKLOG.md

Capture deferred requests instead of losing them in conversation. Each item should say what user outcome it enables and why it was deferred.

## decisions/

Create an ADR only for decisions expensive to reverse: framework, rendering model, authentication, primary data layer, state strategy, or design-system adoption. Include context, decision, consequences, and alternatives considered.

## milestones/

Use milestones for work larger than one focused session. Each milestone needs an objective, scope, explicit non-goals, user-visible acceptance criteria, dependencies, and a single exit condition.

For a small app, `PRODUCT.md`, `ARCHITECTURE.md`, and `STATE.md` can each be a few paragraphs. Compress documentation rather than omitting the source of truth.
