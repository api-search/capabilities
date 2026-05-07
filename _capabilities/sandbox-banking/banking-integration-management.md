---
categories: []
consumed_apis: []
description: Banking integration workflow management capability using the Glyue Integration Gateway API. Provides unified access to integration workflow lifecycle management, service request adapter configuration, field mapping definition, and integration execution for financial institutions connecting core banking systems with fintech applications. Designed for integration engineers, bank operations teams, and fintech developers building connections between banking cores (Fiserv, Jack Henry, FIS) and loan origination systems, CRMs, and KYC/AML services.
layout: capability
name: Sandbox Banking Integration Management
operations:
- description: List all Glyue integration workflows.
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: Create a new integration workflow.
  method: POST
  name: create-integration
  path: /v1/integrations
- description: Get full details of an integration including service requests and field mappings.
  method: GET
  name: get-integration
  path: /v1/integrations/{integrationId}
- description: Update an existing integration workflow configuration.
  method: PUT
  name: update-integration
  path: /v1/integrations/{integrationId}
- description: Delete an integration workflow.
  method: DELETE
  name: delete-integration
  path: /v1/integrations/{integrationId}
- description: Execute an integration workflow with an input payload.
  method: POST
  name: run-integration
  path: /v1/integrations/{integrationId}/run
- description: List service request adapters in an integration.
  method: GET
  name: list-service-requests
  path: /v1/integrations/{integrationId}/service-requests
- description: Add a service request adapter step to an integration.
  method: POST
  name: create-service-request
  path: /v1/integrations/{integrationId}/service-requests
- description: List field mapping rules for an integration.
  method: GET
  name: list-field-mappings
  path: /v1/integrations/{integrationId}/field-mappings
- description: Create a field mapping rule for source-to-target data transformation.
  method: POST
  name: create-field-mapping
  path: /v1/integrations/{integrationId}/field-mappings
- description: List value mapping tables for enum translation between systems.
  method: GET
  name: list-value-mappings
  path: /v1/value-mappings
- description: Create a value mapping table.
  method: POST
  name: create-value-mapping
  path: /v1/value-mappings
- description: List integration run history with status, timestamps, and error details.
  method: GET
  name: list-run-history
  path: /v1/run-history
- description: List all Glyue adapters (Fiserv, Jack Henry, FIS, Salesforce, nCino, etc.).
  method: GET
  name: list-adapters
  path: /v1/adapters
