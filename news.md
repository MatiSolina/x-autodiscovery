<!-- state:{"last_tweet_id":"2072311906086551680"} -->
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

## 2026-06-30 — Vercel Services
**What it is:** Run multiple frameworks (a Next.js frontend plus Python/Go/Rust/Node backends) in a single Vercel project, declared under a `services` key in vercel.json, with atomic deploy/rollback, shared preview URLs, and private service-to-service bindings that never touch the public internet.
**Why you'd use it:** Keep your full stack in sync on one domain and one deploy instead of stitching separate clouds; backends auto-scale on Fluid compute with Active CPU pricing and are reachable internally via injected URLs.
**Docs:** https://vercel.com/docs/services
**Announcement:** https://x.com/vercel/status/2071951670058324353

## 2026-06-30 — Run any Dockerfile on Vercel
**What it is:** Add a `Dockerfile.vercel` and Vercel builds, stores, deploys, and autoscales any HTTP server (Go, Rails, Spring Boot, Express, Laravel, ASP.NET, FastAPI, nginx) on Fluid compute with Active CPU pricing; the server just needs to listen on `$PORT`.
**Why you'd use it:** Ship an existing containerized backend with one `vercel deploy`, getting a preview URL per push, shared observability, and a first-class container running beside your frontend on the same platform.
**Docs:** https://vercel.com/docs/functions/container-images
**Announcement:** https://x.com/vercel/status/2071951027302224262

## 2026-06-30 — Vercel and Shopify are rebuilding Hydrogen
**What it is:** Announced at Vercel Ship 26: Hydrogen is being rebuilt from the ground up as open source and runtime-agnostic, with core/client/server layers usable from Svelte, Nuxt, Next.js, or any custom framework.
**Why you'd use it:** Build headless Shopify storefronts with the framework you already use and deploy them anywhere JavaScript runs, including Vercel.
**Docs:** https://vercel.com/docs/frameworks
**Announcement:** https://vercel.com/blog/vercel-and-shopify-are-rebuilding-hydrogen

## 2026-06-30 — VCR: Vercel Container Registry
**What it is:** An OCI-compliant container image registry hosted on Vercel that works with standard `docker push`, `pull`, and `tag`, with OIDC or access-token auth.
**Why you'd use it:** Pushed images are auto-optimized into precompiled snapshots for fast cold starts in Vercel Functions and Sandboxes — no separate registry to manage.
**Docs:** https://vercel.com/docs/container-registry
**Announcement:** https://vercel.com/changelog/introducing-vcr-vercel-container-registry

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

## 2026-06-29 — Realtime voice, speech, and transcription on AI Gateway
**What it is:** AI Gateway now routes audio alongside text/image/video — realtime two-way voice, text-to-speech, and speech-to-text behind one API key with the same provider routing, observability, spend controls, and BYOK; available in beta in AI SDK 7 via `useRealtime`, `generateSpeech`, and `transcribe`, with models from OpenAI and xAI.
**Why you'd use it:** Build low-latency voice agents and audio features without a separate STT→LLM→TTS pipeline, new keys, or new billing.
**Docs:** https://vercel.com/blog/realtime-voice-agents-on-ai-gateway
**Announcement:** https://x.com/vercel/status/2071620375621009416

## 2026-06-25 — AI SDK 7
**What it is:** A major release of the TypeScript AI SDK focused on production agents, adding tool approvals, durable `WorkflowAgent` execution, first-class timeouts, sandbox support, `HarnessAgent` for plugging in runtimes like Claude Code/Codex/Pi, redesigned global telemetry, lifecycle events, and experimental realtime voice and video generation.
**Why you'd use it:** Build, run, and observe long-running agents that survive deploys and approvals, with one interface across every provider and OpenTelemetry observability out of the box.
**Docs:** https://vercel.com/docs/ai-sdk
**Announcement:** https://x.com/vercel/status/2070155382488764566

## 2026-06-23 — Deploy Node servers with zero configuration
**What it is:** Vercel detects a `server.ts` at the project root (or `src/`) and deploys it as a Node.js app on Fluid compute — joining Express, Koa, and NestJS zero-config support.
**Why you'd use it:** Deploy a plain Node HTTP server with `vc deploy` and no config files, billed with Active CPU pricing.
**Docs:** https://vercel.com/docs/functions/runtimes/node-js
**Announcement:** https://vercel.com/changelog/deploy-node-servers-with-zero-configuration

