---
categories: []
consumed_apis: []
description: Gender-API determines whether a first name is more likely used by males or females, with optional localization by country, IP address, or browser locale. The API returns a gender prediction and an accuracy score, and supports email parsing, multi-name lookup, and country-of-origin queries.
layout: capability
name: Gender API
operations:
- description: Get gender for a name
  method: GET
  name: getgender
  path: /get
- description: Get likely country of origin for a name
  method: GET
  name: getcountryoforigin
  path: /get-country-of-origin
- description: Get account statistics
  method: GET
  name: getstats
  path: /get-stats
personas: []
provider_name: Gender API
provider_slug: gender-api
search_terms:
- get likely country of origin for a name
- getgender
- gender
- demographics
- names
- identity
- get gender for a name
- getcountryoforigin
- getstats
- api
- ai
- personal data
- get account statistics
slug: gender-api-capability
source_filename: gender-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Gender API\n  description: Gender-API determines whether a first name is more likely used by males or females, with optional localization\n    by country, IP address, or browser locale. The API returns a gender prediction and an accuracy score, and supports email\n    parsing, multi-name lookup, and country-of-origin queries.\n  tags:\n  - Gender\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: gender-api\n    baseUri: https://gender-api.com\n    description: Gender API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{GENDER_API_TOKEN}}'\n    resources:\n    - name: get\n      path: /get\n      operations:\n      - name: getgender\n        method: GET\n        description: Get gender for a name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description:\
  \ First name (or full name with split=true) to look up. Supports semicolon-separated lists when multi=true.\n        - name: email\n          in: query\n          type: string\n          description: Email address from which to extract the name.\n        - name: country\n          in: query\n          type: string\n          description: ISO 3166-1 alpha-2 country code to localize the lookup.\n        - name: ip\n          in: query\n          type: string\n          description: Client IP address used to localize the lookup.\n        - name: locale\n          in: query\n          type: string\n          description: Browser locale (e.g. en_US, de_DE) used to localize the lookup.\n        - name: split\n          in: query\n          type: boolean\n          description: When true, splits a full name and resolves the first name automatically.\n        - name: multi\n          in: query\n          type: boolean\n          description: When true, accepts a semicolon-separated list of names\
  \ (max 100 per request).\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: Gender-API key (alternatively send via apiKey query or Authorization header per account configuration).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-country-of-origin\n      path: /get-country-of-origin\n      operations:\n      - name: getcountryoforigin\n        method: GET\n        description: Get likely country of origin for a name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n        - name: key\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-stats\n      path: /get-stats\n      operations:\n      - name: getstats\n\
  \        method: GET\n        description: Get account statistics\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gender-api-rest\n    description: REST adapter for Gender API.\n    resources:\n    - path: /get\n      name: getgender\n      operations:\n      - method: GET\n        name: getgender\n        description: Get gender for a name\n        call: gender-api.getgender\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get-country-of-origin\n      name: getcountryoforigin\n      operations:\n      - method: GET\n        name: getcountryoforigin\n        description: Get likely country of origin for a name\n        call: gender-api.getcountryoforigin\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /get-stats\n      name: getstats\n      operations:\n      - method: GET\n        name: getstats\n        description: Get account statistics\n        call: gender-api.getstats\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gender-api-mcp\n    transport: http\n    description: MCP adapter for Gender API for AI agent use.\n    tools:\n    - name: getgender\n      description: Get gender for a name\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gender-api.getgender\n      with:\n        name: tools.name\n        email: tools.email\n        country: tools.country\n        ip: tools.ip\n        locale: tools.locale\n        split: tools.split\n        multi: tools.multi\n        key: tools.key\n      inputParameters:\n      - name: name\n        type: string\n        description: First name (or full name with split=true)\
  \ to look up. Supports semicolon-separated lists when multi=true.\n      - name: email\n        type: string\n        description: Email address from which to extract the name.\n      - name: country\n        type: string\n        description: ISO 3166-1 alpha-2 country code to localize the lookup.\n      - name: ip\n        type: string\n        description: Client IP address used to localize the lookup.\n      - name: locale\n        type: string\n        description: Browser locale (e.g. en_US, de_DE) used to localize the lookup.\n      - name: split\n        type: boolean\n        description: When true, splits a full name and resolves the first name automatically.\n      - name: multi\n        type: boolean\n        description: When true, accepts a semicolon-separated list of names (max 100 per request).\n      - name: key\n        type: string\n        description: Gender-API key (alternatively send via apiKey query or Authorization header per account configuration).\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcountryoforigin\n      description: Get likely country of origin for a name\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gender-api.getcountryoforigin\n      with:\n        name: tools.name\n        key: tools.key\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstats\n      description: Get account statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gender-api.getstats\n      with:\n        key: tools.key\n      inputParameters:\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GENDER_API_TOKEN: GENDER_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gender-api/refs/heads/main/capabilities/gender-api-capability.yaml
tags:
- Gender
- Api
- API
tools:
- description: Get gender for a name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgender
- description: Get likely country of origin for a name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcountryoforigin
- description: Get account statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstats
---
