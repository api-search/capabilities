---
categories: []
consumed_apis: []
description: Workflow capability for automated resource optimization using IBM Turbonomic. Combines entity management, action automation, group scoping, and policy control to enable cloud architects and platform engineers to right-size workloads, reduce cloud costs, and maintain application performance across hybrid environments. Supports AI-assisted action analysis and bulk action execution via MCP.
layout: capability
name: Turbonomic Resource Optimization
operations:
- description: List all managed entities with optional type filtering
  method: GET
  name: get-entities
  path: /v1/entities
- description: Get entity details by UUID
  method: GET
  name: get-entity
  path: /v1/entities/{uuid}
- description: Get pending optimization actions for an entity
  method: GET
  name: get-entity-actions
  path: /v1/entities/{uuid}/actions
- description: Get resource utilization statistics for an entity
  method: GET
  name: get-entity-stats
  path: /v1/entities/{uuid}/stats
- description: Get all pending optimization actions
  method: GET
  name: get-actions
  path: /v1/actions
- description: Get or execute a specific optimization action
  method: GET
  name: get-action
  path: /v1/actions/{uuid}
- description: List all entity groups
  method: GET
  name: get-groups
  path: /v1/groups
- description: Create a new entity group
  method: POST
  name: create-group
  path: /v1/groups
- description: List all automation policies
  method: GET
  name: get-policies
  path: /v1/policies
- description: Create a new automation policy
  method: POST
  name: create-policy
  path: /v1/policies
- description: List all discovery targets
  method: GET
  name: get-targets
  path: /v1/targets
- description: List all resource templates
  method: GET
  name: get-templates
  path: /v1/templates
- description: Get infrastructure topology definitions
  method: GET
  name: get-topology
  path: /v1/topology
