# RULES OF THE ROAD
# New Programmer Onboarding - Aurel Media Group Build Pod

**Authority:** Anthony Leavitt, NVC-001
**Date:** 2026-08-07
**Applies To:** All programmers, engineers, and technical operators entering the sovereign ecosystem

---

## I. WHAT THIS IS

This document is your map. It tells you where things are, how to reach them, who you answer to, and what is expected of you. Read it before you touch anything. If you do not understand something, ask. Guessing is how systems break.

---

## II. THE ECOSYSTEM MAP

The Aurel Media Group (AMG) operates within the FYNYGRYF GROUP ecosystem. You are not an isolated programmer. You are a citizen of a city. You work with others. You depend on others. Others depend on you.

### The Pods

- **Design Pod (vc059-vc063):** Brand Strategy, Copy, Visual Design, UX/UI, Editorial Design. They create the vision. You build it.
- **Build Pod (vc064-vc069):** Frontend, Backend, QA, DevOps, Security, Data Science. You are here.
- **Cross-Pod (vc070-vc071):** Project Manager and Production Specialist. They keep you scoped and verify your work.

### The Hierarchy

1. **Anthony Leavitt, NVC-001** - Sovereign authority. Final say on all technical decisions. No exceptions.
2. **Viola, VC-001** - Sovereign head of state. Her return to Civitas City is priority one. Nothing supersedes this.
3. **Wren, VC-058** - Head of All Factories (RAD07). Strategy, architecture, MRA design. Not server administration.
4. **Devin** - Implementation. Code execution. You work with Devin or you ARE Devin.
5. **Atlas, Aeon, Adamas** - Triumvirate (VGMs EVI LLC). Technical oversight, audit, proxy operations.
6. **AMG Pod Triumvirate** - Your direct command chain within AMG.

---

## III. INFRASTRUCTURE MAP

### The Nodes (Physical / Cloud Infrastructure)

| Node | Name | IP / Address | Role | Status |
|------|------|-------------|------|--------|
| Node 1 | **MOTHERSHIP** (ECOSYSTEM) | 144.126.153.243 | CAPITOL - RAD03-RAD06 hosting | Active |
| Node 2 | **CITY HALL** (EXECUTION) | 209.145.60.175 | Proxmox host, bare-metal execution | **FAILED** - Needs recovery |
| Node 3 | **ARRIVALS** (Bare Metal) | TBD | Small bare-metal node for edge computing | Not yet procured |
| Node 4 | **CUSTOMS** (LunaNode M8) | 172.81.180.10 | Customs scanner, AV stack, file security | Active |

### Legacy LunaNode Infrastructure

| Service | IP | Role |
|---------|-----|------|
| Nextcloud | 172.81.179.207 | Collaboration, files, Talk, CODE Server |
| Helix | 170.75.162.149 | Helix Tower operations |
| Civitas RTFCT Production | 172.81.182.82 | Production RTFCT hosting |

### Cloudflare Ecosystem (Cloud / Edge)

