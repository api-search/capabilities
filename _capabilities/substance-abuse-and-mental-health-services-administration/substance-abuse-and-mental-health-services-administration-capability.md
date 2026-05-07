---
categories: []
consumed_apis: []
description: The SAMHSA Behavioral Health Treatment Services Locator API provides search access to over 14,000 substance use disorder and mental health treatment facilities across the United States. The API powers findtreatment.gov and allows developers to build treatment locator tools for their communities.
layout: capability
name: SAMHSA Behavioral Health Treatment Services Locator API
operations:
- description: Search Treatment Facilities
  method: GET
  name: searchtreatmentfacilities
  path: /listing
personas: []
provider_name: Substance Abuse and Mental Health Services Administration
provider_slug: substance-abuse-and-mental-health-services-administration
search_terms:
- behavioral health
- substance
- public health
- mental health
- health
- search treatment facilities
- substance use disorders
- services
- abuse
- and
- mental
- federal government
- searchtreatmentfacilities
- open data
- healthcare
slug: substance-abuse-and-mental-health-services-administration-capability
source_filename: substance-abuse-and-mental-health-services-administration-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAMHSA Behavioral Health Treatment Services Locator API\n  description: The SAMHSA Behavioral Health Treatment Services Locator API provides search access to over 14,000 substance\n    use disorder and mental health treatment facilities across the United States. The API powers findtreatment.gov and allows\n    developers to build treatment locator tools for their communities.\n  tags:\n  - Substance\n  - Abuse\n  - And\n  - Mental\n  - Health\n  - Services\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: substance-abuse-and-mental-health-services-administration\n    baseUri: https://findtreatment.gov/locator/listing\n    description: SAMHSA Behavioral Health Treatment Services Locator API HTTP API.\n    resources:\n    - name: listing\n      path: /listing\n      operations:\n      - name: searchtreatmentfacilities\n        method: GET\n        description: Search Treatment Facilities\n\
  \        inputParameters:\n        - name: sAddr\n          in: query\n          type: string\n          description: Street address to search near\n        - name: sCity\n          in: query\n          type: string\n          description: City to search in\n        - name: sState\n          in: query\n          type: string\n          description: Two-letter state abbreviation (e.g., CA, TX)\n        - name: sZip\n          in: query\n          type: string\n          description: ZIP code to search near\n        - name: sDistance\n          in: query\n          type: integer\n          description: Search radius in miles\n        - name: sCatCode\n          in: query\n          type: string\n          description: 'Category code: SA (substance abuse), MH (mental health), CO (co-occurring)'\n        - name: sType\n          in: query\n          type: string\n          description: Facility type code\n        - name: sService\n          in: query\n          type: string\n          description:\
  \ Service type code (e.g., detox, residential, outpatient)\n        - name: sMedicaid\n          in: query\n          type: string\n          description: Filter for Medicaid-accepting facilities\n        - name: sMedicare\n          in: query\n          type: string\n          description: Filter for Medicare-accepting facilities\n        - name: sSlidingFee\n          in: query\n          type: string\n          description: Filter for sliding-scale fee facilities\n        - name: sNoFee\n          in: query\n          type: string\n          description: Filter for no-cost treatment facilities\n        - name: page\n          in: query\n          type: integer\n          description: Page number for paginated results\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type:\
  \ rest\n    port: 8080\n    namespace: substance-abuse-and-mental-health-services-administration-rest\n    description: REST adapter for SAMHSA Behavioral Health Treatment Services Locator API.\n    resources:\n    - path: /listing\n      name: searchtreatmentfacilities\n      operations:\n      - method: GET\n        name: searchtreatmentfacilities\n        description: Search Treatment Facilities\n        call: substance-abuse-and-mental-health-services-administration.searchtreatmentfacilities\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: substance-abuse-and-mental-health-services-administration-mcp\n    transport: http\n    description: MCP adapter for SAMHSA Behavioral Health Treatment Services Locator API for AI agent use.\n    tools:\n    - name: searchtreatmentfacilities\n      description: Search Treatment Facilities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: substance-abuse-and-mental-health-services-administration.searchtreatmentfacilities\n      with:\n        sAddr: tools.sAddr\n        sCity: tools.sCity\n        sState: tools.sState\n        sZip: tools.sZip\n        sDistance: tools.sDistance\n        sCatCode: tools.sCatCode\n        sType: tools.sType\n        sService: tools.sService\n        sMedicaid: tools.sMedicaid\n        sMedicare: tools.sMedicare\n        sSlidingFee: tools.sSlidingFee\n        sNoFee: tools.sNoFee\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: sAddr\n        type: string\n        description: Street address to search near\n      - name: sCity\n        type: string\n        description: City to search in\n      - name: sState\n        type: string\n        description: Two-letter state abbreviation (e.g., CA, TX)\n      - name: sZip\n        type: string\n        description: ZIP code to search near\n      - name: sDistance\n        type: integer\n\
  \        description: Search radius in miles\n      - name: sCatCode\n        type: string\n        description: 'Category code: SA (substance abuse), MH (mental health), CO (co-occurring)'\n      - name: sType\n        type: string\n        description: Facility type code\n      - name: sService\n        type: string\n        description: Service type code (e.g., detox, residential, outpatient)\n      - name: sMedicaid\n        type: string\n        description: Filter for Medicaid-accepting facilities\n      - name: sMedicare\n        type: string\n        description: Filter for Medicare-accepting facilities\n      - name: sSlidingFee\n        type: string\n        description: Filter for sliding-scale fee facilities\n      - name: sNoFee\n        type: string\n        description: Filter for no-cost treatment facilities\n      - name: page\n        type: integer\n        description: Page number for paginated results\n      - name: pageSize\n        type: integer\n        description:\
  \ Number of results per page\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/substance-abuse-and-mental-health-services-administration/refs/heads/main/capabilities/substance-abuse-and-mental-health-services-administration-capability.yaml
tags:
- Substance
- Abuse
- And
- Mental
- Health
- Services
tools:
- description: Search Treatment Facilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchtreatmentfacilities
---
