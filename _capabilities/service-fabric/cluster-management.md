---
categories: []
consumed_apis:
- sf-api
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
- list services
- get detailed information about a specific cluster node by name
- get cluster health
- individual application management
- cluster management
- get application info
- list applications
- service management within an application
- get health state for an application and its services
- list all applications deployed in the service fabric cluster. optionally filter by application type name.
- open source
- application lifecycle
- individual node information
- azure
- cloud native
- health monitoring
- kubernetes
- cluster node management
- application lifecycle management
- get application
- list nodes
- delete a deployed service fabric application and all its services. use forceremove=true only when the application is stuck in a deleting state.
- overall cluster health state
- get information for a specific cluster node
- get application health
- list services within an application
- get detailed information about a specific deployed application
- list all nodes in the cluster
- deploy a new service fabric application to the cluster. requires the application type to be provisioned first. provide name (fabric:/myapp), typename, and typeversion.
- get the health state of a specific application, including per-service health rollups and any active health events.
- get node
- distributed systems
- containers
- delete a deployed application
- get the overall health state of the service fabric cluster. returns aggregated health state (ok/warning/error) plus per-node and per-application health states.
- get the aggregated health state of the cluster
- microservices
- get node info
- list all nodes in the service fabric cluster. filter by node status (up, down, all). includes node name, ip, node type, and health state.
- get information for a specific application
- list all services within a specific service fabric application
- list all deployed applications
- deploy a new application
- delete application
- application health monitoring
- create application
slug: cluster-management
source_filename: cluster-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Service Fabric Cluster Management\"\n  description: >-\n    Unified capability for managing Azure Service Fabric clusters, including\n    application lifecycle, node management, service monitoring, and cluster health.\n    Enables platform engineers and SREs to deploy applications, monitor cluster health,\n    and manage the Service Fabric runtime via REST API.\n  tags:\n    - Distributed Systems\n    - Cluster Management\n    - Application Lifecycle\n    - Health Monitoring\n    - Microservices\n    - Azure\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SF_CLUSTER_ENDPOINT: SF_CLUSTER_ENDPOINT\n\ncapability:\n  consumes:\n    - import: sf-api\n      location: ./shared/service-fabric-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sf-cluster-management-api\n      description: \"Unified REST API for Service Fabric cluster and application management.\"\
  \n      resources:\n        - path: /v1/cluster/health\n          name: cluster-health\n          description: \"Overall cluster health state\"\n          operations:\n            - method: GET\n              name: get-cluster-health\n              description: \"Get the aggregated health state of the cluster\"\n              call: \"sf-api.get-cluster-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nodes\n          name: nodes\n          description: \"Cluster node management\"\n          operations:\n            - method: GET\n              name: list-nodes\n              description: \"List all nodes in the cluster\"\n              call: \"sf-api.get-node-info-list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nodes/{node_name}\n          name: node\n          description: \"Individual node information\"\n          operations:\n\
  \            - method: GET\n              name: get-node\n              description: \"Get information for a specific cluster node\"\n              call: \"sf-api.get-node-info\"\n              with:\n                nodeName: \"rest.node_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications\n          name: applications\n          description: \"Application lifecycle management\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all deployed applications\"\n              call: \"sf-api.get-application-info-list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-application\n              description: \"Deploy a new application\"\n              call: \"sf-api.create-application\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{application_id}\n          name: application\n          description: \"Individual application management\"\n          operations:\n            - method: GET\n              name: get-application\n              description: \"Get information for a specific application\"\n              call: \"sf-api.get-application-info\"\n              with:\n                applicationId: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-application\n              description: \"Delete a deployed application\"\n              call: \"sf-api.delete-application\"\n              with:\n                applicationId: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{application_id}/health\n\
  \          name: application-health\n          description: \"Application health monitoring\"\n          operations:\n            - method: GET\n              name: get-application-health\n              description: \"Get health state for an application and its services\"\n              call: \"sf-api.get-application-health\"\n              with:\n                applicationId: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications/{application_id}/services\n          name: services\n          description: \"Service management within an application\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List services within an application\"\n              call: \"sf-api.get-service-info-list\"\n              with:\n                applicationId: \"rest.application_id\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sf-cluster-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Service Fabric cluster management and health monitoring.\"\n      tools:\n        - name: get-cluster-health\n          description: >-\n            Get the overall health state of the Service Fabric cluster. Returns\n            aggregated health state (Ok/Warning/Error) plus per-node and\n            per-application health states.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sf-api.get-cluster-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-nodes\n          description: >-\n            List all nodes in the Service Fabric cluster. Filter by node status\n            (up, down, all). Includes node name, IP, node type, and health state.\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"sf-api.get-node-info-list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-node-info\n          description: \"Get detailed information about a specific cluster node by name\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sf-api.get-node-info\"\n          with:\n            nodeName: \"tools.node_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-applications\n          description: >-\n            List all applications deployed in the Service Fabric cluster.\n            Optionally filter by application type name.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sf-api.get-application-info-list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-application-info\n\
  \          description: \"Get detailed information about a specific deployed application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sf-api.get-application-info\"\n          with:\n            applicationId: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-application\n          description: >-\n            Deploy a new Service Fabric application to the cluster. Requires the\n            application type to be provisioned first. Provide Name (fabric:/MyApp),\n            TypeName, and TypeVersion.\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sf-api.create-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-application\n          description: >-\n            Delete a deployed Service Fabric application and all its services.\n\
  \            Use ForceRemove=true only when the application is stuck in a deleting state.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"sf-api.delete-application\"\n          with:\n            applicationId: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-application-health\n          description: >-\n            Get the health state of a specific application, including per-service\n            health rollups and any active health events.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sf-api.get-application-health\"\n          with:\n            applicationId: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-services\n          description: \"List all services within a specific Service\
  \ Fabric application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sf-api.get-service-info-list\"\n          with:\n            applicationId: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
