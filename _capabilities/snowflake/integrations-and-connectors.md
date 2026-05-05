---
api_specs:
- filename: api-integration.yaml
  format: yaml
  label: snowflake-api-integration
  slug: snowflake-api-integration
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/api-integration.yaml
- filename: catalog-integration.yaml
  format: yaml
  label: snowflake-catalog-integration
  slug: snowflake-catalog-integration
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/catalog-integration.yaml
- filename: notification-integration.yaml
  format: yaml
  label: snowflake-notification-integration
  slug: snowflake-notification-integration
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/notification-integration.yaml
categories: []
consumed_apis:
- snowflake-api-integration
- snowflake-catalog-integration
- snowflake-notification-integration
description: Unified workflow for managing API integrations, catalog integrations, and notification integrations. Used by Platform Engineers and Data Architects to connect Snowflake with external services, catalogs, and notification systems.
layout: capability
name: Snowflake Integrations and Connectors
operations:
- description: List API integrations
  method: GET
  name: list-api-integrations
  path: /v1/api-integrations
- description: Create an API integration
  method: POST
  name: create-api-integration
  path: /v1/api-integrations
- description: List catalog integrations
  method: GET
  name: list-catalog-integrations
  path: /v1/catalog-integrations
- description: Create a catalog integration
  method: POST
  name: create-catalog-integration
  path: /v1/catalog-integrations
- description: List notification integrations
  method: GET
  name: list-notification-integrations
  path: /v1/notification-integrations
- description: Create a notification integration
  method: POST
  name: create-notification-integration
  path: /v1/notification-integrations
