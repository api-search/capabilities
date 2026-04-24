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
- product engineer
- check email address reputation, deliverability, and risk score to detect fraudulent or disposable emails
- check phone number risk and validity
- ip intelligence
- check ip address risk signals
- company enrichment
- check email address risk and reputation
- compliance analyst
- detection and blocking of fraudulent users, transactions, and bot activity
- engineer building data pipelines and enrichment workflows
- exchange rates, vat validation, and iban validation for financial compliance
- engineer building fraud detection and threat intelligence systems
- exchange rates
- vat validation
- avatars
- web scraping
- check email risk
- email reputation, phone intelligence, and ip intelligence for fraud prevention
- currencies
- finance engineer
- iban validation
- developer building payment, billing, and financial compliance systems
- data engineer
- public holidays
- phone validation
- ip geolocation, company enrichment, and timezone data for user profile enrichment
- phone intelligence
- check phone intelligence
- security professional responsible for detecting and blocking fraudulent users and transactions
- fraud detection
- professional ensuring regulatory compliance for vat, banking, and financial reporting
- currency conversion, vat compliance, and banking validation for financial applications
- contacts
- validate phone number and retrieve carrier, line type, voip status, and risk score
- ip geolocation
- email reputation
- image processing
- analyze ip address for vpn, proxy, tor, abuse, hosting, and security risk signals
- developer building user onboarding and personalization features
- email validation
- check ip intelligence and security flags
- check phone intelligence and risk score
- fraud analyst
- screenshots
- check email reputation
- check ip intelligence
- security
- automatic enrichment of user profiles with geographic, company, and temporal data
- check email reputation and risk score
- abstract api
- check ip risk
- timezones
- check phone risk
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
