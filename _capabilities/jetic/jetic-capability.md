---
categories: []
consumed_apis: []
description: The Jetic Platform API provides programmatic access to manage integrations, deployments, clusters, and API specifications on the Jetic cloud-native Integration Platform. Jetic is built on Apache Camel and Kubernetes, enabling users to design, build, deploy, and monitor integrations and REST APIs.
layout: capability
name: Jetic Platform API
operations:
- description: Jetic List integrations
  method: GET
  name: listintegrations
  path: /integrations
- description: Jetic Create an integration
  method: POST
  name: createintegration
  path: /integrations
- description: Jetic Get an integration
  method: GET
  name: getintegration
  path: /integrations/{integrationId}
- description: Jetic Update an integration
  method: PUT
  name: updateintegration
  path: /integrations/{integrationId}
- description: Jetic Delete an integration
  method: DELETE
  name: deleteintegration
  path: /integrations/{integrationId}
- description: Jetic List routes for an integration
  method: GET
  name: listintegrationroutes
  path: /integrations/{integrationId}/routes
- description: Jetic List deployments
  method: GET
  name: listdeployments
  path: /deployments
- description: Jetic Get a deployment
  method: GET
  name: getdeployment
  path: /deployments/{deploymentId}
- description: Jetic Undeploy a deployment
  method: DELETE
  name: deletedeployment
  path: /deployments/{deploymentId}
- description: Jetic Deploy an integration
  method: POST
  name: deployintegration
  path: /integrations/{integrationId}/deploy
- description: Jetic List clusters
  method: GET
  name: listclusters
  path: /clusters
- description: Jetic Register a cluster
  method: POST
  name: registercluster
  path: /clusters
- description: Jetic Get cluster details
  method: GET
  name: getcluster
  path: /clusters/{clusterId}
- description: Jetic Remove a cluster
  method: DELETE
  name: removecluster
  path: /clusters/{clusterId}
- description: Jetic Get cluster status
  method: GET
  name: getclusterstatus
  path: /clusters/{clusterId}/status
- description: Jetic List API specifications
  method: GET
  name: listapispecifications
  path: /api-specifications
- description: Jetic Create or import an API specification
  method: POST
  name: createapispecification
  path: /api-specifications
- description: Jetic Get an API specification
  method: GET
  name: getapispecification
  path: /api-specifications/{specificationId}
- description: Jetic Update an API specification
  method: PUT
  name: updateapispecification
  path: /api-specifications/{specificationId}
- description: Jetic Delete an API specification
  method: DELETE
  name: deleteapispecification
  path: /api-specifications/{specificationId}
- description: Jetic Get deployment logs
  method: GET
  name: getdeploymentlogs
  path: /deployments/{deploymentId}/logs
- description: Jetic Get deployment metrics
  method: GET
  name: getdeploymentmetrics
  path: /deployments/{deploymentId}/metrics