personas: []
provider_name: Snowflake
provider_slug: snowflake
search_terms:
- create api integration
- data warehousing
- list api integrations
- delete an api integration
- list notification integrations
- delete a catalog integration
- create a notification integration
- delete api integration
- delete notification integration
- create notification integration
- api integration management
- fetch notification integration
- delete a notification integration
- fetch api integration details
- connectors
- snowflake
- database
- create catalog integration
- fetch notification integration details
- integrations
- create an api integration
- create a catalog integration
- notification integration management
- data lakes
- delete catalog integration
- fetch catalog integration details
- fetch catalog integration
- data sharing
- sql
- fetch api integration
- list catalog integrations
- catalog integration management
slug: integrations-and-connectors
source_filename: integrations-and-connectors.yaml
source_heading: Capability Spec
source_yaml: "# Snowflake Integrations and Connectors — Applied Capability\n#\n# Composition: imports three source HTTP capabilities (api-integration,\n# catalog-integration, notification-integration) and unifies them into a\n# single integration-management surface for Snowflake.\n#\n# Triple exposure (one capability, three channels):\n#   1. REST       — conventional HTTP clients (port 8085)\n#   2. MCP/HTTP   — remote MCP clients such as hosted AI agents (port 9085)\n#   3. MCP/stdio  — local MCP clients such as Claude Desktop, IDE agents\n#   4. Skill      — Agent Skills exposure for agent-compatible metadata\n#\n# Aligned with Naftiko Framework v1.0.0-alpha1 spec patterns from\n# Guide - Use Cases (#1 AI integration, #2 Rightsize AI context,\n# #8 Capability-first context engineering).\n\nnaftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Integrations and Connectors\"\n  description: \"Unified workflow for managing API integrations, catalog integrations, and notification integrations.\
  \ Used by Platform Engineers and Data Architects to connect Snowflake with external services, catalogs, and notification systems.\"\n  tags:\n    - Snowflake\n    - Integrations\n    - Connectors\n  created: \"2026-04-18\"\n  modified: \"2026-04-23\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-api-integration\n      location: ./shared/api-integration.yaml\n    - import: snowflake-catalog-integration\n      location: ./shared/catalog-integration.yaml\n    - import: snowflake-notification-integration\n      location: ./shared/notification-integration.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: snowflake-integrations-api\n      description: \"Unified REST API for Snowflake integration management.\"\n      resources:\n        - path: /v1/api-integrations\n          name: api-integrations\n          description: \"\
  API integration management\"\n          operations:\n            - method: GET\n              name: list-api-integrations\n              description: \"List API integrations\"\n              call: \"snowflake-api-integration.list-api-integrations\"\n              hints:\n                readOnly: true\n                destructive: false\n                idempotent: true\n              outputParameters:\n                - name: integrations\n                  type: array\n                  description: \"Array of API integration objects\"\n                  mapping: \"$.data\"\n                - name: totalCount\n                  type: integer\n                  description: \"Count of returned integrations\"\n                  mapping: \"$.data.length\"\n            - method: POST\n              name: create-api-integration\n              description: \"Create an API integration\"\n              call: \"snowflake-api-integration.create-api-integration\"\n              hints:\n       \
  \         readOnly: false\n                destructive: false\n                idempotent: false\n              inputParameters:\n                - name: name\n                  type: string\n                  description: \"Unique name of the API integration\"\n                  required: true\n                  mapping: \"$.body.name\"\n                - name: api_provider\n                  type: string\n                  description: \"API provider (e.g. aws_api_gateway, azure_api_management, google_api_gateway)\"\n                  required: true\n                  mapping: \"$.body.api_provider\"\n                - name: api_allowed_prefixes\n                  type: array\n                  description: \"Allowed endpoint prefixes for the external function\"\n                  required: true\n                  mapping: \"$.body.api_allowed_prefixes\"\n                - name: enabled\n                  type: boolean\n                  description: \"Whether the integration is enabled\
  \ on create\"\n                  required: false\n                  mapping: \"$.body.enabled\"\n              outputParameters:\n                - name: integrationName\n                  type: string\n                  description: \"Name of the created integration\"\n                  mapping: \"$.name\"\n                - name: status\n                  type: string\n                  description: \"Operation status\"\n                  mapping: \"$.status\"\n        - path: /v1/catalog-integrations\n          name: catalog-integrations\n          description: \"Catalog integration management\"\n          operations:\n            - method: GET\n              name: list-catalog-integrations\n              description: \"List catalog integrations\"\n              call: \"snowflake-catalog-integration.list-catalog-integrations\"\n              hints:\n                readOnly: true\n                destructive: false\n                idempotent: true\n              outputParameters:\n\
  \                - name: integrations\n                  type: array\n                  description: \"Array of catalog integration objects\"\n                  mapping: \"$.data\"\n                - name: totalCount\n                  type: integer\n                  description: \"Count of returned integrations\"\n                  mapping: \"$.data.length\"\n            - method: POST\n              name: create-catalog-integration\n              description: \"Create a catalog integration\"\n              call: \"snowflake-catalog-integration.create-catalog-integration\"\n              hints:\n                readOnly: false\n                destructive: false\n                idempotent: false\n              inputParameters:\n                - name: name\n                  type: string\n                  description: \"Unique name of the catalog integration\"\n                  required: true\n                  mapping: \"$.body.name\"\n                - name: catalog_source\n   \
  \               type: string\n                  description: \"Catalog source (e.g. GLUE, OBJECT_STORE, POLARIS)\"\n                  required: true\n                  mapping: \"$.body.catalog_source\"\n                - name: table_format\n                  type: string\n                  description: \"Table format (e.g. ICEBERG, DELTA)\"\n                  required: true\n                  mapping: \"$.body.table_format\"\n                - name: enabled\n                  type: boolean\n                  description: \"Whether the integration is enabled on create\"\n                  required: false\n                  mapping: \"$.body.enabled\"\n              outputParameters:\n                - name: integrationName\n                  type: string\n                  description: \"Name of the created integration\"\n                  mapping: \"$.name\"\n                - name: status\n                  type: string\n                  description: \"Operation status\"\n         \
  \         mapping: \"$.status\"\n        - path: /v1/notification-integrations\n          name: notification-integrations\n          description: \"Notification integration management\"\n          operations:\n            - method: GET\n              name: list-notification-integrations\n              description: \"List notification integrations\"\n              call: \"snowflake-notification-integration.list-notification-integrations\"\n              hints:\n                readOnly: true\n                destructive: false\n                idempotent: true\n              outputParameters:\n                - name: integrations\n                  type: array\n                  description: \"Array of notification integration objects\"\n                  mapping: \"$.data\"\n                - name: totalCount\n                  type: integer\n                  description: \"Count of returned integrations\"\n                  mapping: \"$.data.length\"\n            - method: POST\n   \
  \           name: create-notification-integration\n              description: \"Create a notification integration\"\n              call: \"snowflake-notification-integration.create-notification-integration\"\n              hints:\n                readOnly: false\n                destructive: false\n                idempotent: false\n              inputParameters:\n                - name: name\n                  type: string\n                  description: \"Unique name of the notification integration\"\n                  required: true\n                  mapping: \"$.body.name\"\n                - name: notification_provider\n                  type: string\n                  description: \"Notification provider (e.g. AWS_SNS, AZURE_EVENT_GRID, GCP_PUBSUB)\"\n                  required: true\n                  mapping: \"$.body.notification_provider\"\n                - name: direction\n                  type: string\n                  description: \"Notification direction (INBOUND or OUTBOUND)\"\
  \n                  required: true\n                  mapping: \"$.body.direction\"\n                - name: enabled\n                  type: boolean\n                  description: \"Whether the integration is enabled on create\"\n                  required: false\n                  mapping: \"$.body.enabled\"\n              outputParameters:\n                - name: integrationName\n                  type: string\n                  description: \"Name of the created integration\"\n                  mapping: \"$.name\"\n                - name: status\n                  type: string\n                  description: \"Operation status\"\n                  mapping: \"$.status\"\n\n    - type: mcp\n      port: 9085\n      namespace: snowflake-integrations-mcp\n      transport: http\n      description: \"MCP server (Streaming HTTP) for AI-assisted Snowflake integration management.\"\n      tools:\n        - name: list-api-integrations\n          description: \"List API integrations\"\n    \
  \      hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-api-integration.list-api-integrations\"\n          outputParameters:\n            - name: integrations\n              type: array\n              description: \"Array of API integration objects\"\n              mapping: \"$.data\"\n            - name: totalCount\n              type: integer\n              description: \"Count of returned integrations\"\n              mapping: \"$.data.length\"\n        - name: create-api-integration\n          description: \"Create an API integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-api-integration.create-api-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Unique name of the API integration\"\n              required: true\n              mapping:\
  \ \"$.body.name\"\n            - name: api_provider\n              type: string\n              description: \"API provider (e.g. aws_api_gateway, azure_api_management, google_api_gateway)\"\n              required: true\n              mapping: \"$.body.api_provider\"\n            - name: api_allowed_prefixes\n              type: array\n              description: \"Allowed endpoint prefixes for the external function\"\n              required: true\n              mapping: \"$.body.api_allowed_prefixes\"\n            - name: enabled\n              type: boolean\n              description: \"Whether the integration is enabled on create\"\n              required: false\n              mapping: \"$.body.enabled\"\n          outputParameters:\n            - name: integrationName\n              type: string\n              description: \"Name of the created integration\"\n              mapping: \"$.name\"\n            - name: status\n              type: string\n              description: \"Operation\
  \ status\"\n              mapping: \"$.status\"\n        - name: fetch-api-integration\n          description: \"Fetch API integration details\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-api-integration.fetch-api-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the API integration to fetch\"\n              required: true\n              mapping: \"$.path.name\"\n          outputParameters:\n            - name: integration\n              type: object\n              description: \"Full API integration record\"\n              mapping: \"$.\"\n        - name: delete-api-integration\n          description: \"Delete an API integration\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snowflake-api-integration.delete-api-integration\"\n  \
  \        inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the API integration to delete\"\n              required: true\n              mapping: \"$.path.name\"\n          outputParameters:\n            - name: status\n              type: string\n              description: \"Delete operation status\"\n              mapping: \"$.status\"\n        - name: list-catalog-integrations\n          description: \"List catalog integrations\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-catalog-integration.list-catalog-integrations\"\n          outputParameters:\n            - name: integrations\n              type: array\n              description: \"Array of catalog integration objects\"\n              mapping: \"$.data\"\n            - name: totalCount\n              type: integer\n              description: \"Count of returned integrations\"\n\
  \              mapping: \"$.data.length\"\n        - name: create-catalog-integration\n          description: \"Create a catalog integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-catalog-integration.create-catalog-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Unique name of the catalog integration\"\n              required: true\n              mapping: \"$.body.name\"\n            - name: catalog_source\n              type: string\n              description: \"Catalog source (e.g. GLUE, OBJECT_STORE, POLARIS)\"\n              required: true\n              mapping: \"$.body.catalog_source\"\n            - name: table_format\n              type: string\n              description: \"Table format (e.g. ICEBERG, DELTA)\"\n              required: true\n              mapping: \"$.body.table_format\"\n           \
  \ - name: enabled\n              type: boolean\n              description: \"Whether the integration is enabled on create\"\n              required: false\n              mapping: \"$.body.enabled\"\n          outputParameters:\n            - name: integrationName\n              type: string\n              description: \"Name of the created integration\"\n              mapping: \"$.name\"\n            - name: status\n              type: string\n              description: \"Operation status\"\n              mapping: \"$.status\"\n        - name: fetch-catalog-integration\n          description: \"Fetch catalog integration details\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-catalog-integration.fetch-catalog-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the catalog integration to fetch\"\n              required:\
  \ true\n              mapping: \"$.path.name\"\n          outputParameters:\n            - name: integration\n              type: object\n              description: \"Full catalog integration record\"\n              mapping: \"$.\"\n        - name: delete-catalog-integration\n          description: \"Delete a catalog integration\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snowflake-catalog-integration.delete-catalog-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the catalog integration to delete\"\n              required: true\n              mapping: \"$.path.name\"\n          outputParameters:\n            - name: status\n              type: string\n              description: \"Delete operation status\"\n              mapping: \"$.status\"\n        - name: list-notification-integrations\n          description: \"List\
  \ notification integrations\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-notification-integration.list-notification-integrations\"\n          outputParameters:\n            - name: integrations\n              type: array\n              description: \"Array of notification integration objects\"\n              mapping: \"$.data\"\n            - name: totalCount\n              type: integer\n              description: \"Count of returned integrations\"\n              mapping: \"$.data.length\"\n        - name: create-notification-integration\n          description: \"Create a notification integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-notification-integration.create-notification-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description:\
  \ \"Unique name of the notification integration\"\n              required: true\n              mapping: \"$.body.name\"\n            - name: notification_provider\n              type: string\n              description: \"Notification provider (e.g. AWS_SNS, AZURE_EVENT_GRID, GCP_PUBSUB)\"\n              required: true\n              mapping: \"$.body.notification_provider\"\n            - name: direction\n              type: string\n              description: \"Notification direction (INBOUND or OUTBOUND)\"\n              required: true\n              mapping: \"$.body.direction\"\n            - name: enabled\n              type: boolean\n              description: \"Whether the integration is enabled on create\"\n              required: false\n              mapping: \"$.body.enabled\"\n          outputParameters:\n            - name: integrationName\n              type: string\n              description: \"Name of the created integration\"\n              mapping: \"$.name\"\n        \
  \    - name: status\n              type: string\n              description: \"Operation status\"\n              mapping: \"$.status\"\n        - name: fetch-notification-integration\n          description: \"Fetch notification integration details\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-notification-integration.fetch-notification-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the notification integration to fetch\"\n              required: true\n              mapping: \"$.path.name\"\n          outputParameters:\n            - name: integration\n              type: object\n              description: \"Full notification integration record\"\n              mapping: \"$.\"\n        - name: delete-notification-integration\n          description: \"Delete a notification integration\"\n          hints:\n     \
  \       readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snowflake-notification-integration.delete-notification-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the notification integration to delete\"\n              required: true\n              mapping: \"$.path.name\"\n          outputParameters:\n            - name: status\n              type: string\n              description: \"Delete operation status\"\n              mapping: \"$.status\"\n\n    - type: mcp\n      namespace: snowflake-integrations-mcp-stdio\n      transport: stdio\n      description: \"MCP server (stdio transport) for local AI clients such as Claude Desktop and IDE agents.\"\n      tools:\n        - name: list-api-integrations\n          description: \"List API integrations\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n\
  \          call: \"snowflake-api-integration.list-api-integrations\"\n        - name: create-api-integration\n          description: \"Create an API integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-api-integration.create-api-integration\"\n        - name: fetch-api-integration\n          description: \"Fetch API integration details\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-api-integration.fetch-api-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the API integration to fetch\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: delete-api-integration\n          description: \"Delete an API integration\"\n          hints:\n            readOnly: false\n            destructive:\
  \ true\n            idempotent: true\n          call: \"snowflake-api-integration.delete-api-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the API integration to delete\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: list-catalog-integrations\n          description: \"List catalog integrations\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-catalog-integration.list-catalog-integrations\"\n        - name: create-catalog-integration\n          description: \"Create a catalog integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-catalog-integration.create-catalog-integration\"\n        - name: fetch-catalog-integration\n          description: \"Fetch catalog integration details\"\
  \n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-catalog-integration.fetch-catalog-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the catalog integration to fetch\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: delete-catalog-integration\n          description: \"Delete a catalog integration\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snowflake-catalog-integration.delete-catalog-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the catalog integration to delete\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: list-notification-integrations\n          description: \"List\
  \ notification integrations\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-notification-integration.list-notification-integrations\"\n        - name: create-notification-integration\n          description: \"Create a notification integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-notification-integration.create-notification-integration\"\n        - name: fetch-notification-integration\n          description: \"Fetch notification integration details\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-notification-integration.fetch-notification-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the notification integration to fetch\"\
  \n              required: true\n              mapping: \"$.path.name\"\n        - name: delete-notification-integration\n          description: \"Delete a notification integration\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snowflake-notification-integration.delete-notification-integration\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the notification integration to delete\"\n              required: true\n              mapping: \"$.path.name\"\n\n    - type: skill\n      namespace: snowflake-integrations-skill\n      description: \"Agent Skills exposure for Snowflake integration management — agent-compatible metadata for autonomous agents.\"\n      skills:\n        - name: snowflake-integrations-skill\n          description: \"Manage Snowflake API, catalog, and notification integrations through a unified agent-facing surface.\"\
  \n          tools:\n            - name: list-api-integrations\n              description: \"List API integrations configured in the Snowflake account\"\n              hints:\n                readOnly: true\n                destructive: false\n                idempotent: true\n              call: \"snowflake-api-integration.list-api-integrations\"\n            - name: create-api-integration\n              description: \"Create a new API integration (e.g. AWS API Gateway, Azure API Management)\"\n              hints:\n                readOnly: false\n                destructive: false\n                idempotent: false\n              call: \"snowflake-api-integration.create-api-integration\"\n            - name: fetch-api-integration\n              description: \"Fetch a single API integration by name\"\n              hints:\n                readOnly: true\n                destructive: false\n                idempotent: true\n              call: \"snowflake-api-integration.fetch-api-integration\"\
  \n            - name: delete-api-integration\n              description: \"Delete an API integration by name\"\n              hints:\n                readOnly: false\n                destructive: true\n                idempotent: true\n              call: \"snowflake-api-integration.delete-api-integration\"\n            - name: list-catalog-integrations\n              description: \"List catalog integrations (Iceberg, Glue, Polaris, etc.)\"\n              hints:\n                readOnly: true\n                destructive: false\n                idempotent: true\n              call: \"snowflake-catalog-integration.list-catalog-integrations\"\n            - name: create-catalog-integration\n              description: \"Create a new catalog integration\"\n              hints:\n                readOnly: false\n                destructive: false\n                idempotent: false\n              call: \"snowflake-catalog-integration.create-catalog-integration\"\n            - name: fetch-catalog-integration\n\
  \              description: \"Fetch a single catalog integration by name\"\n              hints:\n                readOnly: true\n                destructive: false\n                idempotent: true\n              call: \"snowflake-catalog-integration.fetch-catalog-integration\"\n            - name: delete-catalog-integration\n              description: \"Delete a catalog integration by name\"\n              hints:\n                readOnly: false\n                destructive: true\n                idempotent: true\n              call: \"snowflake-catalog-integration.delete-catalog-integration\"\n            - name: list-notification-integrations\n              description: \"List notification integrations (AWS SNS, Azure Event Grid, GCP Pub/Sub, etc.)\"\n              hints:\n                readOnly: true\n                destructive: false\n                idempotent: true\n              call: \"snowflake-notification-integration.list-notification-integrations\"\n            - name:\
  \ create-notification-integration\n              description: \"Create a new notification integration\"\n              hints:\n                readOnly: false\n                destructive: false\n                idempotent: false\n              call: \"snowflake-notification-integration.create-notification-integration\"\n            - name: fetch-notification-integration\n              description: \"Fetch a single notification integration by name\"\n              hints:\n                readOnly: true\n                destructive: false\n                idempotent: true\n              call: \"snowflake-notification-integration.fetch-notification-integration\"\n            - name: delete-notification-integration\n              description: \"Delete a notification integration by name\"\n              hints:\n                readOnly: false\n                destructive: true\n                idempotent: true\n              call: \"snowflake-notification-integration.delete-notification-integration\"\
  \n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/integrations-and-connectors.yaml
tags:
- Snowflake
- Integrations
- Connectors
tools:
- description: List API integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-integrations
- description: Create an API integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-integration
- description: Fetch API integration details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-api-integration
- description: Delete an API integration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-integration
- description: List catalog integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-catalog-integrations
- description: Create a catalog integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-catalog-integration
- description: Fetch catalog integration details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-catalog-integration
- description: Delete a catalog integration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-catalog-integration
- description: List notification integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-notification-integrations
- description: Create a notification integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-notification-integration
- description: Fetch notification integration details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-notification-integration
- description: Delete a notification integration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-notification-integration
- description: List API integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-integrations
- description: Create an API integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-integration
- description: Fetch API integration details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-api-integration
- description: Delete an API integration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-integration
- description: List catalog integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-catalog-integrations
- description: Create a catalog integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-catalog-integration
- description: Fetch catalog integration details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-catalog-integration
- description: Delete a catalog integration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-catalog-integration
- description: List notification integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-notification-integrations
- description: Create a notification integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-notification-integration
- description: Fetch notification integration details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-notification-integration
- description: Delete a notification integration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-notification-integration
---
