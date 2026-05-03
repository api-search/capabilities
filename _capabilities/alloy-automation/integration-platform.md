---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Integration Platform
operations: []
personas: []
provider_name: Alloy Automation
provider_slug: alloy-automation
search_terms:
- unified api
- ipaas
- embedded integrations
- workflows
- automation
- integrations
slug: integration-platform
source_filename: integration-platform.yaml
source_heading: Capability Spec
source_yaml: "name: Integration Platform\ndescription: >-\n  Workflow capability composition for building and managing native integrations\n  using the Alloy Automation platform. Supports embedded iPaaS, connectivity API,\n  and MCP-based AI integration workflows.\nversion: 2025-09\ncapabilities:\n  - shared/embedded.yaml\n  - shared/connectivity.yaml\nworkflows:\n  - id: user-integration-setup\n    name: User Integration Setup\n    description: Onboard a new user and configure their first integration\n    steps:\n      - step: create-user\n        capability: embedded\n        operation: createUser\n        description: Create the end user in Alloy\n      - step: generate-token\n        capability: embedded\n        operation: generateUserToken\n        description: Generate JWT for frontend SDK operations\n      - step: list-integrations\n        capability: embedded\n        operation: listIntegrations\n        description: Show available integrations to the user\n  - id: connector-action-flow\n\
  \    name: Connector Action Flow\n    description: Discover and execute actions on a third-party connector\n    steps:\n      - step: list-connectors\n        capability: connectivity\n        operation: listConnectors\n        description: Discover available connectors\n      - step: list-resources\n        capability: connectivity\n        operation: listConnectorResources\n        description: Discover resources in a connector\n      - step: get-action\n        capability: connectivity\n        operation: getConnectorAction\n        description: Get action schema and parameters\n      - step: create-credential\n        capability: connectivity\n        operation: createCredential\n        description: Create credentials for the connector\n      - step: execute-action\n        capability: connectivity\n        operation: executeConnectorAction\n        description: Execute the connector action\n  - id: workflow-monitoring\n    name: Workflow Monitoring\n    description: Monitor workflow\
  \ health and handle errors\n    steps:\n      - step: list-errors\n        capability: embedded\n        operation: listWorkflowErrors\n        description: Check for workflow execution errors\n      - step: list-logs\n        capability: embedded\n        operation: listWorkflowLogs\n        description: Review execution history\n      - step: deactivate-on-error\n        capability: embedded\n        operation: deactivateWorkflow\n        description: Disable workflow if persistent errors\ntools:\n  - id: create-user\n    capability: embedded\n    operation: createUser\n    description: Create an end user in the Alloy platform\n  - id: list-integrations\n    capability: embedded\n    operation: listIntegrations\n    description: List available integrations for a user\n  - id: trigger-event\n    capability: embedded\n    operation: triggerEvent\n    description: Trigger a custom workflow event\n  - id: list-connectors\n    capability: connectivity\n    operation: listConnectors\n    description:\
  \ List all available third-party connectors\n  - id: execute-action\n    capability: connectivity\n    operation: executeConnectorAction\n    description: Execute a connector action for a user\n  - id: create-credential\n    capability: connectivity\n    operation: createCredential\n    description: Store connector credentials for a user\n  - id: list-workflow-errors\n    capability: embedded\n    operation: listWorkflowErrors\n    description: Retrieve workflow execution errors\n  - id: upgrade-workflow\n    capability: embedded\n    operation: upgradeWorkflow\n    description: Upgrade a user's workflow to a new version\nrest_port: 8080\nmcp_port: 9090\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/alloy-automation/refs/heads/main/capabilities/integration-platform.yaml
tags: []
tools: []
---
