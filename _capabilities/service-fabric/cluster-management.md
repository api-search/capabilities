---
categories: []
consumed_apis: []
description: Unified capability for managing Azure Service Fabric clusters, including application lifecycle, node management, service monitoring, and cluster health. Enables platform engineers and SREs to deploy applications, monitor cluster health, and manage the Service Fabric runtime via REST API.
layout: capability
name: Service Fabric Cluster Management
operations:
- description: Get the aggregated health state of the cluster
  method: GET
  name: get-cluster-health
  path: /v1/cluster/health
- description: List all nodes in the cluster
  method: GET
  name: list-nodes
  path: /v1/nodes
- description: Get information for a specific cluster node
  method: GET
  name: get-node
  path: /v1/nodes/{node_name}
- description: List all deployed applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Deploy a new application
  method: POST
  name: create-application
  path: /v1/applications
- description: Get information for a specific application
  method: GET
  name: get-application
  path: /v1/applications/{application_id}
- description: Delete a deployed application
  method: DELETE
  name: delete-application
  path: /v1/applications/{application_id}
- description: Get health state for an application and its services
  method: GET
  name: get-application-health
  path: /v1/applications/{application_id}/health
- description: List services within an application
  method: GET
  name: list-services
  path: /v1/applications/{application_id}/services
