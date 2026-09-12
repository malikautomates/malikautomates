# Hi, I'm Muhammed Abdulmalik (Malik) 👋

### I build production agentic AI systems — voice, chat, and workflow — that automate real business processes end-to-end. I got here by spending 3+ years as the person who fixes things when they break.

**Based in:** Winnipeg, Manitoba, Canada
**Reach me:** [m.abdulmaliksani008@gmail.com](mailto:m.abdulmaliksani008@gmail.com) · [LinkedIn](https://www.linkedin.com/in/muhammed-abdulmalik-a84131267) · [@malikautomates_](https://instagram.com/malikautomates_)

---

## What I ship

I take manual business workflows — support intake, IT onboarding, call handling — and replace them with agentic systems that run live, not notebook demos. My current production work:

### 🎫 Voice/Text-to-Ticket Automation — n8n · OpenAI Whisper · Anthropic Claude · Jira
Running in production at Norshel Incorporated. A support request comes in by voice or text, gets transcribed, classified, and filed as a fully detailed Jira ticket — end-to-end in under 60 seconds. Previously a 10–15 minute manual intake.

### 🧠 RAG Pipeline — Vortex FX
Queries are embedded (OpenAI `text-embedding-3-small`), matched against a ~6,200-chunk trading-literature corpus in a Supabase/pgvector store via a custom Postgres similarity function (HNSW-indexed, cosine distance, top-5 above threshold), and injected into the system prompt for Claude Sonnet 4.6 to generate against. Retrieval runs inside a `Promise.allSettled` alongside five other live context sources (real-time OANDA pricing, open-signal P&L, win-rate stats, economic calendar, session history), so a slow or failed lookup degrades the answer instead of breaking it.

### ⚙️ PowerShell New-Hire Onboarding Automation
Provisions new staff across Active Directory, Microsoft 365 licensing, MFA, and VPN access from a single CSV. 60+ minutes of manual setup → under 5 minutes, zero configuration drift. Built first at Transmission Company of Nigeria; still the pattern I reuse everywhere.

### ☎️ Vortex AI SaaS — AI Receptionist
Inbound calls and SMS routed through Vapi's voice-AI platform and Twilio, with a webhook security layer verifying every inbound event (Vapi static-secret, Twilio HMAC-SHA1) before it reaches the app. A separate n8n workflow handles outbound follow-up: triggers on missed calls and a schedule, pulls caller context from a Google Sheets CRM, and places the call via the ElevenLabs API.

### 🌐 norshelinc.ca
Lead the end-to-end build and ongoing management of the org's public site — domain, DNS, hosting, content, and the backend. The backend (`norshelinc-portal`) is a Python/FastAPI service with JWT-based authentication (bcrypt hashing, token verification, rejection of tampered/expired tokens), deployed to Fly.io behind a hard CI/CD gate: the deploy job can't run unless the full verify suite (linting, auth test coverage, app-startup check) passes.

---

## Public labs & portfolio tools

Three repositories, written the same way as the production work above: the
design decision behind each choice, a real test suite or regenerated
verification evidence, and — where something didn't work cleanly the first
time — the limitation, named directly, not smoothed over.

### 🐍 [python-projects](https://github.com/malikautomates/python-projects)
Standalone Python automation tools, each with a pytest suite and a README
walkthrough built from real, regenerable screenshots — not mockups.
Currently: a rule-based helpdesk ticket triage CLI (categorization,
priority, SLA-breach detection) and an M365 user lifecycle tool
(onboarding/offboarding via Microsoft Graph, app-only auth, a dry-run mode
that needs zero credentials).

### 🪟 [windows-server-2025-ad-lab](https://github.com/malikautomates/windows-server-2025-ad-lab)
A Windows Server 2025 Active Directory lab across 13 modules — domain
controller deployment, OU design and delegation, Group Policy, DHCP/DNS
administration, bulk user provisioning, and a helpdesk ticket runbook —
each with design rationale and verification evidence.

### 📧 [microsoft-365-administration-lab](https://github.com/malikautomates/microsoft-365-administration-lab)
A full Microsoft 365 tenant administered end to end across 13 labs:
identity and licensing, least-privilege delegation with PIM, Conditional
Access, Exchange Online, Teams, SharePoint, DLP, Intune, and a service desk
runbook resolving a real account-lockout case.

---

## Where the instinct comes from

I didn't start in AI. I started on a help desk, and that's still how I think: notice the manual bottleneck, script it, measure whether it actually got faster.

- **IT Support Specialist — Norshel Incorporated** (Winnipeg, MB, Mar 2025–Present) — Tier 1 support across Windows 10/11 and M365; M365 user/mailbox/MFA administration and onboarding-offboarding.
- **Technical Support Specialist (Part-Time) — Western Drug Distribution Company** (Winnipeg, MB, Aug 2023–Feb 2025) — First point of contact for escalated hardware and M365 incidents across warehouse operations; resolved 95% of escalations independently, cut operational downtime 40%.
- **Technical Support Specialist and Help Desk Technician — Transmission Company of Nigeria** (Abuja, Nigeria, Jul 2020–Feb 2023) — Tier 1-2 support to 50+ staff, ServiceNow queue at 98% SLA adherence. Where the onboarding automation above started.

**Track record:** 98% user satisfaction · 95% first-contact resolution · 98% SLA adherence · Post-Degree Diploma, Network and Systems Administration / Network Security (University of Winnipeg).

---

## Current stack

- **Agents & Orchestration:** n8n, Vapi voice agents, Claude Agent SDK, LangGraph *(building)*
- **LLMs & RAG:** Anthropic Claude (primary), OpenAI APIs, pgvector/Supabase similarity search, prompt engineering
- **IT & Identity — where the AI work is grounded:** Microsoft 365, Entra ID/Azure AD, Active Directory, Group Policy, MFA, Windows Server 2016–2025, Linux server administration, ServiceNow, Jira
- **Scripting & Automation:** PowerShell, Python, Bash, REST APIs, webhooks
- **CI/CD & Deployment:** GitHub Actions (lint, test, build gates), Vercel, Fly.io, Docker
- **Networking & Security:** TCP/IP, DNS, DHCP, VLAN, VPN, firewalls, Cisco switches/routers
- **Other:** Git/GitHub, basic HTML/CSS, Model Context Protocol (MCP)

---

## Shipped, not just building

CI/CD runs across two active repositories on every push and PR: linting, test suites (63 tests on the flagship Next.js app, 21 on webhook-security-critical paths, 8 on auth primitives), and build verification. `norshelinc-portal` — the FastAPI backend behind norshelinc.ca — has a genuine hard gate: the deploy job is dependency-blocked on a verify job covering ruff linting, pytest coverage of bcrypt hashing, JWT round-trips, and rejection of tampered/expired/malformed tokens. Nothing ships there unless every check passes.

## Building (Project Vortex Ascent)

| Focus | Status | Where |
|---|---|---|
| Multi-provider LLM API mastery | 🚀 Building | `llm-toolkit` |
| Prompt engineering as system design | ✅ Live | Vortex FX, AI Receptionist |
| RAG architecture & retrieval | ✅ Shipped | Vortex FX |
| CI/CD & deployment gates | ✅ Shipped | 2 active repos |
| Agent orchestration (LangGraph/MCP) | 🚀 Building | `business-ops-agent` (flagship) |
| Evaluation & observability | 🚀 Building | eval harness + RAGAS |

Each one answers a specific hiring question rather than padding a skills list.

---

## Certifications

Cisco CCNA · ITIL Foundation · CompTIA Security+ *(in progress)* · Anthropic: Claude Code in Action, Building with the Claude API, Claude with Google Cloud's Vertex AI, AI Fluency: Framework and Foundations, Claude 101

---

## The positioning

I'm not a data scientist and I'm not just a prompt writer. I take business problems, build durable agentic workflows around them, and keep them running in production — the ops discipline came from 3+ years in IT support and network security; the AI chops came from building n8n, Vapi, and Claude systems, a real RAG pipeline, and CI/CD gates that actually block bad deploys.

---

## Let's connect

- 📧 [m.abdulmaliksani008@gmail.com](mailto:m.abdulmaliksani008@gmail.com)
- 💼 [LinkedIn](https://www.linkedin.com/in/muhammed-abdulmalik-a84131267)
- 📺 [@malikautomates_](https://instagram.com/malikautomates_) — build-in-public on Instagram, TikTok, X

Hiring for AI Engineer or support-engineering roles? Already running agentic systems in production? I'd like to see what you're building.
