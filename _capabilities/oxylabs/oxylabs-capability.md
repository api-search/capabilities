---
categories: []
consumed_apis: []
description: Oxylabs provides web scraping and data extraction APIs including the Web Scraper API (Realtime and Push-Pull), the Dashboard API for usage and statistics, and the Residential Public API for sub-user and stats management.
layout: capability
name: Oxylabs Web Intelligence APIs
operations:
- description: Submit a scraping job
  method: POST
  name: submitquery
  path: /queries
- description: List statistics filter instances
  method: GET
  name: liststatsfilters
  path: /stats/v1/filters/instances
- description: Get usage statistics
  method: GET
  name: getusagestats
  path: /stats/v1/usage
- description: Residential API login
  method: POST
  name: residentiallogin
  path: /login
- description: List sub-users
  method: GET
  name: listsubusers
  path: /users/{userId}/sub-users
- description: Create a sub-user
  method: POST
  name: createsubuser
  path: /users/{userId}/sub-users
- description: Get sub-user
  method: GET
  name: getsubuser
  path: /users/{userId}/sub-users/{subUserId}
- description: Update sub-user
  method: PATCH
  name: updatesubuser
  path: /users/{userId}/sub-users/{subUserId}
- description: Delete sub-user
  method: DELETE
  name: deletesubuser
  path: /users/{userId}/sub-users/{subUserId}
- description: Get sub-user target statistics
  method: GET
  name: getsubusertargetstats
  path: /users/{userId}/sub-users/{subUserId}/target-stats
- description: Get client statistics
  method: GET
  name: getclientstats
  path: /users/{userId}/client-stats
