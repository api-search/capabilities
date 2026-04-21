---
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
- notification integration management
- list api integrations
- delete catalog integration
- fetch notification integration
- delete an api integration
- data warehousing
- database
- delete a notification integration
- sql
- snowflake
- catalog integration management
- delete notification integration
- fetch api integration
- data lakes
- delete a catalog integration
- delete api integration
- create a catalog integration
- create notification integration
- api integration management
- connectors
- create api integration
- fetch api integration details
- fetch notification integration details
- fetch catalog integration details
- list notification integrations
- create an api integration
- create a notification integration
- create catalog integration
- fetch catalog integration
- integrations
- data sharing
- list catalog integrations
slug: integrations-and-connectors
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
