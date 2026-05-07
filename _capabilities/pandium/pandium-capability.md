---
categories: []
consumed_apis: []
description: The Pandium API provides programmatic access to native Pandium resources including integrations, tenants, and runs. It uses standard REST conventions and HTTP methods, allowing B2B SaaS companies to manage their integration platform, trigger syncs, proxy connector calls, and manage tenant metadata.
layout: capability
name: Pandium API
operations:
- description: Pandium List all integrations
  method: GET
  name: listintegrations
  path: /v2/integrations
- description: Pandium Get a single integration
  method: GET
  name: getintegration
  path: /v2/integrations/{integration_id}
- description: Pandium List releases for an integration
  method: GET
  name: listintegrationreleases
  path: /v2/integrations/{integration_id}/releases
- description: Pandium Get a single release
  method: GET
  name: getintegrationrelease
  path: /v2/integrations/{integration_id}/releases/{release_id}
- description: Pandium List all tenants
  method: GET
  name: listtenants
  path: /v2/tenants
- description: Pandium Create a tenant
  method: POST
  name: createtenant
  path: /v2/tenants
- description: Pandium Get a single tenant
  method: GET
  name: gettenant
  path: /v2/tenants/{tenant_id}
- description: Pandium Update a tenant
  method: PATCH
  name: updatetenant
  path: /v2/tenants/{tenant_id}
- description: Pandium Trigger a sync for a tenant
  method: POST
  name: triggertenantsync
  path: /v2/tenants/{tenant_id}/sync
- description: Pandium List runs for a tenant
  method: GET
  name: listtenantruns
  path: /v2/tenants/{tenant_id}/runs
- description: Pandium Get run status by trigger ID
  method: GET
  name: getrunbytriggerid
  path: /v2/tenants/{tenant_id}/runs/{trigger_id}
- description: Pandium Proxy a connector call
  method: POST
  name: proxyconnectorcall
  path: /v2/tenants/{tenant_id}/connectors/{connector_name}/call
- description: Pandium Get tenant metadata
  method: GET
  name: gettenantmetadata
  path: /v2/tenants/{tenant_id}/metadata
- description: Pandium Update tenant metadata
  method: PATCH
  name: updatetenantmetadata
  path: /v2/tenants/{tenant_id}/metadata
