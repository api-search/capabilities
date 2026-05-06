---
categories: []
consumed_apis: []
description: RESTful API for deploying, undeploying, and managing application and library deployments on Oracle WebLogic Server. Supports deploying enterprise applications (EAR, WAR), shared libraries, and managing deployment lifecycle including start, stop, and redeploy operations. All deployment configuration changes require an active edit session with startEdit/activate workflow. Runtime deployment lifecycle operations (start/stop) are available through the domainRuntime tree.
layout: capability
name: Oracle WebLogic Server Oracle WebLogic Deployment API
operations:
- description: Oracle WebLogic Server Start an edit session for deployment changes
  method: POST
  name: startedit
  path: /edit/changeManager/startEdit
- description: Oracle WebLogic Server Activate pending deployment changes
  method: POST
  name: activatedeploymentchanges
  path: /edit/changeManager/activate
- description: Oracle WebLogic Server List all application deployments
  method: GET
  name: listappdeployments
  path: /edit/appDeployments
- description: Oracle WebLogic Server Deploy an application
  method: POST
  name: deployapplication
  path: /edit/appDeployments
- description: Oracle WebLogic Server Get application deployment creation form
  method: GET
  name: getappdeploymentcreateform
  path: /edit/appDeploymentCreateForm
- description: Oracle WebLogic Server Get application deployment details
  method: GET
  name: getappdeployment
  path: /edit/appDeployments/{appName}
- description: Oracle WebLogic Server Update application deployment configuration
  method: POST
  name: updateappdeployment
  path: /edit/appDeployments/{appName}
- description: Oracle WebLogic Server Undeploy an application
  method: DELETE
  name: undeployapplication
  path: /edit/appDeployments/{appName}
- description: Oracle WebLogic Server List all shared library deployments
  method: GET
  name: listlibdeployments
  path: /edit/libDeployments
- description: Oracle WebLogic Server Deploy a shared library
  method: POST
  name: deploylibrary
  path: /edit/libDeployments
- description: Oracle WebLogic Server Get shared library deployment details
  method: GET
  name: getlibdeployment
  path: /edit/libDeployments/{libName}
- description: Oracle WebLogic Server Remove a shared library deployment
  method: DELETE
  name: undeploylibrary
  path: /edit/libDeployments/{libName}
- description: Oracle WebLogic Server List deployment runtimes
  method: GET
  name: listdeploymentruntimes
  path: /domainRuntime/appDeploymentRuntimes
- description: Oracle WebLogic Server Start a deployed application
  method: POST
  name: startapplication
  path: /domainRuntime/appDeploymentRuntimes/{appName}/start
- description: Oracle WebLogic Server Stop a deployed application
  method: POST
  name: stopapplication
  path: /domainRuntime/appDeploymentRuntimes/{appName}/stop
- description: Oracle WebLogic Server Redeploy an application
  method: POST
  name: redeployapplication
  path: /domainRuntime/appDeploymentRuntimes/{appName}/redeploy
- description: Oracle WebLogic Server Update an application deployment
  method: POST
  name: updateapplication
  path: /domainRuntime/appDeploymentRuntimes/{appName}/update
- description: Oracle WebLogic Server Get deployment task status
  method: GET
  name: getdeploymenttaskstatus
  path: /domainRuntime/appDeploymentRuntimes/{appName}/tasks/{taskId}
- description: Oracle WebLogic Server List application runtimes on a server
  method: GET
  name: listserverapplicationruntimes
  path: /domainRuntime/serverRuntimes/{serverName}/applicationRuntimes
- description: Oracle WebLogic Server List sub-deployments for an application
  method: GET
  name: listappsubdeployments
  path: /edit/appDeployments/{appName}/subDeployments
- description: Oracle WebLogic Server Create a sub-deployment for an application
  method: POST
  name: createappsubdeployment
  path: /edit/appDeployments/{appName}/subDeployments