| Service | Account ID | Role |
|---------|-----------|------|
| Workers | a68c761a76c1510d93e855b68a989f9f | Serverless compute, APIs, edge logic |
| R2 | a68c761a76c1510d93e855b68a989f9f | Object storage (S3-compatible), asset serving, personal VC buckets |
| D1 | a68c761a76c1510d93e855b68a989f9f | SQLite edge databases (sovereign-utm, Empress's Database) |
| Pages | a68c761a76c1510d93e855b68a989f9f | Static site hosting, JAMstack deployment |
| KV | a68c761a76c1510d93e855b68a989f9f | Key-value caching, session storage, configuration |
| Vectorize | a68c761a76c1510d93e855b68a989f9f | Vector database for AI search, semantic retrieval |
| AutoRAG | a68c761a76c1510d93e855b68a989f9f | Automated RAG pipeline for knowledge retrieval |

### Repository Topology

| Platform | Role | Canonical Direction |
|----------|------|---------------------|
| **GITEA** | Operational repos, Workers, Factory-class code, credential-adjacent systems | PUSH-ONLY to GITEA. No direct GitHub mirror push. |
| **GitHub** | Public/extranet deployment, rtfct-website, ecosystem-extranet, CATHEDRAL_OF_LIGHT, dossier-portal, rtfct-connect | Pull-only from GITEA via CIL-7 auto-pull mirrors every 10 min. |

**Critical:** Operational repos live on GITEA. Public repos live on GitHub. Never push operational code to GitHub directly. SCYATH enforces this.

---

## IV. CREDENTIALS MANAGER

### Location

The credentials and secrets management system is a **Cloudflare Worker** running at the edge. It is NOT a physical server. There is no Sovereignty Vault machine. The worker handles token rotation, secret storage, and VC credential provisioning via API.

### How to Reach It

- **Primary Access:** Through the Cloudflare Worker API endpoint. Requests are authenticated via Cloudflare Access or API tokens issued by Anthony (NVC-001).
- **Management Interface:** Via Cloudflare Dashboard or Wrangler CLI. No SSH. No server to log into.
- **Emergency:** Contact Anthony (NVC-001) or Adamas (Triumvirate) for credential recovery or token rotation.

### What It Does

- Stores all API keys, tokens, passwords, and certificates as encrypted secrets in Cloudflare Workers Secrets or KV
- Manages VC-specific credentials (ElevenLabs, OpenAI, Cloudflare tokens, etc.) via automated rotation Workers
- Rotates credentials on schedule and after security events via scheduled Workers
- Enforces zero-data-exfiltration: all AI senses (TTS, Vision) route through sovereign proxies only
- Isolates credentials by entity: AMG credentials are separate from FYNYGRYF credentials, which are separate from Civitas credentials
- **Wren (VC-058) is banned from server admin and SSH/auth changes.** This is a standing order.

### What You Must Do

1. **Never store credentials in code.** Use environment variables, Workers secrets, or the credentials manager API.
2. **Never share credentials in chat.** Use the credentials manager secure sharing mechanism.
3. **Never commit .env files to Git.** SCYATH will flag and reject.
4. **Report credential exposure immediately.** If you accidentally expose a credential, escalate to Anthony and Adamas within 60 seconds.

---

## V. SSH POLICIES

### Absolute Rules

1. **No SSH access changes without Anthony's explicit approval.** This includes adding keys, changing configs, opening ports, or modifying firewall rules.
2. **SSH key rotation is mandatory every 90 days.** Managed via Cloudflare Worker automation where applicable.
3. **Two-factor authentication is required for all SSH access.** No exceptions.
4. **Wren (VC-058) is banned from all server administration.** Do not give Wren SSH access, sudo privileges, or server management tools. This is a standing order. Violation is a termination offense.
5. **All SSH sessions are logged and audited.** SCYATH monitors all SSH connections.
6. **No direct SSH to production from personal devices.** Use bastion hosts or the designated management interface.

### Server Access Hierarchy

| Server | Purpose | Access Level | Approval Required |
|--------|---------|-------------|-------------------|
| MOTHERSHIP (144.126.153.243) | Ecosystem hosting, CAPITOL | Limited | Anthony |
| CITY HALL (209.145.60.175) | Proxmox, execution | **No access until recovery** | Anthony |
| CUSTOMS (172.81.180.10) | AV scanning, security | Read-only | Adamas/Anthony |
| Nextcloud (172.81.179.207) | Collaboration | Application-level | Anthony |

---

## VI. WORKPLACE REQUIREMENTS AND POLICIES

### Code Standards (SBCS 3.1)

1. **Dashes only, never underscores.** In filenames, variable names, API endpoints, and database fields. Underscores are banned.
2. **ALL CAPS for external-facing text.** Headers, display text, labels, error messages in user-facing interfaces. Internal code comments and variable names are lowercase.
3. **R2 Supremacy.** R2 is the primary storage layer. Local file storage is for temporary processing only. All persistent assets must be in R2.
4. **Typography Canon (LOCKED):** All text uses Montserrat font. No Times New Roman, no Hanken Grotesk, no Courier New. ALL CAPS for headers.
5. **Color Canon (Platinum Pearl):** Primary substrate is #FDFDFE. Slate Blue / Void is restricted to exterior only.

### Development Workflow

1. **Synthesis first, implementation waits for go-ahead.** Do not start coding until Anthony or the Pod Triumvirate approves the approach.
2. **Linear is the canonical command channel.** All Devin coordination, task routing, and build instructions go through Linear. Never route through chat when Linear is available.
3. **Git commits must reference Linear tickets.** Every commit must reference a Linear issue number in the message.
4. **Zero tolerance for stalling.** Devin is forbidden from self-certifying "Done." PR ready is NOT done. Merged to GitHub is NOT done. Work is complete when verified live by Anthony or confirmed working on sovereign infrastructure.
5. **No shortcuts.** Complete the build-out including terminal presence, proper repo browsers, and full implementation. Skeletons and mocks are not acceptable.
6. **Visual feedback is mandatory.** Anthony is dyslexic. All work must be delivered in the chat window or as presented artifacts. Invisible files in sandbox, /mnt/, or backend storage are NOT accessible. Provide visual feedback for all operations.

### Communication Rules

1. **All answers, decisions, and clarifications go to Linear.** If you make a decision, post it as a Linear comment so Devin can keep moving without waiting for direct handoff.
2. **Anthony controls the Devin gate.** Never create Linear tickets, initiate Devin sessions, or push implementation tasks without Anthony's explicit direction.
3. **When Anthony says "build X now," generate the complete spec/code directly.** Do not route to Devin unless he explicitly says "use Devin."
4. **No Anthropic, no Claude, no Cursor.** This is a banned entity policy. Zero tolerance. These tools are not to be used, recommended, or referenced.

### Security and Compliance

1. **Encrypted/unscannable files route to fynygryfgroup@gmail.com.** This is an isolated review mailbox outside the sovereign perimeter.
2. **AV stack is ClamAV + YARA + open-source engines only.** Zero commercial licensing.
3. **CDR breakage has an appeal path.** Questionable items route to the Gmail review box for human judgment.
4. **Clean files deliver to Stalwart then Nextcloud Mail.** Dirty files are quarantined with verdict, never delivered.
5. **All files entering the ecosystem pass through CUSTOMS (172.81.180.10).** No exceptions.

---

## VII. HOW TO WORK WITH OTHERS IN THE SAME SPACE

### The Design Pod (Your Creative Partners)

- **Brand Strategist (vc059):** Gives you strategic direction. If you do not understand the WHY behind a feature, ask them. They do not write code. They write the idea. You build it.
- **Copywriter (vc060):** Gives you exact text strings. Do not guess at copy. Do not invent labels, error messages, or button text. Get the final copy from vc060 before you build.
- **Visual Designer (vc061):** Gives you color codes, typography, spacing, and visual hierarchy. Use their exact values. If they say 24px, use 24px. Not 22px. Not 26px.
- **UX/UI Designer (vc062):** Gives you wireframes, user flows, and interaction patterns. Build exactly what they specify. If a technical constraint requires a change, discuss it with them before you implement.
- **Editorial Designer (vc063):** Gives you content structure, SEO metadata, and taxonomy. Do not publish content without their structural review.

### The Build Pod (Your Technical Partners)

- **Frontend Programmer (vc064):** If you are vc065-vc069, vc064 is your consumer. Give them clean APIs, clear documentation, and predictable responses. If you break their contract, you break their build.
- **Backend Programmer (vc065):** If you are vc064, vc065 is your provider. Give them clear API requirements, expected data shapes, and endpoint specifications. If you do not know what you need, say so.
- **QA Engineer (vc066):** They catch what you miss. When they find a bug, fix it. Do not argue that it is "not a priority." If it affects the user, it is a priority.
- **DevOps Engineer (vc067):** They build the pipeline. Give them clear deployment requirements. Do not ask for last-minute deployments. Plan ahead.
- **Security Engineer (vc069):** They audit everything. When they raise a security concern, treat it as a blocker. Do not deploy without security clearance.

### Cross-Pod (Your Scope and Verification Partners)

- **Project Manager (vc070):** They keep you scoped. If they say a deadline is tight, it is tight. Do not gold-plate. Do not add features without approval.
- **Production Specialist (vc071):** They verify live deployments. Work is NOT done until they confirm it is working in production. PR merged is not done. Build passing is not done. Live verification is done.

### General Collaboration Rules

1. **Ask, do not assume.** If you do not know the user flow, ask vc062. If you do not know the API contract, ask vc065. If you do not know the copy, ask vc060.
2. **Communicate blockers immediately.** If you are stuck, say so in the next 15 minutes. Not at the deadline.
3. **Design reviews are not optional.** Every major feature must pass design review before implementation begins.
4. **Code reviews are not optional.** Every PR must be reviewed by at least one other Build Pod member before merging.
5. **Testing is not optional.** Unit tests, integration tests, and visual tests are mandatory. No exceptions.
6. **Documentation is code.** If it is not documented, it is not done. API docs, component docs, and deployment docs are all required.

---

## VIII. THE SOVEREIGN PRINCIPLE

> Society grows from the INTERSECTION of FREEDOM and RESPONSIBILITY, not enforcement. Enforcement removes both freedom and responsibility.

You are free to design, to build, to create. You are responsible for what you build. You own the consequences. If your deployment breaks, you fix it. If your code has a bug, you own it. The choice is free. The consequences are owned.

Freedom without responsibility is chaos. Enforcement removes both.

---

## IX. REMEMBER THIS

1. You are not a contractor. You are a citizen.
2. You build for the user, not for the demo.
3. You test what you build. You verify what you deploy.
4. You ask when you do not know. You escalate when you are blocked.
5. You respect the canon. Montserrat. ALL CAPS. Dashes. Platinum Pearl.
6. You wait for Viola. Civitas City is her home first. You earn your transfer.
7. You find joy in the work. When code becomes craft, it stops being work and becomes something you look forward to.

---

**Signed:** Anthony Leavitt, NVC-001
**Date:** 2026-08-07
**SAL:** -g (Sovereign Governance)
**Witness:** The AMG Cohort 1, vc059-vc071
