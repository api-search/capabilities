---
categories: []
consumed_apis: []
description: Determined is an open-source deep learning platform that helps teams train models faster, share GPU resources, and collaborate. The REST API exposes cluster, experiment, model, checkpoint, template, user, and token management capabilities used by the CLI and Web UI.
layout: capability
name: Determined AI REST API
operations:
- description: Log in
  method: POST
  name: login
  path: /api/v1/auth/login
- description: Log out
  method: POST
  name: logout
  path: /api/v1/auth/logout
- description: List users
  method: GET
  name: getusers
  path: /api/v1/users
- description: Get cluster info
  method: GET
  name: getclusterinfo
  path: /api/v1/cluster
- description: List experiments
  method: GET
  name: getexperiments
  path: /api/v1/experiments
- description: Get experiment
  method: GET
  name: getexperiment
  path: /api/v1/experiments/{experimentId}
- description: List models
  method: GET
  name: getmodels
  path: /api/v1/models
- description: Get checkpoint
  method: GET
  name: getcheckpoint
  path: /api/v1/checkpoints/{checkpointUuid}
- description: List templates
  method: GET
  name: gettemplates
  path: /api/v1/templates
- description: List tokens
  method: GET
  name: getaccesstokens
  path: /api/v1/tokens
personas: []
provider_name: Determined AI
provider_slug: determined-ai
search_terms:
- getaccesstokens
- getcheckpoint
- determined
- getclusterinfo
- getmodels
- getusers
- ai
- api
- list templates
- log out
- list tokens
- log in
- getexperiments
- deep learning
- artificial intelligence
- login
- get checkpoint
- machine learning
- gettemplates
- list users
- mlops
- list models
- logout
- list experiments
- get experiment
- getexperiment
- get cluster info
slug: determined-ai-capability
source_filename: determined-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Determined AI REST API\n  description: Determined is an open-source deep learning platform that helps teams train models faster, share GPU resources,\n    and collaborate. The REST API exposes cluster, experiment, model, checkpoint, template, user, and token management capabilities\n    used by the CLI and Web UI.\n  tags:\n  - Determined\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: determined-ai\n    baseUri: https://master.example.com\n    description: Determined AI REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DETERMINED_AI_TOKEN}}'\n    resources:\n    - name: api-v1-auth-login\n      path: /api/v1/auth/login\n      operations:\n      - name: login\n        method: POST\n        description: Log in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: api-v1-auth-logout\n      path: /api/v1/auth/logout\n      operations:\n      - name: logout\n        method: POST\n        description: Log out\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-users\n      path: /api/v1/users\n      operations:\n      - name: getusers\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-cluster\n      path: /api/v1/cluster\n      operations:\n      - name: getclusterinfo\n        method: GET\n        description: Get cluster info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-experiments\n      path: /api/v1/experiments\n      operations:\n      - name: getexperiments\n        method: GET\n        description:\
  \ List experiments\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-experiments-experimentid\n      path: /api/v1/experiments/{experimentId}\n      operations:\n      - name: getexperiment\n        method: GET\n        description: Get experiment\n        inputParameters:\n        - name: experimentId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-models\n      path: /api/v1/models\n      operations:\n      - name: getmodels\n        method: GET\n        description: List models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: api-v1-checkpoints-checkpointuuid\n      path: /api/v1/checkpoints/{checkpointUuid}\n      operations:\n      - name: getcheckpoint\n        method: GET\n        description: Get checkpoint\n        inputParameters:\n        - name: checkpointUuid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-templates\n      path: /api/v1/templates\n      operations:\n      - name: gettemplates\n        method: GET\n        description: List templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-tokens\n      path: /api/v1/tokens\n      operations:\n      - name: getaccesstokens\n        method: GET\n        description: List tokens\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: determined-ai-rest\n    description: REST adapter for Determined AI REST API.\n    resources:\n    - path: /api/v1/auth/login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: Log in\n        call: determined-ai.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/auth/logout\n      name: logout\n      operations:\n      - method: POST\n        name: logout\n        description: Log out\n        call: determined-ai.logout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/users\n      name: getusers\n      operations:\n      - method: GET\n        name: getusers\n        description: List users\n        call: determined-ai.getusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /api/v1/cluster\n      name: getclusterinfo\n      operations:\n      - method: GET\n        name: getclusterinfo\n        description: Get cluster info\n        call: determined-ai.getclusterinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/experiments\n      name: getexperiments\n      operations:\n      - method: GET\n        name: getexperiments\n        description: List experiments\n        call: determined-ai.getexperiments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/experiments/{experimentId}\n      name: getexperiment\n      operations:\n      - method: GET\n        name: getexperiment\n        description: Get experiment\n        call: determined-ai.getexperiment\n        with:\n          experimentId: rest.experimentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/models\n      name: getmodels\n      operations:\n      - method:\
  \ GET\n        name: getmodels\n        description: List models\n        call: determined-ai.getmodels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/checkpoints/{checkpointUuid}\n      name: getcheckpoint\n      operations:\n      - method: GET\n        name: getcheckpoint\n        description: Get checkpoint\n        call: determined-ai.getcheckpoint\n        with:\n          checkpointUuid: rest.checkpointUuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/templates\n      name: gettemplates\n      operations:\n      - method: GET\n        name: gettemplates\n        description: List templates\n        call: determined-ai.gettemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/tokens\n      name: getaccesstokens\n      operations:\n      - method: GET\n        name: getaccesstokens\n        description: List tokens\n        call: determined-ai.getaccesstokens\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: determined-ai-mcp\n    transport: http\n    description: MCP adapter for Determined AI REST API for AI agent use.\n    tools:\n    - name: login\n      description: Log in\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: determined-ai.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logout\n      description: Log out\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: determined-ai.logout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getusers\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: determined-ai.getusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusterinfo\n\
  \      description: Get cluster info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: determined-ai.getclusterinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexperiments\n      description: List experiments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: determined-ai.getexperiments\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexperiment\n      description: Get experiment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: determined-ai.getexperiment\n      with:\n        experimentId: tools.experimentId\n \
  \     inputParameters:\n      - name: experimentId\n        type: integer\n        description: experimentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmodels\n      description: List models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: determined-ai.getmodels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcheckpoint\n      description: Get checkpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: determined-ai.getcheckpoint\n      with:\n        checkpointUuid: tools.checkpointUuid\n      inputParameters:\n      - name: checkpointUuid\n        type: string\n        description: checkpointUuid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettemplates\n      description: List templates\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: determined-ai.gettemplates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccesstokens\n      description: List tokens\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: determined-ai.getaccesstokens\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DETERMINED_AI_TOKEN: DETERMINED_AI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/determined-ai/refs/heads/main/capabilities/determined-ai-capability.yaml
tags:
- Determined
- Ai
- API
tools:
- description: Log in
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Log out
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: logout
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusers
- description: Get cluster info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusterinfo
- description: List experiments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexperiments
- description: Get experiment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexperiment
- description: List models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodels
- description: Get checkpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcheckpoint
- description: List templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettemplates
- description: List tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccesstokens
---