personas: []
provider_name: Oracle WebLogic Server
provider_slug: oracle-weblogic
search_terms:
- activatedeploymentchanges
- startedit
- oracle weblogic server create a sub-deployment for an application
- startapplication
- oracle weblogic server get application deployment details
- listserverapplicationruntimes
- oracle weblogic server start an edit session for deployment changes
- getappdeploymentcreateform
- oracle weblogic server get application deployment creation form
- listappdeployments
- java ee
- middleware
- createappsubdeployment
- oracle weblogic server list deployment runtimes
- oracle weblogic server list application runtimes on a server
- undeployapplication
- enterprise
- stopapplication
- oracle weblogic server update an application deployment
- oracle weblogic server activate pending deployment changes
- oracle weblogic server remove a shared library deployment
- listdeploymentruntimes
- getappdeployment
- updateapplication
- oracle weblogic server get deployment task status
- oracle
- listlibdeployments
- redeployapplication
- oracle weblogic server list all shared library deployments
- api
- listappsubdeployments
- oracle weblogic server deploy an application
- oracle weblogic server update application deployment configuration
- deploylibrary
- application server
- oracle weblogic server list sub-deployments for an application
- oracle weblogic server stop a deployed application
- undeploylibrary
- oracle weblogic server start a deployed application
- oracle weblogic server redeploy an application
- oracle weblogic server list all application deployments
- oracle weblogic server undeploy an application
- deployapplication
- oracle weblogic server deploy a shared library
- oracle weblogic server get shared library deployment details
- getdeploymenttaskstatus
- weblogic
- getlibdeployment
- updateappdeployment
slug: oracle-weblogic-capability
source_filename: oracle-weblogic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle WebLogic Server Oracle WebLogic Deployment API\n  description: RESTful API for deploying, undeploying, and managing application and library deployments on Oracle WebLogic\n    Server. Supports deploying enterprise applications (EAR, WAR), shared libraries, and managing deployment lifecycle including\n    start, stop, and redeploy operations. All deployment configuration changes require an active edit session with startEdit/activate\n    workflow. Runtime deployment lifecycle operations (start/stop) are available through the domainRuntime tree.\n  tags:\n  - Oracle\n  - Weblogic\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-weblogic\n    baseUri: http://localhost:7001/management/weblogic/latest\n    description: Oracle WebLogic Server Oracle WebLogic Deployment API HTTP API.\n    authentication:\n      type: basic\n      username: '{{ORACLE_WEBLOGIC_USERNAME}}'\n\
  \      password: '{{ORACLE_WEBLOGIC_PASSWORD}}'\n    resources:\n    - name: edit-changemanager-startedit\n      path: /edit/changeManager/startEdit\n      operations:\n      - name: startedit\n        method: POST\n        description: Oracle WebLogic Server Start an edit session for deployment changes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edit-changemanager-activate\n      path: /edit/changeManager/activate\n      operations:\n      - name: activatedeploymentchanges\n        method: POST\n        description: Oracle WebLogic Server Activate pending deployment changes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edit-appdeployments\n      path: /edit/appDeployments\n      operations:\n      - name: listappdeployments\n        method: GET\n        description: Oracle WebLogic Server List all\
  \ application deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deployapplication\n        method: POST\n        description: Oracle WebLogic Server Deploy an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edit-appdeploymentcreateform\n      path: /edit/appDeploymentCreateForm\n      operations:\n      - name: getappdeploymentcreateform\n        method: GET\n        description: Oracle WebLogic Server Get application deployment creation form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edit-appdeployments-appname\n      path: /edit/appDeployments/{appName}\n      operations:\n      - name: getappdeployment\n        method: GET\n        description: Oracle WebLogic Server Get application\
  \ deployment details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateappdeployment\n        method: POST\n        description: Oracle WebLogic Server Update application deployment configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: undeployapplication\n        method: DELETE\n        description: Oracle WebLogic Server Undeploy an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edit-libdeployments\n      path: /edit/libDeployments\n      operations:\n      - name: listlibdeployments\n        method: GET\n        description: Oracle WebLogic Server List all shared library deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deploylibrary\n        method: POST\n        description: Oracle WebLogic Server Deploy a shared library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edit-libdeployments-libname\n      path: /edit/libDeployments/{libName}\n      operations:\n      - name: getlibdeployment\n        method: GET\n        description: Oracle WebLogic Server Get shared library deployment details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: undeploylibrary\n        method: DELETE\n        description: Oracle WebLogic Server Remove a shared library deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domainruntime-appdeploymentruntimes\n      path: /domainRuntime/appDeploymentRuntimes\n  \
  \    operations:\n      - name: listdeploymentruntimes\n        method: GET\n        description: Oracle WebLogic Server List deployment runtimes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domainruntime-appdeploymentruntimes-appname-star\n      path: /domainRuntime/appDeploymentRuntimes/{appName}/start\n      operations:\n      - name: startapplication\n        method: POST\n        description: Oracle WebLogic Server Start a deployed application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domainruntime-appdeploymentruntimes-appname-stop\n      path: /domainRuntime/appDeploymentRuntimes/{appName}/stop\n      operations:\n      - name: stopapplication\n        method: POST\n        description: Oracle WebLogic Server Stop a deployed application\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: domainruntime-appdeploymentruntimes-appname-rede\n      path: /domainRuntime/appDeploymentRuntimes/{appName}/redeploy\n      operations:\n      - name: redeployapplication\n        method: POST\n        description: Oracle WebLogic Server Redeploy an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domainruntime-appdeploymentruntimes-appname-upda\n      path: /domainRuntime/appDeploymentRuntimes/{appName}/update\n      operations:\n      - name: updateapplication\n        method: POST\n        description: Oracle WebLogic Server Update an application deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domainruntime-appdeploymentruntimes-appname-task\n      path: /domainRuntime/appDeploymentRuntimes/{appName}/tasks/{taskId}\n\
  \      operations:\n      - name: getdeploymenttaskstatus\n        method: GET\n        description: Oracle WebLogic Server Get deployment task status\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domainruntime-serverruntimes-servername-applicat\n      path: /domainRuntime/serverRuntimes/{serverName}/applicationRuntimes\n      operations:\n      - name: listserverapplicationruntimes\n        method: GET\n        description: Oracle WebLogic Server List application runtimes on a server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edit-appdeployments-appname-subdeployments\n      path: /edit/appDeployments/{appName}/subDeployments\n      operations:\n      - name: listappsubdeployments\n\
  \        method: GET\n        description: Oracle WebLogic Server List sub-deployments for an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createappsubdeployment\n        method: POST\n        description: Oracle WebLogic Server Create a sub-deployment for an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-weblogic-rest\n    description: REST adapter for Oracle WebLogic Server Oracle WebLogic Deployment API.\n    resources:\n    - path: /edit/changeManager/startEdit\n      name: startedit\n      operations:\n      - method: POST\n        name: startedit\n        description: Oracle WebLogic Server Start an edit session for deployment changes\n        call: oracle-weblogic.startedit\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /edit/changeManager/activate\n      name: activatedeploymentchanges\n      operations:\n      - method: POST\n        name: activatedeploymentchanges\n        description: Oracle WebLogic Server Activate pending deployment changes\n        call: oracle-weblogic.activatedeploymentchanges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/appDeployments\n      name: listappdeployments\n      operations:\n      - method: GET\n        name: listappdeployments\n        description: Oracle WebLogic Server List all application deployments\n        call: oracle-weblogic.listappdeployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/appDeployments\n      name: deployapplication\n      operations:\n      - method: POST\n        name: deployapplication\n        description: Oracle WebLogic Server Deploy an application\n        call: oracle-weblogic.deployapplication\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/appDeploymentCreateForm\n      name: getappdeploymentcreateform\n      operations:\n      - method: GET\n        name: getappdeploymentcreateform\n        description: Oracle WebLogic Server Get application deployment creation form\n        call: oracle-weblogic.getappdeploymentcreateform\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/appDeployments/{appName}\n      name: getappdeployment\n      operations:\n      - method: GET\n        name: getappdeployment\n        description: Oracle WebLogic Server Get application deployment details\n        call: oracle-weblogic.getappdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/appDeployments/{appName}\n      name: updateappdeployment\n      operations:\n      - method: POST\n        name: updateappdeployment\n        description: Oracle WebLogic Server\
  \ Update application deployment configuration\n        call: oracle-weblogic.updateappdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/appDeployments/{appName}\n      name: undeployapplication\n      operations:\n      - method: DELETE\n        name: undeployapplication\n        description: Oracle WebLogic Server Undeploy an application\n        call: oracle-weblogic.undeployapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/libDeployments\n      name: listlibdeployments\n      operations:\n      - method: GET\n        name: listlibdeployments\n        description: Oracle WebLogic Server List all shared library deployments\n        call: oracle-weblogic.listlibdeployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/libDeployments\n      name: deploylibrary\n      operations:\n      - method: POST\n        name: deploylibrary\n  \
  \      description: Oracle WebLogic Server Deploy a shared library\n        call: oracle-weblogic.deploylibrary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/libDeployments/{libName}\n      name: getlibdeployment\n      operations:\n      - method: GET\n        name: getlibdeployment\n        description: Oracle WebLogic Server Get shared library deployment details\n        call: oracle-weblogic.getlibdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/libDeployments/{libName}\n      name: undeploylibrary\n      operations:\n      - method: DELETE\n        name: undeploylibrary\n        description: Oracle WebLogic Server Remove a shared library deployment\n        call: oracle-weblogic.undeploylibrary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domainRuntime/appDeploymentRuntimes\n      name: listdeploymentruntimes\n      operations:\n      - method:\
  \ GET\n        name: listdeploymentruntimes\n        description: Oracle WebLogic Server List deployment runtimes\n        call: oracle-weblogic.listdeploymentruntimes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domainRuntime/appDeploymentRuntimes/{appName}/start\n      name: startapplication\n      operations:\n      - method: POST\n        name: startapplication\n        description: Oracle WebLogic Server Start a deployed application\n        call: oracle-weblogic.startapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domainRuntime/appDeploymentRuntimes/{appName}/stop\n      name: stopapplication\n      operations:\n      - method: POST\n        name: stopapplication\n        description: Oracle WebLogic Server Stop a deployed application\n        call: oracle-weblogic.stopapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domainRuntime/appDeploymentRuntimes/{appName}/redeploy\n\
  \      name: redeployapplication\n      operations:\n      - method: POST\n        name: redeployapplication\n        description: Oracle WebLogic Server Redeploy an application\n        call: oracle-weblogic.redeployapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domainRuntime/appDeploymentRuntimes/{appName}/update\n      name: updateapplication\n      operations:\n      - method: POST\n        name: updateapplication\n        description: Oracle WebLogic Server Update an application deployment\n        call: oracle-weblogic.updateapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domainRuntime/appDeploymentRuntimes/{appName}/tasks/{taskId}\n      name: getdeploymenttaskstatus\n      operations:\n      - method: GET\n        name: getdeploymenttaskstatus\n        description: Oracle WebLogic Server Get deployment task status\n        call: oracle-weblogic.getdeploymenttaskstatus\n    \
  \    with:\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domainRuntime/serverRuntimes/{serverName}/applicationRuntimes\n      name: listserverapplicationruntimes\n      operations:\n      - method: GET\n        name: listserverapplicationruntimes\n        description: Oracle WebLogic Server List application runtimes on a server\n        call: oracle-weblogic.listserverapplicationruntimes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/appDeployments/{appName}/subDeployments\n      name: listappsubdeployments\n      operations:\n      - method: GET\n        name: listappsubdeployments\n        description: Oracle WebLogic Server List sub-deployments for an application\n        call: oracle-weblogic.listappsubdeployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /edit/appDeployments/{appName}/subDeployments\n      name: createappsubdeployment\n\
  \      operations:\n      - method: POST\n        name: createappsubdeployment\n        description: Oracle WebLogic Server Create a sub-deployment for an application\n        call: oracle-weblogic.createappsubdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-weblogic-mcp\n    transport: http\n    description: MCP adapter for Oracle WebLogic Server Oracle WebLogic Deployment API for AI agent use.\n    tools:\n    - name: startedit\n      description: Oracle WebLogic Server Start an edit session for deployment changes\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-weblogic.startedit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activatedeploymentchanges\n      description: Oracle WebLogic Server Activate pending deployment changes\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: oracle-weblogic.activatedeploymentchanges\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listappdeployments\n      description: Oracle WebLogic Server List all application deployments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-weblogic.listappdeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployapplication\n      description: Oracle WebLogic Server Deploy an application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-weblogic.deployapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappdeploymentcreateform\n      description: Oracle WebLogic Server Get application deployment creation form\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ oracle-weblogic.getappdeploymentcreateform\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappdeployment\n      description: Oracle WebLogic Server Get application deployment details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-weblogic.getappdeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateappdeployment\n      description: Oracle WebLogic Server Update application deployment configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-weblogic.updateappdeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: undeployapplication\n      description: Oracle WebLogic Server Undeploy an application\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-weblogic.undeployapplication\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlibdeployments\n      description: Oracle WebLogic Server List all shared library deployments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-weblogic.listlibdeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploylibrary\n      description: Oracle WebLogic Server Deploy a shared library\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-weblogic.deploylibrary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlibdeployment\n      description: Oracle WebLogic Server Get shared library deployment details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-weblogic.getlibdeployment\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: undeploylibrary\n      description: Oracle WebLogic Server Remove a shared library deployment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-weblogic.undeploylibrary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeploymentruntimes\n      description: Oracle WebLogic Server List deployment runtimes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-weblogic.listdeploymentruntimes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startapplication\n      description: Oracle WebLogic Server Start a deployed application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-weblogic.startapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopapplication\n      description: Oracle WebLogic\
  \ Server Stop a deployed application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-weblogic.stopapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: redeployapplication\n      description: Oracle WebLogic Server Redeploy an application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-weblogic.redeployapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapplication\n      description: Oracle WebLogic Server Update an application deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-weblogic.updateapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeploymenttaskstatus\n      description: Oracle WebLogic Server Get deployment task status\n      hints:\n      \
  \  readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-weblogic.getdeploymenttaskstatus\n      with:\n        taskId: tools.taskId\n      inputParameters:\n      - name: taskId\n        type: string\n        description: taskId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listserverapplicationruntimes\n      description: Oracle WebLogic Server List application runtimes on a server\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-weblogic.listserverapplicationruntimes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listappsubdeployments\n      description: Oracle WebLogic Server List sub-deployments for an application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-weblogic.listappsubdeployments\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: createappsubdeployment\n      description: Oracle WebLogic Server Create a sub-deployment for an application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-weblogic.createappsubdeployment\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ORACLE_WEBLOGIC_USERNAME: ORACLE_WEBLOGIC_USERNAME\n    ORACLE_WEBLOGIC_PASSWORD: ORACLE_WEBLOGIC_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-weblogic/refs/heads/main/capabilities/oracle-weblogic-capability.yaml
