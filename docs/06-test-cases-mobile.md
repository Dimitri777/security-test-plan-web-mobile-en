# 6. Mobile Application Test Cases (Selected)

## Data Storage

| ID           | Title                                         | Priority | Expected Result                               |
|--------------|-----------------------------------------------|----------|-----------------------------------------------|
| MOB-STOR-01  | Sensitive data in SharedPreferences / UserDefaults | Critical | No tokens, PINs or PII in cleartext          |
| MOB-STOR-02  | SQLite / Realm encryption                     | High     | Database encrypted, key not hardcoded         |
| MOB-STOR-03  | Keychain / Keystore usage                     | High     | Proper accessibility flags                    |
| MOB-STOR-04  | Backup / iTunes / ADB backup exclusion       | Medium   | Sensitive files excluded from backup          |

## Communication

| ID           | Title                                         | Priority | Expected Result                               |
|--------------|-----------------------------------------------|----------|-----------------------------------------------|
| MOB-COMM-01  | Certificate pinning bypass                    | High     | Pinning implemented and hard to bypass        |
| MOB-COMM-02  | Cleartext traffic                             | Critical | No HTTP allowed (Android Network Security Config / ATS) |
| MOB-COMM-03  | Improper TLS validation                       | Critical | Certificate validation not disabled           |

## Authentication & Biometrics

| ID           | Title                                         | Priority | Expected Result                               |
|--------------|-----------------------------------------------|----------|-----------------------------------------------|
| MOB-AUTH-01  | Biometric bypass (Frida / runtime)            | High     | Proper local authentication checks            |
| MOB-AUTH-02  | Local PIN / pattern storage                   | High     | Secure storage + rate limiting                |
| MOB-AUTH-03  | Deep link authentication bypass               | High     | Sensitive actions require re-auth             |

## Platform & Configuration

| ID           | Title                                         | Priority | Expected Result                               |
|--------------|-----------------------------------------------|----------|-----------------------------------------------|
| MOB-CONF-01  | Debuggable flag                               | High     | Released builds not debuggable                |
| MOB-CONF-02  | Jailbreak detection / root detection            | Medium   | Appropriate reaction (optional)               |
| MOB-CONF-03  | Device permissions excess                    | Medium   | Only necessary permissions requested          |
