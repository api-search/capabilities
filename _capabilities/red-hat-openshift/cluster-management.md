---
categories: []
consumed_apis: []
description: Unified capability for managing OpenShift clusters and workloads. Combines the OpenShift Container Platform API for namespace and workload management with the Cluster Manager API for fleet-level cluster lifecycle operations. Used by platform engineers and SRE teams to provision clusters, manage namespaces, deploy routes, and monitor builds.
layout: capability
name: Red Hat OpenShift Cluster Management
operations:
- description: List all managed OpenShift clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Create a new OpenShift cluster
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: Get cluster details and status
  method: GET
  name: get-cluster
  path: /v1/clusters/{id}
- description: Delete an OpenShift cluster
  method: DELETE
  name: delete-cluster
  path: /v1/clusters/{id}
- description: List OpenShift projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create an OpenShift project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get project details
  method: GET
  name: get-project
  path: /v1/projects/{name}
- description: Delete an OpenShift project
  method: DELETE
  name: delete-project
  path: /v1/projects/{name}
- description: List routes in a namespace
  method: GET
  name: list-routes
  path: /v1/namespaces/{namespace}/routes
- description: Create a route to expose a service
  method: POST
  name: create-route
  path: /v1/namespaces/{namespace}/routes
- description: List builds in a namespace
  method: GET
  name: list-builds
  path: /v1/namespaces/{namespace}/builds
