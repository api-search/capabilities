---
consumed_apis:
- apifuse
description: Unified workflow for managing embedded integrations within SaaS products - browsing connectors, building workflows, monitoring usage analytics, and managing user connections.
layout: capability
name: Apifuse Embedded Integration Management
operations:
- description: List all integrations.
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: List all connectors.
  method: GET
  name: list-connectors
  path: /v1/connectors
- description: List workflows.
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Create a workflow.
  method: POST
  name: create-workflow
  path: /v1/workflows
- description: Get analytics data.
  method: GET
  name: get-analytics
  path: /v1/analytics
personas: []
provider_name: Apifuse
provider_slug: apifuse
search_terms:
- browse pre-built connectors.
- create workflow
- integration analytics.
- Integration Developer
- saas
- list workflows
- developer implementing and automating embedded integration workflows.
- browse and manage integrations.
- get analytics data.
- manage workflows.
- integrations
- create a workflow.
- browse all available embedded integrations, optionally filtered by category.
- ipaas
- list all integrations.
- list integrations
- marketplace
- create a new automation workflow connecting two or more integrated platforms.
- list all connectors.
- list all pre-built connectors available for embedding into your saas product.
- managing native integrations within saas products.
- apifuse
- list connectors
- integration platform
- workflow automation
- embedded integrations
- list workflows.
- list all integration workflows configured in the embedded marketplace.
- retrieve integration usage analytics including total tasks, active integrations, and active users.
- product manager building native integrations into a saas product.
- SaaS Product Manager
- get analytics
slug: embedded-integration-management
tags:
- Apifuse
- Embedded Integrations
- Workflow Automation
- SaaS
tools:
- description: Browse all available embedded integrations, optionally filtered by category.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-integrations
- description: List all pre-built connectors available for embedding into your SaaS product.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-connectors
- description: List all integration workflows configured in the embedded marketplace.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-workflows
- description: Create a new automation workflow connecting two or more integrated platforms.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workflow
- description: Retrieve integration usage analytics including total tasks, active integrations, and active users.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-analytics
---