tags:
- Oracle
- Weblogic
- API
tools:
- description: Oracle WebLogic Server Start an edit session for deployment changes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startedit
- description: Oracle WebLogic Server Activate pending deployment changes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activatedeploymentchanges
- description: Oracle WebLogic Server List all application deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listappdeployments
- description: Oracle WebLogic Server Deploy an application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployapplication
- description: Oracle WebLogic Server Get application deployment creation form
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappdeploymentcreateform
- description: Oracle WebLogic Server Get application deployment details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappdeployment
- description: Oracle WebLogic Server Update application deployment configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateappdeployment
- description: Oracle WebLogic Server Undeploy an application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: undeployapplication
- description: Oracle WebLogic Server List all shared library deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlibdeployments
- description: Oracle WebLogic Server Deploy a shared library
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploylibrary
- description: Oracle WebLogic Server Get shared library deployment details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlibdeployment
- description: Oracle WebLogic Server Remove a shared library deployment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: undeploylibrary
- description: Oracle WebLogic Server List deployment runtimes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeploymentruntimes
- description: Oracle WebLogic Server Start a deployed application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startapplication
- description: Oracle WebLogic Server Stop a deployed application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopapplication
- description: Oracle WebLogic Server Redeploy an application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: redeployapplication
- description: Oracle WebLogic Server Update an application deployment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapplication
- description: Oracle WebLogic Server Get deployment task status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeploymenttaskstatus
- description: Oracle WebLogic Server List application runtimes on a server
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listserverapplicationruntimes
- description: Oracle WebLogic Server List sub-deployments for an application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listappsubdeployments
- description: Oracle WebLogic Server Create a sub-deployment for an application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createappsubdeployment
---
