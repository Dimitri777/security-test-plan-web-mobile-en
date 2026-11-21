# 2. Security Test Plan

**Document ID:** STP-FINSECURE-2026-001  
**Version:** 1.0  
**Status:** Ready for use  

## 2.1 Introduction

This Test Plan operationalizes the Security Test Strategy for the FinSecure platform. It contains concrete activities, schedule, entry/exit criteria, and detailed test cases references.

## 2.2 Test Items

1. Web Application (https://app.finsecure.example)
2. iOS Application (version X.Y)
3. Android Application (version X.Y)
4. Backend API (api.finsecure.example)
5. Authentication & Session Management subsystem
6. Payment / Transfer business logic

## 2.3 Features to be Tested

### Authentication & Session Management
- Password-based login
- Multi-factor authentication (TOTP / push / SMS)
- Session timeout and concurrent session handling
- Password reset flow
- Account lockout mechanisms
- “Remember me” / persistent sessions

### Authorization
- Horizontal privilege escalation (user A → user B data)
- Vertical privilege escalation (customer → admin)
- IDOR on account numbers, transaction IDs, documents
- Role matrix validation

### Input Validation & Injection
- SQL Injection / NoSQL Injection
- Cross-Site Scripting (reflected, stored, DOM)
- Command Injection
- SSRF
- XML / XXE (if applicable)
- Template Injection

### Business Logic
- Negative amounts / overdraft
- Race conditions on transfers
- Limit bypass
- Transaction replay

### Cryptography & Transport
- TLS configuration (protocols, ciphers, HSTS)
- Certificate pinning (mobile)
- Sensitive data in transit and at rest
- Key storage on mobile devices

### Mobile-Specific
- Insecure data storage (Keychain / SharedPreferences / SQLite)
- Insecure communication
- Reverse engineering resistance (basic)
- Deep linking / URL scheme security
- Biometric authentication bypass attempts
- Backup and debug flag issues

### API Security
- Broken Object Level Authorization
- Broken Authentication
- Excessive Data Exposure
- Rate limiting / resource consumption
- Mass assignment
- Security misconfiguration

## 2.4 Features Not to be Tested

- Third-party payment gateway internals
- OS-level vulnerabilities on end-user devices
- Social engineering of end users
- Physical security of mobile devices

## 2.5 Approach

1. **Reconnaissance & Information Gathering** (1–2 days)
2. **Automated Scanning** (SAST + DAST + SCA + mobile scanners)
3. **Manual Testing** according to prioritized attack surfaces
4. **Exploitation & Proof-of-Concept** for confirmed issues
5. **Reporting & Retesting**

## 2.6 Pass / Fail Criteria

A test case is considered **Failed** if:
- The vulnerability is confirmed and reproducible, **or**
- A security control is missing or ineffective against the tested attack vector.

Severity is assigned using CVSS 3.1 + business impact.

## 2.7 Suspension Criteria

Testing will be suspended if:
- Critical production-like environment becomes unavailable
- Destructive testing causes unintended data loss
- Legal / compliance hold is issued

## 2.8 Test Deliverables

1. Security Test Plan (this document)
2. Detailed findings report (with evidence)
3. Executive summary
4. Risk matrix
5. Retest report (after remediation)

## 2.9 Environmental Needs

- Staging environment identical to production (network segmentation, WAF rules, etc.)
- Test accounts with different roles
- Jailbroken / rooted devices + clean devices
- Proxy tools (Burp Suite Professional / OWASP ZAP)
- Mobile analysis tools (MobSF, Frida, Objection, etc.)

## 2.10 Responsibilities

See Strategy document (Section 1.6).

## 2.11 Schedule (Example)

| Phase                      | Duration   | Dependencies          |
|----------------------------|------------|-----------------------|
| Kick-off & Threat modeling | 2 days     | Access granted        |
| Automated scanning         | 3 days     | Environment ready     |
| Manual web + API testing   | 7–10 days  | Scanning completed    |
| Mobile testing             | 5–7 days   | Apps provided         |
| Reporting                  | 3 days     | All testing finished  |
| Retesting                  | 3–5 days   | Fixes deployed        |

## 2.12 Risks and Contingencies

| Risk                              | Mitigation                              |
|-----------------------------------|-----------------------------------------|
| Incomplete staging data           | Generate synthetic data sets            |
| WAF blocking legitimate tests     | Whitelist tester IPs / disable rules    |
| Limited time for mobile reverse   | Focus on high-impact issues first       |
| Scope creep                       | Strict change control                   |
