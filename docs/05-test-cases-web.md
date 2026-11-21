# 5. Web Application Test Cases (Selected)

## Authentication

| ID          | Title                                      | Priority | Expected Result                          |
|-------------|--------------------------------------------|----------|------------------------------------------|
| WEB-AUTH-01 | Brute-force / credential stuffing          | High     | Account lockout or rate limiting works   |
| WEB-AUTH-02 | MFA bypass attempts                        | Critical | MFA cannot be skipped                    |
| WEB-AUTH-03 | Session fixation                           | High     | Session ID regenerated after login       |
| WEB-AUTH-04 | Password reset token predictability        | High     | Tokens are random and single-use         |
| WEB-AUTH-05 | Concurrent session handling                | Medium   | Configurable limit enforced              |

## Authorization / Access Control

| ID          | Title                                      | Priority | Expected Result                          |
|-------------|--------------------------------------------|----------|------------------------------------------|
| WEB-AUTHZ-01| Horizontal privilege escalation (IDOR)     | Critical | User cannot access another user’s data   |
| WEB-AUTHZ-02| Vertical privilege escalation              | Critical | Customer cannot reach admin functions    |
| WEB-AUTHZ-03| Forced browsing to restricted pages        | High     | Proper 403 / redirect                    |

## Injection & Client-Side

| ID          | Title                                      | Priority | Expected Result                          |
|-------------|--------------------------------------------|----------|------------------------------------------|
| WEB-INJ-01  | SQL / NoSQL Injection                      | Critical | Input is parameterized / escaped         |
| WEB-INJ-02  | Reflected XSS                              | High     | Output encoding / CSP blocks             |
| WEB-INJ-03  | Stored XSS                                 | Critical | Sanitization + CSP                       |
| WEB-INJ-04  | DOM-based XSS                              | High     | Safe DOM manipulation                    |
| WEB-INJ-05  | SSRF                                       | High     | URL validation / allow-list              |

## Business Logic

| ID          | Title                                      | Priority | Expected Result                          |
|-------------|--------------------------------------------|----------|------------------------------------------|
| WEB-BL-01   | Negative transfer amount                   | Critical | Rejected by server-side validation       |
| WEB-BL-02   | Race condition on balance                  | High     | Atomic operations / locking              |
| WEB-BL-03   | Limit bypass                               | High     | Server-side enforcement of limits        |
