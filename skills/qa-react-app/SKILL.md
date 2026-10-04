---
name: qa-react-app
description: Add, run, or strengthen automated QA for an existing React application using the project's test stack or suitable lightweight tools. Use when the user asks to test the app, add tests, check for regressions, add Playwright, or validate release quality. Do not use for a read-only architecture review.
---

# Qa React App

Load `react-qa`, then tailor coverage to the application rather than installing a fixed test stack blindly.

## 1. Discover

Read the package scripts, framework configuration, routes, providers, feature boundaries, data layer, environment variables, and existing tests. Identify the primary journeys and the failures that would be expensive or embarrassing.

## 2. Create a risk-based matrix

For each critical journey, list the happy path, validation, empty data, server error, authorization, retry/recovery, and responsive/accessibility concerns. Choose the lowest reliable layer for each check.

## 3. Extend infrastructure only as needed

Reuse the existing runner and conventions. For a Vite app without tests, Vitest + Testing Library is a natural unit/component choice and Playwright is a natural browser choice, but verify current official setup before installing. Add network mocking only when features depend on HTTP boundaries.

Do not expose internal globals solely to make tests easier when the same behavior can be exercised through the UI or public feature boundary.

## 4. Write and run tests

Start with focused tests for the requested risk. Add one critical browser smoke journey before broad end-to-end coverage. Include accessibility checks on representative stable states. Use deterministic fixtures and accessible selectors.

Run focused tests first, then the full supported suite. Fix implementation bugs when tests reveal them. Change a test only when its expectation or selector is genuinely stale, and preserve the original requirement in the updated assertion.

## 5. Report

Report tests added or run, behaviors covered, command results, artifacts or failure traces, gaps intentionally left, and exact commands the user can rerun.
