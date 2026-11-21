# 3. Scope and Objectives (Detailed)

## 3.1 Business Objectives

Protect customer funds, personal data and trust in the FinSecure brand by ensuring that security controls are effective against common and advanced attacks targeting web and mobile banking applications.

## 3.2 Technical Objectives

- Verify that authentication cannot be bypassed or abused.
- Confirm that authorization correctly enforces least privilege.
- Ensure sensitive data is protected both in transit and at rest.
- Validate that the API does not expose excessive information or allow mass assignment.
- Check mobile applications for insecure storage, weak cryptography and improper certificate validation.
- Identify business logic flaws that could lead to financial loss.

## 3.3 In-Scope Assets

| Asset                        | Criticality | Notes                              |
|------------------------------|-------------|------------------------------------|
| Customer authentication      | Critical    | Passwords, MFA, biometrics         |
| Account balances & history   | Critical    | Direct financial impact            |
| Transfer / payment functions | Critical    | Fraud risk                         |
| Personal data (PII)          | High        | GDPR / privacy regulations         |
| Session tokens / cookies     | High        | Session hijacking risk             |
| Admin / support interfaces   | High        | Privilege escalation               |
| Mobile local storage         | High        | Device compromise scenarios        |

## 3.4 Attack Surface Summary

- Public web login and registration pages
- Authenticated web dashboard
- Mobile deep links and custom URL schemes
- API endpoints (documented and undocumented)
- WebSocket / real-time channels (if present)
- File upload functionality (documents, statements)
- Password recovery and account recovery flows
