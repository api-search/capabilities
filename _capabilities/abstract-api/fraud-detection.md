---
categories:
- security
consumed_apis: []
description: Unified fraud detection and risk assessment workflow combining email reputation, phone intelligence, and IP intelligence APIs. Used by security engineers, fraud analysts, and compliance teams to detect and block fraudulent users at signup or transaction time.
layout: capability
name: Abstract API Fraud Detection
operations:
- description: Check email reputation and risk score
  method: GET
  name: check-email-risk
  path: /v1/email-risk
- description: Check phone intelligence and risk score
  method: GET
  name: check-phone-risk
  path: /v1/phone-risk
- description: Check IP intelligence and security flags
  method: GET
  name: check-ip-risk
  path: /v1/ip-risk
personas:
- description: Security professional responsible for detecting and blocking fraudulent users and transactions
  id: fraud-analyst
  name: Fraud Analyst
- description: Engineer building fraud detection and threat intelligence systems
  id: security-engineer
  name: Security Engineer
provider_name: Abstract API
provider_slug: abstract-api
search_terms:
- check phone intelligence
- validate phone number and retrieve carrier, line type, voip status, and risk score
- fraud detection
- security engineer
- check phone risk
- professional ensuring regulatory compliance for vat, banking, and financial reporting
- check ip intelligence
- detection and blocking of fraudulent users, transactions, and bot activity
- data engineer
- check email reputation and risk score
- check phone number risk and validity
- finance engineer
- contacts
- ip geolocation, company enrichment, and timezone data for user profile enrichment
- image processing
- iban validation
- engineer building fraud detection and threat intelligence systems
- compliance analyst
- exchange rates
- check ip risk
- security
- check ip intelligence and security flags
- security professional responsible for detecting and blocking fraudulent users and transactions
- phone validation
- engineer building data pipelines and enrichment workflows
- web scraping
- avatars
- exchange rates, vat validation, and iban validation for financial compliance
- check phone intelligence and risk score
- developer building user onboarding and personalization features
- email reputation
- email validation
- check email address risk and reputation
- vat validation
- currency conversion, vat compliance, and banking validation for financial applications
- abstract api
- screenshots
- currencies
- product engineer
- email reputation, phone intelligence, and ip intelligence for fraud prevention
- ip geolocation
- phone intelligence
- ip intelligence
- check email risk
- automatic enrichment of user profiles with geographic, company, and temporal data
- check email address reputation, deliverability, and risk score to detect fraudulent or disposable emails
- fraud analyst
- timezones
- company enrichment
- check ip address risk signals
- check email reputation
- analyze ip address for vpn, proxy, tor, abuse, hosting, and security risk signals
- developer building payment, billing, and financial compliance systems
- public holidays
slug: fraud-detection
source_filename: fraud-detection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Abstract API Fraud Detection\n  description: Unified fraud detection and risk assessment workflow combining email reputation, phone intelligence, and IP\n    intelligence APIs. Used by security engineers, fraud analysts, and compliance teams to detect and block fraudulent users\n    at signup or transaction time.\n  tags:\n  - Abstract Api\n  - Fraud Detection\n  - Security\n  - Email Reputation\n  - Phone Intelligence\n  - Ip Intelligence\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    EMAIL_REPUTATION_API_KEY: EMAIL_REPUTATION_API_KEY\n    PHONE_INTELLIGENCE_API_KEY: PHONE_INTELLIGENCE_API_KEY\n    IP_INTELLIGENCE_API_KEY: IP_INTELLIGENCE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: email-reputation\n    baseUri: https://emailreputation.abstractapi.com/v1\n    description: Email Reputation API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{env.EMAIL_REPUTATION_API_KEY}}'\n\
  \      placement: query\n    resources:\n    - name: email-reputation\n      path: /\n      description: Email Reputation API email-reputation resource\n      operations:\n      - name: getEmailReputation\n        method: GET\n        description: Abstract API Get Email Reputation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: phone-intelligence\n    baseUri: https://phoneintelligence.abstractapi.com/v1\n    description: Phone Intelligence API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{env.PHONE_INTELLIGENCE_API_KEY}}'\n      placement: query\n    resources:\n    - name: phone-intelligence\n      path: /\n      description: Phone Intelligence API phone-intelligence resource\n      operations:\n      - name: getPhoneIntelligence\n        method: GET\n        description: Abstract API Get Phone Intelligence\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: ip-intelligence\n    baseUri: https://ip-intelligence.abstractapi.com/v1\n    description: IP Intelligence API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{env.IP_INTELLIGENCE_API_KEY}}'\n      placement: query\n    resources:\n    - name: ip-intelligence\n      path: /\n      description: IP Intelligence API ip-intelligence resource\n      operations:\n      - name: getIPIntelligence\n        method: GET\n        description: Abstract API Get IP Intelligence\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fraud-detection-api\n    description: Unified REST API for fraud detection and risk assessment.\n    resources:\n    - path: /v1/email-risk\n      name: email-risk\n      description: Check email\
  \ address risk and reputation\n      operations:\n      - method: GET\n        name: check-email-risk\n        description: Check email reputation and risk score\n        call: email-reputation.getEmailReputation\n        with:\n          email: rest.email\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/phone-risk\n      name: phone-risk\n      description: Check phone number risk and validity\n      operations:\n      - method: GET\n        name: check-phone-risk\n        description: Check phone intelligence and risk score\n        call: phone-intelligence.getPhoneIntelligence\n        with:\n          phone: rest.phone\n          country: rest.country\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ip-risk\n      name: ip-risk\n      description: Check IP address risk signals\n      operations:\n      - method: GET\n        name: check-ip-risk\n        description: Check IP intelligence and security\
  \ flags\n        call: ip-intelligence.getIPIntelligence\n        with:\n          ip_address: rest.ip_address\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fraud-detection-mcp\n    transport: http\n    description: MCP server for AI-assisted fraud detection and risk assessment.\n    tools:\n    - name: check-email-reputation\n      description: Check email address reputation, deliverability, and risk score to detect fraudulent or disposable emails\n      hints:\n        readOnly: true\n        openWorld: true\n      call: email-reputation.getEmailReputation\n      with:\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-phone-intelligence\n      description: Validate phone number and retrieve carrier, line type, VoIP status, and risk score\n      hints:\n        readOnly: true\n        openWorld: true\n      call: phone-intelligence.getPhoneIntelligence\n\
  \      with:\n        phone: tools.phone\n        country: tools.country\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-ip-intelligence\n      description: Analyze IP address for VPN, proxy, Tor, abuse, hosting, and security risk signals\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ip-intelligence.getIPIntelligence\n      with:\n        ip_address: tools.ip_address\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/abstract-api/refs/heads/main/capabilities/fraud-detection.yaml
tags:
- Abstract Api
- Fraud Detection
- Security
- Email Reputation
- Phone Intelligence
- Ip Intelligence
tools:
- description: Check email address reputation, deliverability, and risk score to detect fraudulent or disposable emails
  hints:
    openWorld: true
    readOnly: true
  name: check-email-reputation
- description: Validate phone number and retrieve carrier, line type, VoIP status, and risk score
  hints:
    openWorld: true
    readOnly: true
  name: check-phone-intelligence
- description: Analyze IP address for VPN, proxy, Tor, abuse, hosting, and security risk signals
  hints:
    openWorld: true
    readOnly: true
  name: check-ip-intelligence
---
