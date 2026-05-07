---
categories: []
consumed_apis: []
description: API management workflow for platform engineers and API producers to manage Gravitee APIs, plans, subscriptions, applications, and platform configuration through the Management API.
layout: capability
name: Gravitee API Management
operations:
- description: List all APIs.
  method: GET
  name: list-apis
  path: /v1/apis
- description: Create a new API definition.
  method: POST
  name: create-api
  path: /v1/apis
- description: Get an API by ID.
  method: GET
  name: get-api
  path: /v1/apis/{apiId}
- description: Delete an API.
  method: DELETE
  name: delete-api
  path: /v1/apis/{apiId}
- description: Deploy an API definition to the gateway.
  method: POST
  name: deploy-api
  path: /v1/apis/{apiId}/lifecycle
- description: Start an API on the gateway.
  method: POST
  name: start-api
  path: /v1/apis/{apiId}/lifecycle
- description: Stop an API on the gateway.
  method: POST
  name: stop-api
  path: /v1/apis/{apiId}/lifecycle
- description: List plans for an API.
  method: GET
  name: list-api-plans
  path: /v1/apis/{apiId}/plans
- description: List subscriptions for an API.
  method: GET
  name: list-api-subscriptions
  path: /v1/apis/{apiId}/subscriptions
- description: List all applications.
  method: GET
  name: list-applications
  path: /v1/applications
- description: List platform users.
  method: GET
  name: list-users
  path: /v1/users
- description: Get platform-wide configuration.
  method: GET
  name: get-configuration
  path: /v1/configuration
- description: List platform audit events.
  method: GET
  name: list-audit-events
  path: /v1/audit