## 2026-06-22 — Vercel Flags
**What it is:** Platform-native feature flags evaluated server-side by default with zero page-performance impact, managed in the same dashboard as your deployments and read in code through the open-source Flags SDK (Next.js/SvelteKit adapters, OpenFeature provider otherwise); includes automatic flag registration, a Precompute CDN pattern, Flags Explorer overrides, and a `vercel flags` CLI.
**Why you'd use it:** Decouple deploying code from releasing features — merge continuously, target segments, run progressive rollouts, and kill a broken feature by toggling a flag without redeploying.
**Docs:** https://vercel.com/blog/vercel-flags-platform-native-feature-flags
**Announcement:** https://x.com/vercel/status/2069178278188085683

## 2026-06-22 — WebSocket support in Public Beta
**What it is:** Vercel Functions can now serve WebSocket connections using standard Node.js libraries (ws, Socket.IO) on Fluid compute, with no extra configuration.
**Why you'd use it:** Build realtime features — interactive AI streaming, chat, collaboration — and only pay for CPU while processing messages, not idle connection time.
**Docs:** https://vercel.com/docs/functions/websockets
**Announcement:** https://vercel.com/changelog/websocket-support-is-now-in-public-beta

## 2026-06-17 — Vercel for Enterprise Apps and Agents
**What it is:** A platform tier for shipping internal apps and agents behind your identity and security boundaries, bundling Vercel Passport (IdP-gated deployments via Okta/Entra/Auth0/OIDC), Vercel Connect (short-lived scoped credentials), Enterprise Managed Users (SAML SSO + Directory Sync lifecycle control), and bring-your-own-cloud on AWS; v0 also connects to Snowflake for governed data apps.
**Why you'd use it:** Let anyone in the company prototype and ship agents safely with access, audit trails, and credential scoping enforced by the platform rather than per-project configuration.
**Docs:** https://vercel.com/blog/vercel-for-enterprise-apps-and-agents
**Announcement:** https://x.com/vercel/status/2067186099508965610

## 2026-06-17 — eve (agent framework)
**What it is:** An open-source agent framework where an agent is a directory (`agent.ts`, `instructions.md`, `tools/`, `skills/`, `subagents/`, `channels/`, `schedules/`) with durable execution, sandboxed compute, human-in-the-loop approvals, subagents, tracing, and evals built in; ships with an `eve dev` terminal UI and channels for Slack, Discord, Teams, Telegram, Twilio, GitHub, and Linear.
**Why you'd use it:** Define what an agent does in files instead of assembling production plumbing — it runs on the Agent Stack (AI SDK, AI Gateway, Workflow SDK, Sandbox, Vercel Connect) and deploys on Vercel.
**Docs:** https://vercel.com/docs/eve
**Announcement:** https://x.com/vercel/status/2067180054979936413

## 2026-06-17 — Vercel Connect
**What it is:** Runtime credential exchange (Public Beta) that replaces stored long-lived provider tokens: register a connector once for Slack, GitHub, Linear, Discord, Notion, Salesforce, Figma, Snowflake, or any OAuth/API service, then request short-lived, per-task-scoped tokens at runtime via `getToken` from `@vercel/connect` using the deployment's OIDC identity; includes per-user scoping, per-environment isolation, revocation, and verified webhook trigger forwarding.
**Why you'd use it:** Give agents access to external systems with least-privilege tokens that expire per task and no provider secret sitting in your environment to leak or rotate.
**Docs:** https://vercel.com/docs/connect
**Announcement:** https://x.com/vercel/status/2067178169006973270

## 2026-06-17 — The Agent Stack
**What it is:** Vercel's bundled set of building blocks for production agents — AI SDK and AI Gateway (connect to/route models), Workflow SDK and Vercel Sandbox (durable, isolated execution), and Vercel Connect and Chat SDK (secure data/tool access and multi-channel delivery) — with eve as the opinionated framework that assembles them.
**Why you'd use it:** Get every capability an agent needs (streaming, models, durability, isolation, channels, integrations) from one stack instead of stitching vendors together or building abstractions yourself.
**Docs:** https://vercel.com/blog/agent-stack
**Announcement:** https://x.com/vercel/status/2067176489641275824

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