personas: []
provider_name: Sandbox Banking
provider_slug: sandbox-banking
search_terms:
- list integrations
- delete an integration workflow.
- execute an integration workflow with an input payload.
- create field mapping
- get full details of an integration workflow including service requests, field mappings, and validation rules.
- create a field mapping rule that transforms a source field to a target field with optional python transformation.
- list value mapping tables for enum translation between systems.
- list run history
- create a new integration workflow.
- banking integration
- glyue
- delete integration
- run integration
- get full audit detail for a specific integration run including request body, response body, and service request execution log.
- add a service request adapter step to an integration workflow (e.g., fiserv createloan, jack henry posttransaction).
- credit unions
- list integration run history for audit and compliance review. filter by integration, status, or date range.
- integration execution endpoint.
- create service request
- list all glyue adapters (fiserv, jack henry, fis, salesforce, ncino, etc.).
- create integration
- create a value mapping table.
- list value mappings
- create a new glyue integration workflow connecting a source system to a target banking system.
- fintech
- get integration
- list field mapping rules for an integration showing source-to-target data transformation configuration.
- list service request adapter steps configured in an integration, showing the execution sequence.
- add a service request adapter step to an integration.
- field mapping
- integration workflow lifecycle management.
- execute a glyue integration workflow with an input payload. returns run id, status, and output from the target banking system.
- integration platform
- list service requests
- individual integration detail and management.
- integration run audit log for glba/ffiec compliance.
- financial services
- list adapters
- get run history
- ipaas
- update an existing integration workflow configuration.
- enumerated value translation tables.
- get full details of an integration including service requests and field mappings.
- create value mapping
- service request adapter configuration.
- source-to-target field mapping configuration.
- list field mapping rules for an integration.
- api integration
- open banking
- banking
- update integration
- list field mappings
- available core banking and fintech adapters.
- list all glyue integration workflows. use to discover available banking integrations.
- list service request adapters in an integration.
- sandbox banking
- list all glyue integration workflows.
- create a field mapping rule for source-to-target data transformation.
- list value mapping tables used for translating enumerated values between banking systems (e.g., loan type codes).
- list all available glyue adapters including core banking systems (fiserv, jack henry, fis) and fintech connectors.
- core banking
- list integration run history with status, timestamps, and error details.
slug: banking-integration-management
source_filename: banking-integration-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sandbox Banking Integration Management\n  description: Banking integration workflow management capability using the Glyue Integration Gateway API. Provides unified\n    access to integration workflow lifecycle management, service request adapter configuration, field mapping definition,\n    and integration execution for financial institutions connecting core banking systems with fintech applications. Designed\n    for integration engineers, bank operations teams, and fintech developers building connections between banking cores (Fiserv,\n    Jack Henry, FIS) and loan origination systems, CRMs, and KYC/AML services.\n  tags:\n  - Banking Integration\n  - Core Banking\n  - Field Mapping\n  - Financial Services\n  - Fintech\n  - Glyue\n  - Integration Platform\n  - iPaaS\n  - Open Banking\n  - Sandbox Banking\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GLYUE_API_TOKEN: GLYUE_API_TOKEN\ncapability:\n\
  \  consumes:\n  - type: http\n    namespace: glyue\n    baseUri: https://{tenant}.sandboxbanking.com/api\n    description: Glyue Integration Gateway REST API.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Token {{GLYUE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: integrations\n      path: /integrations\n      description: Integration workflow management.\n      operations:\n      - name: list-integrations\n        method: GET\n        description: List all integration workflows.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (active, inactive, draft, testing, deprecated).\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-integration\n        method: POST\n        description: Create a new integration workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            status: '{{tools.status}}'\n            integrationType: '{{tools.integrationType}}'\n            sourceSystem: '{{tools.sourceSystem}}'\n            targetSystem: '{{tools.targetSystem}}'\n    - name: integration-detail\n      path: /integrations/{integrationId}\n      description: Individual integration management.\n      operations:\n      - name: get-integration\n        method: GET\n        description: Get integration workflow details.\n        inputParameters:\n\
  \        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-integration\n        method: PUT\n        description: Update an integration workflow.\n        inputParameters:\n        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            status: '{{tools.status}}'\n      - name: delete-integration\n        method: DELETE\n        description: Delete an integration workflow.\n        inputParameters:\n        - name: integrationId\n          in:\
  \ path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integration-run\n      path: /integrations/{integrationId}/run\n      description: Integration execution.\n      operations:\n      - name: run-integration\n        method: POST\n        description: Execute an integration workflow with an input payload.\n        inputParameters:\n        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payload: '{{tools.payload}}'\n    - name: service-requests\n      path: /integrations/{integrationId}/service-requests\n      description:\
  \ Service request adapter management.\n      operations:\n      - name: list-service-requests\n        method: GET\n        description: List service request adapters in an integration.\n        inputParameters:\n        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service-request\n        method: POST\n        description: Add a service request adapter to an integration.\n        inputParameters:\n        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n\
  \            adapter: '{{tools.adapter}}'\n            operation: '{{tools.operation}}'\n    - name: field-mappings\n      path: /integrations/{integrationId}/field-mappings\n      description: Field mapping configuration.\n      operations:\n      - name: list-field-mappings\n        method: GET\n        description: List field mappings for an integration.\n        inputParameters:\n        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-field-mapping\n        method: POST\n        description: Create a field mapping rule.\n        inputParameters:\n        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: Integration identifier.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sourceField: '{{tools.sourceField}}'\n            targetField: '{{tools.targetField}}'\n            transform: '{{tools.transform}}'\n    - name: value-mappings\n      path: /value-mappings\n      description: Value mapping table management.\n      operations:\n      - name: list-value-mappings\n        method: GET\n        description: List value mapping tables.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-value-mapping\n        method: POST\n        description: Create a value mapping table.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            entries: '{{tools.entries}}'\n    - name: run-history\n      path: /run-history\n      description: Integration run audit log access.\n      operations:\n      - name: list-run-history\n        method: GET\n        description: List integration run history entries.\n        inputParameters:\n        - name: integration_id\n          in: query\n          type: string\n          required: false\n          description: Filter by integration ID.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by run status.\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date filter (ISO 8601).\n        - name: end_date\n          in: query\n          type: string\n          required:\
  \ false\n          description: End date filter (ISO 8601).\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-run-history\n        method: GET\n        description: Get full audit detail for a specific integration run.\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n          description: Run identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: adapters\n      path: /adapters\n      description: Available banking system and fintech adapter listing.\n      operations:\n      - name: list-adapters\n        method: GET\n        description: List all available Glyue adapters.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: banking-integration-api\n    description: Unified REST API for Sandbox Banking Glyue integration workflow management.\n    resources:\n    - path: /v1/integrations\n      name: integrations\n      description: Integration workflow lifecycle management.\n      operations:\n      - method: GET\n        name: list-integrations\n        description: List all Glyue integration workflows.\n        call: glyue.list-integrations\n        with:\n          status: rest.status\n          page: rest.page\n          page_size: rest.page_size\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-integration\n        description: Create a new integration workflow.\n        call: glyue.create-integration\n        with:\n          name: rest.name\n          description: rest.description\n\
  \          status: rest.status\n          integrationType: rest.integrationType\n          sourceSystem: rest.sourceSystem\n          targetSystem: rest.targetSystem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integrations/{integrationId}\n      name: integration-detail\n      description: Individual integration detail and management.\n      operations:\n      - method: GET\n        name: get-integration\n        description: Get full details of an integration including service requests and field mappings.\n        call: glyue.get-integration\n        with:\n          integrationId: rest.integrationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-integration\n        description: Update an existing integration workflow configuration.\n        call: glyue.update-integration\n        with:\n          integrationId: rest.integrationId\n          name: rest.name\n         \
  \ status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-integration\n        description: Delete an integration workflow.\n        call: glyue.delete-integration\n        with:\n          integrationId: rest.integrationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integrations/{integrationId}/run\n      name: integration-run\n      description: Integration execution endpoint.\n      operations:\n      - method: POST\n        name: run-integration\n        description: Execute an integration workflow with an input payload.\n        call: glyue.run-integration\n        with:\n          integrationId: rest.integrationId\n          payload: rest.payload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integrations/{integrationId}/service-requests\n      name: service-requests\n      description: Service request adapter\
  \ configuration.\n      operations:\n      - method: GET\n        name: list-service-requests\n        description: List service request adapters in an integration.\n        call: glyue.list-service-requests\n        with:\n          integrationId: rest.integrationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-service-request\n        description: Add a service request adapter step to an integration.\n        call: glyue.create-service-request\n        with:\n          integrationId: rest.integrationId\n          name: rest.name\n          adapter: rest.adapter\n          operation: rest.operation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integrations/{integrationId}/field-mappings\n      name: field-mappings\n      description: Source-to-target field mapping configuration.\n      operations:\n      - method: GET\n        name: list-field-mappings\n        description:\
  \ List field mapping rules for an integration.\n        call: glyue.list-field-mappings\n        with:\n          integrationId: rest.integrationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-field-mapping\n        description: Create a field mapping rule for source-to-target data transformation.\n        call: glyue.create-field-mapping\n        with:\n          integrationId: rest.integrationId\n          sourceField: rest.sourceField\n          targetField: rest.targetField\n          transform: rest.transform\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/value-mappings\n      name: value-mappings\n      description: Enumerated value translation tables.\n      operations:\n      - method: GET\n        name: list-value-mappings\n        description: List value mapping tables for enum translation between systems.\n        call: glyue.list-value-mappings\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-value-mapping\n        description: Create a value mapping table.\n        call: glyue.create-value-mapping\n        with:\n          name: rest.name\n          description: rest.description\n          entries: rest.entries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/run-history\n      name: run-history\n      description: Integration run audit log for GLBA/FFIEC compliance.\n      operations:\n      - method: GET\n        name: list-run-history\n        description: List integration run history with status, timestamps, and error details.\n        call: glyue.list-run-history\n        with:\n          integration_id: rest.integration_id\n          status: rest.status\n          start_date: rest.start_date\n          end_date: rest.end_date\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/adapters\n      name: adapters\n      description: Available core banking and fintech adapters.\n      operations:\n      - method: GET\n        name: list-adapters\n        description: List all Glyue adapters (Fiserv, Jack Henry, FIS, Salesforce, nCino, etc.).\n        call: glyue.list-adapters\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: banking-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted Sandbox Banking Glyue integration management and execution.\n    tools:\n    - name: list-integrations\n      description: List all Glyue integration workflows. Use to discover available banking integrations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: glyue.list-integrations\n      with:\n        status: tools.status\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-integration\n      description:\
  \ Get full details of an integration workflow including service requests, field mappings, and validation\n        rules.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: glyue.get-integration\n      with:\n        integrationId: tools.integrationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-integration\n      description: Create a new Glyue integration workflow connecting a source system to a target banking system.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: glyue.create-integration\n      with:\n        name: tools.name\n        description: tools.description\n        status: tools.status\n        integrationType: tools.integrationType\n        sourceSystem: tools.sourceSystem\n        targetSystem: tools.targetSystem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-integration\n      description: Execute a Glyue integration\
  \ workflow with an input payload. Returns run ID, status, and output from the\n        target banking system.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: glyue.run-integration\n      with:\n        integrationId: tools.integrationId\n        payload: tools.payload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-requests\n      description: List service request adapter steps configured in an integration, showing the execution sequence.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: glyue.list-service-requests\n      with:\n        integrationId: tools.integrationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-service-request\n      description: Add a service request adapter step to an integration workflow (e.g., Fiserv createLoan, Jack Henry postTransaction).\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: glyue.create-service-request\n      with:\n        integrationId: tools.integrationId\n        name: tools.name\n        adapter: tools.adapter\n        operation: tools.operation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-field-mappings\n      description: List field mapping rules for an integration showing source-to-target data transformation configuration.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: glyue.list-field-mappings\n      with:\n        integrationId: tools.integrationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-field-mapping\n      description: Create a field mapping rule that transforms a source field to a target field with optional Python transformation.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: glyue.create-field-mapping\n      with:\n  \
  \      integrationId: tools.integrationId\n        sourceField: tools.sourceField\n        targetField: tools.targetField\n        transform: tools.transform\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-run-history\n      description: List integration run history for audit and compliance review. Filter by integration, status, or date range.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: glyue.list-run-history\n      with:\n        integration_id: tools.integration_id\n        status: tools.status\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-run-history\n      description: Get full audit detail for a specific integration run including request body, response body, and service\n        request execution log.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: glyue.get-run-history\n \
  \     with:\n        runId: tools.runId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-adapters\n      description: List all available Glyue adapters including core banking systems (Fiserv, Jack Henry, FIS) and fintech\n        connectors.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: glyue.list-adapters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-value-mappings\n      description: List value mapping tables used for translating enumerated values between banking systems (e.g., loan type\n        codes).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: glyue.list-value-mappings\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sandbox-banking/refs/heads/main/capabilities/banking-integration-management.yaml