personas: []
provider_name: Service Fabric
provider_slug: service-fabric
search_terms:
- individual node information
- list all deployed applications
- get information for a specific cluster node
- health monitoring
- get information for a specific application
- deploy a new application
- cluster node management
- distributed systems
- delete a deployed service fabric application and all its services. use forceremove=true only when the application is stuck in a deleting state.
- get node info
- azure
- application lifecycle management
- list all nodes in the cluster
- list nodes
- delete a deployed application
- list services
- get detailed information about a specific cluster node by name
- list all services within a specific service fabric application
- cluster management
- containers
- get the health state of a specific application, including per-service health rollups and any active health events.
- application lifecycle
- get health state for an application and its services
- list all nodes in the service fabric cluster. filter by node status (up, down, all). includes node name, ip, node type, and health state.
- list all applications deployed in the service fabric cluster. optionally filter by application type name.
- cloud native
- individual application management
- kubernetes
- get the overall health state of the service fabric cluster. returns aggregated health state (ok/warning/error) plus per-node and per-application health states.
- open source
- application health monitoring
- service management within an application
- deploy a new service fabric application to the cluster. requires the application type to be provisioned first. provide name (fabric:/myapp), typename, and typeversion.
- delete application
- get application health
- get detailed information about a specific deployed application
- get the aggregated health state of the cluster
- overall cluster health state
- list services within an application
- get application info
- create application
- get application
- list applications
- microservices
- get node
- get cluster health
slug: cluster-management
source_filename: cluster-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Service Fabric Cluster Management\n  description: Unified capability for managing Azure Service Fabric clusters, including application lifecycle, node management,\n    service monitoring, and cluster health. Enables platform engineers and SREs to deploy applications, monitor cluster health,\n    and manage the Service Fabric runtime via REST API.\n  tags:\n  - Distributed Systems\n  - Cluster Management\n  - Application Lifecycle\n  - Health Monitoring\n  - Microservices\n  - Azure\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SF_CLUSTER_ENDPOINT: SF_CLUSTER_ENDPOINT\ncapability:\n  consumes:\n  - type: http\n    namespace: sf-api\n    baseUri: http://{{SF_CLUSTER_ENDPOINT}}:19080\n    description: Service Fabric HTTP Gateway\n    resources:\n    - name: cluster-health\n      path: /$/GetClusterHealth\n      description: Cluster health state\n      operations:\n      - name: get-cluster-health\n\
  \        method: GET\n        description: Returns the health state of the entire Service Fabric cluster\n        inputParameters:\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version (9.1)\n        - name: NodesHealthStateFilter\n          in: query\n          type: integer\n          required: false\n          description: Health state filter for nodes\n        - name: ApplicationsHealthStateFilter\n          in: query\n          type: integer\n          required: false\n          description: Health state filter for applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /Nodes\n      description: Cluster node listing\n      operations:\n      - name: get-node-info-list\n        method: GET\n        description: Returns the list of nodes in the Service Fabric cluster\n        inputParameters:\n\
  \        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        - name: NodeStatusFilter\n          in: query\n          type: string\n          required: false\n          description: Filter nodes by status (up, down, all, etc.)\n        - name: MaxResults\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: ContinuationToken\n          in: query\n          type: string\n          required: false\n          description: Pagination continuation token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node\n      path: /Nodes/{nodeName}\n      description: Individual node information\n      operations:\n      - name: get-node-info\n        method: GET\n        description: Returns information about a specific cluster node\n        inputParameters:\n\
  \        - name: nodeName\n          in: path\n          type: string\n          required: true\n          description: Node name\n        - name: api-version\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /Applications\n      description: Application listing\n      operations:\n      - name: get-application-info-list\n        method: GET\n        description: Returns the list of applications in the cluster\n        inputParameters:\n        - name: api-version\n          in: query\n          type: string\n          required: true\n        - name: ApplicationTypeName\n          in: query\n          type: string\n          required: false\n          description: Filter by application type name\n        - name: ContinuationToken\n          in: query\n          type: string\n          required: false\n\
  \        - name: MaxResults\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application\n      path: /Applications/{applicationId}\n      description: Individual application operations\n      operations:\n      - name: get-application-info\n        method: GET\n        description: Returns information about a specific application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application ID\n        - name: api-version\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create-application\n      path: /Applications/$/Create\n      description: Create a new application\n\
  \      operations:\n      - name: create-application\n        method: POST\n        description: Creates a Service Fabric application\n        inputParameters:\n        - name: api-version\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            TypeName: '{{tools.type_name}}'\n            TypeVersion: '{{tools.type_version}}'\n    - name: delete-application\n      path: /Applications/{applicationId}/$/Delete\n      description: Delete an application\n      operations:\n      - name: delete-application\n        method: POST\n        description: Deletes a Service Fabric application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n        - name: api-version\n         \
  \ in: query\n          type: string\n          required: true\n        - name: ForceRemove\n          in: query\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-health\n      path: /Applications/{applicationId}/$/GetHealth\n      description: Application health state\n      operations:\n      - name: get-application-health\n        method: GET\n        description: Returns health state for a specific application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n        - name: api-version\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /Applications/{applicationId}/$/GetServices\n\
  \      description: Services within an application\n      operations:\n      - name: get-service-info-list\n        method: GET\n        description: Returns services in a specific application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n        - name: api-version\n          in: query\n          type: string\n          required: true\n        - name: ServiceTypeName\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sf-cluster-management-api\n    description: Unified REST API for Service Fabric cluster and application management.\n    resources:\n    - path: /v1/cluster/health\n      name: cluster-health\n      description: Overall cluster health state\n      operations:\n      - method: GET\n     \
  \   name: get-cluster-health\n        description: Get the aggregated health state of the cluster\n        call: sf-api.get-cluster-health\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes\n      name: nodes\n      description: Cluster node management\n      operations:\n      - method: GET\n        name: list-nodes\n        description: List all nodes in the cluster\n        call: sf-api.get-node-info-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes/{node_name}\n      name: node\n      description: Individual node information\n      operations:\n      - method: GET\n        name: get-node\n        description: Get information for a specific cluster node\n        call: sf-api.get-node-info\n        with:\n          nodeName: rest.node_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description:\
  \ Application lifecycle management\n      operations:\n      - method: GET\n        name: list-applications\n        description: List all deployed applications\n        call: sf-api.get-application-info-list\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-application\n        description: Deploy a new application\n        call: sf-api.create-application\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{application_id}\n      name: application\n      description: Individual application management\n      operations:\n      - method: GET\n        name: get-application\n        description: Get information for a specific application\n        call: sf-api.get-application-info\n        with:\n          applicationId: rest.application_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-application\n\
  \        description: Delete a deployed application\n        call: sf-api.delete-application\n        with:\n          applicationId: rest.application_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{application_id}/health\n      name: application-health\n      description: Application health monitoring\n      operations:\n      - method: GET\n        name: get-application-health\n        description: Get health state for an application and its services\n        call: sf-api.get-application-health\n        with:\n          applicationId: rest.application_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{application_id}/services\n      name: services\n      description: Service management within an application\n      operations:\n      - method: GET\n        name: list-services\n        description: List services within an application\n        call: sf-api.get-service-info-list\n\
  \        with:\n          applicationId: rest.application_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sf-cluster-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Service Fabric cluster management and health monitoring.\n    tools:\n    - name: get-cluster-health\n      description: Get the overall health state of the Service Fabric cluster. Returns aggregated health state (Ok/Warning/Error)\n        plus per-node and per-application health states.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sf-api.get-cluster-health\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nodes\n      description: List all nodes in the Service Fabric cluster. Filter by node status (up, down, all). Includes node name,\n        IP, node type, and health state.\n      hints:\n        readOnly: true\n        idempotent: true\n      call:\
  \ sf-api.get-node-info-list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-node-info\n      description: Get detailed information about a specific cluster node by name\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sf-api.get-node-info\n      with:\n        nodeName: tools.node_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-applications\n      description: List all applications deployed in the Service Fabric cluster. Optionally filter by application type name.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sf-api.get-application-info-list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application-info\n      description: Get detailed information about a specific deployed application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sf-api.get-application-info\n      with:\n        applicationId:\
  \ tools.application_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application\n      description: Deploy a new Service Fabric application to the cluster. Requires the application type to be provisioned\n        first. Provide Name (fabric:/MyApp), TypeName, and TypeVersion.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sf-api.create-application\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-application\n      description: Delete a deployed Service Fabric application and all its services. Use ForceRemove=true only when the application\n        is stuck in a deleting state.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sf-api.delete-application\n      with:\n        applicationId: tools.application_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application-health\n      description:\
  \ Get the health state of a specific application, including per-service health rollups and any active health\n        events.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sf-api.get-application-health\n      with:\n        applicationId: tools.application_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-services\n      description: List all services within a specific Service Fabric application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sf-api.get-service-info-list\n      with:\n        applicationId: tools.application_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/service-fabric/refs/heads/main/capabilities/cluster-management.yaml
