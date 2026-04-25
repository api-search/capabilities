---
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
- get liberty server runtime information
- list clusters in liberty collective
- liberty
- list liberty applications
- list was servers
- application lifecycle management across was and liberty
- get liberty server information
- list members
- stop a was server
- middleware
- list was servers in the cell
- administration
- get was health
- get liberty server info
- list mbeans
- list jmx mbeans via rest connector
- was list applications
- list applications on traditional was
- list applications on liberty
- list liberty collective members
- liberty list applications
- get was server health status
- application server
- cloud native
- list deployed applications on traditional websphere
- list collective clusters
- get was config
- list deployed applications on liberty
- list was applications
- microservices
- list registered mbeans
- list liberty collective clusters
- list was configuration resource types
- was start server
- cluster management
- list collective members
- get liberty server configuration
- jmx mbean access
- list installed liberty features
- ibm websphere
- server management
- get liberty health check results
- collective member management
- server configuration
- enterprise java
- list features
- start a was server
- liberty get server info
- get collective controller information
- get liberty config
- list servers
- get controller info
- liberty feature management
- was list servers
- get liberty health
- j2ee
- was stop server
- list was clusters
slug: server-administration
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
