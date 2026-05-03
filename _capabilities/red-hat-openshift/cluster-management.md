---
categories: []
consumed_apis:
- openshift-api
- openshift-cluster-mgr
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
- create cluster
- delete an openshift project and all resources within it
- cluster management
- route management for exposing services
- list projects
- delete an openshift project
- create route
- list available versions
- list openshift projects (namespaces) the current user can access
- hybrid cloud
- create project
- delete project
- create a new openshift project with default rbac policies
- create a route to expose a service with a hostname and optional tls
- list builds
- create an openshift project
- get details, status, and api endpoint for an openshift cluster
- kubernetes
- list http/https routes exposing services in a namespace
- list cluster addons
- list routes
- list available openshift versions for cluster creation or upgrade
- individual cluster management
- managed openshift cluster fleet
- list machine pools
- create a new openshift cluster
- red hat
- list openshift projects
- list builds in a namespace
- create a route to expose a service
- enterprise
- get cluster
- list installed add-ons for an openshift cluster
- containers
- get project details
- list all managed openshift clusters
- list compute node machine pools for an openshift cluster
- get cluster details and status
- paas
- list clusters
- get details and status of an openshift project
- individual project management
- openshift
- delete an openshift cluster
- delete cluster
- get project
- list routes in a namespace
- openshift project management
- list all managed openshift clusters across cloud providers
- build management
- list builds in an openshift namespace
slug: cluster-management
source_filename: cluster-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Red Hat OpenShift Cluster Management\"\n  description: >-\n    Unified capability for managing OpenShift clusters and workloads. Combines\n    the OpenShift Container Platform API for namespace and workload management\n    with the Cluster Manager API for fleet-level cluster lifecycle operations.\n    Used by platform engineers and SRE teams to provision clusters, manage\n    namespaces, deploy routes, and monitor builds.\n  tags:\n    - Cluster Management\n    - Containers\n    - Kubernetes\n    - OpenShift\n    - Red Hat\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      OPENSHIFT_API_TOKEN: OPENSHIFT_API_TOKEN\n      OPENSHIFT_API_URL: OPENSHIFT_API_URL\n      OCM_API_TOKEN: OCM_API_TOKEN\n\ncapability:\n  consumes:\n    - import: openshift-api\n      location: ./shared/openshift-api.yaml\n    - import: openshift-cluster-mgr\n      location: ./shared/cluster-manager-api.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: openshift-cluster-mgmt-rest\n      description: \"Unified REST API for OpenShift cluster and workload management.\"\n      resources:\n        - path: /v1/clusters\n          name: clusters\n          description: \"Managed OpenShift cluster fleet\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description: \"List all managed OpenShift clusters\"\n              call: \"openshift-cluster-mgr.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cluster\n              description: \"Create a new OpenShift cluster\"\n              call: \"openshift-cluster-mgr.create-cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{id}\n          name: cluster\n          description:\
  \ \"Individual cluster management\"\n          operations:\n            - method: GET\n              name: get-cluster\n              description: \"Get cluster details and status\"\n              call: \"openshift-cluster-mgr.get-cluster\"\n              with:\n                cluster_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-cluster\n              description: \"Delete an OpenShift cluster\"\n              call: \"openshift-cluster-mgr.delete-cluster\"\n              with:\n                cluster_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects\n          name: projects\n          description: \"OpenShift project management\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List OpenShift projects\"\
  \n              call: \"openshift-api.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create an OpenShift project\"\n              call: \"openshift-api.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{name}\n          name: project\n          description: \"Individual project management\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get project details\"\n              call: \"openshift-api.get-project\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-project\n              description: \"Delete an\
  \ OpenShift project\"\n              call: \"openshift-api.delete-project\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/namespaces/{namespace}/routes\n          name: routes\n          description: \"Route management for exposing services\"\n          operations:\n            - method: GET\n              name: list-routes\n              description: \"List routes in a namespace\"\n              call: \"openshift-api.list-routes\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-route\n              description: \"Create a route to expose a service\"\n              call: \"openshift-api.create-route\"\n              with:\n                namespace: \"rest.namespace\"\n            \
  \  outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/namespaces/{namespace}/builds\n          name: builds\n          description: \"Build management\"\n          operations:\n            - method: GET\n              name: list-builds\n              description: \"List builds in a namespace\"\n              call: \"openshift-api.list-builds\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: openshift-cluster-mgmt-mcp\n      transport: http\n      description: \"MCP server for AI-assisted OpenShift cluster and workload management.\"\n      tools:\n        - name: list-clusters\n          description: \"List all managed OpenShift clusters across cloud providers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"openshift-cluster-mgr.list-clusters\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cluster\n          description: \"Get details, status, and API endpoint for an OpenShift cluster\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"openshift-cluster-mgr.get-cluster\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cluster-addons\n          description: \"List installed add-ons for an OpenShift cluster\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"openshift-cluster-mgr.list-addons\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-machine-pools\n          description: \"List compute node machine pools for an OpenShift cluster\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"openshift-cluster-mgr.list-machine-pools\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: \"List OpenShift projects (namespaces) the current user can access\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"openshift-api.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-project\n          description: \"Create a new OpenShift project with default RBAC policies\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"openshift-api.create-project\"\n          with:\n            project_name: \"tools.project_name\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n        - name: get-project\n          description: \"Get details and status of an OpenShift project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"openshift-api.get-project\"\n          with:\n            name: \"tools.project_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-project\n          description: \"Delete an OpenShift project and all resources within it\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"openshift-api.delete-project\"\n          with:\n            name: \"tools.project_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-routes\n          description: \"List HTTP/HTTPS routes exposing services in a namespace\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"openshift-api.list-routes\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-route\n          description: \"Create a route to expose a service with a hostname and optional TLS\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"openshift-api.create-route\"\n          with:\n            namespace: \"tools.namespace\"\n            route_name: \"tools.route_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-builds\n          description: \"List builds in an OpenShift namespace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"openshift-api.list-builds\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: list-available-versions\n          description: \"List available OpenShift versions for cluster creation or upgrade\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"openshift-cluster-mgr.list-versions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
