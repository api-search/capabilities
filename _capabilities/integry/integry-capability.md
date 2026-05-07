---
categories: []
consumed_apis: []
description: Integry is an embedded integration platform that lets SaaS companies offer native integrations to their users. The API exposes apps, functions, and flows used to predict, list, retrieve, and call integration functions on behalf of end users.
layout: capability
name: Integry API
operations:
- description: List apps
  method: POST
  name: listapps
  path: /apps/list
- description: Get app
  method: POST
  name: getapp
  path: /apps/{app_name}/get
- description: List functions
  method: POST
  name: listfunctions
  path: /functions/list
- description: Predict functions
  method: POST
  name: predictfunctions
  path: /functions/predict
- description: Get function
  method: POST
  name: getfunction
  path: /functions/{function_name}/get
- description: Call function
  method: POST
  name: callfunction
  path: /functions/{function_name}/call
personas: []
provider_name: Integry
provider_slug: integry
search_terms:
- embedded ipaas
- get app
- predictfunctions
- get function
- callfunction
- getfunction
- predict functions
- listapps
- integry
- list apps
- list functions
- integration
- call function
- api
- listfunctions
- getapp
- native integrations
slug: integry-capability
source_filename: integry-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Integry API\n  description: Integry is an embedded integration platform that lets SaaS companies offer native integrations to their users.\n    The API exposes apps, functions, and flows used to predict, list, retrieve, and call integration functions on behalf of\n    end users.\n  tags:\n  - Integry\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: integry\n    baseUri: https://api.integry.io\n    description: Integry API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: App-Key\n      value: '{{INTEGRY_TOKEN}}'\n    resources:\n    - name: apps-list\n      path: /apps/list\n      operations:\n      - name: listapps\n        method: POST\n        description: List apps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-name-get\n      path:\
  \ /apps/{app_name}/get\n      operations:\n      - name: getapp\n        method: POST\n        description: Get app\n        inputParameters:\n        - name: app_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-list\n      path: /functions/list\n      operations:\n      - name: listfunctions\n        method: POST\n        description: List functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-predict\n      path: /functions/predict\n      operations:\n      - name: predictfunctions\n        method: POST\n        description: Predict functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-function-name-get\n\
  \      path: /functions/{function_name}/get\n      operations:\n      - name: getfunction\n        method: POST\n        description: Get function\n        inputParameters:\n        - name: function_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-function-name-call\n      path: /functions/{function_name}/call\n      operations:\n      - name: callfunction\n        method: POST\n        description: Call function\n        inputParameters:\n        - name: function_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: integry-rest\n    description: REST adapter for Integry API.\n    resources:\n    - path: /apps/list\n\
  \      name: listapps\n      operations:\n      - method: POST\n        name: listapps\n        description: List apps\n        call: integry.listapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_name}/get\n      name: getapp\n      operations:\n      - method: POST\n        name: getapp\n        description: Get app\n        call: integry.getapp\n        with:\n          app_name: rest.app_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/list\n      name: listfunctions\n      operations:\n      - method: POST\n        name: listfunctions\n        description: List functions\n        call: integry.listfunctions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/predict\n      name: predictfunctions\n      operations:\n      - method: POST\n        name: predictfunctions\n        description: Predict functions\n        call: integry.predictfunctions\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/{function_name}/get\n      name: getfunction\n      operations:\n      - method: POST\n        name: getfunction\n        description: Get function\n        call: integry.getfunction\n        with:\n          function_name: rest.function_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/{function_name}/call\n      name: callfunction\n      operations:\n      - method: POST\n        name: callfunction\n        description: Call function\n        call: integry.callfunction\n        with:\n          function_name: rest.function_name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: integry-mcp\n    transport: http\n    description: MCP adapter for Integry API for AI agent use.\n    tools:\n    - name: listapps\n      description: List apps\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: integry.listapps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapp\n      description: Get app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: integry.getapp\n      with:\n        app_name: tools.app_name\n      inputParameters:\n      - name: app_name\n        type: string\n        description: app_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfunctions\n      description: List functions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: integry.listfunctions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: predictfunctions\n      description: Predict functions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ integry.predictfunctions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfunction\n      description: Get function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: integry.getfunction\n      with:\n        function_name: tools.function_name\n      inputParameters:\n      - name: function_name\n        type: string\n        description: function_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: callfunction\n      description: Call function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: integry.callfunction\n      with:\n        function_name: tools.function_name\n      inputParameters:\n      - name: function_name\n        type: string\n        description: function_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace:\
  \ env\n  keys:\n    INTEGRY_TOKEN: INTEGRY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/integry/refs/heads/main/capabilities/integry-capability.yaml
tags:
- Integry
- API
tools:
- description: List apps
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listapps
- description: Get app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getapp
- description: List functions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listfunctions
- description: Predict functions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: predictfunctions
- description: Get function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getfunction
- description: Call function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: callfunction
---
