---
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
- delete a notification integration
- create notification integration
- database
- sql
- data warehousing
- fetch notification integration details
- connectors
- data lakes
- fetch catalog integration
- snowflake
- fetch catalog integration details
- catalog integration management
- fetch api integration
- create a notification integration
- create catalog integration
- fetch api integration details
- delete api integration
- create api integration
- delete a catalog integration
- list notification integrations
- api integration management
- create an api integration
- fetch notification integration
- notification integration management
- delete notification integration
- integrations
- list catalog integrations
- delete an api integration
- delete catalog integration
- list api integrations
- data sharing
- create a catalog integration
slug: integrations-and-connectors
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Integrations and Connectors\"\n  description: \"Unified workflow for managing API integrations, catalog integrations, and notification integrations. Used by Platform Engineers and Data Architects to connect Snowflake with external services, catalogs, and notification systems.\"\n  tags:\n    - Snowflake\n    - Integrations\n    - Connectors\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-api-integration\n      location: ./shared/api-integration.yaml\n    - import: snowflake-catalog-integration\n      location: ./shared/catalog-integration.yaml\n    - import: snowflake-notification-integration\n      location: ./shared/notification-integration.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: snowflake-integrations-api\n\
  \      description: \"Unified REST API for Snowflake integration management.\"\n      resources:\n        - path: /v1/api-integrations\n          name: api-integrations\n          description: \"API integration management\"\n          operations:\n            - method: GET\n              name: list-api-integrations\n              description: \"List API integrations\"\n              call: \"snowflake-api-integration.list-api-integrations\"\n            - method: POST\n              name: create-api-integration\n              description: \"Create an API integration\"\n              call: \"snowflake-api-integration.create-api-integration\"\n        - path: /v1/catalog-integrations\n          name: catalog-integrations\n          description: \"Catalog integration management\"\n          operations:\n            - method: GET\n              name: list-catalog-integrations\n              description: \"List catalog integrations\"\n              call: \"snowflake-catalog-integration.list-catalog-integrations\"\
  \n            - method: POST\n              name: create-catalog-integration\n              description: \"Create a catalog integration\"\n              call: \"snowflake-catalog-integration.create-catalog-integration\"\n        - path: /v1/notification-integrations\n          name: notification-integrations\n          description: \"Notification integration management\"\n          operations:\n            - method: GET\n              name: list-notification-integrations\n              description: \"List notification integrations\"\n              call: \"snowflake-notification-integration.list-notification-integrations\"\n            - method: POST\n              name: create-notification-integration\n              description: \"Create a notification integration\"\n              call: \"snowflake-notification-integration.create-notification-integration\"\n\n    - type: mcp\n      port: 9085\n      namespace: snowflake-integrations-mcp\n      transport: http\n      description: \"MCP\
  \ server for AI-assisted Snowflake integration management.\"\n      tools:\n        - name: list-api-integrations\n          description: \"List API integrations\"\n          hints:\n            readOnly: true\n          call: \"snowflake-api-integration.list-api-integrations\"\n        - name: create-api-integration\n          description: \"Create an API integration\"\n          hints:\n            readOnly: false\n          call: \"snowflake-api-integration.create-api-integration\"\n        - name: fetch-api-integration\n          description: \"Fetch API integration details\"\n          hints:\n            readOnly: true\n          call: \"snowflake-api-integration.fetch-api-integration\"\n        - name: delete-api-integration\n          description: \"Delete an API integration\"\n          hints:\n            destructive: true\n          call: \"snowflake-api-integration.delete-api-integration\"\n        - name: list-catalog-integrations\n          description: \"List catalog integrations\"\
  \n          hints:\n            readOnly: true\n          call: \"snowflake-catalog-integration.list-catalog-integrations\"\n        - name: create-catalog-integration\n          description: \"Create a catalog integration\"\n          hints:\n            readOnly: false\n          call: \"snowflake-catalog-integration.create-catalog-integration\"\n        - name: fetch-catalog-integration\n          description: \"Fetch catalog integration details\"\n          hints:\n            readOnly: true\n          call: \"snowflake-catalog-integration.fetch-catalog-integration\"\n        - name: delete-catalog-integration\n          description: \"Delete a catalog integration\"\n          hints:\n            destructive: true\n          call: \"snowflake-catalog-integration.delete-catalog-integration\"\n        - name: list-notification-integrations\n          description: \"List notification integrations\"\n          hints:\n            readOnly: true\n          call: \"snowflake-notification-integration.list-notification-integrations\"\
  \n        - name: create-notification-integration\n          description: \"Create a notification integration\"\n          hints:\n            readOnly: false\n          call: \"snowflake-notification-integration.create-notification-integration\"\n        - name: fetch-notification-integration\n          description: \"Fetch notification integration details\"\n          hints:\n            readOnly: true\n          call: \"snowflake-notification-integration.fetch-notification-integration\"\n        - name: delete-notification-integration\n          description: \"Delete a notification integration\"\n          hints:\n            destructive: true\n          call: \"snowflake-notification-integration.delete-notification-integration\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/integrations-and-connectors.yaml
tags:
- Snowflake
- Integrations
- Connectors
tools:
- description: List API integrations
  hints:
    readOnly: true
  name: list-api-integrations
- description: Create an API integration
  hints:
    readOnly: false
  name: create-api-integration
- description: Fetch API integration details
  hints:
    readOnly: true
  name: fetch-api-integration
- description: Delete an API integration
  hints:
    destructive: true
  name: delete-api-integration
- description: List catalog integrations
  hints:
    readOnly: true
  name: list-catalog-integrations
- description: Create a catalog integration
  hints:
    readOnly: false
  name: create-catalog-integration
- description: Fetch catalog integration details
  hints:
    readOnly: true
  name: fetch-catalog-integration
- description: Delete a catalog integration
  hints:
    destructive: true
  name: delete-catalog-integration
- description: List notification integrations
  hints:
    readOnly: true
  name: list-notification-integrations
- description: Create a notification integration
  hints:
    readOnly: false
  name: create-notification-integration
- description: Fetch notification integration details
  hints:
    readOnly: true
  name: fetch-notification-integration
- description: Delete a notification integration
  hints:
    destructive: true
  name: delete-notification-integration
---