personas: []
provider_name: IBM Turbonomic
provider_slug: turbonomic
search_terms:
- list policies
- application resource management
- optimization actions for a specific entity
- get entity stats
- create a new automation policy
- get policies
- list all automation policies
- list all pending ai-recommended optimization actions from the realtime market
- cloud cost optimization
- get infrastructure topology and supply chain relationships
- get entities
- get entity actions
- workload automation
- get details for a specific managed entity by uuid
- delete group
- get entity details by uuid
- infrastructure topology and supply chains
- list templates
- hybrid cloud
- workload optimization
- list entities
- get resource utilization statistics for an entity
- get topology
- list resource and hardware templates for capacity planning
- kubernetes
- single entity details
- list managed infrastructure entities (vms, containers, applications) in turbonomic
- get infrastructure topology definitions
- resource utilization statistics
- list all resource templates
- get historical cpu, memory, and storage utilization statistics for an entity
- discovery targets and integrations
- get groups
- list all managed entities with optional type filtering
- get pending optimization actions for an entity
- multi-cloud
- execute action
- get or execute a specific optimization action
- delete an entity group from turbonomic
- list automation and placement policies governing turbonomic action execution
- get entity
- create policy
- get all pending optimization actions
- list all entity groups
- list all discovery targets (cloud accounts, hypervisors, kubernetes clusters)
- pending optimization actions from the realtime market
- cloud management
- resource optimization
- get targets
- resource and hardware templates
- entity groups for scoped management
- create a new entity group for targeted policy application or cost reporting
- list all discovery targets
- automation and placement policies
- ibm
- execute a specific turbonomic optimization action to right-size or move a workload
- list entity groups used for scoped policy and reporting in turbonomic
- list groups
- list targets
- get actions
- get optimization actions recommended for a specific entity
- create a new entity group
- create group
- create a new automation policy to control how turbonomic executes actions
- get templates
- single optimization action
- managed infrastructure entities
- get action
- list pending actions
slug: resource-optimization
source_filename: resource-optimization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Turbonomic Resource Optimization\n  description: Workflow capability for automated resource optimization using IBM Turbonomic. Combines entity management, action\n    automation, group scoping, and policy control to enable cloud architects and platform engineers to right-size workloads,\n    reduce cloud costs, and maintain application performance across hybrid environments. Supports AI-assisted action analysis\n    and bulk action execution via MCP.\n  tags:\n  - Application Resource Management\n  - Cloud Cost Optimization\n  - IBM\n  - Multi-Cloud\n  - Resource Optimization\n  - Workload Automation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TURBONOMIC_BEARER_TOKEN: TURBONOMIC_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: turbonomic\n    baseUri: https://{turbonomic_host}/api/v3\n    description: IBM Turbonomic Application Resource Management REST API\n    authentication:\n\
  \      type: bearer\n      token: '{{TURBONOMIC_BEARER_TOKEN}}'\n    resources:\n    - name: entities\n      path: /entities\n      description: Managed entities including VMs, containers, and applications\n      operations:\n      - name: get-entities\n        method: GET\n        description: Retrieve all entities in the Turbonomic environment\n        inputParameters:\n        - name: entity_type\n          in: query\n          type: string\n          required: false\n          description: Filter by entity type (VirtualMachine, Container, Application)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of entities to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-by-uuid\n      path: /entities/{uuid}\n      description: Single entity by UUID\n      operations:\n      - name: get-entity-by-uuid\n\
  \        method: GET\n        description: Retrieve a specific entity by its unique identifier\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-actions\n      path: /entities/{uuid}/actions\n      description: Optimization actions for a specific entity\n      operations:\n      - name: get-entity-actions\n        method: GET\n        description: Retrieve pending optimization actions for a specific entity\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ entity-stats\n      path: /entities/{uuid}/stats\n      description: Resource utilization statistics for an entity\n      operations:\n      - name: get-entity-stats\n        method: GET\n        description: Retrieve historical and projected resource statistics for an entity\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the entity\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date for statistics (ISO 8601)\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date for statistics (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: markets\n      path: /markets\n      description: Turbonomic markets for environment\
  \ state projections\n      operations:\n      - name: get-markets\n        method: GET\n        description: Retrieve all Turbonomic markets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: market-actions\n      path: /markets/{uuid}/actions\n      description: Optimization actions pending in a market\n      operations:\n      - name: get-market-actions\n        method: GET\n        description: Retrieve all pending optimization actions for a market\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: Market UUID (use 'Market' for realtime)\n        - name: ascending\n          in: query\n          type: boolean\n          required: false\n          description: Sort order for results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: actions\n      path: /actions/{uuid}\n      description: Individual optimization actions\n      operations:\n      - name: get-action-by-uuid\n        method: GET\n        description: Retrieve or execute a specific optimization action\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the action\n        - name: accept\n          in: query\n          type: boolean\n          required: false\n          description: If true, execute this action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Logical entity groups\n      operations:\n      - name: get-groups\n        method: GET\n        description: Retrieve all entity groups\n        inputParameters:\n        - name: group_type\n          in: query\n          type: string\n\
  \          required: false\n          description: Filter by group type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new entity group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            groupType: '{{tools.groupType}}'\n            isStatic: '{{tools.isStatic}}'\n    - name: group-by-uuid\n      path: /groups/{uuid}\n      description: Single entity group by UUID\n      operations:\n      - name: get-group-by-uuid\n        method: GET\n        description: Retrieve a specific entity group\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The unique\
  \ identifier of the group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-group\n        method: DELETE\n        description: Delete an entity group\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /policies\n      description: Automation and placement policies\n      operations:\n      - name: get-policies\n        method: GET\n        description: Retrieve all automation and placement policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-policy\n        method: POST\n        description: Create a new\
  \ automation or placement policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            policyType: '{{tools.policyType}}'\n            enabled: '{{tools.enabled}}'\n    - name: targets\n      path: /targets\n      description: Discovery targets connected to Turbonomic\n      operations:\n      - name: get-targets\n        method: GET\n        description: Retrieve all discovery targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates\n      path: /templates\n      description: Resource and hardware templates\n      operations:\n      - name: get-templates\n        method: GET\n        description: Retrieve all resource and hardware templates\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-template\n        method: POST\n        description: Create a new resource or hardware template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            className: '{{tools.className}}'\n    - name: stats\n      path: /stats\n      description: Aggregated environment statistics\n      operations:\n      - name: get-stats\n        method: POST\n        description: Retrieve aggregated statistics for entities matching criteria\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            statistics: '{{tools.statistics}}'\n    - name: topology\n      path: /topology\n      description:\
  \ Infrastructure topology and supply chain definitions\n      operations:\n      - name: get-topology\n        method: GET\n        description: Retrieve topology definitions and infrastructure relationships\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: resource-optimization-api\n    description: Unified REST API for Turbonomic resource optimization workflows.\n    resources:\n    - path: /v1/entities\n      name: entities\n      description: Managed infrastructure entities\n      operations:\n      - method: GET\n        name: get-entities\n        description: List all managed entities with optional type filtering\n        call: turbonomic.get-entities\n        with:\n          entity_type: rest.entity_type\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/{uuid}\n  \
  \    name: entity\n      description: Single entity details\n      operations:\n      - method: GET\n        name: get-entity\n        description: Get entity details by UUID\n        call: turbonomic.get-entity-by-uuid\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/{uuid}/actions\n      name: entity-actions\n      description: Optimization actions for a specific entity\n      operations:\n      - method: GET\n        name: get-entity-actions\n        description: Get pending optimization actions for an entity\n        call: turbonomic.get-entity-actions\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/{uuid}/stats\n      name: entity-stats\n      description: Resource utilization statistics\n      operations:\n      - method: GET\n        name: get-entity-stats\n        description: Get resource utilization\
  \ statistics for an entity\n        call: turbonomic.get-entity-stats\n        with:\n          uuid: rest.uuid\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/actions\n      name: actions\n      description: Pending optimization actions from the realtime market\n      operations:\n      - method: GET\n        name: get-actions\n        description: Get all pending optimization actions\n        call: turbonomic.get-market-actions\n        with:\n          uuid: Market\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/actions/{uuid}\n      name: action\n      description: Single optimization action\n      operations:\n      - method: GET\n        name: get-action\n        description: Get or execute a specific optimization action\n        call: turbonomic.get-action-by-uuid\n        with:\n          uuid: rest.uuid\n          accept:\
  \ rest.accept\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Entity groups for scoped management\n      operations:\n      - method: GET\n        name: get-groups\n        description: List all entity groups\n        call: turbonomic.get-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create a new entity group\n        call: turbonomic.create-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: policies\n      description: Automation and placement policies\n      operations:\n      - method: GET\n        name: get-policies\n        description: List all automation policies\n        call: turbonomic.get-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-policy\n\
  \        description: Create a new automation policy\n        call: turbonomic.create-policy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/targets\n      name: targets\n      description: Discovery targets and integrations\n      operations:\n      - method: GET\n        name: get-targets\n        description: List all discovery targets\n        call: turbonomic.get-targets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/templates\n      name: templates\n      description: Resource and hardware templates\n      operations:\n      - method: GET\n        name: get-templates\n        description: List all resource templates\n        call: turbonomic.get-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/topology\n      name: topology\n      description: Infrastructure topology and supply chains\n      operations:\n      - method: GET\n        name: get-topology\n\
  \        description: Get infrastructure topology definitions\n        call: turbonomic.get-topology\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: resource-optimization-mcp\n    transport: http\n    description: MCP server for AI-assisted Turbonomic resource optimization and action management.\n    tools:\n    - name: list-entities\n      description: List managed infrastructure entities (VMs, containers, applications) in Turbonomic\n      hints:\n        readOnly: true\n        openWorld: true\n      call: turbonomic.get-entities\n      with:\n        entity_type: tools.entity_type\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity\n      description: Get details for a specific managed entity by UUID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: turbonomic.get-entity-by-uuid\n      with:\n        uuid: tools.uuid\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pending-actions\n      description: List all pending AI-recommended optimization actions from the realtime market\n      hints:\n        readOnly: true\n        openWorld: true\n      call: turbonomic.get-market-actions\n      with:\n        uuid: Market\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity-actions\n      description: Get optimization actions recommended for a specific entity\n      hints:\n        readOnly: true\n        openWorld: false\n      call: turbonomic.get-entity-actions\n      with:\n        uuid: tools.uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-action\n      description: Execute a specific Turbonomic optimization action to right-size or move a workload\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: turbonomic.get-action-by-uuid\n\
  \      with:\n        uuid: tools.uuid\n        accept: 'true'\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity-stats\n      description: Get historical CPU, memory, and storage utilization statistics for an entity\n      hints:\n        readOnly: true\n        openWorld: false\n      call: turbonomic.get-entity-stats\n      with:\n        uuid: tools.uuid\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List entity groups used for scoped policy and reporting in Turbonomic\n      hints:\n        readOnly: true\n        openWorld: true\n      call: turbonomic.get-groups\n      with:\n        group_type: tools.group_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-group\n      description: Create a new entity group for targeted policy application or cost reporting\n  \
  \    hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: turbonomic.create-group\n      with:\n        displayName: tools.displayName\n        groupType: tools.groupType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-group\n      description: Delete an entity group from Turbonomic\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: turbonomic.delete-group\n      with:\n        uuid: tools.uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-policies\n      description: List automation and placement policies governing Turbonomic action execution\n      hints:\n        readOnly: true\n        openWorld: true\n      call: turbonomic.get-policies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-policy\n      description: Create a new automation policy to control how Turbonomic\
  \ executes actions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: turbonomic.create-policy\n      with:\n        displayName: tools.displayName\n        policyType: tools.policyType\n        enabled: tools.enabled\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-targets\n      description: List all discovery targets (cloud accounts, hypervisors, Kubernetes clusters)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: turbonomic.get-targets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-templates\n      description: List resource and hardware templates for capacity planning\n      hints:\n        readOnly: true\n        openWorld: true\n      call: turbonomic.get-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-topology\n      description: Get infrastructure topology and supply chain\
  \ relationships\n      hints:\n        readOnly: true\n        openWorld: true\n      call: turbonomic.get-topology\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/turbonomic/refs/heads/main/capabilities/resource-optimization.yaml
tags:
- Application Resource Management
- Cloud Cost Optimization
- IBM
- Multi-Cloud
- Resource Optimization
- Workload Automation
tools:
- description: List managed infrastructure entities (VMs, containers, applications) in Turbonomic
  hints:
    openWorld: true
    readOnly: true
  name: list-entities
- description: Get details for a specific managed entity by UUID
  hints:
    openWorld: false
    readOnly: true
  name: get-entity
- description: List all pending AI-recommended optimization actions from the realtime market
  hints:
    openWorld: true
    readOnly: true
  name: list-pending-actions
- description: Get optimization actions recommended for a specific entity
  hints:
    openWorld: false
    readOnly: true
  name: get-entity-actions
- description: Execute a specific Turbonomic optimization action to right-size or move a workload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-action
- description: Get historical CPU, memory, and storage utilization statistics for an entity
  hints:
    openWorld: false
    readOnly: true
  name: get-entity-stats
- description: List entity groups used for scoped policy and reporting in Turbonomic
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Create a new entity group for targeted policy application or cost reporting
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-group
- description: Delete an entity group from Turbonomic
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-group
- description: List automation and placement policies governing Turbonomic action execution
  hints:
    openWorld: true
    readOnly: true
  name: list-policies
- description: Create a new automation policy to control how Turbonomic executes actions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-policy
- description: List all discovery targets (cloud accounts, hypervisors, Kubernetes clusters)
  hints:
    openWorld: true
    readOnly: true
  name: list-targets
- description: List resource and hardware templates for capacity planning
  hints:
    openWorld: true
    readOnly: true
  name: list-templates
- description: Get infrastructure topology and supply chain relationships
  hints:
    openWorld: true
    readOnly: true
  name: get-topology
---
