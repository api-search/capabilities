---
api_specs:
- filename: weblogic-deployment-openapi.yml
  format: yaml
  label: weblogic-deployment
  slug: weblogic-deployment
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/weblogic/refs/heads/main/openapi/weblogic-deployment-openapi.yml
categories: []
consumed_apis:
- weblogic-deployment
- weblogic-monitoring
description: Unified capability for managing Oracle WebLogic Server application deployments and shared libraries. Combines the deployment API with monitoring to support the full deploy-verify-manage lifecycle. Used by DevOps engineers and release managers to deploy, redeploy, start, stop, and monitor Java EE applications.
layout: capability
name: Oracle WebLogic Application Deployment
operations:
- description: List all application deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Deploy an application at runtime
  method: POST
  name: deploy
  path: /v1/deployments
- description: Get an application deployment
  method: GET
  name: get-deployment
  path: /v1/deployments/{deploymentName}
- description: Undeploy an application
  method: DELETE
  name: undeploy
  path: /v1/deployments/{deploymentName}
- description: Redeploy an application
  method: POST
  name: redeploy
  path: /v1/deployments/{deploymentName}/redeploy
- description: Start a deployed application
  method: POST
  name: start-application
  path: /v1/deployments/{deploymentName}/start
- description: Stop a deployed application
  method: POST
  name: stop-application
  path: /v1/deployments/{deploymentName}/stop
- description: Get deployment metrics and servlet statistics
  method: GET
  name: get-deployment-metrics
  path: /v1/deployments/{deploymentName}/metrics
- description: List all shared library deployments
  method: GET
  name: list-libraries
  path: /v1/libraries
- description: Create a shared library deployment
  method: POST
  name: create-library
  path: /v1/libraries
