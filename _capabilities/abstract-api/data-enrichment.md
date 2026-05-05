---
categories: []
consumed_apis:
- ip-geolocation
- company-enrichment
- timezones
description: Unified data enrichment workflow combining IP geolocation, company enrichment, and timezone APIs. Used by product teams and data engineers to automatically enrich user profiles, personalize experiences, and localize content at signup or session start.
layout: capability
name: Abstract API Data Enrichment
operations:
- description: Get location data for an IP address
  method: GET
  name: geolocate-ip
  path: /v1/ip-location
- description: Get company details from domain or email
  method: GET
  name: enrich-company
  path: /v1/company
- description: Retrieve timezone and current time for a location
  method: GET
  name: get-timezone
  path: /v1/timezone
personas:
- description: Developer building user onboarding and personalization features
  id: product-engineer
  name: Product Engineer
- description: Engineer building data pipelines and enrichment workflows
  id: data-engineer
  name: Data Engineer
provider_name: Abstract API
provider_slug: abstract-api
search_terms:
- engineer building fraud detection and threat intelligence systems
- ip geolocation, company enrichment, and timezone data for user profile enrichment
- abstract api
- get timezone
- geolocate an ip address
- timezones
- developer building user onboarding and personalization features
- compliance analyst
- enrich company data
- email validation
- public holidays
- get company details from domain or email
- convert time between zones
- web scraping
- phone validation
- get current timezone for a location
- convert date/time from one timezone to another
- vat validation
- engineer building data pipelines and enrichment workflows
- iban validation
- professional ensuring regulatory compliance for vat, banking, and financial reporting
- data enrichment
- enrich company data from domain
- retrieve company name, industry, headcount, logo, and location from a domain or email
- geolocate an ip address to get country, city, timezone, and currency data
- developer building payment, billing, and financial compliance systems
- security professional responsible for detecting and blocking fraudulent users and transactions
- retrieve timezone and current time for a location
- fraud analyst
- automatic enrichment of user profiles with geographic, company, and temporal data
- currency conversion, vat compliance, and banking validation for financial applications
- enrich company
- email reputation, phone intelligence, and ip intelligence for fraud prevention
- security engineer
- avatars
- ip intelligence
- get current time and timezone information for any location
- currencies
- get current timezone
- finance engineer
- geolocate ip
- image processing
- data engineer
- contacts
- detection and blocking of fraudulent users, transactions, and bot activity
- exchange rates
- geolocation
- product engineer
- geolocate ip address
- company enrichment
- ip geolocation
- screenshots
- get location data for an ip address
- exchange rates, vat validation, and iban validation for financial compliance
slug: data-enrichment
source_filename: data-enrichment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Abstract API Data Enrichment\"\n  description: \"Unified data enrichment workflow combining IP geolocation, company enrichment, and timezone APIs. Used by product teams and data engineers to automatically enrich user profiles, personalize experiences, and localize content at signup or session start.\"\n  tags:\n    - Abstract Api\n    - Data Enrichment\n    - Geolocation\n    - Company Enrichment\n    - Timezones\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      IP_GEOLOCATION_API_KEY: IP_GEOLOCATION_API_KEY\n      COMPANY_ENRICHMENT_API_KEY: COMPANY_ENRICHMENT_API_KEY\n      TIMEZONES_API_KEY: TIMEZONES_API_KEY\n\ncapability:\n  consumes:\n    - import: ip-geolocation\n      location: ./shared/ip-geolocation.yaml\n    - import: company-enrichment\n      location: ./shared/company-enrichment.yaml\n    - import: timezones\n      location: ./shared/timezones.yaml\n\n  exposes:\n\
  \    - type: rest\n      port: 8081\n      namespace: data-enrichment-api\n      description: \"Unified REST API for user and session data enrichment.\"\n      resources:\n        - path: /v1/ip-location\n          name: ip-location\n          description: \"Geolocate an IP address\"\n          operations:\n            - method: GET\n              name: geolocate-ip\n              description: \"Get location data for an IP address\"\n              call: \"ip-geolocation.getIPGeolocation\"\n              with:\n                ip_address: \"rest.ip_address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/company\n          name: company\n          description: \"Enrich company data from domain\"\n          operations:\n            - method: GET\n              name: enrich-company\n              description: \"Get company details from domain or email\"\n              call: \"company-enrichment.getCompanyEnrichment\"\
  \n              with:\n                domain: \"rest.domain\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/timezone\n          name: timezone\n          description: \"Get current timezone for a location\"\n          operations:\n            - method: GET\n              name: get-timezone\n              description: \"Retrieve timezone and current time for a location\"\n              call: \"timezones.getCurrentTime\"\n              with:\n                location: \"rest.location\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: data-enrichment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted data enrichment and user personalization.\"\n      tools:\n        - name: geolocate-ip-address\n          description: \"Geolocate an IP address to\
  \ get country, city, timezone, and currency data\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ip-geolocation.getIPGeolocation\"\n          with:\n            ip_address: \"tools.ip_address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enrich-company-data\n          description: \"Retrieve company name, industry, headcount, logo, and location from a domain or email\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"company-enrichment.getCompanyEnrichment\"\n          with:\n            domain: \"tools.domain\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-current-timezone\n          description: \"Get current time and timezone information for any location\"\n          hints:\n            readOnly: true\n            openWorld: true\n  \
  \        call: \"timezones.getCurrentTime\"\n          with:\n            location: \"tools.location\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: convert-time-between-zones\n          description: \"Convert date/time from one timezone to another\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"timezones.convertTime\"\n          with:\n            base_location: \"tools.base_location\"\n            target_location: \"tools.target_location\"\n            base_datetime: \"tools.base_datetime\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/abstract-api/refs/heads/main/capabilities/data-enrichment.yaml
tags:
- Abstract Api
- Data Enrichment
- Geolocation
- Company Enrichment
- Timezones
tools:
- description: Geolocate an IP address to get country, city, timezone, and currency data
  hints:
    openWorld: true
    readOnly: true
  name: geolocate-ip-address
- description: Retrieve company name, industry, headcount, logo, and location from a domain or email
  hints:
    openWorld: true
    readOnly: true
  name: enrich-company-data
- description: Get current time and timezone information for any location
  hints:
    openWorld: true
    readOnly: true
  name: get-current-timezone
- description: Convert date/time from one timezone to another
  hints:
    openWorld: false
    readOnly: true
  name: convert-time-between-zones
---
