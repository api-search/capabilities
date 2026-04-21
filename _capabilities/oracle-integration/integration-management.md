---
consumed_apis:
- oracle-developer-api
- oracle-process-api
description: Unified workflow for managing Oracle Integration lifecycle including integrations, connections, packages, monitoring, B2B trading partners, process automation, tasks, and decision models. Used by integration developers and platform administrators.
layout: capability
name: Oracle Integration Management
operations:
- description: List all connections.
  method: GET
  name: list-connections
  path: /v1/connections
- description: List all integrations.
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: List monitoring instances.
  method: GET
  name: list-instances
  path: /v1/monitoring/instances
- description: List errored instances.
  method: GET
  name: list-errors
  path: /v1/monitoring/errors
- description: List all packages.
  method: GET
  name: list-packages
  path: /v1/packages
- description: List all trading partners.
  method: GET
  name: list-trading-partners
  path: /v1/trading-partners
- description: List process instances.
  method: GET
  name: list-process-instances
  path: /v1/processes
- description: List user tasks.
  method: GET
  name: list-tasks
  path: /v1/tasks
personas: []
provider_name: Oracle Integration
provider_slug: oracle-integration
search_terms:
- get details of a specific connection.
- test a connection for connectivity.
- list all process definitions.
- list packages
- b2b integration
- designs and manages business process definitions and decision models.
- test connection
- b2b trading partner management and document exchange.
- list user tasks.
- list process analytics queries.
- Integration Developer
- list all b2b trading partners.
- Platform Administrator
- get task details.
- list workspace spaces.
- list trading partners
- unified management of integrations, connections, monitoring, b2b, processes, and tasks.
- monitoring
- list connections
- list errored integration instances.
- errored integration instances.
- get details of a specific integration.
- list monitoring instances
- manages the oracle integration platform including monitoring, users, and configuration.
- api management
- oracle integration
- list monitoring instances.
- list all oracle integration connections.
- integration
- list all packages.
- integration connections.
- user tasks.
- process instances.
- list errors
- integration flows.
- list process definitions
- get connection
- get process instance details.
- b2b
- get process instance
- manages b2b trading partners, agreements, and document exchange.
- get integration
- get task
- integration packages.
- list errored instances.
- real-time monitoring of integration instances and error handling.
- list monitoring errors
- ipaas
- business process management with tasks and decision models.
- list integration monitoring instances.
- list all integrations.
- list integrations
- integration management
- process automation
- list process instances.
- list instances
- list all integration packages.
- list spaces
- builds and manages integration flows, connections, and adapters.
- integration flow design, deployment, and lifecycle management.
- integration monitoring instances.
- enterprise integration
- automation
- list analytics queries
- cloud integration
- list all connections.
- list all oracle integration flows.
- list all trading partners.
- list process instances
- list dmn decision model spaces.
- b2b trading partners.
- list tasks
- list dmn spaces
slug: integration-management
tags:
- Oracle Integration
- Integration Management
- Process Automation
- B2B
- Monitoring
tools:
- description: List all Oracle Integration connections.
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: Get details of a specific connection.
  hints:
    readOnly: true
  name: get-connection
- description: Test a connection for connectivity.
  hints:
    readOnly: true
  name: test-connection
- description: List all Oracle Integration flows.
  hints:
    openWorld: true
    readOnly: true
  name: list-integrations
- description: Get details of a specific integration.
  hints:
    readOnly: true
  name: get-integration
- description: List integration monitoring instances.
  hints:
    openWorld: true
    readOnly: true
  name: list-monitoring-instances
- description: List errored integration instances.
  hints:
    readOnly: true
  name: list-monitoring-errors
- description: List all integration packages.
  hints:
    readOnly: true
  name: list-packages
- description: List all B2B trading partners.
  hints:
    openWorld: true
    readOnly: true
  name: list-trading-partners
- description: List all process definitions.
  hints:
    readOnly: true
  name: list-process-definitions
- description: List process instances.
  hints:
    openWorld: true
    readOnly: true
  name: list-process-instances
- description: Get process instance details.
  hints:
    readOnly: true
  name: get-process-instance
- description: List user tasks.
  hints:
    openWorld: true
    readOnly: true
  name: list-tasks
- description: Get task details.
  hints:
    readOnly: true
  name: get-task
- description: List DMN decision model spaces.
  hints:
    readOnly: true
  name: list-dmn-spaces
- description: List workspace spaces.
  hints:
    readOnly: true
  name: list-spaces
- description: List process analytics queries.
  hints:
    readOnly: true
  name: list-analytics-queries
---
