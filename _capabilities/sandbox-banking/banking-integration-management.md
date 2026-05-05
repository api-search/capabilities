---
categories: []
consumed_apis:
- glyue
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
- update an existing integration workflow configuration.
- list run history
- available core banking and fintech adapters.
- core banking
- create integration
- list all glyue integration workflows. use to discover available banking integrations.
- create a new glyue integration workflow connecting a source system to a target banking system.
- glyue
- ipaas
- enumerated value translation tables.
- list value mappings
- fintech
- list service requests
- list value mapping tables for enum translation between systems.
- list adapters
- get integration
- field mapping
- open banking
- list service request adapters in an integration.
- create service request
- banking integration
- get full details of an integration including service requests and field mappings.
- execute a glyue integration workflow with an input payload. returns run id, status, and output from the target banking system.
- credit unions
- list integration run history for audit and compliance review. filter by integration, status, or date range.
- api integration
- delete integration
- create a value mapping table.
- add a service request adapter step to an integration.
- list value mapping tables used for translating enumerated values between banking systems (e.g., loan type codes).
- run integration
- create field mapping
- list field mapping rules for an integration showing source-to-target data transformation configuration.
- individual integration detail and management.
- service request adapter configuration.
- sandbox banking
- get full audit detail for a specific integration run including request body, response body, and service request execution log.
- get run history
- banking
- create value mapping
- list all glyue integration workflows.
- list integrations
- list all available glyue adapters including core banking systems (fiserv, jack henry, fis) and fintech connectors.
- add a service request adapter step to an integration workflow (e.g., fiserv createloan, jack henry posttransaction).
- execute an integration workflow with an input payload.
- list field mapping rules for an integration.
- list integration run history with status, timestamps, and error details.
- create a new integration workflow.
- integration execution endpoint.
- source-to-target field mapping configuration.
- update integration
- integration run audit log for glba/ffiec compliance.
- create a field mapping rule that transforms a source field to a target field with optional python transformation.
- list all glyue adapters (fiserv, jack henry, fis, salesforce, ncino, etc.).
- integration platform
- list service request adapter steps configured in an integration, showing the execution sequence.
- create a field mapping rule for source-to-target data transformation.
- financial services
- integration workflow lifecycle management.
- list field mappings
- delete an integration workflow.
- get full details of an integration workflow including service requests, field mappings, and validation rules.
slug: banking-integration-management
source_filename: banking-integration-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sandbox Banking Integration Management\"\n  description: >-\n    Banking integration workflow management capability using the Glyue Integration\n    Gateway API. Provides unified access to integration workflow lifecycle management,\n    service request adapter configuration, field mapping definition, and integration\n    execution for financial institutions connecting core banking systems with fintech\n    applications. Designed for integration engineers, bank operations teams, and fintech\n    developers building connections between banking cores (Fiserv, Jack Henry, FIS) and\n    loan origination systems, CRMs, and KYC/AML services.\n  tags:\n    - Banking Integration\n    - Core Banking\n    - Field Mapping\n    - Financial Services\n    - Fintech\n    - Glyue\n    - Integration Platform\n    - iPaaS\n    - Open Banking\n    - Sandbox Banking\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n\
  \    keys:\n      GLYUE_API_TOKEN: GLYUE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: glyue\n      location: ./shared/glyue.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: banking-integration-api\n      description: \"Unified REST API for Sandbox Banking Glyue integration workflow management.\"\n      resources:\n        - path: /v1/integrations\n          name: integrations\n          description: \"Integration workflow lifecycle management.\"\n          operations:\n            - method: GET\n              name: list-integrations\n              description: \"List all Glyue integration workflows.\"\n              call: \"glyue.list-integrations\"\n              with:\n                status: \"rest.status\"\n                page: \"rest.page\"\n                page_size: \"rest.page_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-integration\n\
  \              description: \"Create a new integration workflow.\"\n              call: \"glyue.create-integration\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n                status: \"rest.status\"\n                integrationType: \"rest.integrationType\"\n                sourceSystem: \"rest.sourceSystem\"\n                targetSystem: \"rest.targetSystem\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/integrations/{integrationId}\n          name: integration-detail\n          description: \"Individual integration detail and management.\"\n          operations:\n            - method: GET\n              name: get-integration\n              description: \"Get full details of an integration including service requests and field mappings.\"\n              call: \"glyue.get-integration\"\n              with:\n                integrationId: \"rest.integrationId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-integration\n              description: \"Update an existing integration workflow configuration.\"\n              call: \"glyue.update-integration\"\n              with:\n                integrationId: \"rest.integrationId\"\n                name: \"rest.name\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-integration\n              description: \"Delete an integration workflow.\"\n              call: \"glyue.delete-integration\"\n              with:\n                integrationId: \"rest.integrationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/integrations/{integrationId}/run\n          name: integration-run\n\
  \          description: \"Integration execution endpoint.\"\n          operations:\n            - method: POST\n              name: run-integration\n              description: \"Execute an integration workflow with an input payload.\"\n              call: \"glyue.run-integration\"\n              with:\n                integrationId: \"rest.integrationId\"\n                payload: \"rest.payload\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/integrations/{integrationId}/service-requests\n          name: service-requests\n          description: \"Service request adapter configuration.\"\n          operations:\n            - method: GET\n              name: list-service-requests\n              description: \"List service request adapters in an integration.\"\n              call: \"glyue.list-service-requests\"\n              with:\n                integrationId: \"rest.integrationId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-service-request\n              description: \"Add a service request adapter step to an integration.\"\n              call: \"glyue.create-service-request\"\n              with:\n                integrationId: \"rest.integrationId\"\n                name: \"rest.name\"\n                adapter: \"rest.adapter\"\n                operation: \"rest.operation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/integrations/{integrationId}/field-mappings\n          name: field-mappings\n          description: \"Source-to-target field mapping configuration.\"\n          operations:\n            - method: GET\n              name: list-field-mappings\n              description: \"List field mapping rules for an integration.\"\n              call: \"glyue.list-field-mappings\"\n              with:\n     \
  \           integrationId: \"rest.integrationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-field-mapping\n              description: \"Create a field mapping rule for source-to-target data transformation.\"\n              call: \"glyue.create-field-mapping\"\n              with:\n                integrationId: \"rest.integrationId\"\n                sourceField: \"rest.sourceField\"\n                targetField: \"rest.targetField\"\n                transform: \"rest.transform\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/value-mappings\n          name: value-mappings\n          description: \"Enumerated value translation tables.\"\n          operations:\n            - method: GET\n              name: list-value-mappings\n              description: \"List value mapping tables for enum translation\
  \ between systems.\"\n              call: \"glyue.list-value-mappings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-value-mapping\n              description: \"Create a value mapping table.\"\n              call: \"glyue.create-value-mapping\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n                entries: \"rest.entries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/run-history\n          name: run-history\n          description: \"Integration run audit log for GLBA/FFIEC compliance.\"\n          operations:\n            - method: GET\n              name: list-run-history\n              description: \"List integration run history with status, timestamps, and error details.\"\n              call: \"glyue.list-run-history\"\n      \
  \        with:\n                integration_id: \"rest.integration_id\"\n                status: \"rest.status\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/adapters\n          name: adapters\n          description: \"Available core banking and fintech adapters.\"\n          operations:\n            - method: GET\n              name: list-adapters\n              description: \"List all Glyue adapters (Fiserv, Jack Henry, FIS, Salesforce, nCino, etc.).\"\n              call: \"glyue.list-adapters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: banking-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Sandbox Banking Glyue integration management\
  \ and execution.\"\n      tools:\n        - name: list-integrations\n          description: \"List all Glyue integration workflows. Use to discover available banking integrations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"glyue.list-integrations\"\n          with:\n            status: \"tools.status\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-integration\n          description: \"Get full details of an integration workflow including service requests, field mappings, and validation rules.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"glyue.get-integration\"\n          with:\n            integrationId: \"tools.integrationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-integration\n          description: \"Create a new\
  \ Glyue integration workflow connecting a source system to a target banking system.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"glyue.create-integration\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            status: \"tools.status\"\n            integrationType: \"tools.integrationType\"\n            sourceSystem: \"tools.sourceSystem\"\n            targetSystem: \"tools.targetSystem\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-integration\n          description: \"Execute a Glyue integration workflow with an input payload. Returns run ID, status, and output from the target banking system.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"glyue.run-integration\"\n          with:\n            integrationId:\
  \ \"tools.integrationId\"\n            payload: \"tools.payload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-service-requests\n          description: \"List service request adapter steps configured in an integration, showing the execution sequence.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"glyue.list-service-requests\"\n          with:\n            integrationId: \"tools.integrationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-service-request\n          description: \"Add a service request adapter step to an integration workflow (e.g., Fiserv createLoan, Jack Henry postTransaction).\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"glyue.create-service-request\"\n          with:\n            integrationId: \"tools.integrationId\"\
  \n            name: \"tools.name\"\n            adapter: \"tools.adapter\"\n            operation: \"tools.operation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-field-mappings\n          description: \"List field mapping rules for an integration showing source-to-target data transformation configuration.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"glyue.list-field-mappings\"\n          with:\n            integrationId: \"tools.integrationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-field-mapping\n          description: \"Create a field mapping rule that transforms a source field to a target field with optional Python transformation.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"glyue.create-field-mapping\"\n    \
  \      with:\n            integrationId: \"tools.integrationId\"\n            sourceField: \"tools.sourceField\"\n            targetField: \"tools.targetField\"\n            transform: \"tools.transform\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-run-history\n          description: \"List integration run history for audit and compliance review. Filter by integration, status, or date range.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"glyue.list-run-history\"\n          with:\n            integration_id: \"tools.integration_id\"\n            status: \"tools.status\"\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-run-history\n          description: \"Get full audit detail for a specific integration run including request body,\
  \ response body, and service request execution log.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"glyue.get-run-history\"\n          with:\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-adapters\n          description: \"List all available Glyue adapters including core banking systems (Fiserv, Jack Henry, FIS) and fintech connectors.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"glyue.list-adapters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-value-mappings\n          description: \"List value mapping tables used for translating enumerated values between banking systems (e.g., loan type codes).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"glyue.list-value-mappings\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