personas: []
provider_name: Jetic
provider_slug: jetic
search_terms:
- listclusters
- createintegration
- jetic delete an api specification
- jetic list clusters
- jetic register a cluster
- getclusterstatus
- jetic get deployment logs
- jetic get cluster status
- jetic remove a cluster
- jetic delete an integration
- jetic undeploy a deployment
- updateintegration
- getintegration
- deleteapispecification
- getapispecification
- jetic list integrations
- jetic list deployments
- listintegrations
- jetic update an api specification
- integrations
- jetic get an api specification
- jetic create an integration
- jetic get a deployment
- deployintegration
- jetic get an integration
- jetic list routes for an integration
- jetic list api specifications
- listintegrationroutes
- deleteintegration
- api
- jetic create or import an api specification
- getdeploymentmetrics
- apache camel
- ipaas
- pro-code api composition
- listapispecifications
- registercluster
- deletedeployment
- listdeployments
- removecluster
- jetic update an integration
- jetic deploy an integration
- createapispecification
- getdeployment
- jetic get cluster details
- getdeploymentlogs
- jetic
- jetic get deployment metrics
- updateapispecification
- getcluster
slug: jetic-capability
source_filename: jetic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Jetic Platform API\n  description: The Jetic Platform API provides programmatic access to manage integrations, deployments, clusters, and API\n    specifications on the Jetic cloud-native Integration Platform. Jetic is built on Apache Camel and Kubernetes, enabling\n    users to design, build, deploy, and monitor integrations and REST APIs.\n  tags:\n  - Jetic\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jetic\n    baseUri: https://app.us1.jetic.io/api/v1\n    description: Jetic Platform API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{JETIC_TOKEN}}'\n    resources:\n    - name: integrations\n      path: /integrations\n      operations:\n      - name: listintegrations\n        method: GET\n        description: Jetic List integrations\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description:\
  \ Page number for pagination.\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results per page.\n        - name: status\n          in: query\n          type: string\n          description: Filter by integration status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createintegration\n        method: POST\n        description: Jetic Create an integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrations-integrationid\n      path: /integrations/{integrationId}\n      operations:\n      - name: getintegration\n        method: GET\n        description: Jetic Get an integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateintegration\n     \
  \   method: PUT\n        description: Jetic Update an integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteintegration\n        method: DELETE\n        description: Jetic Delete an integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrations-integrationid-routes\n      path: /integrations/{integrationId}/routes\n      operations:\n      - name: listintegrationroutes\n        method: GET\n        description: Jetic List routes for an integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /deployments\n      operations:\n      - name: listdeployments\n        method: GET\n        description: Jetic List deployments\n        inputParameters:\n        - name: clusterId\n\
  \          in: query\n          type: string\n          description: Filter deployments by cluster.\n        - name: status\n          in: query\n          type: string\n          description: Filter by deployment status.\n        - name: page\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments-deploymentid\n      path: /deployments/{deploymentId}\n      operations:\n      - name: getdeployment\n        method: GET\n        description: Jetic Get a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedeployment\n        method: DELETE\n        description: Jetic Undeploy a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: integrations-integrationid-deploy\n      path: /integrations/{integrationId}/deploy\n      operations:\n      - name: deployintegration\n        method: POST\n        description: Jetic Deploy an integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters\n      path: /clusters\n      operations:\n      - name: listclusters\n        method: GET\n        description: Jetic List clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registercluster\n        method: POST\n        description: Jetic Register a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters-clusterid\n      path: /clusters/{clusterId}\n      operations:\n      - name: getcluster\n\
  \        method: GET\n        description: Jetic Get cluster details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removecluster\n        method: DELETE\n        description: Jetic Remove a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters-clusterid-status\n      path: /clusters/{clusterId}/status\n      operations:\n      - name: getclusterstatus\n        method: GET\n        description: Jetic Get cluster status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-specifications\n      path: /api-specifications\n      operations:\n      - name: listapispecifications\n        method: GET\n        description: Jetic List API specifications\n        inputParameters:\n        - name: page\n        \
  \  in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapispecification\n        method: POST\n        description: Jetic Create or import an API specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-specifications-specificationid\n      path: /api-specifications/{specificationId}\n      operations:\n      - name: getapispecification\n        method: GET\n        description: Jetic Get an API specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapispecification\n        method: PUT\n        description: Jetic Update an API specification\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deleteapispecification\n        method: DELETE\n        description: Jetic Delete an API specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments-deploymentid-logs\n      path: /deployments/{deploymentId}/logs\n      operations:\n      - name: getdeploymentlogs\n        method: GET\n        description: Jetic Get deployment logs\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          description: Type of logs to retrieve.\n        - name: since\n          in: query\n          type: string\n          description: Retrieve logs since this timestamp.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of log lines.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: deployments-deploymentid-metrics\n      path: /deployments/{deploymentId}/metrics\n      operations:\n      - name: getdeploymentmetrics\n        method: GET\n        description: Jetic Get deployment metrics\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n          description: Start of the metrics time range.\n        - name: to\n          in: query\n          type: string\n          description: End of the metrics time range.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jetic-rest\n    description: REST adapter for Jetic Platform API.\n    resources:\n    - path: /integrations\n      name: listintegrations\n      operations:\n      - method: GET\n        name: listintegrations\n        description: Jetic List integrations\n        call: jetic.listintegrations\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrations\n      name: createintegration\n      operations:\n      - method: POST\n        name: createintegration\n        description: Jetic Create an integration\n        call: jetic.createintegration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrations/{integrationId}\n      name: getintegration\n      operations:\n      - method: GET\n        name: getintegration\n        description: Jetic Get an integration\n        call: jetic.getintegration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrations/{integrationId}\n      name: updateintegration\n      operations:\n      - method: PUT\n        name: updateintegration\n        description: Jetic Update an integration\n        call: jetic.updateintegration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrations/{integrationId}\n\
  \      name: deleteintegration\n      operations:\n      - method: DELETE\n        name: deleteintegration\n        description: Jetic Delete an integration\n        call: jetic.deleteintegration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrations/{integrationId}/routes\n      name: listintegrationroutes\n      operations:\n      - method: GET\n        name: listintegrationroutes\n        description: Jetic List routes for an integration\n        call: jetic.listintegrationroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments\n      name: listdeployments\n      operations:\n      - method: GET\n        name: listdeployments\n        description: Jetic List deployments\n        call: jetic.listdeployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments/{deploymentId}\n      name: getdeployment\n      operations:\n      - method: GET\n\
  \        name: getdeployment\n        description: Jetic Get a deployment\n        call: jetic.getdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments/{deploymentId}\n      name: deletedeployment\n      operations:\n      - method: DELETE\n        name: deletedeployment\n        description: Jetic Undeploy a deployment\n        call: jetic.deletedeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrations/{integrationId}/deploy\n      name: deployintegration\n      operations:\n      - method: POST\n        name: deployintegration\n        description: Jetic Deploy an integration\n        call: jetic.deployintegration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters\n      name: listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: Jetic List clusters\n        call: jetic.listclusters\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters\n      name: registercluster\n      operations:\n      - method: POST\n        name: registercluster\n        description: Jetic Register a cluster\n        call: jetic.registercluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{clusterId}\n      name: getcluster\n      operations:\n      - method: GET\n        name: getcluster\n        description: Jetic Get cluster details\n        call: jetic.getcluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{clusterId}\n      name: removecluster\n      operations:\n      - method: DELETE\n        name: removecluster\n        description: Jetic Remove a cluster\n        call: jetic.removecluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{clusterId}/status\n      name: getclusterstatus\n   \
  \   operations:\n      - method: GET\n        name: getclusterstatus\n        description: Jetic Get cluster status\n        call: jetic.getclusterstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-specifications\n      name: listapispecifications\n      operations:\n      - method: GET\n        name: listapispecifications\n        description: Jetic List API specifications\n        call: jetic.listapispecifications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-specifications\n      name: createapispecification\n      operations:\n      - method: POST\n        name: createapispecification\n        description: Jetic Create or import an API specification\n        call: jetic.createapispecification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-specifications/{specificationId}\n      name: getapispecification\n      operations:\n      - method: GET\n\
  \        name: getapispecification\n        description: Jetic Get an API specification\n        call: jetic.getapispecification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-specifications/{specificationId}\n      name: updateapispecification\n      operations:\n      - method: PUT\n        name: updateapispecification\n        description: Jetic Update an API specification\n        call: jetic.updateapispecification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-specifications/{specificationId}\n      name: deleteapispecification\n      operations:\n      - method: DELETE\n        name: deleteapispecification\n        description: Jetic Delete an API specification\n        call: jetic.deleteapispecification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments/{deploymentId}/logs\n      name: getdeploymentlogs\n      operations:\n      - method: GET\n\
  \        name: getdeploymentlogs\n        description: Jetic Get deployment logs\n        call: jetic.getdeploymentlogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments/{deploymentId}/metrics\n      name: getdeploymentmetrics\n      operations:\n      - method: GET\n        name: getdeploymentmetrics\n        description: Jetic Get deployment metrics\n        call: jetic.getdeploymentmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jetic-mcp\n    transport: http\n    description: MCP adapter for Jetic Platform API for AI agent use.\n    tools:\n    - name: listintegrations\n      description: Jetic List integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.listintegrations\n      with:\n        page: tools.page\n        limit: tools.limit\n        status: tools.status\n      inputParameters:\n\
  \      - name: page\n        type: integer\n        description: Page number for pagination.\n      - name: limit\n        type: integer\n        description: Number of results per page.\n      - name: status\n        type: string\n        description: Filter by integration status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createintegration\n      description: Jetic Create an integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jetic.createintegration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintegration\n      description: Jetic Get an integration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.getintegration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateintegration\n      description: Jetic Update an integration\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: true\n      call: jetic.updateintegration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteintegration\n      description: Jetic Delete an integration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jetic.deleteintegration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listintegrationroutes\n      description: Jetic List routes for an integration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.listintegrationroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeployments\n      description: Jetic List deployments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.listdeployments\n      with:\n        clusterId: tools.clusterId\n        status:\
  \ tools.status\n        page: tools.page\n        limit: tools.limit\n      inputParameters:\n      - name: clusterId\n        type: string\n        description: Filter deployments by cluster.\n      - name: status\n        type: string\n        description: Filter by deployment status.\n      - name: page\n        type: integer\n        description: page\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeployment\n      description: Jetic Get a deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.getdeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedeployment\n      description: Jetic Undeploy a deployment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jetic.deletedeployment\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: deployintegration\n      description: Jetic Deploy an integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jetic.deployintegration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclusters\n      description: Jetic List clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.listclusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registercluster\n      description: Jetic Register a cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jetic.registercluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcluster\n      description: Jetic Get cluster details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: jetic.getcluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removecluster\n      description: Jetic Remove a cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jetic.removecluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusterstatus\n      description: Jetic Get cluster status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.getclusterstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapispecifications\n      description: Jetic List API specifications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.listapispecifications\n      with:\n        page: tools.page\n        limit: tools.limit\n      inputParameters:\n      - name: page\n        type: integer\n       \
  \ description: page\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapispecification\n      description: Jetic Create or import an API specification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jetic.createapispecification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapispecification\n      description: Jetic Get an API specification\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.getapispecification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapispecification\n      description: Jetic Update an API specification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: jetic.updateapispecification\n      outputParameters:\n \
  \     - type: object\n        mapping: $.\n    - name: deleteapispecification\n      description: Jetic Delete an API specification\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jetic.deleteapispecification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeploymentlogs\n      description: Jetic Get deployment logs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.getdeploymentlogs\n      with:\n        type: tools.type\n        since: tools.since\n        limit: tools.limit\n      inputParameters:\n      - name: type\n        type: string\n        description: Type of logs to retrieve.\n      - name: since\n        type: string\n        description: Retrieve logs since this timestamp.\n      - name: limit\n        type: integer\n        description: Maximum number of log lines.\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: getdeploymentmetrics\n      description: Jetic Get deployment metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetic.getdeploymentmetrics\n      with:\n        from: tools.from\n        to: tools.to\n      inputParameters:\n      - name: from\n        type: string\n        description: Start of the metrics time range.\n      - name: to\n        type: string\n        description: End of the metrics time range.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JETIC_TOKEN: JETIC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jetic/refs/heads/main/capabilities/jetic-capability.yaml
tags:
- Jetic
- API
tools:
- description: Jetic List integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrations
- description: Jetic Create an integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createintegration
- description: Jetic Get an integration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintegration
- description: Jetic Update an integration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateintegration
- description: Jetic Delete an integration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteintegration
- description: Jetic List routes for an integration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrationroutes
- description: Jetic List deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeployments
- description: Jetic Get a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeployment
- description: Jetic Undeploy a deployment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedeployment
- description: Jetic Deploy an integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployintegration
- description: Jetic List clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
- description: Jetic Register a cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registercluster
- description: Jetic Get cluster details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcluster
- description: Jetic Remove a cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removecluster
- description: Jetic Get cluster status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusterstatus
- description: Jetic List API specifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapispecifications
- description: Jetic Create or import an API specification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapispecification
- description: Jetic Get an API specification
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapispecification
- description: Jetic Update an API specification
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapispecification
- description: Jetic Delete an API specification
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapispecification
- description: Jetic Get deployment logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeploymentlogs
- description: Jetic Get deployment metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeploymentmetrics
---