tags:
- Banking Integration
- Core Banking
- Field Mapping
- Financial Services
- Fintech
- Glyue
- Integration Platform
- iPaaS
- Open Banking
- Sandbox Banking
tools:
- description: List all Glyue integration workflows. Use to discover available banking integrations.
  hints:
    openWorld: true
    readOnly: true
  name: list-integrations
- description: Get full details of an integration workflow including service requests, field mappings, and validation rules.
  hints:
    openWorld: false
    readOnly: true
  name: get-integration
- description: Create a new Glyue integration workflow connecting a source system to a target banking system.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-integration
- description: Execute a Glyue integration workflow with an input payload. Returns run ID, status, and output from the target banking system.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: run-integration
- description: List service request adapter steps configured in an integration, showing the execution sequence.
  hints:
    openWorld: false
    readOnly: true
  name: list-service-requests
- description: Add a service request adapter step to an integration workflow (e.g., Fiserv createLoan, Jack Henry postTransaction).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-service-request
- description: List field mapping rules for an integration showing source-to-target data transformation configuration.
  hints:
    openWorld: false
    readOnly: true
  name: list-field-mappings
- description: Create a field mapping rule that transforms a source field to a target field with optional Python transformation.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-field-mapping
- description: List integration run history for audit and compliance review. Filter by integration, status, or date range.
  hints:
    openWorld: false
    readOnly: true
  name: list-run-history
- description: Get full audit detail for a specific integration run including request body, response body, and service request execution log.
  hints:
    openWorld: false
    readOnly: true
  name: get-run-history
- description: List all available Glyue adapters including core banking systems (Fiserv, Jack Henry, FIS) and fintech connectors.
  hints:
    openWorld: true
    readOnly: true
  name: list-adapters
- description: List value mapping tables used for translating enumerated values between banking systems (e.g., loan type codes).
  hints:
    openWorld: false
    readOnly: true
  name: list-value-mappings
---
