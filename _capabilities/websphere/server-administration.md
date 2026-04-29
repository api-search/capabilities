---
categories: []
consumed_apis:
- admin-rest
- liberty-admin
- rest-connector
- collective-controller
description: Unified workflow for administering WebSphere Application Server and Liberty environments, combining traditional admin, Liberty admin, collective controller, and JMX connector APIs for platform administrators.
layout: capability
name: WebSphere Server Administration
operations:
- description: List applications on traditional WAS
  method: GET
  name: list-was-applications
  path: /v1/applications
- description: List applications on Liberty
  method: GET
  name: list-liberty-applications
  path: /v1/applications
- description: List WAS servers
  method: GET
  name: list-servers
  path: /v1/servers
- description: Get Liberty server information
  method: GET
  name: get-liberty-server-info
  path: /v1/servers
- description: List WAS clusters
  method: GET
  name: list-was-clusters
  path: /v1/clusters
- description: List Liberty collective clusters
  method: GET
  name: list-collective-clusters
  path: /v1/clusters
- description: List collective members
  method: GET
  name: list-members
  path: /v1/members
- description: List WAS configuration resource types
  method: GET
  name: get-was-config
  path: /v1/configuration
- description: Get Liberty server configuration
  method: GET
  name: get-liberty-config
  path: /v1/configuration
- description: List registered MBeans
  method: GET
  name: list-mbeans
  path: /v1/mbeans
- description: List installed Liberty features
  method: GET
  name: list-features
  path: /v1/features
