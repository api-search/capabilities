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
- security engineer
- public holidays
- fraud detection
- vat validation
- check phone intelligence and risk score
- check email reputation and risk score
- ip geolocation, company enrichment, and timezone data for user profile enrichment
- product engineer
- engineer building data pipelines and enrichment workflows
- finance engineer
- check phone number risk and validity
- developer building user onboarding and personalization features
- check phone intelligence
- web scraping
- phone intelligence
- compliance analyst
- email validation
- fraud analyst
- avatars
- ip geolocation
- check phone risk
- check email address risk and reputation
- analyze ip address for vpn, proxy, tor, abuse, hosting, and security risk signals
- contacts
- check email reputation
- data engineer
- timezones
- iban validation
- abstract api
- image processing
- phone validation
- check email address reputation, deliverability, and risk score to detect fraudulent or disposable emails
- email reputation, phone intelligence, and ip intelligence for fraud prevention
- check ip intelligence
- security
- currency conversion, vat compliance, and banking validation for financial applications
- check email risk
- exchange rates
- check ip intelligence and security flags
- screenshots
- company enrichment
- validate phone number and retrieve carrier, line type, voip status, and risk score
- email reputation
- check ip risk
- detection and blocking of fraudulent users, transactions, and bot activity
- security professional responsible for detecting and blocking fraudulent users and transactions
- ip intelligence
- check ip address risk signals
- currencies
- exchange rates, vat validation, and iban validation for financial compliance
- automatic enrichment of user profiles with geographic, company, and temporal data
- developer building payment, billing, and financial compliance systems
- professional ensuring regulatory compliance for vat, banking, and financial reporting
- engineer building fraud detection and threat intelligence systems
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
