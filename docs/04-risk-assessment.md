# 4. Risk Assessment (Preliminary)

## 4.1 Threat Actors

| Actor                    | Motivation                  | Capability          |
|--------------------------|-----------------------------|---------------------|
| Opportunistic attackers  | Financial gain              | Low–Medium          |
| Organized cybercrime     | Large-scale fraud           | High                |
| Insider (malicious)      | Fraud / data theft          | Medium–High         |
| Competitors / activists  | Reputation damage           | Medium              |

## 4.2 High-Level Risk Matrix (Pre-Testing)

| Risk Scenario                              | Likelihood | Impact   | Risk Level |
|--------------------------------------------|------------|----------|------------|
| Account takeover via credential stuffing   | High       | Critical | Critical   |
| IDOR leading to data of other customers    | Medium     | Critical | High       |
| XSS → session theft                        | Medium     | High     | High       |
| Insecure mobile storage of tokens          | High       | High     | High       |
| Business logic flaw in transfers           | Medium     | Critical | High       |
| SSRF to internal services                  | Low        | High     | Medium     |
| Broken certificate pinning                 | Medium     | Medium   | Medium     |

## 4.3 Risk-Based Prioritization of Testing

1. Authentication & Session Management  
2. Authorization / IDOR / BOLA  
3. Business Logic (transfers, limits)  
4. Mobile data storage & communication  
5. Injection attacks  
6. Configuration & cryptographic issues  
