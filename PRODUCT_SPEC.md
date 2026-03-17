# DocForge — Product Specification

**Version:** 0.1 (Prototype)
**Author:** Sulagna Sasmal
**Status:** Interactive Prototype · Pre-product
**Last Updated:** March 2026

---

## 1. Problem Statement

Documentation teams in regulated industries — FinTech, healthcare, enterprise software — face a structural problem that no existing tool fully solves:

> **Documentation is treated as an afterthought in engineering pipelines, not a first-class engineering artifact.**

The consequences are predictable and expensive:

- Docs drift from code because they live in separate tools (Confluence, Notion, Google Docs)
- No automated quality gates catch errors before they reach readers
- Multi-format delivery (HTML, PDF, API reference) requires manual, error-prone processes
- Compliance audits fail because doc changes aren't traceable in version history
- New engineers can't contribute to docs because the workflow is opaque and undocumented
- Technical writers are isolated from the release pipeline, causing docs to lag features by weeks

**The core gap:** There is no tool built specifically for documentation engineers that combines pipeline management, content structure governance, style enforcement, and multi-format output in a single interface.

---

## 2. What DocForge Is

DocForge is a **Docs-as-Code platform for documentation engineers** — a unified interface to manage the entire documentation pipeline: from writing in structured Markdown, through automated linting and quality gates, to multi-format output delivery and continuous deployment.

It is not a writing assistant. It is not a documentation host. It is the **engineering layer** that sits between source files and published documentation — the same way a CI/CD platform sits between code and production.

### Core Positioning

| DocForge is... | DocForge is not... |
|---|---|
| A documentation pipeline platform | A writing tool or AI assistant |
| Built for documentation engineers | Built for developers or marketers |
| Focused on structure, governance, and delivery | Focused on content generation |
| Docs-as-Code native (Git, CI/CD, Markdown) | A CMS or page editor |
| Compliance-ready (DITA, Vale, audit trails) | A general-purpose knowledge base |

---

## 3. Why Not [Existing Tools]

### Why not GitHub Copilot / ChatGPT / AI writing tools?

AI tools generate text. DocForge engineers a system.

Copilot and AI writing assistants operate at the **sentence and paragraph level** — they help you write faster. DocForge operates at the **architecture level** — it governs how documentation is structured, validated, built, and deployed across an entire product.

Specific gaps AI tools don't address:
- DITA content taxonomy (Concept / Task / Reference / Tutorial / Troubleshooting topic classification)
- Vale/MSTP style enforcement as a commit-time quality gate
- Multi-format build pipelines (HTML portal, PDF, OpenAPI spec, Postman collection, JSON schema, CHANGELOG — from a single source)
- Pipeline health monitoring (build history, contributor activity, open issues)
- YAML-based configuration for environment-aware deployments

AI is a **writing accelerator**. DocForge is a **documentation operating system**.

### Why not Confluence or Notion?

Confluence and Notion are **document stores** — wikis with collaboration features. They have no concept of:
- Version-controlled source files (no Git integration at the pipeline level)
- Automated quality gates (no linting on save/commit)
- Structured output formats (no PDF export pipeline, no OpenAPI generation)
- CI/CD integration (no pipeline triggers, no build artifacts)

Writing in Confluence is like writing code in Google Docs — the collaboration works, but the engineering infrastructure doesn't exist.

### Why not GitBook or Mintlify?

GitBook and Mintlify are excellent **documentation hosting platforms** — they make published docs look good and connect to GitHub for sync. But they are consumer-facing layer tools, not pipeline tools:

- They don't enforce style guides at write-time
- They don't support DITA topic classification
- They don't generate multiple output formats from a single source
- They don't provide pipeline health visibility or build monitoring
- They are built for developer-facing API docs, not documentation engineering teams

### Why not ReadMe or Stoplight?

These are **API documentation tools** — excellent for OpenAPI-first workflows, but narrow in scope. They don't handle:
- Non-API documentation (user guides, compliance docs, runbooks, tutorials)
- Style governance across document types
- DITA-based content reuse and topic management
- Multi-team documentation pipelines

### Why not a custom internal toolchain?

Many large engineering orgs build their own documentation pipelines. The problem: **those pipelines are built by engineers for engineers**, not by documentation professionals who understand content architecture. The result is brittle, undocumented toolchains that break when the one engineer who built it leaves. DocForge is opinionated around documentation team needs — built by someone who is both a technical writer and an engineer.

---

## 4. Target Users

### Primary: Documentation Engineers / Senior Technical Writers

