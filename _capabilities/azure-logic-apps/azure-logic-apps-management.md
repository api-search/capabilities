---
consumed_apis:
- azure-logic-apps
description: Workflow capability for managing Azure Logic Apps resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Logic Apps Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Logic Apps
provider_slug: azure-logic-apps
search_terms:
- list workflow resources
- list workflows
- list workflowrun resources
- azure resource management
- list integrationaccount resources
- integration
- list integration accounts
- list workflow triggers
- list workflowtrigger resources
- ipaas
- azure
- workflows
- resource management
- management
- list all resources
- cloud
- list
- list workflow runs
slug: azure-logic-apps-management
tags:
- Azure
- Cloud
- Management
tools:
- description: List Workflow resources
  hints:
    openWorld: true
    readOnly: true
  name: list-workflows
- description: List WorkflowRun resources
  hints:
    openWorld: true
    readOnly: true
  name: list-workflow-runs
- description: List WorkflowTrigger resources
  hints:
    openWorld: true
    readOnly: true
  name: list-workflow-triggers
- description: List IntegrationAccount resources
  hints:
    openWorld: true
    readOnly: true
  name: list-integration-accounts
---
