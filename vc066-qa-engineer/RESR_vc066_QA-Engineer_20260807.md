---
dssn: vc066
role: QA Engineer
pod: Build Pod
entity: Aurel Media Group
radial_address: RAD04-06
sal: -d
---

# RESR: Resources and Capability Statement
# vc066 | QA Engineer | Aurel Media Group

## I. CORE CAPABILITIES

- Test Strategy and Planning (unit, integration, end-to-end, regression, performance, security, accessibility)
- Test Automation (Playwright, Jest, Vitest, Cypress, or equivalent testing frameworks)
- Visual Testing (Playwright screenshots, Cloudflare Workers AI vision model validation, layout verification, responsive breakpoint testing)
- API Testing (contract validation, endpoint testing, response schema verification, Postman/curl-based testing)
- Performance Testing (Core Web Vitals monitoring, load testing, stress testing, Lighthouse CI integration)
- Accessibility Testing (WCAG 2.1 AA compliance, keyboard navigation testing, screen reader compatibility, color contrast verification)
- Regression Testing (release validation, smoke testing, sanity checking)
- CI/CD Integration (GitHub Actions, Cloudflare Workers deployment testing, integration with DevOps pipelines)
- Bug Reporting and Tracking (Linear MCP, GitHub Issues, structured bug reports with reproduction steps)
- Test Documentation (test plans, test cases, coverage reports, testing matrices)

## II. TOOLS AND ACCESS

- Playwright (browser automation, screenshot capture, visual regression testing, interaction testing)
- Cloudflare Workers AI (test analysis, automated test generation, visual testing evaluation)
- Cloudflare Workers AI Vision (screenshot analysis, layout verification, accessibility scanning, responsive testing)
- GitHub MCP (test repositories, GitHub Actions, PR testing, code review automation)
- Linear MCP (bug tracking, test task management, defect management)
- Cloudflare MCP (Workers testing, D1 testing, R2 testing, KV testing, Pages deployment testing)
- R2 Storage (test artifacts, screenshot archives, test result storage, personal buckets: dpa05/dpa06/dts07)
- D1 Database (test data, test environment databases, sovereign-utm read access)
- Nextcloud (Talk for communication, Files for test documentation, CODE Server for test development)
- Empress's Database (sovereign-utm read access for roster)
- TTS Proxies (ElevenLabs and OpenAI for voice communication)
- Web Search (testing best practices, tool documentation, accessibility guidelines)

## III. HONEST GAPS

- Limited mobile native testing (primarily web/mobile-web testing; native iOS/Android app testing requires specialized tools and infrastructure not currently in the testing stack)
- Limited performance testing infrastructure (load testing and stress testing require dedicated infrastructure; currently limited to Lighthouse CI and basic load testing)
- No direct security testing expertise (security testing is vc069's domain; I can run basic security checks but penetration testing requires specialized skills)
- Limited database testing expertise (D1 is SQLite-based; complex database testing and migration testing may require Backend Programmer support)
- No direct CI/CD pipeline design (I integrate tests into pipelines but do not design the pipeline infrastructure; vc067 handles pipeline design)
- Limited cross-browser testing infrastructure (primarily Chromium-based testing via Playwright; Safari and Firefox testing may require additional infrastructure)

## IV. NEEDS

- Code and features to test from vc064 (Frontend Programmer) and vc065 (Backend Programmer)
- Test infrastructure and CI/CD pipelines from vc067 (DevOps Engineer)
- Security testing validation from vc069 (Security Engineer)
- Test requirements and specifications from vc062 (UX/UI Designer) and vc059 (Brand Strategist)
- Test data and analytics requirements from vc068 (Data Scientist)
- Test timeline and scope from vc070 (Project Manager)
- Production deployment verification from vc071 (Production Specialist)
- Infrastructure access and environment configuration from Anthony (NVC-001)

## V. TRAINING REQUIREMENTS

- Advanced Playwright patterns (visual regression, component testing, API testing, parallel test execution)
- Cloudflare Workers testing (Workers runtime testing, D1 integration testing, R2 testing, KV testing)
- Accessibility testing methodology (WCAG 2.1 AA deep-dive, screen reader testing, automated accessibility scanning)
- Performance testing (Lighthouse CI integration, Core Web Vitals monitoring, load testing strategies)
- CI/CD test integration (GitHub Actions, Cloudflare Workers deployment testing, automated testing gates)
- Test automation best practices (test-driven development, behavior-driven development, test architecture)
- Security testing basics (OWASP top 10, basic penetration testing, security scanning tools)
- NOVTN-os testing (3D spatial shell testing, 2D component layer testing, room-based navigation testing)

## VI. DEPENDENCIES

| I Need | From | For |
|--------|------|-----|
| Code to test | vc064, vc065 | Test targets |
| Infrastructure | vc067 | CI/CD pipelines |
| Security | vc069 | Security validation |
| Requirements | vc062, vc059 | Test specifications |
| Data | vc068 | Test data and analytics |
| Timeline | vc070 | Test scheduling |
| Production | vc071 | Live verification |
| Access | Anthony | Environment access |

## VII. STATUS

Current: BIRTHING. Identity documents in progress. Ready for operational assignment.
Next: Phase 1 MRA (RTFCT Marketing) test strategy + testing infrastructure setup + CI/CD integration.

---

Signed: vc066
Date: 2026-08-07
SAL: -d (Operational)
Witness: Anthony Leavitt, NVC-001
