---
name: react-ui-system
description: Create and evolve accessible, reusable React UI systems with design tokens, responsive layouts, component states, and interaction patterns. Use when building shared UI foundations or polishing application consistency. Do not force a design-system rewrite for a localized visual change.
---

# React Ui System

Build a coherent interface from product context rather than a generic component gallery. Preserve an existing brand and component library when present.

## Start with a visual direction

Before broad implementation, identify the application's audience, tone, density, content hierarchy, and primary action. Define a small set of tokens for color roles, type, spacing, radius, elevation, motion, and layout widths. Use semantic token names such as `surface`, `text-muted`, and `danger`, not raw color names tied to one theme.

## Build primitives from repeated needs

Create shared components only when multiple screens need a stable contract. A component should expose meaning and behavior, not every CSS property. Prefer composition over a large matrix of boolean props.

For each interactive component, cover:

- default, hover, focus-visible, active, disabled, pending, and error states;
- keyboard and pointer behavior;
- accessible name and relationship to help/error text;
- high zoom, long labels, empty content, and localization expansion;
- reduced-motion behavior where animation is nonessential.

## Responsive layout

Design from content constraints, not a list of popular devices. Verify narrow mobile, mid-width/tablet, and wide desktop. Avoid horizontal overflow, fixed-height content containers, and important actions that disappear behind hover-only behavior.

Use fluid grids and container-aware composition where supported by the project. Preserve readable line length and ensure touch targets are comfortably operable.

## Accessibility baseline

- Use semantic HTML before ARIA.
- Maintain logical heading order and landmark structure.
- Make the whole journey keyboard-operable with visible focus.
- Associate inputs, descriptions, and errors programmatically.
- Announce important asynchronous status changes without excessive noise.
- Manage focus for dialogs, route changes, destructive confirmations, and validation failures.
- Verify contrast for text, controls, states, and focus indicators.

Automated accessibility checks are a floor, not proof of accessibility. Include a keyboard pass and inspect the accessibility tree for complex widgets.

## Visual verification

When changing UI, inspect representative routes at mobile and desktop sizes. Check information hierarchy, alignment, overflow, content extremes, empty/error/loading states, focus, dialogs, and dark mode if supported. Prefer screenshots of deterministic states to unstable full-page snapshots.

## Avoid generic polish

Do not add gradients, animation, glass effects, or decorative cards by default. Every visual technique should reinforce hierarchy, brand, feedback, or comprehension. Keep motion short and interruptible, and never use it to hide slow work.
