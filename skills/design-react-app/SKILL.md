---
name: design-react-app
description: Audit and improve the visual design, interaction quality, responsiveness, and accessibility of an existing React application. Use for visual polish, layout, design consistency, responsive behavior, or UX refinement. Do not use for primarily business-logic or data changes.
---

# Design React App

Preserve the product's identity while making hierarchy, comprehension, and interaction quality visibly better.

## Audit representative states

Read the existing styling and component conventions, then inspect key routes and states: initial, populated, empty, loading, error, validation, destructive confirmation, and long-content cases. Check narrow mobile and wide desktop widths, keyboard flow, focus visibility, contrast, overflow, and reduced motion.

## Define a coherent direction

State the intended hierarchy, density, type scale, color roles, spacing rhythm, and component language. Reuse current tokens and primitives when they exist. If they do not, introduce the smallest semantic token layer that resolves repeated inconsistency.

Load `react-ui-system` for shared components or tokens.

## Implement in impact order

1. Fix broken layout, unreadable contrast, inaccessible interactions, and misleading states.
2. Clarify page hierarchy and primary actions.
3. Normalize repeated spacing, typography, controls, and feedback.
4. Add purposeful transitions or micro-interactions only when they communicate change.

Do not turn every section into a card, decorate every surface, or impose a fashionable visual style that conflicts with the product.

## Verify

Run available checks and inspect changed routes at representative widths. Exercise keyboard navigation, forms, dialogs, menus, and focus restoration. Use automated accessibility checks as a supplement to manual interaction. Capture deterministic screenshots if the project uses visual regression.

Report the visual and interaction improvements, affected routes, verification performed, and any content or brand assets still needed.
