---
categories: []
consumed_apis: []
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
- get liberty server info
- liberty get server info
- get was health
- list liberty applications
- server configuration
- get liberty config
- list installed liberty features
- middleware
- list collective clusters
- collective member management
- list applications on liberty
- jmx mbean access
- list jmx mbeans via rest connector
- list deployed applications on traditional websphere
- liberty feature management
- get was server health status
- get liberty health
- get liberty server information
- cloud native
- j2ee
- list members
- list liberty collective clusters
- was stop server
- list was configuration resource types
- list deployed applications on liberty
- list registered mbeans
- was list servers
- list features
- list servers
- list was clusters
- administration
- list clusters in liberty collective
- start a was server
- get collective controller information
- list liberty collective members
- cluster management
- list applications on traditional was
- get controller info
- get liberty health check results
- enterprise java
- list was servers
- liberty list applications
- get was config
- list mbeans
- application lifecycle management across was and liberty
- was list applications
- get liberty server runtime information
- list was servers in the cell
- application server
- list collective members
- get liberty server configuration
- stop a was server
- list was applications
- microservices
- ibm websphere
- liberty
- server management
- was start server
slug: server-administration
source_filename: server-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WebSphere Server Administration\n  description: Unified workflow for administering WebSphere Application Server and Liberty environments, combining traditional\n    admin, Liberty admin, collective controller, and JMX connector APIs for platform administrators.\n  tags:\n  - IBM WebSphere\n  - Administration\n  - Server Management\n  - Liberty\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEBSPHERE_USERNAME: WEBSPHERE_USERNAME\n    WEBSPHERE_PASSWORD: WEBSPHERE_PASSWORD\n    LIBERTY_USERNAME: LIBERTY_USERNAME\n    LIBERTY_PASSWORD: LIBERTY_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: admin-rest\n    baseUri: https://localhost:9443/ibm/api\n    description: REST API for WebSphere Application Server administration\n    authentication:\n      type: basic\n      username: '{{WEBSPHERE_USERNAME}}'\n      password: '{{WEBSPHERE_PASSWORD}}'\n    resources:\n    - name: applications\n\
  \      path: /applications\n      description: Application deployment and lifecycle management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List deployed applications\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by application status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get application details\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-application\n        method: POST\n        description: Deploy a new application\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            contextRoot: '{{tools.contextRoot}}'\n            targetServer: '{{tools.targetServer}}'\n      - name: start-application\n        method: POST\n        description: Start a deployed application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-application\n        method: POST\n        description: Stop a running application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uninstall-application\n        method: DELETE\n        description: Uninstall a deployed application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: servers\n      path: /servers\n      description: Server configuration and management\n      operations:\n      - name: list-servers\n        method: GET\n        description: List all servers in the cell\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-server\n        method: GET\n        description: Get server details\n        inputParameters:\n        - name: serverName\n   \
  \       in: path\n          type: string\n          required: true\n          description: Server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-server\n        method: POST\n        description: Start a server\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-server\n        method: POST\n        description: Stop a server\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters\n\
  \      path: /clusters\n      description: Cluster management operations\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List all clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cluster\n        method: GET\n        description: Get cluster details\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-cluster\n        method: POST\n        description: Start all members of a cluster\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: stop-cluster\n        method: POST\n        description: Stop all members of a cluster\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /monitoring\n      description: Performance monitoring and health checks\n      operations:\n      - name: get-performance-data\n        method: GET\n        description: Get performance monitoring data\n        inputParameters:\n        - name: module\n          in: query\n          type: string\n          required: false\n          description: Performance module name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: get-health-status\n        method: GET\n        description: Get server health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /config\n      description: Server configuration management\n      operations:\n      - name: list-config-resources\n        method: GET\n        description: List configuration resource types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-config-resources\n        method: GET\n        description: List resources of a specific type\n        inputParameters:\n        - name: resourceType\n          in: path\n          type: string\n          required: true\n          description: Configuration resource type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  - type: http\n    namespace: liberty-admin\n    baseUri: https://localhost:9443/ibm/api\n    description: Liberty Admin REST API for server configuration and management\n    authentication:\n      type: basic\n      username: '{{LIBERTY_USERNAME}}'\n      password: '{{LIBERTY_PASSWORD}}'\n    resources:\n    - name: server\n      path: /server\n      description: Server runtime management\n      operations:\n      - name: get-server-info\n        method: GET\n        description: Get Liberty server information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-server-dump\n        method: POST\n        description: Create a server dump for diagnostics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            include: '{{tools.include}}'\n      - name:\
  \ create-java-dump\n        method: POST\n        description: Create a Java core dump\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: config\n      path: /config\n      description: Server configuration management\n      operations:\n      - name: get-server-config\n        method: GET\n        description: Get server configuration\n        inputParameters:\n        - name: depth\n          in: query\n          type: integer\n          required: false\n          description: Depth of nested elements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-server-config\n        method: PUT\n        description: Update server configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-config-element\n     \
  \   method: GET\n        description: Get a specific configuration element\n        inputParameters:\n        - name: elementName\n          in: path\n          type: string\n          required: true\n          description: Configuration element name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-config-element\n        method: POST\n        description: Create a configuration element\n        inputParameters:\n        - name: elementName\n          in: path\n          type: string\n          required: true\n          description: Configuration element name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-config-element\n        method: DELETE\n        description: Delete a configuration element\n        inputParameters:\n        - name: elementName\n          in: path\n          type: string\n\
  \          required: true\n          description: Configuration element name\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Element unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      description: Application deployment and lifecycle\n      operations:\n      - name: list-applications\n        method: GET\n        description: List deployed applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get application details\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-application\n        method: POST\n        description: Start an application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-application\n        method: POST\n        description: Stop an application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restart-application\n        method: POST\n        description: Restart an application\n        inputParameters:\n     \
  \   - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: features\n      path: /features\n      description: Liberty feature management\n      operations:\n      - name: list-features\n        method: GET\n        description: List installed features\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-feature\n        method: GET\n        description: Get feature details\n        inputParameters:\n        - name: featureName\n          in: path\n          type: string\n          required: true\n          description: Feature symbolic name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: logging\n\
  \      path: /logging\n      description: Log access and configuration\n      operations:\n      - name: get-log-config\n        method: GET\n        description: Get logging configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-log-config\n        method: PUT\n        description: Update logging configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-log-messages\n        method: GET\n        description: Get recent log messages\n        inputParameters:\n        - name: maxMessages\n          in: query\n          type: integer\n          required: false\n          description: Maximum messages to return\n        - name: level\n          in: query\n          type: string\n          required: false\n          description: Minimum log level\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /monitoring\n      description: Server monitoring and metrics\n      operations:\n      - name: get-metrics\n        method: GET\n        description: Get MicroProfile Metrics data\n        inputParameters:\n        - name: scope\n          in: query\n          type: string\n          required: false\n          description: Metrics scope (base, vendor, application)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-health\n        method: GET\n        description: Get MicroProfile Health check results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: rest-connector\n    baseUri: https://localhost:9443/IBMJMXConnectorREST/api\n    description: JMX REST Connector\
  \ for Liberty server MBean access\n    authentication:\n      type: basic\n      username: '{{LIBERTY_USERNAME}}'\n      password: '{{LIBERTY_PASSWORD}}'\n    resources:\n    - name: mbeans\n      path: /mbeans\n      description: JMX MBean operations\n      operations:\n      - name: list-mbeans\n        method: GET\n        description: List registered MBeans\n        inputParameters:\n        - name: objectName\n          in: query\n          type: string\n          required: false\n          description: ObjectName pattern filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-mbean-info\n        method: GET\n        description: Get MBean metadata\n        inputParameters:\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: JMX ObjectName\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: get-mbean-attributes\n        method: GET\n        description: Get MBean attribute values\n        inputParameters:\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: JMX ObjectName\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invoke-mbean-operation\n        method: POST\n        description: Invoke an MBean operation\n        inputParameters:\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: JMX ObjectName\n        - name: operationName\n          in: path\n          type: string\n          required: true\n          description: Operation name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notifications\n\
  \      path: /notifications\n      description: JMX notification subscriptions\n      operations:\n      - name: list-notification-subscriptions\n        method: GET\n        description: List notification subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-notification-subscription\n        method: POST\n        description: Subscribe to MBean notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            objectName: '{{tools.objectName}}'\n      - name: get-notifications\n        method: GET\n        description: Get pending notifications\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-notification-subscription\n        method: DELETE\n        description: Delete a notification subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: collective-controller\n    baseUri: https://localhost:9443/ibm/api/collective\n    description: Liberty Collective Controller REST API\n    authentication:\n      type: basic\n      username: '{{LIBERTY_USERNAME}}'\n      password: '{{LIBERTY_PASSWORD}}'\n    resources:\n    - name: members\n      path: /members\n      description: Collective member management\n      operations:\n      - name: list-members\n        method: GET\n        description:\
  \ List collective members\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by member status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-member\n        method: GET\n        description: Get member details\n        inputParameters:\n        - name: memberName\n          in: path\n          type: string\n          required: true\n          description: Member server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-member\n        method: POST\n        description: Start a collective member\n        inputParameters:\n        - name: memberName\n          in: path\n          type: string\n          required: true\n          description: Member server name\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-member\n        method: POST\n        description: Stop a collective member\n        inputParameters:\n        - name: memberName\n          in: path\n          type: string\n          required: true\n          description: Member server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters\n      path: /clusters\n      description: Cluster management\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List clusters in the collective\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description: Create a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: get-cluster\n        method: GET\n        description: Get cluster details\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-cluster\n        method: POST\n        description: Start all cluster members\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-cluster\n        method: POST\n        description: Stop all cluster members\n    \
  \    inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scaling\n      path: /scaling/policies\n      description: Auto-scaling policy management\n      operations:\n      - name: list-scaling-policies\n        method: GET\n        description: List scaling policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-scaling-policy\n        method: POST\n        description: Create a scaling policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            clusterName: '{{tools.clusterName}}'\n\
  \    - name: controller\n      path: /controller\n      description: Collective controller operations\n      operations:\n      - name: get-controller-info\n        method: GET\n        description: Get controller information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: server-admin-api\n    description: Unified REST API for WebSphere server administration.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: Application lifecycle management across WAS and Liberty\n      operations:\n      - method: GET\n        name: list-was-applications\n        description: List applications on traditional WAS\n        call: admin-rest.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-liberty-applications\n        description: List applications\
  \ on Liberty\n        call: liberty-admin.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers\n      name: servers\n      description: Server management\n      operations:\n      - method: GET\n        name: list-servers\n        description: List WAS servers\n        call: admin-rest.list-servers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-liberty-server-info\n        description: Get Liberty server information\n        call: liberty-admin.get-server-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters\n      name: clusters\n      description: Cluster management\n      operations:\n      - method: GET\n        name: list-was-clusters\n        description: List WAS clusters\n        call: admin-rest.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ GET\n        name: list-collective-clusters\n        description: List Liberty collective clusters\n        call: collective-controller.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members\n      name: members\n      description: Collective member management\n      operations:\n      - method: GET\n        name: list-members\n        description: List collective members\n        call: collective-controller.list-members\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/configuration\n      name: configuration\n      description: Server configuration\n      operations:\n      - method: GET\n        name: get-was-config\n        description: List WAS configuration resource types\n        call: admin-rest.list-config-resources\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-liberty-config\n        description: Get Liberty server\
  \ configuration\n        call: liberty-admin.get-server-config\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mbeans\n      name: mbeans\n      description: JMX MBean access\n      operations:\n      - method: GET\n        name: list-mbeans\n        description: List registered MBeans\n        call: rest-connector.list-mbeans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/features\n      name: features\n      description: Liberty feature management\n      operations:\n      - method: GET\n        name: list-features\n        description: List installed Liberty features\n        call: liberty-admin.list-features\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: server-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted WebSphere server administration.\n    tools:\n    - name: was-list-applications\n      description:\
  \ List deployed applications on traditional WebSphere\n      hints:\n        readOnly: true\n        openWorld: true\n      call: admin-rest.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liberty-list-applications\n      description: List deployed applications on Liberty\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liberty-admin.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: was-list-servers\n      description: List WAS servers in the cell\n      hints:\n        readOnly: true\n      call: admin-rest.list-servers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liberty-get-server-info\n      description: Get Liberty server runtime information\n      hints:\n        readOnly: true\n      call: liberty-admin.get-server-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: was-start-server\n \
  \     description: Start a WAS server\n      hints:\n        readOnly: false\n        idempotent: true\n      call: admin-rest.start-server\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: was-stop-server\n      description: Stop a WAS server\n      hints:\n        readOnly: false\n        idempotent: true\n      call: admin-rest.stop-server\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-collective-members\n      description: List Liberty collective members\n      hints:\n        readOnly: true\n      call: collective-controller.list-members\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-collective-clusters\n      description: List clusters in Liberty collective\n      hints:\n        readOnly: true\n      call: collective-controller.list-clusters\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: get-controller-info\n      description: Get collective controller information\n      hints:\n        readOnly: true\n      call: collective-controller.get-controller-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-mbeans\n      description: List JMX MBeans via REST connector\n      hints:\n        readOnly: true\n      call: rest-connector.list-mbeans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-features\n      description: List installed Liberty features\n      hints:\n        readOnly: true\n      call: liberty-admin.list-features\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-liberty-config\n      description: Get Liberty server configuration\n      hints:\n        readOnly: true\n      call: liberty-admin.get-server-config\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-was-health\n\
  \      description: Get WAS server health status\n      hints:\n        readOnly: true\n      call: admin-rest.get-health-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-liberty-health\n      description: Get Liberty health check results\n      hints:\n        readOnly: true\n      call: liberty-admin.get-health\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