personas: []
provider_name: Red Hat OpenShift
provider_slug: red-hat-openshift
search_terms:
- get details, status, and api endpoint for an openshift cluster
- containers
- get cluster
- build management
- list all managed openshift clusters
- individual cluster management
- route management for exposing services
- red hat
- list installed add-ons for an openshift cluster
- list machine pools
- create a route to expose a service with a hostname and optional tls
- delete an openshift project and all resources within it
- paas
- individual project management
- create route
- delete an openshift cluster
- create an openshift project
- list all managed openshift clusters across cloud providers
- delete cluster
- list compute node machine pools for an openshift cluster
- list clusters
- create project
- list projects
- kubernetes
- create a new openshift cluster
- list openshift projects
- delete project
- list routes in a namespace
- create a new openshift project with default rbac policies
- openshift project management
- list routes
- get details and status of an openshift project
- list builds
- list http/https routes exposing services in a namespace
- list available openshift versions for cluster creation or upgrade
- get cluster details and status
- cluster management
- list openshift projects (namespaces) the current user can access
- enterprise
- get project details
- delete an openshift project
- managed openshift cluster fleet
- openshift
- create cluster
- get project
- hybrid cloud
- create a route to expose a service
- list available versions
- list cluster addons
- list builds in an openshift namespace
- list builds in a namespace
slug: cluster-management
source_filename: cluster-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Red Hat OpenShift Cluster Management\n  description: Unified capability for managing OpenShift clusters and workloads. Combines the OpenShift Container Platform\n    API for namespace and workload management with the Cluster Manager API for fleet-level cluster lifecycle operations. Used\n    by platform engineers and SRE teams to provision clusters, manage namespaces, deploy routes, and monitor builds.\n  tags:\n  - Cluster Management\n  - Containers\n  - Kubernetes\n  - OpenShift\n  - Red Hat\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    OPENSHIFT_API_TOKEN: OPENSHIFT_API_TOKEN\n    OPENSHIFT_API_URL: OPENSHIFT_API_URL\n    OCM_API_TOKEN: OCM_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: openshift-api\n    baseUri: '{{OPENSHIFT_API_URL}}'\n    description: OpenShift Container Platform REST API\n    authentication:\n      type: bearer\n      token: '{{OPENSHIFT_API_TOKEN}}'\n\
  \    resources:\n    - name: projects\n      path: /apis/project.openshift.io/v1/projects\n      description: OpenShift project management\n      operations:\n      - name: list-projects\n        method: GET\n        description: List OpenShift projects accessible to the current user\n        inputParameters:\n        - name: labelSelector\n          in: query\n          type: string\n          required: false\n          description: Label selector to filter projects\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of projects to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new OpenShift project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            apiVersion: project.openshift.io/v1\n            kind: Project\n            metadata:\n              name: '{{tools.project_name}}'\n    - name: project\n      path: /apis/project.openshift.io/v1/projects/{name}\n      description: Individual OpenShift project\n      operations:\n      - name: get-project\n        method: GET\n        description: Get OpenShift project details\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        description: Delete an OpenShift project\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Project name\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes\n      path: /apis/route.openshift.io/v1/namespaces/{namespace}/routes\n      description: OpenShift route management\n      operations:\n      - name: list-routes\n        method: GET\n        description: List routes in a namespace\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace to list routes in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-route\n        method: POST\n        description: Create a new route to expose a service\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace to create route in\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiVersion: route.openshift.io/v1\n            kind: Route\n            metadata:\n              name: '{{tools.route_name}}'\n              namespace: '{{tools.namespace}}'\n    - name: builds\n      path: /apis/build.openshift.io/v1/namespaces/{namespace}/builds\n      description: OpenShift build management\n      operations:\n      - name: list-builds\n        method: GET\n        description: List builds in a namespace\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace to list builds in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: openshift-cluster-mgr\n    baseUri: https://api.openshift.com\n    description: OpenShift Cluster Manager\
  \ API via Red Hat Hybrid Cloud Console\n    authentication:\n      type: bearer\n      token: '{{OCM_API_TOKEN}}'\n    resources:\n    - name: clusters\n      path: /api/clusters_mgmt/v1/clusters\n      description: OpenShift cluster lifecycle management\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List all OpenShift clusters\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: SQL-like search filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description:\
  \ Create a new OpenShift cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.cluster_name}}'\n            cloud_provider:\n              id: '{{tools.cloud_provider}}'\n            region:\n              id: '{{tools.region}}'\n    - name: cluster\n      path: /api/clusters_mgmt/v1/clusters/{cluster_id}\n      description: Individual cluster management\n      operations:\n      - name: get-cluster\n        method: GET\n        description: Get cluster details and status\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-cluster\n        method: DELETE\n        description:\
  \ Delete an OpenShift cluster\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: addons\n      path: /api/clusters_mgmt/v1/clusters/{cluster_id}/addons\n      description: Cluster add-on management\n      operations:\n      - name: list-addons\n        method: GET\n        description: List installed add-ons for a cluster\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: machine-pools\n      path: /api/clusters_mgmt/v1/clusters/{cluster_id}/machine_pools\n      description: Cluster machine pool management\n\
  \      operations:\n      - name: list-machine-pools\n        method: GET\n        description: List machine pools for a cluster\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: versions\n      path: /api/clusters_mgmt/v1/versions\n      description: Available OpenShift versions\n      operations:\n      - name: list-versions\n        method: GET\n        description: List available OpenShift versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openshift-cluster-mgmt-rest\n    description: Unified REST API for OpenShift cluster and workload management.\n    resources:\n    - path: /v1/clusters\n    \
  \  name: clusters\n      description: Managed OpenShift cluster fleet\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List all managed OpenShift clusters\n        call: openshift-cluster-mgr.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cluster\n        description: Create a new OpenShift cluster\n        call: openshift-cluster-mgr.create-cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{id}\n      name: cluster\n      description: Individual cluster management\n      operations:\n      - method: GET\n        name: get-cluster\n        description: Get cluster details and status\n        call: openshift-cluster-mgr.get-cluster\n        with:\n          cluster_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-cluster\n\
  \        description: Delete an OpenShift cluster\n        call: openshift-cluster-mgr.delete-cluster\n        with:\n          cluster_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: OpenShift project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List OpenShift projects\n        call: openshift-api.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create an OpenShift project\n        call: openshift-api.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{name}\n      name: project\n      description: Individual project management\n      operations:\n      - method: GET\n        name: get-project\n        description: Get project details\n        call: openshift-api.get-project\n\
  \        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-project\n        description: Delete an OpenShift project\n        call: openshift-api.delete-project\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/routes\n      name: routes\n      description: Route management for exposing services\n      operations:\n      - method: GET\n        name: list-routes\n        description: List routes in a namespace\n        call: openshift-api.list-routes\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-route\n        description: Create a route to expose a service\n        call: openshift-api.create-route\n        with:\n          namespace: rest.namespace\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/builds\n      name: builds\n      description: Build management\n      operations:\n      - method: GET\n        name: list-builds\n        description: List builds in a namespace\n        call: openshift-api.list-builds\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: openshift-cluster-mgmt-mcp\n    transport: http\n    description: MCP server for AI-assisted OpenShift cluster and workload management.\n    tools:\n    - name: list-clusters\n      description: List all managed OpenShift clusters across cloud providers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openshift-cluster-mgr.list-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster\n      description: Get details, status, and API endpoint for\
  \ an OpenShift cluster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openshift-cluster-mgr.get-cluster\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cluster-addons\n      description: List installed add-ons for an OpenShift cluster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openshift-cluster-mgr.list-addons\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-machine-pools\n      description: List compute node machine pools for an OpenShift cluster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openshift-cluster-mgr.list-machine-pools\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List OpenShift projects (namespaces)\
  \ the current user can access\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openshift-api.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new OpenShift project with default RBAC policies\n      hints:\n        readOnly: false\n        openWorld: false\n      call: openshift-api.create-project\n      with:\n        project_name: tools.project_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get details and status of an OpenShift project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openshift-api.get-project\n      with:\n        name: tools.project_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-project\n      description: Delete an OpenShift project and all resources within it\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: openshift-api.delete-project\n      with:\n        name: tools.project_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-routes\n      description: List HTTP/HTTPS routes exposing services in a namespace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openshift-api.list-routes\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-route\n      description: Create a route to expose a service with a hostname and optional TLS\n      hints:\n        readOnly: false\n        openWorld: false\n      call: openshift-api.create-route\n      with:\n        namespace: tools.namespace\n        route_name: tools.route_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-builds\n      description: List builds in an OpenShift namespace\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: openshift-api.list-builds\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-available-versions\n      description: List available OpenShift versions for cluster creation or upgrade\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openshift-cluster-mgr.list-versions\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/red-hat-openshift/refs/heads/main/capabilities/cluster-management.yaml
tags:
- Cluster Management
- Containers
- Kubernetes
- OpenShift
- Red Hat
tools:
- description: List all managed OpenShift clusters across cloud providers
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: Get details, status, and API endpoint for an OpenShift cluster
  hints:
    openWorld: true
    readOnly: true
  name: get-cluster
- description: List installed add-ons for an OpenShift cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-cluster-addons
- description: List compute node machine pools for an OpenShift cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-machine-pools
- description: List OpenShift projects (namespaces) the current user can access
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Create a new OpenShift project with default RBAC policies
  hints:
    openWorld: false
    readOnly: false
  name: create-project
- description: Get details and status of an OpenShift project
  hints:
    openWorld: true
    readOnly: true
  name: get-project
- description: Delete an OpenShift project and all resources within it
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
- description: List HTTP/HTTPS routes exposing services in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-routes
- description: Create a route to expose a service with a hostname and optional TLS
  hints:
    openWorld: false
    readOnly: false
  name: create-route
- description: List builds in an OpenShift namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-builds
- description: List available OpenShift versions for cluster creation or upgrade
  hints:
    openWorld: true
    readOnly: true
  name: list-available-versions
---