personas: []
provider_name: Gravitee
provider_slug: gravitee
search_terms:
- list all apis.
- list plans defined for an api.
- list all applications registered on the platform.
- delete api
- delete a gravitee api definition.
- register a new application.
- update api
- start a gravitee api on the gateway.
- get an api by id.
- list api plans
- create api
- gravitee
- start an api on the gateway.
- list platform users.
- create application
- deploy a gravitee api to the gateway.
- deploy an api definition to the gateway.
- get api
- graphql
- open source
- api management
- deploy api
- stop a gravitee api on the gateway.
- get platform-wide configuration settings.
- get platform-wide configuration.
- list subscriptions for an api.
- stop api
- plans for an api.
- administration
- list all applications.
- list users
- get configuration
- stop an api on the gateway.
- list platform audit events.
- api gateway
- list plans for an api.
- subscriptions for an api.
- get a gravitee api definition by id.
- create a new plan for an api.
- platform users.
- delete an api.
- api definitions.
- start api
- single api definition.
- api lifecycle controls.
- list applications
- audit events.
- list all apis on the gravitee platform.
- update a gravitee api definition.
- platform configuration.
- create plan
- list audit events
- create a new gravitee api definition.
- application registry.
- list apis
- list api subscriptions
- create a new api definition.
slug: api-management
source_filename: api-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Gravitee API Management\n  description: API management workflow for platform engineers and API producers to manage Gravitee APIs, plans, subscriptions,\n    applications, and platform configuration through the Management API.\n  tags:\n  - Gravitee\n  - API Management\n  - Administration\n  created: '2026-05-04'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GRAVITEE_MANAGEMENT_URL: GRAVITEE_MANAGEMENT_URL\n    GRAVITEE_MANAGEMENT_TOKEN: GRAVITEE_MANAGEMENT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: gravitee-management\n    baseUri: '{GRAVITEE_MANAGEMENT_URL}'\n    description: Gravitee Management API for platform administration.\n    authentication:\n      type: bearer\n      value: '{{GRAVITEE_MANAGEMENT_TOKEN}}'\n      placement: header\n    resources:\n    - name: apis\n      path: /apis\n      description: API definition management.\n      operations:\n      - name: list-apis\n        method:\
  \ GET\n        description: List all APIs on the platform.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api\n        method: POST\n        description: Create a new API definition.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n\
  \            version: '{{tools.version}}'\n            definitionVersion: '{{tools.definitionVersion}}'\n            type: '{{tools.type}}'\n      - name: get-api\n        method: GET\n        description: Get an API definition by ID.\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: API identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-api\n        method: PUT\n        description: Update an API definition.\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: API identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      \
  \      description: '{{tools.description}}'\n            version: '{{tools.version}}'\n            visibility: '{{tools.visibility}}'\n            lifecycleState: '{{tools.lifecycleState}}'\n      - name: delete-api\n        method: DELETE\n        description: Delete an API definition.\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: API identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-api\n        method: POST\n        description: Deploy the current API definition to the gateway.\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: API identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-api\n\
  \        method: POST\n        description: Start an API on the gateway.\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: API identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-api\n        method: POST\n        description: Stop an API on the gateway.\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: API identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-plans\n      path: /apis/{apiId}/plans\n      description: Plans defined for a specific API.\n      operations:\n      - name: list-api-plans\n        method: GET\n        description: List all plans defined for an API.\n        inputParameters:\n\
  \        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: API identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-plan\n        method: POST\n        description: Create a new plan for an API.\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: API identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            security: '{{tools.security}}'\n            validation: '{{tools.validation}}'\n    - name: api-subscriptions\n      path: /apis/{apiId}/subscriptions\n      description: Subscriptions for a specific\
  \ API.\n      operations:\n      - name: list-api-subscriptions\n        method: GET\n        description: List all subscriptions for an API.\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: API identifier.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by subscription status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      description: Application registration.\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all applications registered on the platform.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: size\n\
  \          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method: POST\n        description: Register a new application.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            type: '{{tools.type}}'\n            settings: '{{tools.settings}}'\n    - name: users\n      path: /users\n      description: Platform users.\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users on the platform.\n        inputParameters:\n        - name: page\n          in: query\n          type:\
  \ integer\n          required: false\n          description: Page number.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /configuration\n      description: Platform configuration.\n      operations:\n      - name: get-configuration\n        method: GET\n        description: Get platform-wide configuration settings.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audit\n      path: /audit\n      description: Platform audit events.\n      operations:\n      - name: list-audit-events\n        method: GET\n        description: List audit events tracking changes across the platform.\n        inputParameters:\n        - name:\
  \ page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: from\n          in: query\n          type: integer\n          required: false\n          description: Start timestamp (epoch ms).\n        - name: to\n          in: query\n          type: integer\n          required: false\n          description: End timestamp (epoch ms).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gravitee-api-management-api\n    description: Unified REST API for Gravitee API management operations.\n    resources:\n    - path: /v1/apis\n      name: apis\n      description: API definitions.\n      operations:\n      - method: GET\n        name: list-apis\n        description:\
  \ List all APIs.\n        call: gravitee-management.list-apis\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-api\n        description: Create a new API definition.\n        call: gravitee-management.create-api\n        with:\n          name: rest.name\n          description: rest.description\n          version: rest.version\n          definitionVersion: rest.definitionVersion\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{apiId}\n      name: api\n      description: Single API definition.\n      operations:\n      - method: GET\n        name: get-api\n        description: Get an API by ID.\n        call: gravitee-management.get-api\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-api\n        description: Delete an API.\n      \
  \  call: gravitee-management.delete-api\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{apiId}/lifecycle\n      name: api-lifecycle\n      description: API lifecycle controls.\n      operations:\n      - method: POST\n        name: deploy-api\n        description: Deploy an API definition to the gateway.\n        call: gravitee-management.deploy-api\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: start-api\n        description: Start an API on the gateway.\n        call: gravitee-management.start-api\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: stop-api\n        description: Stop an API on the gateway.\n        call: gravitee-management.stop-api\n        with:\n          apiId: rest.apiId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{apiId}/plans\n      name: api-plans\n      description: Plans for an API.\n      operations:\n      - method: GET\n        name: list-api-plans\n        description: List plans for an API.\n        call: gravitee-management.list-api-plans\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{apiId}/subscriptions\n      name: api-subscriptions\n      description: Subscriptions for an API.\n      operations:\n      - method: GET\n        name: list-api-subscriptions\n        description: List subscriptions for an API.\n        call: gravitee-management.list-api-subscriptions\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: Application registry.\n      operations:\n\
  \      - method: GET\n        name: list-applications\n        description: List all applications.\n        call: gravitee-management.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Platform users.\n      operations:\n      - method: GET\n        name: list-users\n        description: List platform users.\n        call: gravitee-management.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/configuration\n      name: configuration\n      description: Platform configuration.\n      operations:\n      - method: GET\n        name: get-configuration\n        description: Get platform-wide configuration.\n        call: gravitee-management.get-configuration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audit\n      name: audit\n      description: Audit events.\n      operations:\n      - method:\
  \ GET\n        name: list-audit-events\n        description: List platform audit events.\n        call: gravitee-management.list-audit-events\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gravitee-api-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Gravitee API management.\n    tools:\n    - name: list-apis\n      description: List all APIs on the Gravitee platform.\n      hints:\n        readOnly: true\n      call: gravitee-management.list-apis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api\n      description: Get a Gravitee API definition by ID.\n      hints:\n        readOnly: true\n      call: gravitee-management.get-api\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api\n      description: Create a new Gravitee API definition.\n      hints:\n        readOnly:\
  \ false\n      call: gravitee-management.create-api\n      with:\n        name: tools.name\n        description: tools.description\n        version: tools.version\n        definitionVersion: tools.definitionVersion\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-api\n      description: Update a Gravitee API definition.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: gravitee-management.update-api\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-api\n      description: Delete a Gravitee API definition.\n      hints:\n        destructive: true\n      call: gravitee-management.delete-api\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-api\n      description: Deploy a Gravitee API to the gateway.\n      hints:\n        readOnly: false\n\
  \        idempotent: true\n      call: gravitee-management.deploy-api\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-api\n      description: Start a Gravitee API on the gateway.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: gravitee-management.start-api\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-api\n      description: Stop a Gravitee API on the gateway.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: gravitee-management.stop-api\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-plans\n      description: List plans defined for an API.\n      hints:\n        readOnly: true\n      call: gravitee-management.list-api-plans\n      with:\n        apiId: tools.apiId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-plan\n      description: Create a new plan for an API.\n      hints:\n        readOnly: false\n      call: gravitee-management.create-plan\n      with:\n        apiId: tools.apiId\n        name: tools.name\n        security: tools.security\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-subscriptions\n      description: List subscriptions for an API.\n      hints:\n        readOnly: true\n      call: gravitee-management.list-api-subscriptions\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-applications\n      description: List all applications registered on the platform.\n      hints:\n        readOnly: true\n      call: gravitee-management.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application\n      description: Register a new application.\n\
  \      hints:\n        readOnly: false\n      call: gravitee-management.create-application\n      with:\n        name: tools.name\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List platform users.\n      hints:\n        readOnly: true\n      call: gravitee-management.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-configuration\n      description: Get platform-wide configuration settings.\n      hints:\n        readOnly: true\n      call: gravitee-management.get-configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-audit-events\n      description: List platform audit events.\n      hints:\n        readOnly: true\n      call: gravitee-management.list-audit-events\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gravitee/refs/heads/main/capabilities/api-management.yaml
