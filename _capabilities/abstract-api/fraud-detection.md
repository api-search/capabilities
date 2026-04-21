---
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
- check ip intelligence
- currencies
- check email risk
- web scraping
- exchange rates, vat validation, and iban validation for financial compliance
- timezones
- check email reputation
- check phone intelligence and risk score
- security
- analyze ip address for vpn, proxy, tor, abuse, hosting, and security risk signals
- contacts
- email reputation
- detection and blocking of fraudulent users, transactions, and bot activity
- fraud analyst
- abstract api
- currency conversion, vat compliance, and banking validation for financial applications
- automatic enrichment of user profiles with geographic, company, and temporal data
- engineer building data pipelines and enrichment workflows
- check phone intelligence
- fraud detection
- email validation
- finance engineer
- check email address risk and reputation
- professional ensuring regulatory compliance for vat, banking, and financial reporting
- vat validation
- public holidays
- security professional responsible for detecting and blocking fraudulent users and transactions
- data engineer
- ip geolocation
- developer building user onboarding and personalization features
- check ip address risk signals
- screenshots
- ip geolocation, company enrichment, and timezone data for user profile enrichment
- product engineer
- avatars
- image processing
- ip intelligence
- check ip intelligence and security flags
- check ip risk
- check email reputation and risk score
- check phone risk
- email reputation, phone intelligence, and ip intelligence for fraud prevention
- iban validation
- company enrichment
- compliance analyst
- engineer building fraud detection and threat intelligence systems
- phone intelligence
- exchange rates
- check phone number risk and validity
- developer building payment, billing, and financial compliance systems
- validate phone number and retrieve carrier, line type, voip status, and risk score
- check email address reputation, deliverability, and risk score to detect fraudulent or disposable emails
- phone validation
- security engineer
slug: fraud-detection
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
