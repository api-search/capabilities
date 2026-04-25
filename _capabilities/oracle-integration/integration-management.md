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
- integration flows.
- list all b2b trading partners.
- b2b trading partner management and document exchange.
- integration flow design, deployment, and lifecycle management.
- list tasks
- b2b
- list connections
- builds and manages integration flows, connections, and adapters.
- manages b2b trading partners, agreements, and document exchange.
- Platform Administrator
- real-time monitoring of integration instances and error handling.
- ipaas
- list errors
- list monitoring instances
- list trading partners
- list all process definitions.
- b2b trading partners.
- list dmn decision model spaces.
- list all packages.
- integration
- list integrations
- list user tasks.
- get integration
- unified management of integrations, connections, monitoring, b2b, processes, and tasks.
- test connection
- list workspace spaces.
- errored integration instances.
- integration packages.
- list analytics queries
- automation
- designs and manages business process definitions and decision models.
- list monitoring errors
- api management
- list errored instances.
- list errored integration instances.
- list all integration packages.
- get process instance
- enterprise integration
- process automation
- user tasks.
- list process analytics queries.
- list instances
- Integration Developer
- oracle integration
- list process instances
- cloud integration
- b2b integration
- monitoring
- list packages
- get details of a specific connection.
- get task
- list process instances.
- list monitoring instances.
- list all oracle integration connections.
- integration connections.
- integration management
- list spaces
- list all trading partners.
- get connection
- integration monitoring instances.
- get task details.
- list all connections.
- get process instance details.
- business process management with tasks and decision models.
- test a connection for connectivity.
- list integration monitoring instances.
- list process definitions
- list dmn spaces
- list all oracle integration flows.
- get details of a specific integration.
- process instances.
- list all integrations.
- manages the oracle integration platform including monitoring, users, and configuration.
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
