# 8. Tools and Test Environment

## Recommended Tools

### Web & API
- Burp Suite Professional
- OWASP ZAP
- Nuclei + custom templates
- Postman / Insomnia + scripts
- sqlmap, ffuf, httpx

### Mobile
- MobSF (static + dynamic)
- Frida + Objection
- Jadx / apktool / Hopper / Ghidra
- Android Studio Emulator + physical devices
- Xcode + Simulator + physical iOS devices
- Burp + mobile proxy certificates

### SAST / SCA
- Semgrep / CodeQL
- Snyk / Dependabot / OWASP Dependency-Check

### Other
- Wireshark / tcpdump
- nmap / masscan (limited)
- Custom scripts (Python)

## Environment Requirements

- Isolated staging environment
- Test user accounts (customer, premium, support, admin)
- Ability to reset state between tests
- Logging of all tester actions for audit
- Whitelist of tester IP addresses on WAF / CDN
