---
categories: []
consumed_apis: []
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
- get current timezone
- security engineer
- professional ensuring regulatory compliance for vat, banking, and financial reporting
- data enrichment
- get company details from domain or email
- detection and blocking of fraudulent users, transactions, and bot activity
- data engineer
- finance engineer
- contacts
- get current timezone for a location
- ip geolocation, company enrichment, and timezone data for user profile enrichment
- iban validation
- engineer building fraud detection and threat intelligence systems
- image processing
- get location data for an ip address
- compliance analyst
- get current time and timezone information for any location
- exchange rates
- enrich company
- security professional responsible for detecting and blocking fraudulent users and transactions
- phone validation
- retrieve company name, industry, headcount, logo, and location from a domain or email
- engineer building data pipelines and enrichment workflows
- web scraping
- avatars
- exchange rates, vat validation, and iban validation for financial compliance
- developer building user onboarding and personalization features
- email validation
- geolocate an ip address
- vat validation
- retrieve timezone and current time for a location
- convert time between zones
- currency conversion, vat compliance, and banking validation for financial applications
- abstract api
- screenshots
- currencies
- product engineer
- geolocation
- email reputation, phone intelligence, and ip intelligence for fraud prevention
- get timezone
- ip geolocation
- ip intelligence
- automatic enrichment of user profiles with geographic, company, and temporal data
- geolocate an ip address to get country, city, timezone, and currency data
- timezones
- fraud analyst
- enrich company data from domain
- enrich company data
- convert date/time from one timezone to another
- company enrichment
- geolocate ip
- developer building payment, billing, and financial compliance systems
- public holidays
- geolocate ip address
slug: data-enrichment
source_filename: data-enrichment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Abstract API Data Enrichment\n  description: Unified data enrichment workflow combining IP geolocation, company enrichment, and timezone APIs. Used by product\n    teams and data engineers to automatically enrich user profiles, personalize experiences, and localize content at signup\n    or session start.\n  tags:\n  - Abstract Api\n  - Data Enrichment\n  - Geolocation\n  - Company Enrichment\n  - Timezones\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    IP_GEOLOCATION_API_KEY: IP_GEOLOCATION_API_KEY\n    COMPANY_ENRICHMENT_API_KEY: COMPANY_ENRICHMENT_API_KEY\n    TIMEZONES_API_KEY: TIMEZONES_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ip-geolocation\n    baseUri: https://ipgeolocation.abstractapi.com/v1\n    description: IP Geolocation API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{env.IP_GEOLOCATION_API_KEY}}'\n      placement: query\n\
  \    resources:\n    - name: ip-geolocation\n      path: /\n      description: IP Geolocation API ip-geolocation resource\n      operations:\n      - name: getIPGeolocation\n        method: GET\n        description: Abstract API Get IP Geolocation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: company-enrichment\n    baseUri: https://companyenrichment.abstractapi.com/v1\n    description: Company Enrichment API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{env.COMPANY_ENRICHMENT_API_KEY}}'\n      placement: query\n    resources:\n    - name: company-enrichment\n      path: /\n      description: Company Enrichment API company-enrichment resource\n      operations:\n      - name: getCompanyEnrichment\n        method: GET\n        description: Abstract API Get Company Enrichment\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n  - type: http\n    namespace: timezones\n    baseUri: https://timezone.abstractapi.com/v1\n    description: Timezone API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{env.TIMEZONES_API_KEY}}'\n      placement: query\n    resources:\n    - name: current_time\n      path: /current_time\n      description: Timezone API current_time resource\n      operations:\n      - name: getCurrentTime\n        method: GET\n        description: Abstract API Get Current Time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: convert_time\n      path: /convert_time\n      description: Timezone API convert_time resource\n      operations:\n      - name: convertTime\n        method: GET\n        description: Abstract API Convert Time Between Timezones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: data-enrichment-api\n    description: Unified REST API for user and session data enrichment.\n    resources:\n    - path: /v1/ip-location\n      name: ip-location\n      description: Geolocate an IP address\n      operations:\n      - method: GET\n        name: geolocate-ip\n        description: Get location data for an IP address\n        call: ip-geolocation.getIPGeolocation\n        with:\n          ip_address: rest.ip_address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/company\n      name: company\n      description: Enrich company data from domain\n      operations:\n      - method: GET\n        name: enrich-company\n        description: Get company details from domain or email\n        call: company-enrichment.getCompanyEnrichment\n        with:\n          domain: rest.domain\n          email: rest.email\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/timezone\n      name: timezone\n      description: Get current timezone for a location\n      operations:\n      - method: GET\n        name: get-timezone\n        description: Retrieve timezone and current time for a location\n        call: timezones.getCurrentTime\n        with:\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: data-enrichment-mcp\n    transport: http\n    description: MCP server for AI-assisted data enrichment and user personalization.\n    tools:\n    - name: geolocate-ip-address\n      description: Geolocate an IP address to get country, city, timezone, and currency data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ip-geolocation.getIPGeolocation\n      with:\n        ip_address: tools.ip_address\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: enrich-company-data\n      description: Retrieve company name, industry, headcount, logo, and location from a domain or email\n      hints:\n        readOnly: true\n        openWorld: true\n      call: company-enrichment.getCompanyEnrichment\n      with:\n        domain: tools.domain\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-timezone\n      description: Get current time and timezone information for any location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: timezones.getCurrentTime\n      with:\n        location: tools.location\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: convert-time-between-zones\n      description: Convert date/time from one timezone to another\n      hints:\n        readOnly: true\n        openWorld: false\n      call: timezones.convertTime\n      with:\n        base_location: tools.base_location\n        target_location:\
  \ tools.target_location\n        base_datetime: tools.base_datetime\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
