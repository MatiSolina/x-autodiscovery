<!-- state:{"last_tweet_id":"0"} -->
# Latest Vercel launches

<!-- entries -->

## 2026-07-03 — Agent Runs in the Vercel MCP and CLI
**What it is:** Inspect Agent Runs from eve agents via new Vercel MCP tools and `vercel agent-runs` CLI commands — list runs and retrieve full traces including reasoning, tool calls, and token usage.
**Why you'd use it:** Your coding agent can debug its own production agents ("show me the latest Agent Runs") without opening the dashboard.
**Docs:** https://vercel.com/docs/mcp
**Announcement:** https://vercel.com/changelog/agent-runs-vercel-mcp-cli

## 2026-07-02 — Routing rules on AI Gateway
**What it is:** Firewall-style rules at the gateway level that rewrite requests for one model to another or deny models outright, applied to every request made with your team's credentials.
**Why you'd use it:** When a model goes down or gets retired, push one rule and all traffic reroutes instantly — no code change or redeploy.
**Docs:** https://vercel.com/docs/ai-gateway
**Announcement:** https://vercel.com/changelog/ai-gateway-routing-rules

## 2026-07-01 — Service Bindings: secure internal communication between services
**What it is:** Declare a binding in `vercel.json` and Vercel injects an internal URL env var so one service (e.g. a Next.js frontend) can privately call another (e.g. a FastAPI backend) in the same deployment.
**Why you'd use it:** Multi-service apps get authenticated, TLS-secured internal routing with a plain `fetch()` — no public endpoints or hand-rolled auth between services.
**Docs:** https://vercel.com/docs/services
**Announcement:** https://vercel.com/changelog/secure-internal-communication-between-services

## 2026-06-30 — Vercel and Shopify are rebuilding Hydrogen
**What it is:** Announced at Vercel Ship 26: Hydrogen is being rebuilt from the ground up as open source and runtime-agnostic, with core/client/server layers usable from Svelte, Nuxt, Next.js, or any custom framework.
**Why you'd use it:** Build headless Shopify storefronts with the framework you already use and deploy them anywhere JavaScript runs, including Vercel.
**Docs:** https://vercel.com/docs/frameworks
**Announcement:** https://vercel.com/blog/vercel-and-shopify-are-rebuilding-hydrogen

## 2026-06-30 — Bring your Dockerfile to Vercel Functions
**What it is:** Vercel Functions now deploy HTTP servers from a `Dockerfile.vercel`/`Containerfile.vercel` as OCI-compatible container images running on Fluid compute.
**Why you'd use it:** Bring existing apps in any language to Vercel while keeping preview deployments, logs, routing, and autoscaling.
**Docs:** https://vercel.com/docs/functions/container-images
**Announcement:** https://vercel.com/changelog/bring-your-dockerfile-to-vercel-functions

## 2026-06-30 — VCR: Vercel Container Registry
**What it is:** An OCI-compliant container image registry hosted on Vercel that works with standard `docker push`, `pull`, and `tag`, with OIDC or access-token auth.
**Why you'd use it:** Pushed images are auto-optimized into precompiled snapshots for fast cold starts in Vercel Functions and Sandboxes — no separate registry to manage.
**Docs:** https://vercel.com/docs/container-registry
**Announcement:** https://vercel.com/changelog/introducing-vcr-vercel-container-registry

## 2026-06-30 — Vercel Services: multiple frameworks in one project
**What it is:** Deploy multiple frontends and backends together in a single Vercel project on a shared domain, defined in `vercel.json`, with private inter-service communication and unified build/preview/rollback.
**Why you'd use it:** Ship a full-stack app (e.g. Next.js frontend + Python backend) as one deployment instead of stitching together separate projects.
**Docs:** https://vercel.com/docs/services
**Announcement:** https://vercel.com/changelog/run-multiple-frameworks-in-one-project-with-vercel-services

## 2026-06-30 — Vercel Private Blob is generally available
**What it is:** Private Blob stores, signed URLs, and OIDC authentication graduate from beta on all plans; upload with `access: 'private'` using the same Blob API.
**Why you'd use it:** Store sensitive files (user uploads, invoices, agent memory) and control exactly who reads them — no static read-write tokens in your environment.
**Docs:** https://vercel.com/docs/vercel-blob
**Announcement:** https://vercel.com/changelog/vercel-private-blob-is-now-generally-available

