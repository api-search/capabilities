---
categories: []
consumed_apis: []
description: REST API providing access to US nonprofit and charity data sourced from IRS filings. Supports lookup of organizations by EIN, public charity (501c3) verification checks, and name-based autocomplete for donation, fundraising, and compliance workflows.
layout: capability
name: CharityAPI
operations:
- description: Get organization by EIN
  method: GET
  name: getorganizationbyein
  path: /organizations/{ein}
- description: Autocomplete organization names
  method: GET
  name: autocompleteorganizations
  path: /organizations/autocomplete/{term}
- description: Check public charity status
  method: GET
  name: publiccharitycheck
  path: /public_charity_check/{ein}
personas: []
provider_name: CharityAPI
provider_slug: charityapi
search_terms:
- autocompleteorganizations
- ein
- tax compliance
- 501c3
- charities
- autocomplete organization names
- getorganizationbyein
- api
- irs
- check public charity status
- non-profits
- donations
- verification
- charityapi
- get organization by ein
- publiccharitycheck
slug: charityapi-capability
source_filename: charityapi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CharityAPI\n  description: REST API providing access to US nonprofit and charity data sourced from IRS filings. Supports lookup of organizations\n    by EIN, public charity (501c3) verification checks, and name-based autocomplete for donation, fundraising, and compliance\n    workflows.\n  tags:\n  - Charityapi\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: charityapi\n    baseUri: https://api.charityapi.org/api\n    description: CharityAPI HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: apikey\n      value: '{{CHARITYAPI_TOKEN}}'\n    resources:\n    - name: organizations-ein\n      path: /organizations/{ein}\n      operations:\n      - name: getorganizationbyein\n        method: GET\n        description: Get organization by EIN\n        inputParameters:\n        - name: ein\n          in: path\n          type: string\n          required:\
  \ true\n          description: Employer Identification Number for the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-autocomplete-term\n      path: /organizations/autocomplete/{term}\n      operations:\n      - name: autocompleteorganizations\n        method: GET\n        description: Autocomplete organization names\n        inputParameters:\n        - name: term\n          in: path\n          type: string\n          required: true\n          description: Partial organization name to match.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-charity-check-ein\n      path: /public_charity_check/{ein}\n      operations:\n      - name: publiccharitycheck\n        method: GET\n        description: Check public charity status\n        inputParameters:\n        - name: ein\n    \
  \      in: path\n          type: string\n          required: true\n          description: Employer Identification Number to verify.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: charityapi-rest\n    description: REST adapter for CharityAPI.\n    resources:\n    - path: /organizations/{ein}\n      name: getorganizationbyein\n      operations:\n      - method: GET\n        name: getorganizationbyein\n        description: Get organization by EIN\n        call: charityapi.getorganizationbyein\n        with:\n          ein: rest.ein\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/autocomplete/{term}\n      name: autocompleteorganizations\n      operations:\n      - method: GET\n        name: autocompleteorganizations\n        description: Autocomplete organization names\n        call: charityapi.autocompleteorganizations\n\
  \        with:\n          term: rest.term\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public_charity_check/{ein}\n      name: publiccharitycheck\n      operations:\n      - method: GET\n        name: publiccharitycheck\n        description: Check public charity status\n        call: charityapi.publiccharitycheck\n        with:\n          ein: rest.ein\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: charityapi-mcp\n    transport: http\n    description: MCP adapter for CharityAPI for AI agent use.\n    tools:\n    - name: getorganizationbyein\n      description: Get organization by EIN\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charityapi.getorganizationbyein\n      with:\n        ein: tools.ein\n      inputParameters:\n      - name: ein\n        type: string\n        description: Employer Identification Number\
  \ for the organization.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: autocompleteorganizations\n      description: Autocomplete organization names\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charityapi.autocompleteorganizations\n      with:\n        term: tools.term\n      inputParameters:\n      - name: term\n        type: string\n        description: Partial organization name to match.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publiccharitycheck\n      description: Check public charity status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charityapi.publiccharitycheck\n      with:\n        ein: tools.ein\n      inputParameters:\n      - name: ein\n        type: string\n        description: Employer Identification Number to verify.\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHARITYAPI_TOKEN: CHARITYAPI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/charityapi/refs/heads/main/capabilities/charityapi-capability.yaml
tags:
- Charityapi
- API
tools:
- description: Get organization by EIN
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationbyein
- description: Autocomplete organization names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: autocompleteorganizations
- description: Check public charity status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: publiccharitycheck
---
