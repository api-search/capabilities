---
categories: []
consumed_apis: []
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
- integrations
- catalog integration management
- fetch notification integration details
- list notification integrations
- create a catalog integration
- delete notification integration
- delete a notification integration
- create notification integration
- delete an api integration
- api integration management
- list api integrations
- delete api integration
- create catalog integration
- sql
- delete catalog integration
- snowflake
- notification integration management
- fetch catalog integration details
- create an api integration
- connectors
- data sharing
- data lakes
- database
- delete a catalog integration
- fetch catalog integration
- data warehousing
- fetch api integration details
- create a notification integration
- fetch notification integration
- list catalog integrations
- create api integration
- fetch api integration
slug: integrations-and-connectors
source_filename: integrations-and-connectors.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Snowflake Integrations and Connectors\n  description: Unified workflow for managing API integrations, catalog integrations, and notification integrations. Used by\n    Platform Engineers and Data Architects to connect Snowflake with external services, catalogs, and notification systems.\n  tags:\n  - Snowflake\n  - Integrations\n  - Connectors\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n    SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: snowflake-api-integration\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake API Integration API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: api-integrations\n      path: /api/v2/api-integrations\n      description: API integration resources\n      operations:\n      - name: list-api-integrations\n\
  \        method: GET\n        description: List API integrations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-integration\n        method: POST\n        description: Create an API integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-api-integration\n        method: GET\n        description: Fetch an API integration by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-integration\n        method: DELETE\n        description: Delete an API integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-catalog-integration\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n\
  \    description: Snowflake Catalog Integration API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: catalog-integrations\n      path: /api/v2/catalog-integrations\n      description: Catalog integration resources\n      operations:\n      - name: list-catalog-integrations\n        method: GET\n        description: List catalog integrations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-catalog-integration\n        method: POST\n        description: Create a catalog integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-catalog-integration\n        method: GET\n        description: Fetch a catalog integration by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: delete-catalog-integration\n        method: DELETE\n        description: Delete a catalog integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-notification-integration\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Notification Integration API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: notification-integrations\n      path: /api/v2/notification-integrations\n      description: Notification integration resources\n      operations:\n      - name: list-notification-integrations\n        method: GET\n        description: List notification integrations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-notification-integration\n        method: POST\n\
  \        description: Create a notification integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-notification-integration\n        method: GET\n        description: Fetch a notification integration by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-notification-integration\n        method: DELETE\n        description: Delete a notification integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8085\n    namespace: snowflake-integrations-api\n    description: Unified REST API for Snowflake integration management.\n    resources:\n    - path: /v1/api-integrations\n      name: api-integrations\n      description: API integration management\n      operations:\n\
  \      - method: GET\n        name: list-api-integrations\n        description: List API integrations\n        call: snowflake-api-integration.list-api-integrations\n        hints:\n          readOnly: true\n          destructive: false\n          idempotent: true\n        outputParameters:\n        - name: integrations\n          type: array\n          description: Array of API integration objects\n          mapping: $.data\n        - name: totalCount\n          type: integer\n          description: Count of returned integrations\n          mapping: $.data.length\n      - method: POST\n        name: create-api-integration\n        description: Create an API integration\n        call: snowflake-api-integration.create-api-integration\n        hints:\n          readOnly: false\n          destructive: false\n          idempotent: false\n        inputParameters:\n        - name: name\n          type: string\n          description: Unique name of the API integration\n          required: true\n\
  \          mapping: $.body.name\n        - name: api_provider\n          type: string\n          description: API provider (e.g. aws_api_gateway, azure_api_management, google_api_gateway)\n          required: true\n          mapping: $.body.api_provider\n        - name: api_allowed_prefixes\n          type: array\n          description: Allowed endpoint prefixes for the external function\n          required: true\n          mapping: $.body.api_allowed_prefixes\n        - name: enabled\n          type: boolean\n          description: Whether the integration is enabled on create\n          required: false\n          mapping: $.body.enabled\n        outputParameters:\n        - name: integrationName\n          type: string\n          description: Name of the created integration\n          mapping: $.name\n        - name: status\n          type: string\n          description: Operation status\n          mapping: $.status\n    - path: /v1/catalog-integrations\n      name: catalog-integrations\n\
  \      description: Catalog integration management\n      operations:\n      - method: GET\n        name: list-catalog-integrations\n        description: List catalog integrations\n        call: snowflake-catalog-integration.list-catalog-integrations\n        hints:\n          readOnly: true\n          destructive: false\n          idempotent: true\n        outputParameters:\n        - name: integrations\n          type: array\n          description: Array of catalog integration objects\n          mapping: $.data\n        - name: totalCount\n          type: integer\n          description: Count of returned integrations\n          mapping: $.data.length\n      - method: POST\n        name: create-catalog-integration\n        description: Create a catalog integration\n        call: snowflake-catalog-integration.create-catalog-integration\n        hints:\n          readOnly: false\n          destructive: false\n          idempotent: false\n        inputParameters:\n        - name: name\n\
  \          type: string\n          description: Unique name of the catalog integration\n          required: true\n          mapping: $.body.name\n        - name: catalog_source\n          type: string\n          description: Catalog source (e.g. GLUE, OBJECT_STORE, POLARIS)\n          required: true\n          mapping: $.body.catalog_source\n        - name: table_format\n          type: string\n          description: Table format (e.g. ICEBERG, DELTA)\n          required: true\n          mapping: $.body.table_format\n        - name: enabled\n          type: boolean\n          description: Whether the integration is enabled on create\n          required: false\n          mapping: $.body.enabled\n        outputParameters:\n        - name: integrationName\n          type: string\n          description: Name of the created integration\n          mapping: $.name\n        - name: status\n          type: string\n          description: Operation status\n          mapping: $.status\n    - path:\
  \ /v1/notification-integrations\n      name: notification-integrations\n      description: Notification integration management\n      operations:\n      - method: GET\n        name: list-notification-integrations\n        description: List notification integrations\n        call: snowflake-notification-integration.list-notification-integrations\n        hints:\n          readOnly: true\n          destructive: false\n          idempotent: true\n        outputParameters:\n        - name: integrations\n          type: array\n          description: Array of notification integration objects\n          mapping: $.data\n        - name: totalCount\n          type: integer\n          description: Count of returned integrations\n          mapping: $.data.length\n      - method: POST\n        name: create-notification-integration\n        description: Create a notification integration\n        call: snowflake-notification-integration.create-notification-integration\n        hints:\n          readOnly:\
  \ false\n          destructive: false\n          idempotent: false\n        inputParameters:\n        - name: name\n          type: string\n          description: Unique name of the notification integration\n          required: true\n          mapping: $.body.name\n        - name: notification_provider\n          type: string\n          description: Notification provider (e.g. AWS_SNS, AZURE_EVENT_GRID, GCP_PUBSUB)\n          required: true\n          mapping: $.body.notification_provider\n        - name: direction\n          type: string\n          description: Notification direction (INBOUND or OUTBOUND)\n          required: true\n          mapping: $.body.direction\n        - name: enabled\n          type: boolean\n          description: Whether the integration is enabled on create\n          required: false\n          mapping: $.body.enabled\n        outputParameters:\n        - name: integrationName\n          type: string\n          description: Name of the created integration\n\
  \          mapping: $.name\n        - name: status\n          type: string\n          description: Operation status\n          mapping: $.status\n  - type: mcp\n    port: 9085\n    namespace: snowflake-integrations-mcp\n    transport: http\n    description: MCP server (Streaming HTTP) for AI-assisted Snowflake integration management.\n    tools:\n    - name: list-api-integrations\n      description: List API integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-api-integration.list-api-integrations\n      outputParameters:\n      - name: integrations\n        type: array\n        description: Array of API integration objects\n        mapping: $.data\n      - name: totalCount\n        type: integer\n        description: Count of returned integrations\n        mapping: $.data.length\n    - name: create-api-integration\n      description: Create an API integration\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: snowflake-api-integration.create-api-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Unique name of the API integration\n        required: true\n        mapping: $.body.name\n      - name: api_provider\n        type: string\n        description: API provider (e.g. aws_api_gateway, azure_api_management, google_api_gateway)\n        required: true\n        mapping: $.body.api_provider\n      - name: api_allowed_prefixes\n        type: array\n        description: Allowed endpoint prefixes for the external function\n        required: true\n        mapping: $.body.api_allowed_prefixes\n      - name: enabled\n        type: boolean\n        description: Whether the integration is enabled on create\n        required: false\n        mapping: $.body.enabled\n      outputParameters:\n      - name: integrationName\n        type: string\n        description: Name of the created integration\n        mapping:\
  \ $.name\n      - name: status\n        type: string\n        description: Operation status\n        mapping: $.status\n    - name: fetch-api-integration\n      description: Fetch API integration details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-api-integration.fetch-api-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the API integration to fetch\n        required: true\n        mapping: $.path.name\n      outputParameters:\n      - name: integration\n        type: object\n        description: Full API integration record\n        mapping: $.\n    - name: delete-api-integration\n      description: Delete an API integration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: snowflake-api-integration.delete-api-integration\n      inputParameters:\n      - name: name\n        type: string\n        description:\
  \ Name of the API integration to delete\n        required: true\n        mapping: $.path.name\n      outputParameters:\n      - name: status\n        type: string\n        description: Delete operation status\n        mapping: $.status\n    - name: list-catalog-integrations\n      description: List catalog integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-catalog-integration.list-catalog-integrations\n      outputParameters:\n      - name: integrations\n        type: array\n        description: Array of catalog integration objects\n        mapping: $.data\n      - name: totalCount\n        type: integer\n        description: Count of returned integrations\n        mapping: $.data.length\n    - name: create-catalog-integration\n      description: Create a catalog integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-catalog-integration.create-catalog-integration\n\
  \      inputParameters:\n      - name: name\n        type: string\n        description: Unique name of the catalog integration\n        required: true\n        mapping: $.body.name\n      - name: catalog_source\n        type: string\n        description: Catalog source (e.g. GLUE, OBJECT_STORE, POLARIS)\n        required: true\n        mapping: $.body.catalog_source\n      - name: table_format\n        type: string\n        description: Table format (e.g. ICEBERG, DELTA)\n        required: true\n        mapping: $.body.table_format\n      - name: enabled\n        type: boolean\n        description: Whether the integration is enabled on create\n        required: false\n        mapping: $.body.enabled\n      outputParameters:\n      - name: integrationName\n        type: string\n        description: Name of the created integration\n        mapping: $.name\n      - name: status\n        type: string\n        description: Operation status\n        mapping: $.status\n    - name: fetch-catalog-integration\n\
  \      description: Fetch catalog integration details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-catalog-integration.fetch-catalog-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the catalog integration to fetch\n        required: true\n        mapping: $.path.name\n      outputParameters:\n      - name: integration\n        type: object\n        description: Full catalog integration record\n        mapping: $.\n    - name: delete-catalog-integration\n      description: Delete a catalog integration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: snowflake-catalog-integration.delete-catalog-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the catalog integration to delete\n        required: true\n        mapping: $.path.name\n      outputParameters:\n\
  \      - name: status\n        type: string\n        description: Delete operation status\n        mapping: $.status\n    - name: list-notification-integrations\n      description: List notification integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-notification-integration.list-notification-integrations\n      outputParameters:\n      - name: integrations\n        type: array\n        description: Array of notification integration objects\n        mapping: $.data\n      - name: totalCount\n        type: integer\n        description: Count of returned integrations\n        mapping: $.data.length\n    - name: create-notification-integration\n      description: Create a notification integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-notification-integration.create-notification-integration\n      inputParameters:\n      - name: name\n \
  \       type: string\n        description: Unique name of the notification integration\n        required: true\n        mapping: $.body.name\n      - name: notification_provider\n        type: string\n        description: Notification provider (e.g. AWS_SNS, AZURE_EVENT_GRID, GCP_PUBSUB)\n        required: true\n        mapping: $.body.notification_provider\n      - name: direction\n        type: string\n        description: Notification direction (INBOUND or OUTBOUND)\n        required: true\n        mapping: $.body.direction\n      - name: enabled\n        type: boolean\n        description: Whether the integration is enabled on create\n        required: false\n        mapping: $.body.enabled\n      outputParameters:\n      - name: integrationName\n        type: string\n        description: Name of the created integration\n        mapping: $.name\n      - name: status\n        type: string\n        description: Operation status\n        mapping: $.status\n    - name: fetch-notification-integration\n\
  \      description: Fetch notification integration details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-notification-integration.fetch-notification-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the notification integration to fetch\n        required: true\n        mapping: $.path.name\n      outputParameters:\n      - name: integration\n        type: object\n        description: Full notification integration record\n        mapping: $.\n    - name: delete-notification-integration\n      description: Delete a notification integration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: snowflake-notification-integration.delete-notification-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the notification integration to delete\n        required: true\n\
  \        mapping: $.path.name\n      outputParameters:\n      - name: status\n        type: string\n        description: Delete operation status\n        mapping: $.status\n  - type: mcp\n    namespace: snowflake-integrations-mcp-stdio\n    transport: stdio\n    description: MCP server (stdio transport) for local AI clients such as Claude Desktop and IDE agents.\n    tools:\n    - name: list-api-integrations\n      description: List API integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-api-integration.list-api-integrations\n    - name: create-api-integration\n      description: Create an API integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-api-integration.create-api-integration\n    - name: fetch-api-integration\n      description: Fetch API integration details\n      hints:\n        readOnly: true\n        destructive: false\n  \
  \      idempotent: true\n      call: snowflake-api-integration.fetch-api-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the API integration to fetch\n        required: true\n        mapping: $.path.name\n    - name: delete-api-integration\n      description: Delete an API integration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: snowflake-api-integration.delete-api-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the API integration to delete\n        required: true\n        mapping: $.path.name\n    - name: list-catalog-integrations\n      description: List catalog integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-catalog-integration.list-catalog-integrations\n    - name: create-catalog-integration\n      description: Create a catalog\
  \ integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-catalog-integration.create-catalog-integration\n    - name: fetch-catalog-integration\n      description: Fetch catalog integration details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-catalog-integration.fetch-catalog-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the catalog integration to fetch\n        required: true\n        mapping: $.path.name\n    - name: delete-catalog-integration\n      description: Delete a catalog integration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: snowflake-catalog-integration.delete-catalog-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the catalog integration to delete\n  \
  \      required: true\n        mapping: $.path.name\n    - name: list-notification-integrations\n      description: List notification integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-notification-integration.list-notification-integrations\n    - name: create-notification-integration\n      description: Create a notification integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-notification-integration.create-notification-integration\n    - name: fetch-notification-integration\n      description: Fetch notification integration details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-notification-integration.fetch-notification-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the notification integration to fetch\n\
  \        required: true\n        mapping: $.path.name\n    - name: delete-notification-integration\n      description: Delete a notification integration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: snowflake-notification-integration.delete-notification-integration\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the notification integration to delete\n        required: true\n        mapping: $.path.name\n  - type: skill\n    namespace: snowflake-integrations-skill\n    description: Agent Skills exposure for Snowflake integration management — agent-compatible metadata for autonomous agents.\n    skills:\n    - name: snowflake-integrations-skill\n      description: Manage Snowflake API, catalog, and notification integrations through a unified agent-facing surface.\n      tools:\n      - name: list-api-integrations\n        description: List API integrations configured in the Snowflake\
  \ account\n        hints:\n          readOnly: true\n          destructive: false\n          idempotent: true\n        call: snowflake-api-integration.list-api-integrations\n      - name: create-api-integration\n        description: Create a new API integration (e.g. AWS API Gateway, Azure API Management)\n        hints:\n          readOnly: false\n          destructive: false\n          idempotent: false\n        call: snowflake-api-integration.create-api-integration\n      - name: fetch-api-integration\n        description: Fetch a single API integration by name\n        hints:\n          readOnly: true\n          destructive: false\n          idempotent: true\n        call: snowflake-api-integration.fetch-api-integration\n      - name: delete-api-integration\n        description: Delete an API integration by name\n        hints:\n          readOnly: false\n          destructive: true\n          idempotent: true\n        call: snowflake-api-integration.delete-api-integration\n      -\
  \ name: list-catalog-integrations\n        description: List catalog integrations (Iceberg, Glue, Polaris, etc.)\n        hints:\n          readOnly: true\n          destructive: false\n          idempotent: true\n        call: snowflake-catalog-integration.list-catalog-integrations\n      - name: create-catalog-integration\n        description: Create a new catalog integration\n        hints:\n          readOnly: false\n          destructive: false\n          idempotent: false\n        call: snowflake-catalog-integration.create-catalog-integration\n      - name: fetch-catalog-integration\n        description: Fetch a single catalog integration by name\n        hints:\n          readOnly: true\n          destructive: false\n          idempotent: true\n        call: snowflake-catalog-integration.fetch-catalog-integration\n      - name: delete-catalog-integration\n        description: Delete a catalog integration by name\n        hints:\n          readOnly: false\n          destructive:\
  \ true\n          idempotent: true\n        call: snowflake-catalog-integration.delete-catalog-integration\n      - name: list-notification-integrations\n        description: List notification integrations (AWS SNS, Azure Event Grid, GCP Pub/Sub, etc.)\n        hints:\n          readOnly: true\n          destructive: false\n          idempotent: true\n        call: snowflake-notification-integration.list-notification-integrations\n      - name: create-notification-integration\n        description: Create a new notification integration\n        hints:\n          readOnly: false\n          destructive: false\n          idempotent: false\n        call: snowflake-notification-integration.create-notification-integration\n      - name: fetch-notification-integration\n        description: Fetch a single notification integration by name\n        hints:\n          readOnly: true\n          destructive: false\n          idempotent: true\n        call: snowflake-notification-integration.fetch-notification-integration\n\
  \      - name: delete-notification-integration\n        description: Delete a notification integration by name\n        hints:\n          readOnly: false\n          destructive: true\n          idempotent: true\n        call: snowflake-notification-integration.delete-notification-integration\n"
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
