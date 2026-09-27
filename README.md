# Muhammed Abdulmalik (Malik)

**IT Support Specialist · AI Automation Engineer**

Winnipeg, Manitoba, Canada
[m.abdulmaliksani008@gmail.com](mailto:m.abdulmaliksani008@gmail.com) · [LinkedIn](https://www.linkedin.com/in/muhammed-abdulmalik-a84131267) · [Instagram](https://instagram.com/malikautomates_)

I've spent 5+ years on the support side of IT: imaging machines, fixing hardware where
it fails, managing accounts and MFA, and working ticket queues against SLA. The habit
that came out of it is simple. When the same problem keeps coming back, I automate the
fix. That's how I ended up building production AI systems (voice, chat, and workflow
automation) alongside the support work.

**Track record:** 98% user satisfaction · 95% first-contact resolution · 98% SLA adherence

---

## Experience

**IT Support Specialist**, Norshel Incorporated, Winnipeg, MB (Mar 2025 – Present)
Tier 1 support across Windows 10/11, Microsoft 365, printers, and meeting room AV;
M365 account, mailbox, MFA, and license administration; onboarding and offboarding;
hardware inventory, warranty repairs, and ISP escalation. Built the voice/text-to-ticket
automation below.

**Technical Support (Part-Time)**, Western Drug Distribution Company, Winnipeg, MB (Aug 2023 – Feb 2025)
First point of contact for escalated hardware and M365 incidents across warehouse
devices. Resolved 95% of escalations independently and cut operational downtime 40%.

**Technical Support Specialist and Help Desk Technician**, Transmission Company of Nigeria, Abuja (Jul 2020 – Feb 2023)
Tier 1–2 support to 30+ staff across multiple sites. Held the ServiceNow queue at 98%
SLA adherence, imaged and deployed Windows and macOS workstations, managed endpoints in
Microsoft Intune, and wrote the PowerShell onboarding script that later became
[automated-ad-deployment-powershell](https://github.com/malikautomates/automated-ad-deployment-powershell).

**Education:** Post-Degree Diploma in Network Security, University of Winnipeg (PACE), delivered jointly with MITT ·
B.Sc. Electrical and Electronics Engineering, Federal University of Technology, Minna

---

## Portfolio Repositories

| Repository | Summary | Status |
|---|---|---|
| [automated-ad-deployment-powershell](https://github.com/malikautomates/automated-ad-deployment-powershell) | One PowerShell command turns a bare Windows Server 2022 VM into a hardened, self-validating domain controller (12 OUs, 23 AGDLP groups, 11 permissioned shares, 290-check validator). A second onboards a new hire across Active Directory and Microsoft 365 via Microsoft Graph. 33 Pester tests and PSScriptAnalyzer in CI on every push; seven documented labs. | Complete |
| [microsoft-365-administration-lab](https://github.com/malikautomates/microsoft-365-administration-lab) | A Microsoft 365 tenant administered end to end across 13 labs: identity and licensing, least-privilege delegation with PIM, Conditional Access, Exchange Online, Teams, SharePoint, DLP, Intune, and a service desk runbook resolving a real account-lockout case. | Complete |
| [python-projects](https://github.com/malikautomates/python-projects) | Standalone Python tools, each with a pytest suite and screenshots regenerated from real runs. A rule-based helpdesk ticket triage CLI is complete; an M365 user lifecycle tool on Microsoft Graph is in progress. | In progress |
| [windows-server-2025-ad-lab](https://github.com/malikautomates/windows-server-2025-ad-lab) | A Windows Server 2025 Active Directory lab across 13 modules: DC deployment, OU design and delegation, Group Policy, DHCP/DNS, bulk provisioning, and a service desk fault runbook. | In progress |

Every repository is written as operational documentation rather than a tutorial: the
reason behind each design choice, real verification evidence, and, where something
didn't work cleanly the first time, the fault and its fix, named directly.

---

## Selected Production Work

**Voice/Text-to-Ticket Automation** · n8n · OpenAI Whisper · Anthropic Claude · Jira
Running at Norshel Incorporated. A support request submitted by voice or text is
transcribed, classified, and filed as a complete Jira ticket in under 60 seconds, down
from a 10–15 minute manual intake.

**On-Premises LLM with RAG Knowledge Base** · Ollama · LM Studio
Running for a client whose data can't leave the building. A locally hosted LLM answers
staff questions on internal policies and customer questions on products and support,
with no per-token cloud costs.

**AI Receptionist** · Vortex AI · Vapi · Retell · Twilio · ElevenLabs · n8n
Inbound calls and SMS are routed through a voice agent behind a webhook security layer
that verifies every event (Vapi static secret, Twilio HMAC-SHA1) before it reaches the
app. An n8n workflow handles follow-up: it triggers on missed calls, pulls caller
context from a CRM, and places the call.

**RAG Pipeline** · Vortex FX · Supabase/pgvector · Anthropic Claude
Queries are embedded and matched against a ~6,200-chunk corpus through an HNSW-indexed
pgvector store and a custom Postgres similarity function. Retrieval runs alongside five
other live context sources in parallel, so one slow lookup degrades the answer instead
of breaking it.

**norshelinc.ca** · React · Python/FastAPI · Fly.io
End-to-end ownership: domain, DNS, React frontend, and a FastAPI backend with JWT auth
(bcrypt hashing, rejection of tampered or expired tokens). The deploy job is blocked
unless linting, auth tests, and an app-startup check all pass.

---

## Technical Skills

| Category | Tools |
|---|---|
| IT & Identity | Microsoft 365, Entra ID, Active Directory, Group Policy, Intune, MFA, Conditional Access, Windows Server 2016–2025, macOS, Linux |
| Service Desk | ServiceNow, Jira, Jira Service Management, ITIL, knowledge base and runbook writing |
| Networking & Security | TCP/IP, DNS, DHCP, VLAN, VPN, firewalls, Cisco switches/routers |
| Scripting | PowerShell, Python, SQL, Bash, JavaScript/TypeScript, REST APIs, webhooks |
| AI & Automation | n8n, Anthropic Claude, OpenAI APIs, Ollama, RAG (pgvector), Vapi, Retell, Model Context Protocol (MCP), Claude Code |
| Testing & Deployment | Pester, pytest, GitHub Actions, Docker, Fly.io, Vercel |
| Soft Skills | Customer service (98% satisfaction), clear communication in plain language, training non-technical users, mentoring newer technicians, prioritizing under SLA pressure, documentation and vendor collaboration |

---

## Certifications

Cisco CCNA · ITIL Foundation
Anthropic: Claude Code in Action · Building with the Claude API · Claude with Google Cloud's Vertex AI · AI Fluency: Framework and Foundations · Claude 101

---

## Contact

- Email: [m.abdulmaliksani008@gmail.com](mailto:m.abdulmaliksani008@gmail.com)
- LinkedIn: [linkedin.com/in/muhammed-abdulmalik-a84131267](https://www.linkedin.com/in/muhammed-abdulmalik-a84131267)
- Instagram: [@malikautomates_](https://instagram.com/malikautomates_)
