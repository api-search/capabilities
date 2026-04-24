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
- list all oracle integration connections.
- integration
- list process instances.
- list workspace spaces.
- list integration monitoring instances.
- process automation
- list all b2b trading partners.
- integration packages.
- list all packages.
- get integration
- list process analytics queries.
- list all integration packages.
- list all process definitions.
- list monitoring errors
- unified management of integrations, connections, monitoring, b2b, processes, and tasks.
- list dmn decision model spaces.
- monitoring
- oracle integration
- integration monitoring instances.
- list all connections.
- b2b
- get task
- list tasks
- get details of a specific integration.
- integration connections.
- integration flow design, deployment, and lifecycle management.
- get task details.
- designs and manages business process definitions and decision models.
- list monitoring instances.
- get details of a specific connection.
- manages b2b trading partners, agreements, and document exchange.
- list analytics queries
- b2b trading partners.
- user tasks.
- list process definitions
- get process instance
- enterprise integration
- automation
- list all oracle integration flows.
- b2b trading partner management and document exchange.
- api management
- get connection
- business process management with tasks and decision models.
- list packages
- get process instance details.
- Platform Administrator
- Integration Developer
- list errored integration instances.
- integration management
- list monitoring instances
- builds and manages integration flows, connections, and adapters.
- list instances
- list trading partners
- list spaces
- manages the oracle integration platform including monitoring, users, and configuration.
- process instances.
- list all integrations.
- list errored instances.
- errored integration instances.
- test a connection for connectivity.
- real-time monitoring of integration instances and error handling.
- cloud integration
- b2b integration
- list user tasks.
- list errors
- list dmn spaces
- integration flows.
- list connections
- test connection
- list all trading partners.
- list integrations
- ipaas
- list process instances
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
