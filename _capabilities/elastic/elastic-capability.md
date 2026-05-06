---
categories: []
consumed_apis: []
description: RESTful API for managing Elastic Cloud hosted deployments. Enables you to perform most operations available in the Elastic Cloud console through API calls, including creating, updating, resizing, and deleting deployments, managing traffic filters, snapshots, and account-level resources.
layout: capability
name: Elastic Cloud API
operations:
- description: List deployments
  method: GET
  name: listdeployments
  path: /api/v1/deployments
- description: Create a deployment
  method: POST
  name: createdeployment
  path: /api/v1/deployments
- description: Get a deployment
  method: GET
  name: getdeployment
  path: /api/v1/deployments/{deployment_id}
- description: Delete a deployment
  method: DELETE
  name: deletedeployment
  path: /api/v1/deployments/{deployment_id}
- description: List traffic filter rulesets
  method: GET
  name: listtrafficfilterrulesets
  path: /api/v1/deployments/traffic-filter/rulesets
- description: Get account information
  method: GET
  name: getaccount
  path: /api/v1/account
personas: []
provider_name: Elastic
provider_slug: elastic
search_terms:
- get a deployment
- visualization
- analytics
- create a deployment
- delete a deployment
- cloud
- list deployments
- security
- listtrafficfilterrulesets
- getaccount
- list traffic filter rulesets
- elastic
- get account information
- api
- observability
- createdeployment
- search
- deletedeployment
- listdeployments
- getdeployment
slug: elastic-capability
source_filename: elastic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Elastic Cloud API\n  description: RESTful API for managing Elastic Cloud hosted deployments. Enables you to perform most operations available\n    in the Elastic Cloud console through API calls, including creating, updating, resizing, and deleting deployments, managing\n    traffic filters, snapshots, and account-level resources.\n  tags:\n  - Elastic\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: elastic\n    baseUri: https://api.elastic-cloud.com\n    description: Elastic Cloud API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{ELASTIC_TOKEN}}'\n    resources:\n    - name: api-v1-deployments\n      path: /api/v1/deployments\n      operations:\n      - name: listdeployments\n        method: GET\n        description: List deployments\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: createdeployment\n        method: POST\n        description: Create a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-deployments-deployment-id\n      path: /api/v1/deployments/{deployment_id}\n      operations:\n      - name: getdeployment\n        method: GET\n        description: Get a deployment\n        inputParameters:\n        - name: deployment_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedeployment\n        method: DELETE\n        description: Delete a deployment\n        inputParameters:\n        - name: deployment_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-deployments-traffic-filter-rulesets\n      path: /api/v1/deployments/traffic-filter/rulesets\n      operations:\n      - name: listtrafficfilterrulesets\n        method: GET\n        description: List traffic filter rulesets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-account\n      path: /api/v1/account\n      operations:\n      - name: getaccount\n        method: GET\n        description: Get account information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: elastic-rest\n    description: REST adapter for Elastic Cloud API.\n    resources:\n    - path: /api/v1/deployments\n      name: listdeployments\n      operations:\n      - method:\
  \ GET\n        name: listdeployments\n        description: List deployments\n        call: elastic.listdeployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/deployments\n      name: createdeployment\n      operations:\n      - method: POST\n        name: createdeployment\n        description: Create a deployment\n        call: elastic.createdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/deployments/{deployment_id}\n      name: getdeployment\n      operations:\n      - method: GET\n        name: getdeployment\n        description: Get a deployment\n        call: elastic.getdeployment\n        with:\n          deployment_id: rest.deployment_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/deployments/{deployment_id}\n      name: deletedeployment\n      operations:\n      - method: DELETE\n        name: deletedeployment\n        description:\
  \ Delete a deployment\n        call: elastic.deletedeployment\n        with:\n          deployment_id: rest.deployment_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/deployments/traffic-filter/rulesets\n      name: listtrafficfilterrulesets\n      operations:\n      - method: GET\n        name: listtrafficfilterrulesets\n        description: List traffic filter rulesets\n        call: elastic.listtrafficfilterrulesets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/account\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Get account information\n        call: elastic.getaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: elastic-mcp\n    transport: http\n    description: MCP adapter for Elastic Cloud API for AI agent use.\n    tools:\n    - name: listdeployments\n\
  \      description: List deployments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: elastic.listdeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdeployment\n      description: Create a deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: elastic.createdeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeployment\n      description: Get a deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: elastic.getdeployment\n      with:\n        deployment_id: tools.deployment_id\n      inputParameters:\n      - name: deployment_id\n        type: string\n        description: deployment_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedeployment\n      description:\
  \ Delete a deployment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: elastic.deletedeployment\n      with:\n        deployment_id: tools.deployment_id\n      inputParameters:\n      - name: deployment_id\n        type: string\n        description: deployment_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtrafficfilterrulesets\n      description: List traffic filter rulesets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: elastic.listtrafficfilterrulesets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccount\n      description: Get account information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: elastic.getaccount\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n\
  \    ELASTIC_TOKEN: ELASTIC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/elastic/refs/heads/main/capabilities/elastic-capability.yaml
tags:
- Elastic
- API
tools:
- description: List deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeployments
- description: Create a deployment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeployment
- description: Get a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeployment
- description: Delete a deployment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedeployment
- description: List traffic filter rulesets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtrafficfilterrulesets
- description: Get account information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
---