Writers who have crossed into engineering — they understand Git, CI/CD, APIs, and want a platform that reflects their actual skill level. Currently underserved: they're too technical for Confluence users and not technical enough to be taken seriously by DevOps teams.

**Pain:** No tool speaks their language. They build their own toolchains or compromise with inferior tools.

### Secondary: Documentation Team Leads / Heads of Docs

Responsible for consistency, quality, and delivery velocity across a writing team. Need pipeline visibility, quality metrics, and governance controls.

**Pain:** No dashboard shows them documentation health the way Datadog shows infrastructure health.

### Tertiary: FinTech / Healthcare / Enterprise Compliance Teams

Organizations where documentation is a regulatory artifact — auditable, versioned, traceable. Git-native documentation is not a preference for them; it's a compliance requirement.

**Pain:** Traditional doc tools (Confluence, SharePoint) don't produce audit trails that satisfy regulatory reviewers.

---

## 5. Core Value Proposition

> **DocForge gives documentation engineers the same pipeline confidence that DevOps tools give software engineers.**

Every feature answers one of three questions:
1. **Is my documentation correct?** (Style linting, structural validation)
2. **Is my documentation delivered?** (Build outputs, CI/CD integration)
3. **Is my documentation healthy?** (Dashboard, metrics, pipeline history)

---

## 6. Feature Map

### Current Prototype (v0.1)

Interactive simulation demonstrating the full platform concept. No backend, no auth, no real file processing. All modules are functional UI with realistic simulated data.

| Module | What It Demonstrates |
|---|---|
| Dashboard | Pipeline health, build history, content metrics, contributor activity |
| Live Editor | Markdown editing with real-time rendered preview, YAML frontmatter |
| Content Map | DITA-based topic taxonomy with visual topology |
| Style Linter | Vale/MSTP rule validation with readability scoring |
| Build Outputs | HTML portal, PDF, OpenAPI, Postman, JSON schema, CHANGELOG preview |
| Config | docforge.config.yml with toggleable build, lint, and deploy settings |

### MVP (v1.0) — Core Engineering Value

| Feature | Description | Priority |
|---|---|---|
| Real Markdown Editor | Monaco/CodeMirror replacing the textarea | P0 |
| GitHub OAuth + Repo Connect | Read real .md files from a connected repo | P0 |
| Real Vale Linting | Run actual Vale rules against content | P0 |
| HTML Build Output | Compile Markdown to a real browsable HTML portal | P1 |
| User Authentication | Login/signup, project isolation | P1 |
| Project Dashboard | Real build run history, not simulated | P1 |
| YAML Config Editor | Save/load real docforge.config.yml per project | P2 |

### V1.5 — Governance Layer

| Feature | Description |
|---|---|
| Custom Style Rules | Upload/edit Vale rules in-app |
| DITA Content Validation | Enforce topic type rules on file structure |
| Team Roles | Writer, Reviewer, Admin access levels |
| PR Comment Integration | Post linting results as GitHub PR comments |
| Slack/Teams Notifications | Build status notifications |

### V2.0 — Enterprise & Compliance

| Feature | Description |
|---|---|
| Audit Log | Full change history per document, exportable |
| Multi-format Output | Real PDF generation (WeasyPrint/Pandoc), real OpenAPI output |
| Confluence/Notion Export | Push to existing enterprise doc tools |
| SSO/SAML | Enterprise identity integration |
| Compliance Report | Automated doc coverage report against a compliance framework |
| On-premise Deployment | Self-hosted option for regulated industries |

---

## 7. Technical Architecture (Target)

```
┌─────────────────────────────────────────────────────┐
│                    DocForge Platform                │
├──────────────┬──────────────┬───────────────────────┤
│  Editor UI   │  Pipeline    │  Build Output Engine  │
│  (Monaco)    │  Dashboard   │  HTML / PDF / OpenAPI │
├──────────────┴──────────────┴───────────────────────┤
│              DocForge Core API (Node.js/Python)      │
├───────────────┬───────────────┬─────────────────────┤
│  GitHub API   │  Vale Engine  │  Pandoc / WeasyPrint │
│  (file sync)  │  (linting)    │  (format builds)     │
├───────────────┴───────────────┴─────────────────────┤
│        PostgreSQL (projects, runs, audit log)        │
│        Redis (job queue for build runs)              │
└─────────────────────────────────────────────────────┘
```

**Current prototype stack:** Pure HTML/CSS/JavaScript — no backend, no database, no build server. Hosted on GitHub Pages.