tags:
- Distributed Systems
- Cluster Management
- Application Lifecycle
- Health Monitoring
- Microservices
- Azure
tools:
- description: Get the overall health state of the Service Fabric cluster. Returns aggregated health state (Ok/Warning/Error) plus per-node and per-application health states.
  hints:
    idempotent: true
    readOnly: true
  name: get-cluster-health
- description: List all nodes in the Service Fabric cluster. Filter by node status (up, down, all). Includes node name, IP, node type, and health state.
  hints:
    idempotent: true
    readOnly: true
  name: list-nodes
- description: Get detailed information about a specific cluster node by name
  hints:
    idempotent: true
    readOnly: true
  name: get-node-info
- description: List all applications deployed in the Service Fabric cluster. Optionally filter by application type name.
  hints:
    idempotent: true
    readOnly: true
  name: list-applications
- description: Get detailed information about a specific deployed application
  hints:
    idempotent: true
    readOnly: true
  name: get-application-info
- description: Deploy a new Service Fabric application to the cluster. Requires the application type to be provisioned first. Provide Name (fabric:/MyApp), TypeName, and TypeVersion.
  hints:
    idempotent: false
    readOnly: false
  name: create-application
- description: Delete a deployed Service Fabric application and all its services. Use ForceRemove=true only when the application is stuck in a deleting state.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-application
- description: Get the health state of a specific application, including per-service health rollups and any active health events.
  hints:
    idempotent: true
    readOnly: true
  name: get-application-health
- description: List all services within a specific Service Fabric application
  hints:
    idempotent: true
    readOnly: true
  name: list-services
---