personas: []
provider_name: Pandium
provider_slug: pandium
search_terms:
- integrations
- pandium get run status by trigger id
- pandium create a tenant
- triggertenantsync
- hubs
- api
- b2b
- gettenantmetadata
- createtenant
- pandium
- gettenant
- proxyconnectorcall
- pandium trigger a sync for a tenant
- listintegrations
- getintegrationrelease
- pandium proxy a connector call
- pandium get tenant metadata
- pandium list all integrations
- listintegrationreleases
- listtenants
- getintegration
- pandium list all tenants
- listtenantruns
- pandium update tenant metadata
- workflows
- updatetenant
- pandium list releases for an integration
- pandium get a single integration
- getrunbytriggerid
- pandium get a single release
- pandium get a single tenant
- updatetenantmetadata
- pandium update a tenant
- pandium list runs for a tenant
slug: pandium-capability
source_filename: pandium-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pandium API\n  description: The Pandium API provides programmatic access to native Pandium resources including integrations, tenants, and\n    runs. It uses standard REST conventions and HTTP methods, allowing B2B SaaS companies to manage their integration platform,\n    trigger syncs, proxy connector calls, and manage tenant metadata.\n  tags:\n  - Pandium\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pandium\n    baseUri: https://api.pandium.io\n    description: Pandium API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{PANDIUM_TOKEN}}'\n    resources:\n    - name: v2-integrations\n      path: /v2/integrations\n      operations:\n      - name: listintegrations\n        method: GET\n        description: Pandium List all integrations\n        inputParameters:\n        - name: skip\n          in: query\n\
  \          type: integer\n          description: Number of records to skip for pagination.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-integrations-integration-id\n      path: /v2/integrations/{integration_id}\n      operations:\n      - name: getintegration\n        method: GET\n        description: Pandium Get a single integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-integrations-integration-id-releases\n      path: /v2/integrations/{integration_id}/releases\n      operations:\n      - name: listintegrationreleases\n        method: GET\n        description: Pandium List releases for an integration\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v2-integrations-integration-id-releases-release-\n      path: /v2/integrations/{integration_id}/releases/{release_id}\n      operations:\n      - name: getintegrationrelease\n        method: GET\n        description: Pandium Get a single release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-tenants\n      path: /v2/tenants\n      operations:\n      - name: listtenants\n        method: GET\n        description: Pandium List all tenants\n        inputParameters:\n        - name: skip\n          in: query\n          type: integer\n          description: Number of records to skip for pagination.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of records to return.\n        - name: integration_id\n          in: query\n          type: integer\n          description:\
  \ Filter tenants by integration ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtenant\n        method: POST\n        description: Pandium Create a tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-tenants-tenant-id\n      path: /v2/tenants/{tenant_id}\n      operations:\n      - name: gettenant\n        method: GET\n        description: Pandium Get a single tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetenant\n        method: PATCH\n        description: Pandium Update a tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-tenants-tenant-id-sync\n      path: /v2/tenants/{tenant_id}/sync\n\
  \      operations:\n      - name: triggertenantsync\n        method: POST\n        description: Pandium Trigger a sync for a tenant\n        inputParameters:\n        - name: mode\n          in: query\n          type: string\n          required: true\n          description: The sync mode to use.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-tenants-tenant-id-runs\n      path: /v2/tenants/{tenant_id}/runs\n      operations:\n      - name: listtenantruns\n        method: GET\n        description: Pandium List runs for a tenant\n        inputParameters:\n        - name: skip\n          in: query\n          type: integer\n          description: Number of records to skip for pagination.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: v2-tenants-tenant-id-runs-trigger-id\n      path: /v2/tenants/{tenant_id}/runs/{trigger_id}\n      operations:\n      - name: getrunbytriggerid\n        method: GET\n        description: Pandium Get run status by trigger ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-tenants-tenant-id-connectors-connector-name-c\n      path: /v2/tenants/{tenant_id}/connectors/{connector_name}/call\n      operations:\n      - name: proxyconnectorcall\n        method: POST\n        description: Pandium Proxy a connector call\n        inputParameters:\n        - name: connector_name\n          in: path\n          type: string\n          required: true\n          description: The name of the connector to call through.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ v2-tenants-tenant-id-metadata\n      path: /v2/tenants/{tenant_id}/metadata\n      operations:\n      - name: gettenantmetadata\n        method: GET\n        description: Pandium Get tenant metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetenantmetadata\n        method: PATCH\n        description: Pandium Update tenant metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pandium-rest\n    description: REST adapter for Pandium API.\n    resources:\n    - path: /v2/integrations\n      name: listintegrations\n      operations:\n      - method: GET\n        name: listintegrations\n        description: Pandium List all integrations\n        call: pandium.listintegrations\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v2/integrations/{integration_id}\n      name: getintegration\n      operations:\n      - method: GET\n        name: getintegration\n        description: Pandium Get a single integration\n        call: pandium.getintegration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/integrations/{integration_id}/releases\n      name: listintegrationreleases\n      operations:\n      - method: GET\n        name: listintegrationreleases\n        description: Pandium List releases for an integration\n        call: pandium.listintegrationreleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/integrations/{integration_id}/releases/{release_id}\n      name: getintegrationrelease\n      operations:\n      - method: GET\n        name: getintegrationrelease\n        description: Pandium Get a single release\n        call: pandium.getintegrationrelease\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /v2/tenants\n      name: listtenants\n      operations:\n      - method: GET\n        name: listtenants\n        description: Pandium List all tenants\n        call: pandium.listtenants\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/tenants\n      name: createtenant\n      operations:\n      - method: POST\n        name: createtenant\n        description: Pandium Create a tenant\n        call: pandium.createtenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/tenants/{tenant_id}\n      name: gettenant\n      operations:\n      - method: GET\n        name: gettenant\n        description: Pandium Get a single tenant\n        call: pandium.gettenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/tenants/{tenant_id}\n      name: updatetenant\n      operations:\n      - method: PATCH\n        name: updatetenant\n        description:\
  \ Pandium Update a tenant\n        call: pandium.updatetenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/tenants/{tenant_id}/sync\n      name: triggertenantsync\n      operations:\n      - method: POST\n        name: triggertenantsync\n        description: Pandium Trigger a sync for a tenant\n        call: pandium.triggertenantsync\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/tenants/{tenant_id}/runs\n      name: listtenantruns\n      operations:\n      - method: GET\n        name: listtenantruns\n        description: Pandium List runs for a tenant\n        call: pandium.listtenantruns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/tenants/{tenant_id}/runs/{trigger_id}\n      name: getrunbytriggerid\n      operations:\n      - method: GET\n        name: getrunbytriggerid\n        description: Pandium Get run status by trigger ID\n        call: pandium.getrunbytriggerid\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/tenants/{tenant_id}/connectors/{connector_name}/call\n      name: proxyconnectorcall\n      operations:\n      - method: POST\n        name: proxyconnectorcall\n        description: Pandium Proxy a connector call\n        call: pandium.proxyconnectorcall\n        with:\n          connector_name: rest.connector_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/tenants/{tenant_id}/metadata\n      name: gettenantmetadata\n      operations:\n      - method: GET\n        name: gettenantmetadata\n        description: Pandium Get tenant metadata\n        call: pandium.gettenantmetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/tenants/{tenant_id}/metadata\n      name: updatetenantmetadata\n      operations:\n      - method: PATCH\n        name: updatetenantmetadata\n        description: Pandium Update tenant metadata\n\
  \        call: pandium.updatetenantmetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pandium-mcp\n    transport: http\n    description: MCP adapter for Pandium API for AI agent use.\n    tools:\n    - name: listintegrations\n      description: Pandium List all integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pandium.listintegrations\n      with:\n        skip: tools.skip\n        limit: tools.limit\n      inputParameters:\n      - name: skip\n        type: integer\n        description: Number of records to skip for pagination.\n      - name: limit\n        type: integer\n        description: Maximum number of records to return.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintegration\n      description: Pandium Get a single integration\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: pandium.getintegration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listintegrationreleases\n      description: Pandium List releases for an integration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pandium.listintegrationreleases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintegrationrelease\n      description: Pandium Get a single release\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pandium.getintegrationrelease\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtenants\n      description: Pandium List all tenants\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pandium.listtenants\n      with:\n        skip: tools.skip\n        limit: tools.limit\n        integration_id:\
  \ tools.integration_id\n      inputParameters:\n      - name: skip\n        type: integer\n        description: Number of records to skip for pagination.\n      - name: limit\n        type: integer\n        description: Maximum number of records to return.\n      - name: integration_id\n        type: integer\n        description: Filter tenants by integration ID.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtenant\n      description: Pandium Create a tenant\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pandium.createtenant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettenant\n      description: Pandium Get a single tenant\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pandium.gettenant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetenant\n      description:\
  \ Pandium Update a tenant\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pandium.updatetenant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: triggertenantsync\n      description: Pandium Trigger a sync for a tenant\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pandium.triggertenantsync\n      with:\n        mode: tools.mode\n      inputParameters:\n      - name: mode\n        type: string\n        description: The sync mode to use.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtenantruns\n      description: Pandium List runs for a tenant\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pandium.listtenantruns\n      with:\n        skip: tools.skip\n        limit: tools.limit\n      inputParameters:\n      - name: skip\n\
  \        type: integer\n        description: Number of records to skip for pagination.\n      - name: limit\n        type: integer\n        description: Maximum number of records to return.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrunbytriggerid\n      description: Pandium Get run status by trigger ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pandium.getrunbytriggerid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxyconnectorcall\n      description: Pandium Proxy a connector call\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pandium.proxyconnectorcall\n      with:\n        connector_name: tools.connector_name\n      inputParameters:\n      - name: connector_name\n        type: string\n        description: The name of the connector to call through.\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: gettenantmetadata\n      description: Pandium Get tenant metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pandium.gettenantmetadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetenantmetadata\n      description: Pandium Update tenant metadata\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pandium.updatetenantmetadata\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PANDIUM_TOKEN: PANDIUM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pandium/refs/heads/main/capabilities/pandium-capability.yaml
tags:
- Pandium
- API
tools:
- description: Pandium List all integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrations
- description: Pandium Get a single integration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintegration
- description: Pandium List releases for an integration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrationreleases
- description: Pandium Get a single release
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintegrationrelease
- description: Pandium List all tenants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtenants
- description: Pandium Create a tenant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtenant
- description: Pandium Get a single tenant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettenant
- description: Pandium Update a tenant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetenant
- description: Pandium Trigger a sync for a tenant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: triggertenantsync
- description: Pandium List runs for a tenant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtenantruns
- description: Pandium Get run status by trigger ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrunbytriggerid
- description: Pandium Proxy a connector call
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: proxyconnectorcall
- description: Pandium Get tenant metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettenantmetadata
- description: Pandium Update tenant metadata
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetenantmetadata
---