personas: []
provider_name: Oxylabs
provider_slug: oxylabs
search_terms:
- getsubusertargetstats
- get client statistics
- listsubusers
- getclientstats
- deletesubuser
- get usage statistics
- residential api login
- data extraction
- create a sub-user
- list sub-users
- residentiallogin
- delete sub-user
- oxylabs
- submitquery
- update sub-user
- api
- scraping
- list statistics filter instances
- updatesubuser
- getsubuser
- liststatsfilters
- getusagestats
- web intelligence
- submit a scraping job
- get sub-user target statistics
- proxies
- createsubuser
- get sub-user
slug: oxylabs-capability
source_filename: oxylabs-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oxylabs Web Intelligence APIs\n  description: Oxylabs provides web scraping and data extraction APIs including the Web Scraper API (Realtime and Push-Pull),\n    the Dashboard API for usage and statistics, and the Residential Public API for sub-user and stats management.\n  tags:\n  - Oxylabs\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oxylabs\n    baseUri: https://realtime.oxylabs.io/v1\n    description: Oxylabs Web Intelligence APIs HTTP API.\n    authentication:\n      type: basic\n      username: '{{OXYLABS_USERNAME}}'\n      password: '{{OXYLABS_PASSWORD}}'\n    resources:\n    - name: queries\n      path: /queries\n      operations:\n      - name: submitquery\n        method: POST\n        description: Submit a scraping job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ stats-v1-filters-instances\n      path: /stats/v1/filters/instances\n      operations:\n      - name: liststatsfilters\n        method: GET\n        description: List statistics filter instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats-v1-usage\n      path: /stats/v1/usage\n      operations:\n      - name: getusagestats\n        method: GET\n        description: Get usage statistics\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n        - name: to\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: login\n      path: /login\n      operations:\n      - name: residentiallogin\n        method: POST\n        description: Residential API login\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: users-userid-sub-users\n      path: /users/{userId}/sub-users\n      operations:\n      - name: listsubusers\n        method: GET\n        description: List sub-users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubuser\n        method: POST\n        description: Create a sub-user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-sub-users-subuserid\n      path: /users/{userId}/sub-users/{subUserId}\n      operations:\n      - name: getsubuser\n        method: GET\n        description: Get sub-user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesubuser\n        method: PATCH\n        description: Update sub-user\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesubuser\n        method: DELETE\n        description: Delete sub-user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-sub-users-subuserid-target-stats\n      path: /users/{userId}/sub-users/{subUserId}/target-stats\n      operations:\n      - name: getsubusertargetstats\n        method: GET\n        description: Get sub-user target statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-client-stats\n      path: /users/{userId}/client-stats\n      operations:\n      - name: getclientstats\n        method: GET\n        description: Get client statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oxylabs-rest\n    description: REST adapter for Oxylabs Web Intelligence APIs.\n    resources:\n    - path: /queries\n      name: submitquery\n      operations:\n      - method: POST\n        name: submitquery\n        description: Submit a scraping job\n        call: oxylabs.submitquery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/v1/filters/instances\n      name: liststatsfilters\n      operations:\n      - method: GET\n        name: liststatsfilters\n        description: List statistics filter instances\n        call: oxylabs.liststatsfilters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/v1/usage\n      name: getusagestats\n      operations:\n      - method: GET\n        name: getusagestats\n        description: Get usage statistics\n        call: oxylabs.getusagestats\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /login\n      name: residentiallogin\n      operations:\n      - method: POST\n        name: residentiallogin\n        description: Residential API login\n        call: oxylabs.residentiallogin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/sub-users\n      name: listsubusers\n      operations:\n      - method: GET\n        name: listsubusers\n        description: List sub-users\n        call: oxylabs.listsubusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/sub-users\n      name: createsubuser\n      operations:\n      - method: POST\n        name: createsubuser\n        description: Create a sub-user\n        call: oxylabs.createsubuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/sub-users/{subUserId}\n      name: getsubuser\n      operations:\n      - method:\
  \ GET\n        name: getsubuser\n        description: Get sub-user\n        call: oxylabs.getsubuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/sub-users/{subUserId}\n      name: updatesubuser\n      operations:\n      - method: PATCH\n        name: updatesubuser\n        description: Update sub-user\n        call: oxylabs.updatesubuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/sub-users/{subUserId}\n      name: deletesubuser\n      operations:\n      - method: DELETE\n        name: deletesubuser\n        description: Delete sub-user\n        call: oxylabs.deletesubuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/sub-users/{subUserId}/target-stats\n      name: getsubusertargetstats\n      operations:\n      - method: GET\n        name: getsubusertargetstats\n        description: Get sub-user target statistics\n\
  \        call: oxylabs.getsubusertargetstats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/client-stats\n      name: getclientstats\n      operations:\n      - method: GET\n        name: getclientstats\n        description: Get client statistics\n        call: oxylabs.getclientstats\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oxylabs-mcp\n    transport: http\n    description: MCP adapter for Oxylabs Web Intelligence APIs for AI agent use.\n    tools:\n    - name: submitquery\n      description: Submit a scraping job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oxylabs.submitquery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststatsfilters\n      description: List statistics filter instances\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: oxylabs.liststatsfilters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getusagestats\n      description: Get usage statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oxylabs.getusagestats\n      with:\n        from: tools.from\n        to: tools.to\n      inputParameters:\n      - name: from\n        type: string\n        description: from\n      - name: to\n        type: string\n        description: to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: residentiallogin\n      description: Residential API login\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oxylabs.residentiallogin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubusers\n      description: List sub-users\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: oxylabs.listsubusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubuser\n      description: Create a sub-user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oxylabs.createsubuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubuser\n      description: Get sub-user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oxylabs.getsubuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesubuser\n      description: Update sub-user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oxylabs.updatesubuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesubuser\n      description: Delete sub-user\n      hints:\n        readOnly:\
  \ false\n        destructive: true\n        idempotent: true\n      call: oxylabs.deletesubuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubusertargetstats\n      description: Get sub-user target statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oxylabs.getsubusertargetstats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclientstats\n      description: Get client statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oxylabs.getclientstats\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OXYLABS_USERNAME: OXYLABS_USERNAME\n    OXYLABS_PASSWORD: OXYLABS_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oxylabs/refs/heads/main/capabilities/oxylabs-capability.yaml
tags:
- Oxylabs
- API
tools:
- description: Submit a scraping job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitquery
- description: List statistics filter instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststatsfilters
- description: Get usage statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusagestats
- description: Residential API login
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: residentiallogin
- description: List sub-users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubusers
- description: Create a sub-user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubuser
- description: Get sub-user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubuser
- description: Update sub-user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesubuser
- description: Delete sub-user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubuser
- description: Get sub-user target statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubusertargetstats
- description: Get client statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclientstats
---
