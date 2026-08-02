### Hi, I'm Hassan.

I build production Claude systems and full-stack SaaS infrastructure. Live products, not prototypes. I work with founders, agencies, and professional services firms that need software still holding up after the demo ends.

Based in Faisalabad, Pakistan. Working hours run US EST / PST.

---

### What I've shipped

**[ScripturePath.ai](https://scripturepath.ai).** Live subscription SaaS that generates full 10-section personalized Bible studies from any scripture passage. Multi-phase LLM pipeline with model tiering (Claude Opus for doctrinal reasoning, Sonnet for metadata, Haiku for utility sections), 4 parallel Anthropic API calls per generation streamed to the client as NDJSON. Nine hard-coded theological guardrails baked into every prompt with regex-checked outputs. Study result caching with normalized cache keys. Prompt caching for the static rules block at 10% input cost. Full Stripe subscription billing with trial support. Verified-source scripture retrieval from vendored KJV (never model-generated). Caught and patched a pre-launch RLS vulnerability that would have let any authenticated user grant themselves unlimited credits.
*Stack: Next.js 16, React 19, TypeScript, Tailwind v4, Supabase (Postgres + RLS), Anthropic SDK, Stripe, Resend, Vercel.*

**Business Succession Group portal (portal.businesssuccessiongroup.com).** Live gated B2B acquisition marketplace connecting qualified buyers with confidential M&A deals for a Canadian advisory firm. Three-tier freemium model (public pipeline → verified buyer → $500/year premium with early access). Digital NDA signature capture with in-portal PDF generation, 6-step buyer intake form, admin moderation queues, bi-directional Zoho CRM sync via OAuth edge functions. Multi-layered RBAC via Supabase RLS with BEFORE-triggers preventing privilege escalation, a public "blind columns" view separated from confidential data at the database layer, and full Stripe subscription billing with webhook-driven tier changes. Real-time admin notification feed with per-admin read state.
*Stack: React 19, Vite, TypeScript, Tailwind v4, Supabase (Postgres + RLS + storage + edge functions), Stripe, Zoho CRM, Resend, react-signature-canvas, jspdf.*

**Reporting and operations platform.** Internal reporting product aggregating transaction data across MongoDB (source of truth) and Supabase into three interconnected dashboards. Custom incremental MongoDB-to-Postgres sync engine (3 pipelines, 72 migrations of schema evolution). Admin-defined custom columns using Postgres expression indexes over jsonb paths, making arbitrary MongoDB document fields sortable and filterable. Upstash Redis for per-user rate limiting and column-library caching. Full RBAC (Admin/Manager/Viewer plus custom roles) with role-scoped CSV export and per-user saved views. Fixie SOCKS proxy for IP-restricted MongoDB Atlas access.
*Stack: Next.js 16, React 18, TypeScript, Supabase, MongoDB, Upstash Redis, Recharts, TanStack Query, TanStack Table.*

**[StellaFlo](https://stellaflo.com).** My own productized service for digital agency owners.

---

### Track record

Public and verifiable:

- **Upwork.** Top Rated, Top 10% of Automation Talent, 100% Job Success. 3,614 hours across 90 projects. $60,000+ earned. [upwork.com/freelancers/ehassannawaz](https://www.upwork.com/freelancers/ehassannawaz)
- **Contra.** 5.00 rating, $50,000+ earned on-platform. [contra.com/ehassannawaz](https://contra.com/ehassannawaz)
- **LinkedIn.** Named recommendations from Scott Duke and Eve Duke of Business Succession Group. [linkedin.com/in/ehassannawaz](https://www.linkedin.com/in/ehassannawaz)

Selected numbers from public portfolio work:

- 14,000-record data quality automation. Duplicates dropped from 23% to under 1%.
- Email-routing AI agent. Handling time cut 70%.
- SaaS onboarding flow. Setup went from two days to 30 minutes.
- Roughly $50,000 in documented annual cost savings across client engagements.

---

### What clients have said

> "We would 100% work with Hassan again. He assisted us with programming an AI agent and was successful in doing so." (Upwork, Automation Developer engagement)

> "Hassan did an incredible job helping us implement lead tracking automations for our roofing company's ad campaign tracking, form fills on their landing page, and connecting the follow-up sequence." (Upwork, SB Pro Roofing)

> "Hassan is an incredibly talented and dependable addition to our team, with a strong ability to design and implement thoughtful automation solutions. He consistently delivers high-quality work and is a pleasure to collaborate with." (Scott Duke, Business Succession Group, LinkedIn recommendation)

---

### Deep-dive case studies

Public writeups of the engineering patterns behind the projects above. No client code, no client data, no proprietary business logic. Just architecture:

- **[Production Claude SaaS patterns](https://github.com/ehassannawaz/case-study-claude-saas-patterns)** covers multi-phase pipelines, non-overridable guardrails, verified-source retrieval, and human-in-the-loop review. Distilled from the ScripturePath.ai build.
- **[Claude + Google Workspace document automation](https://github.com/ehassannawaz/case-study-claude-document-automation)** covers the Google Sheets to Slides deck-generation pipeline: grounding contracts, prompt caching for 75% cost reduction, model tiering per output, chart re-linking as a Slides API workaround, stateful bot UX with background execution.
- **[Gated B2B marketplace on Supabase](https://github.com/ehassannawaz/case-study-gated-marketplace-supabase)** covers tiered RLS, column-level access via views, privilege-escalation triggers, in-portal NDA capture with PDF generation, Stripe subscription tiers driven by webhook, bi-directional Zoho CRM sync.
- **[MongoDB + Supabase operations dashboard](https://github.com/ehassannawaz/case-study-mongo-supabase-ops-dashboard)** covers custom incremental sync between MongoDB and Postgres, admin-defined custom columns via jsonb expression indexes, Redis-cached hot-path lookups, RBAC as data, and RBAC-safe CSV export.
- **[Agency automation patterns](https://github.com/ehassannawaz/case-study-agency-automation)** covers n8n/CRM reliability patterns from 3,614 hours of Upwork production work: Zapier-to-n8n migrations, stage-derived pipeline automation, idempotent webhooks, credential hygiene, monitoring against silent failures.

---

### Why the repo list here is short

Most of my production code lives in client GitHub organizations, not this account. That's on purpose.

When a client hires me to build production systems, the code belongs in their org so their business continuity isn't tied to my availability. It's standard for senior contract work and non-negotiable under most NDAs.

For technical evaluation I run architecture walk-throughs live on a call with screen-share into the actual client repos (with the client's written read-only permission). That gives a much sharper read than static repo browsing anyway. Happy to walk through decisions, tradeoffs, and code quality on any of the projects above.

---

### Stack I ship on daily

**AI:** Claude Code (daily driver for architecture and pair-programming), Anthropic SDK direct, Claude Agent SDK, Claude Skills, prompt caching, prompt engineering, anti-hallucination guardrail design, structured LLM output with JSON schema validation, streaming responses (NDJSON), human-in-the-loop review patterns

**Frontend:** React 19, Next.js 15/16, TypeScript, Tailwind v4, Vite, shadcn/ui, Radix UI, Recharts, TanStack Query, TanStack Table

**Backend:** Supabase (Auth, Postgres with RLS, storage, Edge Functions, Realtime), MongoDB, Deno, Node.js

**Payments and email:** Stripe (subscriptions, trials, webhooks, customer portal), Resend

**Infrastructure:** Vercel, Netlify, GitHub Actions, Upstash Redis

**Automation:** n8n (primary), Zapier, Make, Zoho Flow, Pipedream

**CRM:** Zoho, HubSpot, GoHighLevel, Salesforce (mid-market)

---

### Where I don't ship

Native iOS / Android publishing and Apple App Store / Google Play submissions are the one lane I don't take on solo. Web and PWA on Vercel or Netlify I ship end-to-end. For projects that need a native mobile front-end, I pair with a mobile specialist who owns the native side while I stay on web, Supabase, Claude, and API integrations. HealthKit and Health Connect at the API level are fine either way (backend / edge function side).

---

### Currently

Ongoing with Business Succession Group (August 2025 to present). Building [StellaFlo](https://stellaflo.com) alongside. Room for one more serious client engagement, Claude SaaS or senior full-stack.

### Get in touch

- Website: [stellaflo.com](https://stellaflo.com)
- LinkedIn: [linkedin.com/in/ehassannawaz](https://www.linkedin.com/in/ehassannawaz)
- Upwork: [upwork.com/freelancers/ehassannawaz](https://www.upwork.com/freelancers/ehassannawaz)
- Contra: [contra.com/ehassannawaz](https://contra.com/ehassannawaz)
- Email: ehassannawaz@gmail.com
