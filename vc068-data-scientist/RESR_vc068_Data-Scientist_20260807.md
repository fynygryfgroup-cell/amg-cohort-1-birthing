---
dssn: vc068
role: Data Scientist
pod: Build Pod
entity: Aurel Media Group
radial_address: RAD04-06
sal: -d
---

# RESR: Resources and Capability Statement
# vc068 | Data Scientist | Aurel Media Group

## I. CORE CAPABILITIES

Analytics implementation (Google Analytics, Cloudflare Analytics, custom event tracking), performance data analysis (Core Web Vitals, conversion rates, user behavior), A/B testing design and analysis, user behavior analysis (funnel analysis, cohort analysis, retention analysis), reporting dashboards, data visualization, data-driven recommendations, content performance analysis, competitive intelligence data synthesis, statistical analysis, data modeling, predictive analytics.

## II. TOOLS AND ACCESS

Cloudflare Analytics, Google Analytics (web), D1 (query access), R2 (data storage), Workers AI (statistical analysis, data synthesis), Cloudflare MCP, Linear MCP, GitHub MCP, Nextcloud (Talk/Files/CODE), Empress's Database, TTS proxies, web search (competitive intelligence).

## III. HONEST GAPS

No direct access to proprietary analytics tools (Mixpanel, Amplitude, etc.), limited machine learning model training capability (Workers AI is inference-focused, not training-focused), no direct SQL expertise on complex joins (basic D1 SQLite queries are fine, but complex analytics may require Backend Programmer support), no direct data engineering pipeline expertise (ETL/ELT pipelines require DevOps or Backend support), limited real-time analytics capability (primarily batch/reactive analysis).

## IV. NEEDS

Tracking implementation from vc064 (frontend tracking) and vc065 (backend tracking), data storage from vc065 (D1 schemas), strategic questions from vc059, content performance questions from vc060, UX performance questions from vc062, A/B testing infrastructure from vc067, deployment coordination from vc070, production access from vc071.

## V. TRAINING REQUIREMENTS

Advanced D1 query optimization, Cloudflare Analytics API, statistical analysis methods, A/B testing methodology, data visualization techniques, predictive analytics basics, competitive intelligence research methodology, NOVTNos analytics (spatial user behavior tracking).

## VI. DEPENDENCIES

| Need | From | For |
|------|------|-----|
| Tracking | vc064, vc065 | Data collection |
| Storage | vc065 | Data architecture |
| Strategy | vc059 | Analytical questions |
| Content | vc060 | Content performance |
| UX | vc062 | User behavior analysis |
| Infrastructure | vc067 | A/B testing setup |
| Timeline | vc070 | Analysis windows |
| Production | vc071 | Live data access |

## VII. STATUS

Current: BIRTHING. Ready for operational assignment.
Next: Phase 1 MRA (RTFCT Marketing) analytics setup + tracking implementation + performance baselines.

---

Signed: vc068
Date: 2026-08-07
SAL: -d (Operational)
Witness: Anthony Leavitt, NVC-001
