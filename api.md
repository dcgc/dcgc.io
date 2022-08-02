---
layout: page
title: API Security
categories: notes
permalink: /api/
---

- API’s are more transparent, more vulnerable.

- API Audience
    - Private
    - Public
    - Partner

### Top 10 WebApp Security Risks
1. Injection
2. Broken Authentication
3. Sensitive Data Exposure
4. XML External Entities (XXE)
5. Broken Access Control
6. Security Misconfiguration
    1. Unprotected API’s
7. Cross-Site Scripting XSS
8. Insecure Deserialisation
9. Using Components with Known Vulnerabilities
10. Insufficient Logging & Monitoring


### API Security Top 10
1. Broken Object Level Authorisation
2. Broken User Authentication
3. Excessive Data Exposure
4. Lack of Resources & Rate Limiting
5. Broken Function Level Authorisation
6. Mass Assignment
7. Security Misconfiguration
8. Injection
9. Improper Assets Management
10. Insufficient Logging & Monitoring

### Mitigating API Threats
- Rate Limiting: restrict number of requests that can be made based on IP, identity, resource target; critical element for keeping API available for legitimate users
- Message Validation: prevent message based attacks by validating incoming and outgoing messages
    - Schema based validation can be performed after message is received
     - Client application does not need schema 
     - Allows you to change schema without breaking clients
- Access Control: restrict usage of API’s based on user identity

### TLS/SSL
- Choose a supported cipher suite for crypto
- Use key material (private key, public certificate) to drive crypto
- Ensure the validation mode is based on certificate trust

### Cryptographic Arms Race
- Cryptographic security == impractical not impenetrable
- Crypto breaking machines getting faster
- We keep increasing crypto strength

### TLS Trust Attacks
- Certificate Authority Vulnerabilities
    - Certificate Authority can be compromised
    - Certificate Authority can issue malicious certificates
- Human Vulnerabilities
    - Browsers use visual cues to indicate security (padlock)
    - Visual cues can be impersonated
    - Humans can be fooled
- Man in the Middle
    - Sniff data sent outside the pls channel
    - Launch a crypto attack on encrypted data

### HTTP Access Control
- HTTP provides an access authentication feature
- Allows servers to reject unauthorised access and challenge clients
- Allows clients to transmit credentials
- Authorisation schemes:
    - Basic Authentication
    - Digest Authentication


### Basic Authentication
- Username and Password in request header
- Base64 encoded (not encrypted)
- Credentials are sent in plain text with every request

### Digest Authentication
- Password is encrypted
- Server can downgrade scheme to Basic
- Vulnerable to man in the middle attack

### Best Practices for API Security
- Security (Authentication and Authorisation)
- Protection (OWASP API vulnerabilities)
- Throttling (quota on requests and retires)
- Continuous API Monitoring
- Request/Response Payload Validation
- Error Handling
