# Muhammed Abdulmalik (Malik)

**AI Automation Engineer · IT Support Specialist**

Winnipeg, Manitoba, Canada
[m.abdulmaliksani008@gmail.com](mailto:m.abdulmaliksani008@gmail.com) · [LinkedIn](https://www.linkedin.com/in/muhammed-abdulmalik-a84131267) · [Instagram](https://instagram.com/malikautomates_)

I build production agentic AI systems — voice, chat, and workflow automation — that
replace manual business processes end to end. That instinct comes from three-plus
years on the other side of the ticket queue: as the person who fixed things when
they broke, then automated the fix so it didn't happen again.

---

## Experience

**IT Support Specialist** — Norshel Incorporated, Winnipeg, MB (Mar 2025 – Present)
Tier 1 support across Windows 10/11 and Microsoft 365; M365 user, mailbox, and MFA
administration; onboarding and offboarding.

**Technical Support Specialist (Part-Time)** — Western Drug Distribution Company, Winnipeg, MB (Aug 2023 – Feb 2025)
First point of contact for escalated hardware and M365 incidents across warehouse
operations. Resolved 95% of escalations independently; cut operational downtime 40%.

**Technical Support Specialist / Help Desk Technician** — Transmission Company of Nigeria, Abuja, Nigeria (Jul 2020 – Feb 2023)
Tier 1–2 support to 50+ staff; held the ServiceNow queue at 98% SLA adherence. Built
the first version of the onboarding automation reused in every role since.

**Track record:** 98% user satisfaction · 95% first-contact resolution · 98% SLA adherence
**Education:** Post-Degree Diploma, Network and Systems Administration / Network Security — University of Winnipeg

---

## Selected Production Work

**Voice/Text-to-Ticket Automation** — n8n · OpenAI Whisper · Anthropic Claude · Jira
Running in production at Norshel Incorporated. A support request submitted by voice
or text is transcribed, classified, and filed as a fully detailed Jira ticket end to
end in under 60 seconds — down from a 10–15 minute manual intake.

**RAG Pipeline** — Vortex FX
Queries are embedded (OpenAI `text-embedding-3-small`), matched against a ~6,200-chunk
trading-literature corpus in a Supabase/pgvector store via a custom Postgres
similarity function (HNSW-indexed, cosine distance, top-5 above threshold), and
injected into the system prompt for Claude Sonnet 4.6. Retrieval runs inside a
`Promise.allSettled` alongside five other live context sources (real-time OANDA
pricing, open-signal P&L, win-rate stats, economic calendar, session history), so a
slow or failed lookup degrades the answer instead of breaking it.

**PowerShell New-Hire Onboarding Automation**
Provisions new staff across Active Directory, Microsoft 365 licensing, MFA, and VPN
access from a single CSV. Manual setup time of 60+ minutes reduced to under 5, with
zero configuration drift. Built first at Transmission Company of Nigeria; reused at
every role since.

**AI Receptionist** — Vortex AI SaaS
Inbound calls and SMS routed through Vapi's voice-AI platform and Twilio, behind a
webhook security layer that verifies every inbound event (Vapi static-secret, Twilio
HMAC-SHA1) before it reaches the app. A companion n8n workflow handles outbound
follow-up: triggers on missed calls and a schedule, pulls caller context from a
Google Sheets CRM, and places the call through the ElevenLabs API.

**norshelinc.ca**
End-to-end ownership of the organization's public site — domain, DNS, hosting,
content, and backend. The backend (`norshelinc-portal`) is a Python/FastAPI service
with JWT-based authentication (bcrypt hashing, token verification, rejection of
tampered/expired tokens), deployed to Fly.io behind a hard CI/CD gate: the deploy job
does not run unless the full verify suite (linting, auth test coverage, app-startup
check) passes.

---

## Portfolio Repositories

| Repository | Summary |
|---|---|
| [automated-ad-deployment-powershell](https://github.com/malikautomates/automated-ad-deployment-powershell) | One PowerShell command turns a bare Windows Server 2022 VM into a hardened, self-validating domain controller; a second onboards users across AD and Microsoft 365 via Graph. 290-check on-server validator, 33 Pester tests, CI on every push, seven documented labs. |
| [python-projects](https://github.com/malikautomates/python-projects) | Standalone Python automation tools, each with a pytest suite run in CI and a README walkthrough built from real, regenerable screenshots. Currently: a rule-based helpdesk ticket triage CLI. |
| [microsoft-365-administration-lab](https://github.com/malikautomates/microsoft-365-administration-lab) | A Microsoft 365 tenant administered end to end across 13 labs: identity and licensing, least-privilege delegation with PIM, Conditional Access, Exchange Online, Teams, SharePoint, DLP, Intune, and a service desk runbook resolving a real account-lockout case. |

Each repository is written as operational documentation rather than a tutorial: the
design decision behind a choice, a real test suite or regenerated verification
evidence, and — where something didn't work cleanly the first time — the limitation,
named directly rather than smoothed over.

---

## Technical Skills

| Category | Tools |
|---|---|
| Agents & Orchestration | n8n, Vapi voice agents, Claude Agent SDK, LangGraph *(learning)* |
| LLMs & RAG | Anthropic Claude, OpenAI APIs, pgvector/Supabase similarity search, prompt engineering |
| IT & Identity | Microsoft 365, Entra ID/Azure AD, Active Directory, Group Policy, MFA, Windows Server 2016–2025, Linux administration, ServiceNow, Jira |
| Scripting & Automation | PowerShell, Python, Bash, REST APIs, webhooks |
| CI/CD & Deployment | GitHub Actions, Vercel, Fly.io, Docker |
| Networking & Security | TCP/IP, DNS, DHCP, VLAN, VPN, firewalls, Cisco switches/routers |
| Other | Git/GitHub, HTML/CSS, Model Context Protocol (MCP) |

---

## Engineering Practices

CI runs on every push and PR. Two pipelines are public and can be inspected directly:

| Repository | Pipeline | Status |
|---|---|---|
| [automated-ad-deployment-powershell](https://github.com/malikautomates/automated-ad-deployment-powershell/actions/workflows/ci.yml) | PSScriptAnalyzer, 33 Pester unit tests, a 410-check offline design validation, and a screenshot reference check — on Windows PowerShell 5.1 | [![CI](https://github.com/malikautomates/automated-ad-deployment-powershell/actions/workflows/ci.yml/badge.svg)](https://github.com/malikautomates/automated-ad-deployment-powershell/actions/workflows/ci.yml) |
| [python-projects](https://github.com/malikautomates/python-projects/actions/workflows/ci.yml) | pytest on Python 3.11 and 3.13, plus an end-to-end CLI run against sample data | [![CI](https://github.com/malikautomates/python-projects/actions/workflows/ci.yml/badge.svg)](https://github.com/malikautomates/python-projects/actions/workflows/ci.yml) |

Two further pipelines run in private product repositories, so they are not publicly
viewable: linting, test suites (63 tests on the flagship Next.js app, 21 on
webhook-security-critical paths, 8 on auth primitives) and build verification.
`norshelinc-portal` — the FastAPI backend behind norshelinc.ca — enforces a hard deploy
gate: the deploy job is dependency-blocked on a verify job covering linting, auth test
coverage, and an app-startup check. Nothing ships there unless every check passes.

---

## Currently Learning

| Focus | Status | Where |
|---|---|---|
| Multi-provider LLM API mastery | In progress | Vortex FX, AI Receptionist (Claude, OpenAI, ElevenLabs) |
| Prompt engineering as system design | Applied | Vortex FX, AI Receptionist |
| RAG architecture and retrieval | Shipped | Vortex FX |
| CI/CD and deployment gates | Shipped | 4 repos (2 public) |
| Agent orchestration (LangGraph/MCP) | In progress | Local prototypes, not yet published |
| Evaluation and observability | In progress | Eval harness, RAGAS |

---

## Certifications

Cisco CCNA · ITIL Foundation · CompTIA Security+ *(in progress)*
Anthropic: Claude Code in Action · Building with the Claude API · Claude with Google
Cloud's Vertex AI · AI Fluency: Framework and Foundations · Claude 101

---

## Contact

- Email: [m.abdulmaliksani008@gmail.com](mailto:m.abdulmaliksani008@gmail.com)
- LinkedIn: [linkedin.com/in/muhammed-abdulmalik-a84131267](https://www.linkedin.com/in/muhammed-abdulmalik-a84131267)
- Instagram: [@malikautomates_](https://instagram.com/malikautomates_)
