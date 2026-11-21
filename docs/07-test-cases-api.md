# 7. API Security Test Cases (Selected)

| ID          | Title                                      | Priority | Expected Result                          |
|-------------|--------------------------------------------|----------|------------------------------------------|
| API-01      | Broken Object Level Authorization (BOLA)   | Critical | Object ownership verified server-side    |
| API-02      | Broken Function Level Authorization        | Critical | Role checks on every sensitive endpoint  |
| API-03      | Excessive Data Exposure                    | High     | Response filtering / DTOs used           |
| API-04      | Mass Assignment                            | High     | Only expected fields accepted            |
| API-05      | Rate limiting / brute-force protection     | High     | Effective throttling                     |
| API-06      | JWT / token validation                     | Critical | Signature, expiration, audience checked  |
| API-07      | GraphQL introspection & complexity         | Medium   | Disabled in production / limited         |
| API-08      | Parameter pollution                        | Medium   | Consistent handling                      |
