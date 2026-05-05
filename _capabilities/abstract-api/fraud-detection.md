---
categories:
- security
consumed_apis:
- email-reputation
- phone-intelligence
- ip-intelligence
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
- check ip intelligence and security flags
- check phone risk
- ip geolocation, company enrichment, and timezone data for user profile enrichment
- abstract api
- engineer building fraud detection and threat intelligence systems
- security
- screenshots
- timezones
- validate phone number and retrieve carrier, line type, voip status, and risk score
- phone intelligence
- developer building user onboarding and personalization features
- check email address reputation, deliverability, and risk score to detect fraudulent or disposable emails
- compliance analyst
- email validation
- check phone number risk and validity
- public holidays
- web scraping
- phone validation
- check ip risk
- analyze ip address for vpn, proxy, tor, abuse, hosting, and security risk signals
- engineer building data pipelines and enrichment workflows
- iban validation
- professional ensuring regulatory compliance for vat, banking, and financial reporting
- vat validation
- check ip intelligence
- developer building payment, billing, and financial compliance systems
- check email reputation
- email reputation
- fraud analyst
- security professional responsible for detecting and blocking fraudulent users and transactions
- automatic enrichment of user profiles with geographic, company, and temporal data
- currency conversion, vat compliance, and banking validation for financial applications
- email reputation, phone intelligence, and ip intelligence for fraud prevention
- check phone intelligence
- security engineer
- ip intelligence
- avatars
- currencies
- finance engineer
- image processing
- data engineer
- detection and blocking of fraudulent users, transactions, and bot activity
- check ip address risk signals
- exchange rates
- check phone intelligence and risk score
- product engineer
- check email address risk and reputation
- check email reputation and risk score
- company enrichment
- ip geolocation
- check email risk
- contacts
- fraud detection
- exchange rates, vat validation, and iban validation for financial compliance
slug: fraud-detection
source_filename: fraud-detection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Abstract API Fraud Detection\"\n  description: \"Unified fraud detection and risk assessment workflow combining email reputation, phone intelligence, and IP intelligence APIs. Used by security engineers, fraud analysts, and compliance teams to detect and block fraudulent users at signup or transaction time.\"\n  tags:\n    - Abstract Api\n    - Fraud Detection\n    - Security\n    - Email Reputation\n    - Phone Intelligence\n    - Ip Intelligence\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      EMAIL_REPUTATION_API_KEY: EMAIL_REPUTATION_API_KEY\n      PHONE_INTELLIGENCE_API_KEY: PHONE_INTELLIGENCE_API_KEY\n      IP_INTELLIGENCE_API_KEY: IP_INTELLIGENCE_API_KEY\n\ncapability:\n  consumes:\n    - import: email-reputation\n      location: ./shared/email-reputation.yaml\n    - import: phone-intelligence\n      location: ./shared/phone-intelligence.yaml\n    - import: ip-intelligence\n\
  \      location: ./shared/ip-intelligence.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: fraud-detection-api\n      description: \"Unified REST API for fraud detection and risk assessment.\"\n      resources:\n        - path: /v1/email-risk\n          name: email-risk\n          description: \"Check email address risk and reputation\"\n          operations:\n            - method: GET\n              name: check-email-risk\n              description: \"Check email reputation and risk score\"\n              call: \"email-reputation.getEmailReputation\"\n              with:\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/phone-risk\n          name: phone-risk\n          description: \"Check phone number risk and validity\"\n          operations:\n            - method: GET\n              name: check-phone-risk\n              description: \"Check phone intelligence\
  \ and risk score\"\n              call: \"phone-intelligence.getPhoneIntelligence\"\n              with:\n                phone: \"rest.phone\"\n                country: \"rest.country\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ip-risk\n          name: ip-risk\n          description: \"Check IP address risk signals\"\n          operations:\n            - method: GET\n              name: check-ip-risk\n              description: \"Check IP intelligence and security flags\"\n              call: \"ip-intelligence.getIPIntelligence\"\n              with:\n                ip_address: \"rest.ip_address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: fraud-detection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted fraud detection and risk assessment.\"\n      tools:\n        - name:\
  \ check-email-reputation\n          description: \"Check email address reputation, deliverability, and risk score to detect fraudulent or disposable emails\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"email-reputation.getEmailReputation\"\n          with:\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-phone-intelligence\n          description: \"Validate phone number and retrieve carrier, line type, VoIP status, and risk score\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"phone-intelligence.getPhoneIntelligence\"\n          with:\n            phone: \"tools.phone\"\n            country: \"tools.country\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-ip-intelligence\n          description: \"Analyze IP address for VPN, proxy,\
  \ Tor, abuse, hosting, and security risk signals\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ip-intelligence.getIPIntelligence\"\n          with:\n            ip_address: \"tools.ip_address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
