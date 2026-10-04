---
name: deploy-react-app
description: Prepare and deploy a React application with preflight verification and post-deploy validation. Use when the user explicitly asks to publish, deploy, or configure hosting. Do not activate for local development servers, previews, or general build troubleshooting.
---

# Deploy React App

Deployment changes external state. Confirm the target project, environment, provider, branch or artifact, and domain before publishing when they are not already explicit.

## Preflight

1. Read repository deployment guidance and provider configuration.
2. Identify the framework's production output and runtime requirements.
3. Check environment-variable names and provider bindings without printing secret values.
4. Verify typecheck, lint, tests, and production build using project scripts.
5. Exercise critical journeys against the production build when feasible.
6. Confirm SPA rewrite/deep-link behavior, asset base paths, API origins, and client/server environment separation.
7. Check that source maps, analytics, error reporting, robots metadata, and caching match the target environment.

Do not publish a known-broken build, bypass failing gates, commit on the user's behalf, create accounts, buy domains, or expose secrets without explicit authorization.

## Deploy

Prefer existing provider configuration and documented project commands. If none exists, use the provider the user chose and follow its current official documentation. Keep environment-specific values outside source control. Use preview/staging before production when available and proportionate.

## Post-deploy validation

Verify the final URL, status, asset loading, deep links and refresh, primary journey, error reporting, and responsive layout. Check the browser console and network failures. For protected apps, verify public and authenticated boundaries without leaking credentials into logs or screenshots.

## Rollback and report

Identify the provider's rollback path before production changes. If validation fails, stop further promotion and roll back when the user authorized deployment and rollback is safe and supported.

Report the environment, deployed revision or artifact, URL, checks performed, configuration changes, remaining manual steps, and rollback instructions.