personas: []
provider_name: Oracle WebLogic Server APIs
provider_slug: weblogic
search_terms:
- undeploy an application
- undeploy
- get deployment metrics and servlet statistics
- libraries
- redeploy an application
- enterprise
- get an application deployment
- application server
- deploy application
- list all application deployments with their runtime metrics
- oracle
- get deployment
- get details for a specific application deployment
- deploy an application archive to weblogic at runtime
- start a stopped or prepared application on weblogic
- deploy
- delete library
- shared library deployment management
- remove a shared library from weblogic
- start a deployed application
- middleware
- get runtime metrics for a deployed application
- list libraries
- list deployments
- list all application deployments on weblogic
- create a shared library deployment
- devops
- applications
- list all deployments monitoring
- start application
- list all application deployments
- stop a deployed application
- undeploy and remove an application from weblogic
- undeploy application
- list all shared library deployments on weblogic
- redeploy
- stop application
- redeploy an application (update in-place) on weblogic
- deploy a new shared library to weblogic
- weblogic
- deployment
- deploy an application at runtime
- java ee
- stop a running application on weblogic (keeps it deployed)
- get deployment metrics
- application deployment lifecycle management
- redeploy application
- list all shared library deployments
- create library
slug: application-deployment
source_filename: application-deployment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle WebLogic Application Deployment\"\n  description: >-\n    Unified capability for managing Oracle WebLogic Server application deployments\n    and shared libraries. Combines the deployment API with monitoring to support\n    the full deploy-verify-manage lifecycle. Used by DevOps engineers and release\n    managers to deploy, redeploy, start, stop, and monitor Java EE applications.\n  tags:\n    - Oracle\n    - WebLogic\n    - Deployment\n    - Applications\n    - Libraries\n    - DevOps\n    - Java EE\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEBLOGIC_ADMIN_USER: WEBLOGIC_ADMIN_USER\n      WEBLOGIC_ADMIN_PASSWORD: WEBLOGIC_ADMIN_PASSWORD\n\ncapability:\n  consumes:\n    - import: weblogic-deployment\n      location: ./shared/weblogic-deployment.yaml\n    - import: weblogic-monitoring\n      location: ./shared/weblogic-monitoring.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8081\n      namespace: weblogic-deployment-workflow-api\n      description: \"Unified REST API for Oracle WebLogic application deployment workflows.\"\n      resources:\n        - path: /v1/deployments\n          name: deployments\n          description: \"Application deployment lifecycle management\"\n          operations:\n            - method: GET\n              name: list-deployments\n              description: \"List all application deployments\"\n              call: \"weblogic-deployment.list-deployments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: deploy\n              description: \"Deploy an application at runtime\"\n              call: \"weblogic-deployment.deploy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{deploymentName}\n          name: deployment\n       \
  \   operations:\n            - method: GET\n              name: get-deployment\n              description: \"Get an application deployment\"\n              call: \"weblogic-deployment.get-deployment\"\n              with:\n                deploymentName: \"rest.deploymentName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: undeploy\n              description: \"Undeploy an application\"\n              call: \"weblogic-deployment.undeploy\"\n              with:\n                deploymentName: \"rest.deploymentName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{deploymentName}/redeploy\n          name: redeploy\n          operations:\n            - method: POST\n              name: redeploy\n              description: \"Redeploy an application\"\n              call: \"weblogic-deployment.redeploy\"\
  \n              with:\n                deploymentName: \"rest.deploymentName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{deploymentName}/start\n          name: start-deployment\n          operations:\n            - method: POST\n              name: start-application\n              description: \"Start a deployed application\"\n              call: \"weblogic-deployment.start-application\"\n              with:\n                deploymentName: \"rest.deploymentName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{deploymentName}/stop\n          name: stop-deployment\n          operations:\n            - method: POST\n              name: stop-application\n              description: \"Stop a deployed application\"\n              call: \"weblogic-deployment.stop-application\"\n              with:\n             \
  \   deploymentName: \"rest.deploymentName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{deploymentName}/metrics\n          name: deployment-metrics\n          operations:\n            - method: GET\n              name: get-deployment-metrics\n              description: \"Get deployment metrics and servlet statistics\"\n              call: \"weblogic-monitoring.get-deployment\"\n              with:\n                deploymentName: \"rest.deploymentName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/libraries\n          name: libraries\n          description: \"Shared library deployment management\"\n          operations:\n            - method: GET\n              name: list-libraries\n              description: \"List all shared library deployments\"\n              call: \"weblogic-deployment.list-libraries\"\n         \
  \     outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-library\n              description: \"Create a shared library deployment\"\n              call: \"weblogic-deployment.create-library\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: weblogic-deployment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Oracle WebLogic application deployment management.\"\n      tools:\n        - name: list-deployments\n          description: \"List all application deployments on WebLogic\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weblogic-deployment.list-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-deployment\n          description: \"Get details\
  \ for a specific application deployment\"\n          hints:\n            readOnly: true\n          call: \"weblogic-deployment.get-deployment\"\n          with:\n            deploymentName: \"tools.deploymentName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deploy-application\n          description: \"Deploy an application archive to WebLogic at runtime\"\n          hints:\n            readOnly: false\n          call: \"weblogic-deployment.deploy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: undeploy-application\n          description: \"Undeploy and remove an application from WebLogic\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"weblogic-deployment.undeploy\"\n          with:\n            deploymentName: \"tools.deploymentName\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: redeploy-application\n          description: \"Redeploy an application (update in-place) on WebLogic\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"weblogic-deployment.redeploy\"\n          with:\n            deploymentName: \"tools.deploymentName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-application\n          description: \"Start a stopped or prepared application on WebLogic\"\n          hints:\n            readOnly: false\n          call: \"weblogic-deployment.start-application\"\n          with:\n            deploymentName: \"tools.deploymentName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stop-application\n          description: \"Stop a running application on WebLogic (keeps it deployed)\"\n          hints:\n            destructive: false\n          call: \"weblogic-deployment.stop-application\"\
  \n          with:\n            deploymentName: \"tools.deploymentName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-deployment-metrics\n          description: \"Get runtime metrics for a deployed application\"\n          hints:\n            readOnly: true\n          call: \"weblogic-monitoring.get-deployment\"\n          with:\n            deploymentName: \"tools.deploymentName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-all-deployments-monitoring\n          description: \"List all application deployments with their runtime metrics\"\n          hints:\n            readOnly: true\n          call: \"weblogic-monitoring.list-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-libraries\n          description: \"List all shared library deployments on WebLogic\"\n          hints:\n \
  \           readOnly: true\n          call: \"weblogic-deployment.list-libraries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-library\n          description: \"Deploy a new shared library to WebLogic\"\n          hints:\n            readOnly: false\n          call: \"weblogic-deployment.create-library\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-library\n          description: \"Remove a shared library from WebLogic\"\n          hints:\n            destructive: true\n          call: \"weblogic-deployment.delete-library\"\n          with:\n            libraryName: \"tools.libraryName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/weblogic/refs/heads/main/capabilities/application-deployment.yaml
tags:
- Oracle
- WebLogic
- Deployment
- Applications
- Libraries
- DevOps
- Java EE
tools:
- description: List all application deployments on WebLogic
  hints:
    openWorld: true
    readOnly: true
  name: list-deployments
- description: Get details for a specific application deployment
  hints:
    readOnly: true
  name: get-deployment
- description: Deploy an application archive to WebLogic at runtime
  hints:
    readOnly: false
  name: deploy-application
- description: Undeploy and remove an application from WebLogic
  hints:
    destructive: true
    idempotent: true
  name: undeploy-application
- description: Redeploy an application (update in-place) on WebLogic
  hints:
    idempotent: false
    readOnly: false
  name: redeploy-application
- description: Start a stopped or prepared application on WebLogic
  hints:
    readOnly: false
  name: start-application
- description: Stop a running application on WebLogic (keeps it deployed)
  hints:
    destructive: false
  name: stop-application
- description: Get runtime metrics for a deployed application
  hints:
    readOnly: true
  name: get-deployment-metrics
- description: List all application deployments with their runtime metrics
  hints:
    readOnly: true
  name: list-all-deployments-monitoring
- description: List all shared library deployments on WebLogic
  hints:
    readOnly: true
  name: list-libraries
- description: Deploy a new shared library to WebLogic
  hints:
    readOnly: false
  name: create-library
- description: Remove a shared library from WebLogic
  hints:
    destructive: true
  name: delete-library
---
