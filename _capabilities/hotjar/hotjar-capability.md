---
categories: []
consumed_apis: []
description: The Hotjar REST API provides programmatic access to Hotjar data and functionality. It allows developers to export survey responses, list surveys, automate user lookup and deletion requests, and integrate Hotjar data into external tools and workflows. The API uses OAuth client credentials authentication, returns JSON responses, supports cursor-based pagination, and is rate limited to 3000 requests per minute. It is available on Observe and Ask Scale plans.
layout: capability
name: Hotjar REST API
operations:
- description: Obtain an OAuth access token
  method: POST
  name: createoauthtoken
  path: /oauth/token
- description: List surveys for a site
  method: GET
  name: listsurveys
  path: /sites/{site_id}/surveys
- description: Get a specific survey
  method: GET
  name: getsurvey
  path: /sites/{site_id}/surveys/{survey_id}
- description: List survey responses
  method: GET
  name: listsurveyresponses
  path: /sites/{site_id}/surveys/{survey_id}/responses
- description: Look up or delete user data
  method: POST
  name: userlookup
  path: /organizations/{organization_id}/user-lookup
personas: []
provider_name: hotjar
provider_slug: hotjar
search_terms:
- getsurvey
- createoauthtoken
- listsurveys
- listsurveyresponses
- get a specific survey
- api
- hotjar
- list surveys for a site
- look up or delete user data
- obtain an oauth access token
- list survey responses
- userlookup
slug: hotjar-capability
source_filename: hotjar-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hotjar REST API\n  description: The Hotjar REST API provides programmatic access to Hotjar data and functionality. It allows developers to\n    export survey responses, list surveys, automate user lookup and deletion requests, and integrate Hotjar data into external\n    tools and workflows. The API uses OAuth client credentials authentication, returns JSON responses, supports cursor-based\n    pagination, and is rate limited to 3000 requests per minute. It is available on Observe and Ask Scale plans.\n  tags:\n  - Hotjar\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hotjar\n    baseUri: https://api.hotjar.io/v1\n    description: Hotjar REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HOTJAR_TOKEN}}'\n    resources:\n    - name: oauth-token\n      path: /oauth/token\n      operations:\n      - name: createoauthtoken\n        method: POST\n\
  \        description: Obtain an OAuth access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-surveys\n      path: /sites/{site_id}/surveys\n      operations:\n      - name: listsurveys\n        method: GET\n        description: List surveys for a site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-surveys-survey-id\n      path: /sites/{site_id}/surveys/{survey_id}\n      operations:\n      - name: getsurvey\n        method: GET\n        description: Get a specific survey\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-surveys-survey-id-responses\n      path: /sites/{site_id}/surveys/{survey_id}/responses\n      operations:\n      - name: listsurveyresponses\n       \
  \ method: GET\n        description: List survey responses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-id-user-lookup\n      path: /organizations/{organization_id}/user-lookup\n      operations:\n      - name: userlookup\n        method: POST\n        description: Look up or delete user data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hotjar-rest\n    description: REST adapter for Hotjar REST API.\n    resources:\n    - path: /oauth/token\n      name: createoauthtoken\n      operations:\n      - method: POST\n        name: createoauthtoken\n        description: Obtain an OAuth access token\n        call: hotjar.createoauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{site_id}/surveys\n\
  \      name: listsurveys\n      operations:\n      - method: GET\n        name: listsurveys\n        description: List surveys for a site\n        call: hotjar.listsurveys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{site_id}/surveys/{survey_id}\n      name: getsurvey\n      operations:\n      - method: GET\n        name: getsurvey\n        description: Get a specific survey\n        call: hotjar.getsurvey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{site_id}/surveys/{survey_id}/responses\n      name: listsurveyresponses\n      operations:\n      - method: GET\n        name: listsurveyresponses\n        description: List survey responses\n        call: hotjar.listsurveyresponses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}/user-lookup\n      name: userlookup\n      operations:\n      - method: POST\n        name:\
  \ userlookup\n        description: Look up or delete user data\n        call: hotjar.userlookup\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hotjar-mcp\n    transport: http\n    description: MCP adapter for Hotjar REST API for AI agent use.\n    tools:\n    - name: createoauthtoken\n      description: Obtain an OAuth access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hotjar.createoauthtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsurveys\n      description: List surveys for a site\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hotjar.listsurveys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsurvey\n      description: Get a specific survey\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: hotjar.getsurvey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsurveyresponses\n      description: List survey responses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hotjar.listsurveyresponses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: userlookup\n      description: Look up or delete user data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hotjar.userlookup\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HOTJAR_TOKEN: HOTJAR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hotjar/refs/heads/main/capabilities/hotjar-capability.yaml
tags:
- Hotjar
- API
tools:
- description: Obtain an OAuth access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createoauthtoken
- description: List surveys for a site
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsurveys
- description: Get a specific survey
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsurvey
- description: List survey responses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsurveyresponses
- description: Look up or delete user data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: userlookup
---