personas: []
provider_name: IBM WebSphere
provider_slug: websphere
search_terms:
- was start server
- list applications on traditional was
- server management
- was list applications
- liberty list applications
- list liberty applications
- cloud native
- list applications on liberty
- j2ee
- stop a was server
- list liberty collective clusters
- get liberty health
- was stop server
- list registered mbeans
- list installed liberty features
- list was clusters
- get liberty server info
- get liberty server configuration
- liberty feature management
- list mbeans
- list deployed applications on traditional websphere
- list jmx mbeans via rest connector
- application server
- list members
- get liberty server runtime information
- get collective controller information
- get was server health status
- list was applications
- microservices
- jmx mbean access
- get liberty config
- list was servers in the cell
- start a was server
- get liberty health check results
- collective member management
- server configuration
- administration
- list deployed applications on liberty
- get liberty server information
- cluster management
- was list servers
- list liberty collective members
- get controller info
- middleware
- list servers
- get was config
- enterprise java
- list was configuration resource types
- liberty get server info
- list features
- list collective members
- list clusters in liberty collective
- ibm websphere
- liberty
- application lifecycle management across was and liberty
- list collective clusters
- get was health
- list was servers
slug: server-administration
source_filename: server-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WebSphere Server Administration\"\n  description: \"Unified workflow for administering WebSphere Application Server and Liberty environments, combining traditional admin, Liberty admin, collective controller, and JMX connector APIs for platform administrators.\"\n  tags:\n    - IBM WebSphere\n    - Administration\n    - Server Management\n    - Liberty\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEBSPHERE_USERNAME: WEBSPHERE_USERNAME\n      WEBSPHERE_PASSWORD: WEBSPHERE_PASSWORD\n      LIBERTY_USERNAME: LIBERTY_USERNAME\n      LIBERTY_PASSWORD: LIBERTY_PASSWORD\n\ncapability:\n  consumes:\n    - import: admin-rest\n      location: ./shared/admin-rest.yaml\n    - import: liberty-admin\n      location: ./shared/liberty-admin.yaml\n    - import: rest-connector\n      location: ./shared/rest-connector.yaml\n    - import: collective-controller\n      location: ./shared/collective-controller.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: server-admin-api\n      description: \"Unified REST API for WebSphere server administration.\"\n      resources:\n        - path: /v1/applications\n          name: applications\n          description: \"Application lifecycle management across WAS and Liberty\"\n          operations:\n            - method: GET\n              name: list-was-applications\n              description: \"List applications on traditional WAS\"\n              call: \"admin-rest.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-liberty-applications\n              description: \"List applications on Liberty\"\n              call: \"liberty-admin.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/servers\n          name: servers\n        \
  \  description: \"Server management\"\n          operations:\n            - method: GET\n              name: list-servers\n              description: \"List WAS servers\"\n              call: \"admin-rest.list-servers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-liberty-server-info\n              description: \"Get Liberty server information\"\n              call: \"liberty-admin.get-server-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters\n          name: clusters\n          description: \"Cluster management\"\n          operations:\n            - method: GET\n              name: list-was-clusters\n              description: \"List WAS clusters\"\n              call: \"admin-rest.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n            - method: GET\n              name: list-collective-clusters\n              description: \"List Liberty collective clusters\"\n              call: \"collective-controller.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/members\n          name: members\n          description: \"Collective member management\"\n          operations:\n            - method: GET\n              name: list-members\n              description: \"List collective members\"\n              call: \"collective-controller.list-members\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/configuration\n          name: configuration\n          description: \"Server configuration\"\n          operations:\n            - method: GET\n              name: get-was-config\n              description: \"List WAS configuration resource types\"\n              call:\
  \ \"admin-rest.list-config-resources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-liberty-config\n              description: \"Get Liberty server configuration\"\n              call: \"liberty-admin.get-server-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/mbeans\n          name: mbeans\n          description: \"JMX MBean access\"\n          operations:\n            - method: GET\n              name: list-mbeans\n              description: \"List registered MBeans\"\n              call: \"rest-connector.list-mbeans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/features\n          name: features\n          description: \"Liberty feature management\"\n          operations:\n            - method: GET\n              name: list-features\n\
  \              description: \"List installed Liberty features\"\n              call: \"liberty-admin.list-features\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: server-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WebSphere server administration.\"\n      tools:\n        - name: was-list-applications\n          description: \"List deployed applications on traditional WebSphere\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"admin-rest.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: liberty-list-applications\n          description: \"List deployed applications on Liberty\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liberty-admin.list-applications\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: was-list-servers\n          description: \"List WAS servers in the cell\"\n          hints:\n            readOnly: true\n          call: \"admin-rest.list-servers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: liberty-get-server-info\n          description: \"Get Liberty server runtime information\"\n          hints:\n            readOnly: true\n          call: \"liberty-admin.get-server-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: was-start-server\n          description: \"Start a WAS server\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"admin-rest.start-server\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: was-stop-server\n\
  \          description: \"Stop a WAS server\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"admin-rest.stop-server\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-collective-members\n          description: \"List Liberty collective members\"\n          hints:\n            readOnly: true\n          call: \"collective-controller.list-members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-collective-clusters\n          description: \"List clusters in Liberty collective\"\n          hints:\n            readOnly: true\n          call: \"collective-controller.list-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-controller-info\n          description: \"Get collective controller information\"\
  \n          hints:\n            readOnly: true\n          call: \"collective-controller.get-controller-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-mbeans\n          description: \"List JMX MBeans via REST connector\"\n          hints:\n            readOnly: true\n          call: \"rest-connector.list-mbeans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-features\n          description: \"List installed Liberty features\"\n          hints:\n            readOnly: true\n          call: \"liberty-admin.list-features\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-liberty-config\n          description: \"Get Liberty server configuration\"\n          hints:\n            readOnly: true\n          call: \"liberty-admin.get-server-config\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-was-health\n          description: \"Get WAS server health status\"\n          hints:\n            readOnly: true\n          call: \"admin-rest.get-health-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-liberty-health\n          description: \"Get Liberty health check results\"\n          hints:\n            readOnly: true\n          call: \"liberty-admin.get-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/websphere/refs/heads/main/capabilities/server-administration.yaml
tags:
- IBM WebSphere
- Administration
- Server Management
- Liberty
tools:
- description: List deployed applications on traditional WebSphere
  hints:
    openWorld: true
    readOnly: true
  name: was-list-applications
- description: List deployed applications on Liberty
  hints:
    openWorld: true
    readOnly: true
  name: liberty-list-applications
- description: List WAS servers in the cell
  hints:
    readOnly: true
  name: was-list-servers
- description: Get Liberty server runtime information
  hints:
    readOnly: true
  name: liberty-get-server-info
- description: Start a WAS server
  hints:
    idempotent: true
    readOnly: false
  name: was-start-server
- description: Stop a WAS server
  hints:
    idempotent: true
    readOnly: false
  name: was-stop-server
- description: List Liberty collective members
  hints:
    readOnly: true
  name: list-collective-members
- description: List clusters in Liberty collective
  hints:
    readOnly: true
  name: list-collective-clusters
- description: Get collective controller information
  hints:
    readOnly: true
  name: get-controller-info
- description: List JMX MBeans via REST connector
  hints:
    readOnly: true
  name: list-mbeans
- description: List installed Liberty features
  hints:
    readOnly: true
  name: list-features
- description: Get Liberty server configuration
  hints:
    readOnly: true
  name: get-liberty-config
- description: Get WAS server health status
  hints:
    readOnly: true
  name: get-was-health
- description: Get Liberty health check results
  hints:
    readOnly: true
  name: get-liberty-health
---