tags:
- Gravitee
- API Management
- Administration
tools:
- description: List all APIs on the Gravitee platform.
  hints:
    readOnly: true
  name: list-apis
- description: Get a Gravitee API definition by ID.
  hints:
    readOnly: true
  name: get-api
- description: Create a new Gravitee API definition.
  hints:
    readOnly: false
  name: create-api
- description: Update a Gravitee API definition.
  hints:
    idempotent: true
    readOnly: false
  name: update-api
- description: Delete a Gravitee API definition.
  hints:
    destructive: true
  name: delete-api
- description: Deploy a Gravitee API to the gateway.
  hints:
    idempotent: true
    readOnly: false
  name: deploy-api
- description: Start a Gravitee API on the gateway.
  hints:
    idempotent: true
    readOnly: false
  name: start-api
- description: Stop a Gravitee API on the gateway.
  hints:
    idempotent: true
    readOnly: false
  name: stop-api
- description: List plans defined for an API.
  hints:
    readOnly: true
  name: list-api-plans
- description: Create a new plan for an API.
  hints:
    readOnly: false
  name: create-plan
- description: List subscriptions for an API.
  hints:
    readOnly: true
  name: list-api-subscriptions
- description: List all applications registered on the platform.
  hints:
    readOnly: true
  name: list-applications
- description: Register a new application.
  hints:
    readOnly: false
  name: create-application
- description: List platform users.
  hints:
    readOnly: true
  name: list-users
- description: Get platform-wide configuration settings.
  hints:
    readOnly: true
  name: get-configuration
- description: List platform audit events.
  hints:
    readOnly: true
  name: list-audit-events
---