## 2026-06-30 — Custom Images for Vercel Sandbox
**What it is:** Sandboxes can now boot from your own custom root filesystem via `Sandbox.create({ image: "repository:tag" })`, pulled from Vercel Container Registry.
**Why you'd use it:** Bring your own OS, toolchain, and dependencies to sandboxed agent/code execution without pre-building snapshots, keeping fast cold starts.
**Docs:** https://vercel.com/docs/sandbox
**Announcement:** https://vercel.com/changelog/vercel-sandbox-now-support-custom-images

## 2026-06-25 — AI SDK 7
**What it is:** A major release turning the AI SDK into an agent platform: reasoning control, tool approvals, durable WorkflowAgent execution, harness integrations (Claude Code, Codex, Deep Agents, OpenCode, Pi), redesigned telemetry, and multimodal APIs for speech, image, and video.
**Why you'd use it:** Build production TypeScript agents with one SDK across every major provider, from model calls to durable, observable agent runs.
**Docs:** https://vercel.com/docs/ai-sdk
**Announcement:** https://vercel.com/changelog/ai-sdk-7

## 2026-06-23 — Deploy Node servers with zero configuration
**What it is:** Vercel detects a `server.ts` at the project root (or `src/`) and deploys it as a Node.js app on Fluid compute — joining Express, Koa, and NestJS zero-config support.
**Why you'd use it:** Deploy a plain Node HTTP server with `vc deploy` and no config files, billed with Active CPU pricing.
**Docs:** https://vercel.com/docs/functions/runtimes/node-js
**Announcement:** https://vercel.com/changelog/deploy-node-servers-with-zero-configuration

## 2026-06-22 — WebSocket support in Public Beta
**What it is:** Vercel Functions can now serve WebSocket connections using standard Node.js libraries (ws, Socket.IO) on Fluid compute, with no extra configuration.
**Why you'd use it:** Build realtime features — interactive AI streaming, chat, collaboration — and only pay for CPU while processing messages, not idle connection time.
**Docs:** https://vercel.com/docs/functions/websockets
**Announcement:** https://vercel.com/changelog/websocket-support-is-now-in-public-beta

## 2026-06-17 — eve: an open-source agent framework
**What it is:** eve (public preview) makes an agent a directory of files — model, instructions, tools, skills, subagents, channels, schedules — with durable execution, sandboxed compute, approvals, and evals built in.
**Why you'd use it:** Go from a two-file agent to production on Vercel without wiring up infrastructure for state, safety, or scheduling yourself.
**Docs:** https://vercel.com/docs/eve
**Announcement:** https://vercel.com/changelog/introducing-eve-an-open-source-agent-framework

## 2026-06-17 — Vercel Connect
**What it is:** Register a connector once and your apps and agents request scoped, short-lived tokens at runtime to access Slack, GitHub, Salesforce, or custom APIs — no long-lived secrets stored.
**Why you'd use it:** Give an agent exactly the access a task needs (e.g. one repo, read-only) instead of a broad provider secret to leak or rotate.
**Docs:** https://vercel.com/docs/connect
**Announcement:** https://vercel.com/changelog/vercel-connect-secure-access-to-external-services-for-your-agents

## 2026-06-17 — Vercel Passport in Public Beta
**What it is:** Enterprise teams can gate deployments behind their own identity provider (Okta, Auth0, any OIDC); Vercel injects a signed JWT header identifying the visitor.
**Why you'd use it:** Protect internal apps and previews with your existing SSO, reusing one OIDC app across projects with team-wide defaults.
**Docs:** https://vercel.com/docs/passport
**Announcement:** https://vercel.com/changelog/vercel-passport-is-now-in-public-beta

## 2026-06-15 — Vercel Functions can run up to 30 minutes
**What it is:** Node.js and Python functions on Pro and Enterprise now support `maxDuration` up to 1800 seconds, more than 2x the previous limit.
**Why you'd use it:** Long LLM reasoning, streaming AI responses, document/media processing, and scraping fit in a Function — with Active CPU billing paused during I/O waits.
**Docs:** https://vercel.com/docs/functions/configuring-functions/duration
**Announcement:** https://vercel.com/changelog/vercel-functions-can-now-run-up-to-30-minutes

## 2026-04-16 — Vercel Flags is generally available
**What it is:** A feature flag provider built into the platform: create flags with targeting rules, segments, and environment controls in the dashboard, consumed via the Flags SDK or OpenFeature.
**Why you'd use it:** Framework-native feature flags for Next.js and SvelteKit with no third-party service, including progressive rollouts and CLI management.
**Docs:** https://vercel.com/docs/flags
**Announcement:** https://vercel.com/changelog/vercel-flags-ga