**Target MVP stack:**
- Frontend: Next.js (TypeScript)
- Backend: Node.js or Python (FastAPI)
- Database: PostgreSQL (Supabase)
- File Sync: GitHub API (OAuth)
- Linting: Vale (CLI, subprocess)
- Build: Pandoc + custom HTML template engine
- Auth: Supabase Auth or Auth0
- Hosting: Vercel (frontend) + Railway/Render (backend)

---

## 8. Competitive Differentiators

| Differentiator | Why It Matters |
|---|---|
| Built by a documentation engineer, not a developer | Product decisions are driven by actual docs team pain, not developer assumptions about writing |
| DITA topic taxonomy built-in | No other modern tool enforces structured topic types — this is a standard in aerospace, medical, and regulated industries |
| Vale linting as a first-class feature | Style governance treated as a quality gate, not an afterthought |
| Pipeline-first mental model | Dashboard and build history as the primary interface, not the editor |
| Compliance-native | Audit trails, version history, and structured output designed for regulated industries from day one |
| Multi-format from a single source | HTML, PDF, OpenAPI, Postman, JSON schema — all from the same Markdown source |

---

## 9. Business Model

### Pricing Tiers (Target)

| Tier | Price | Target |
|---|---|---|
| Solo | Free | Individual technical writers, portfolio use |
| Team | $49/seat/month | Docs teams of 3–15 people |
| Studio | $149/seat/month | Large teams with governance and compliance features |
| Enterprise | Custom | On-premise, SSO, compliance reporting, SLA |

### Revenue Drivers
- Seat-based SaaS (primary)
- Professional services: documentation audit, pipeline setup, style guide migration
- Compliance templates: pre-built DITA maps and Vale rulesets for specific regulatory frameworks (SOC 2, FDA, GDPR)

---

## 10. Success Metrics

### Prototype (Current)
- [ ] Viewed by target employers / hiring managers
- [ ] Clear "why I built this" narrative communicated
- [ ] No broken experience in light or dark mode

### MVP
- 50 active users in month 1 (beta)
- <3 second build time for a 50-file documentation project
- Vale linting accuracy: 0 false negatives on Microsoft Style Guide core rules
- NPS ≥ 40 from beta users

### V1.0
- 500 active teams
- $25K MRR
- 3 design partners in FinTech or healthcare

---

## 11. Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Vale is a CLI tool with complex setup | High | Medium | Bundle Vale as a compiled binary or use a WASM port |
| GitHub API rate limits throttle file sync | Medium | High | Cache repo state, use webhooks for incremental sync |
| PDF generation quality is inconsistent across tools | High | Medium | Start with HTML-only output; PDF in V1.5 using WeasyPrint |
| Solo founder — hard to scale engineering and writing simultaneously | High | High | Build in public; attract contributors from docs-as-code community |
| Established players (Mintlify) could add pipeline features | Medium | High | Move faster on compliance features — that's not their market |
| "Demo vs. product" perception gap | High | Medium | Always label the prototype clearly; ship MVP before major announcement |

---

## 12. Current Status

**State:** Interactive prototype deployed at [GitHub Pages](https://sulagnasasmal.github.io/Documentation-Center-Platform/)

**What works:** Full UI simulation of all 6 modules — dashboard, editor, content map, linter, build outputs, config. TTS narrator with per-view guided narration. Light/dark mode. Smooth view transitions. Responsive layout.

**What doesn't (yet):** Real GitHub repo connection, real Vale linting, real build output generation, user accounts, data persistence.

**Next step to MVP:** Replace the editor textarea with Monaco/CodeMirror and connect GitHub OAuth to read a real repository. Everything else can be simulated until real linting and build are wired up.

---

## 13. Why This, Why Now, Why Me

**Why this:** Documentation engineering is an underdeveloped discipline. Most tools were built for either developers (GitHub, VS Code) or content managers (Confluence, Notion). The documentation engineer — someone who understands both the writing craft and the delivery infrastructure — has no platform built for them.

**Why now:** Docs-as-Code has crossed the chasm. Teams at Stripe, Twilio, and AWS publish documentation the same way they deploy software. The methodology is proven. What's missing is the tooling that makes it accessible to teams that aren't building their own pipeline from scratch.

**Why me:** I am the user. I've written API documentation for FinTech platforms, built compliance documentation frameworks, and learned enough engineering to build the infrastructure that made my own work better. DocForge is not a product I'm building about a problem I've read about. It's the tool I needed and couldn't find.

---

*This document is a living specification. It will be updated as the product evolves from prototype to MVP.*
