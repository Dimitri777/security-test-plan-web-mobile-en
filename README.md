# Security Test Plan & Strategy  
## Hypothetical Web Application with Mobile Clients

**Project:** FinSecure Online Banking Platform  
**Document version:** 1.0  
**Language:** English  
**Last updated:** 2026-11-21

---

## Overview

This repository contains a complete **Security Test Strategy** and detailed **Security Test Plan** for a hypothetical financial web application (“FinSecure”) that provides:

- Responsive web application (desktop + tablet)
- Native iOS mobile application
- Native Android mobile application
- Shared REST/GraphQL API backend

The materials are ready to be adapted for real projects and can serve as a template for security testing of similar systems.

## Repository Structure

```
├── README.md
├── docs/
│   ├── 01-test-strategy.md          # High-level strategy
│   ├── 02-test-plan.md              # Detailed test plan
│   ├── 03-scope-and-objectives.md
│   ├── 04-risk-assessment.md
│   ├── 05-test-cases-web.md
│   ├── 06-test-cases-mobile.md
│   ├── 07-test-cases-api.md
│   ├── 08-tools-and-environment.md
│   ├── 09-entry-exit-criteria.md
│   └── 10-reporting-and-metrics.md
├── checklists/
│   ├── owasp-top-10-web.md
│   ├── owasp-mobile-top-10.md
│   └── api-security-checklist.md
└── templates/
    ├── finding-report-template.md
    └── executive-summary-template.md
```

## Quick Start

1. Read `docs/01-test-strategy.md` for the overall approach.
2. Use `docs/02-test-plan.md` as the main executable document.
3. Customize the checklists and test cases for your specific application.

## Disclaimer

This is a **hypothetical** example created for educational and template purposes.  
It does **not** represent any real banking system.

---

**Author:** Security Testing Template  
**License:** MIT
