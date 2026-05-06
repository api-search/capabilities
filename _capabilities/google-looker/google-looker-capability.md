---
categories: []
consumed_apis: []
description: A simplified OpenAPI representation for Google Looker covering core Looker API 4.0 endpoints used to authenticate, fetch users, and run looks. This spec is a curated index entry pointing to the upstream Looker OpenAPI for full coverage.
layout: capability
name: Google Looker API
operations:
- description: Login
  method: POST
  name: login
  path: /login
- description: Get Current User
  method: GET
  name: getcurrentuser
  path: /user
- description: Get All Users
  method: GET
  name: getallusers
  path: /users
- description: Get All Looks
  method: GET
  name: getalllooks
  path: /looks
- description: Run Look
  method: GET
  name: runlook
  path: /looks/{look_id}/run/{result_format}
personas: []
provider_name: Google Looker
provider_slug: google-looker
search_terms:
- get current user
- getcurrentuser
- login
- get all users
- looker
- google
- api
- get all looks
- run look
- runlook
- getalllooks
- getallusers
slug: google-looker-capability
source_filename: google-looker-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Looker API\n  description: A simplified OpenAPI representation for Google Looker covering core Looker API 4.0 endpoints used to authenticate,\n    fetch users, and run looks. This spec is a curated index entry pointing to the upstream Looker OpenAPI for full coverage.\n  tags:\n  - Google\n  - Looker\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-looker\n    baseUri: https://your-instance.cloud.looker.com:19999/api/4.0\n    description: Google Looker API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_LOOKER_TOKEN}}'\n    resources:\n    - name: login\n      path: /login\n      operations:\n      - name: login\n        method: POST\n        description: Login\n        inputParameters:\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: Looker API client ID\
  \ for the user account being authenticated.\n        - name: client_secret\n          in: query\n          type: string\n          required: true\n          description: Looker API client secret paired with the client_id.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /user\n      operations:\n      - name: getcurrentuser\n        method: GET\n        description: Get Current User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: getallusers\n        method: GET\n        description: Get All Users\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page number to retrieve when paginating user results.\n        - name: per_page\n          in: query\n          type:\
  \ integer\n          description: Number of user records to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: looks\n      path: /looks\n      operations:\n      - name: getalllooks\n        method: GET\n        description: Get All Looks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: looks-look-id-run-result-format\n      path: /looks/{look_id}/run/{result_format}\n      operations:\n      - name: runlook\n        method: GET\n        description: Run Look\n        inputParameters:\n        - name: look_id\n          in: path\n          type: string\n          required: true\n          description: Numeric identifier of the Look to execute.\n        - name: result_format\n          in: path\n          type: string\n          required: true\n          description: Output format for the executed\
  \ Look results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-looker-rest\n    description: REST adapter for Google Looker API.\n    resources:\n    - path: /login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: Login\n        call: google-looker.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user\n      name: getcurrentuser\n      operations:\n      - method: GET\n        name: getcurrentuser\n        description: Get Current User\n        call: google-looker.getcurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: getallusers\n      operations:\n      - method: GET\n        name: getallusers\n        description: Get All Users\n        call: google-looker.getallusers\n     \
  \   outputParameters:\n        - type: object\n          mapping: $.\n    - path: /looks\n      name: getalllooks\n      operations:\n      - method: GET\n        name: getalllooks\n        description: Get All Looks\n        call: google-looker.getalllooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /looks/{look_id}/run/{result_format}\n      name: runlook\n      operations:\n      - method: GET\n        name: runlook\n        description: Run Look\n        call: google-looker.runlook\n        with:\n          look_id: rest.look_id\n          result_format: rest.result_format\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-looker-mcp\n    transport: http\n    description: MCP adapter for Google Looker API for AI agent use.\n    tools:\n    - name: login\n      description: Login\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: google-looker.login\n      with:\n        client_id: tools.client_id\n        client_secret: tools.client_secret\n      inputParameters:\n      - name: client_id\n        type: string\n        description: Looker API client ID for the user account being authenticated.\n        required: true\n      - name: client_secret\n        type: string\n        description: Looker API client secret paired with the client_id.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurrentuser\n      description: Get Current User\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-looker.getcurrentuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getallusers\n      description: Get All Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-looker.getallusers\n      with:\n\
  \        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: page\n        type: integer\n        description: Page number to retrieve when paginating user results.\n      - name: per_page\n        type: integer\n        description: Number of user records to return per page.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getalllooks\n      description: Get All Looks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-looker.getalllooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runlook\n      description: Run Look\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-looker.runlook\n      with:\n        look_id: tools.look_id\n        result_format: tools.result_format\n      inputParameters:\n      - name: look_id\n        type: string\n        description: Numeric\
  \ identifier of the Look to execute.\n        required: true\n      - name: result_format\n        type: string\n        description: Output format for the executed Look results.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_LOOKER_TOKEN: GOOGLE_LOOKER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-looker/refs/heads/main/capabilities/google-looker-capability.yaml
tags:
- Google
- Looker
- API
tools:
- description: Login
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Get Current User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentuser
- description: Get All Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallusers
- description: Get All Looks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalllooks
- description: Run Look
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: runlook
---
