---
categories: []
consumed_apis: []
description: Unified workflow for IT administrators combining environment provisioning, update management, process scheduling, integration broker, REST API management, application services framework, and component interface operations across PeopleSoft platform APIs.
layout: capability
name: PeopleSoft Platform Administration
operations:
- description: Retrieve provisioned environments.
  method: GET
  name: list-environments
  path: /v1/environments
- description: Provision a new environment.
  method: POST
  name: provision-environment
  path: /v1/environments
- description: Retrieve available provisioning templates.
  method: GET
  name: list-templates
  path: /v1/templates
- description: Retrieve available updates.
  method: GET
  name: list-updates
  path: /v1/updates
- description: Initiate application of a specific update.
  method: POST
  name: apply-update
  path: /v1/updates/{updateId}/apply
- description: Retrieve process requests and their run status.
  method: GET
  name: list-processes
  path: /v1/processes
- description: Submit a new process request.
  method: POST
  name: submit-process
  path: /v1/processes
- description: Retrieve the status of a specific process instance.
  method: GET
  name: get-process-status
  path: /v1/processes/{processInstance}
- description: Invoke a service operation using GET.
  method: GET
  name: get-service-operation
  path: /v1/service-operations/{serviceOperation}
- description: Invoke a service operation using POST.
  method: POST
  name: post-service-operation
  path: /v1/service-operations/{serviceOperation}
- description: Retrieve PeopleSoft resource data.
  method: GET
  name: get-resource
  path: /v1/resources/{resource}
- description: Create a new PeopleSoft resource.
  method: POST
  name: create-resource
  path: /v1/resources/{resource}
- description: Retrieve data from an ASF-defined service.
  method: GET
  name: get-service-resource
  path: /v1/services/{serviceName}
- description: Create a resource via an ASF-defined service.
  method: POST
  name: create-service-resource
  path: /v1/services/{serviceName}
- description: Retrieve data from a component interface.
  method: GET
  name: get-component-data
  path: /v1/component-interfaces/{componentInterface}
- description: Create a new record via a component interface.
  method: POST
  name: create-component-data
  path: /v1/component-interfaces/{componentInterface}
- description: Update an existing record via a component interface.
  method: PUT
  name: update-component-data
  path: /v1/component-interfaces/{componentInterface}
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- update an existing record via a component interface.
- submit process
- apply updates
- invoke an integration broker service operation using post.
- supply chain management
- retrieve data from a peoplesoft component interface.
- peoplesoft environments
- integration
- list environments
- list processes
- peoplesoft rest resources
- retrieve provisioned environments.
- integration broker service operations
- invoke a service operation using post.
- post service operation
- create a new peoplesoft resource.
- create a resource via an asf-defined service.
- update an existing record via a peoplesoft component interface.
- create service resource
- get resource
- devops
- peopletools platform services.
- peoplesoft
- provision a new peoplesoft environment on oci.
- list templates
- cloud manager
- retrieve available provisioning templates.
- create resource
- asf service resources
- campus solutions.
- financial and supply chain management.
- process instance details
- available updates and change packages
- human capital management.
- create a new peoplesoft resource via rest.
- get component data
- create a new record via a peoplesoft component interface.
- process requests
- erp
- financial management
- retrieve available updates.
- retrieve peoplesoft resource data via rest.
- crm
- invoke a service operation using get.
- retrieve provisioned peoplesoft environments.
- get service resource
- create a new record via a component interface.
- enterprise software
- platform administration
- peopletools
- retrieve the status of a specific process instance.
- hcm
- retrieve data from a component interface.
- submit a new process request.
- retrieve available updates and change packages.
- invoke a synchronous integration broker service operation using get.
- submit a new process request for scheduling.
- campus solutions
- retrieve peoplesoft resource data.
- component interface resources
- initiate application of a specific update or change package.
- get service operation
- provision environment
- provisioning templates
- retrieve process requests and their run status.
- provision a new environment.
- get process status
- apply update
- retrieve data from an asf-defined service.
- create component data
- update component data
- initiate application of a specific update.
- list updates
slug: platform-administration
source_filename: platform-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PeopleSoft Platform Administration\n  description: Unified workflow for IT administrators combining environment provisioning, update management, process scheduling,\n    integration broker, REST API management, application services framework, and component interface operations across PeopleSoft\n    platform APIs.\n  tags:\n  - PeopleSoft\n  - Platform Administration\n  - Cloud Manager\n  - Integration\n  - DevOps\n  - PeopleTools\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n    PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: cloud-manager\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/cloudmgr/v1\n    description: PeopleSoft Cloud Manager API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n\
  \    - name: environments\n      path: /environments\n      description: Environment provisioning and management\n      operations:\n      - name: list-environments\n        method: GET\n        description: Retrieve a list of provisioned PeopleSoft environments.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: provision-environment\n        method: POST\n        description: Provision a new PeopleSoft environment on OCI from a template.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            templateId: '{{tools.templateId}}'\n            environmentName: '{{tools.environmentName}}'\n            configuration: '{{tools.configuration}}'\n    - name: templates\n      path: /templates\n      description: Provisioning template operations\n      operations:\n   \
  \   - name: list-templates\n        method: GET\n        description: Retrieve available provisioning templates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: update-manager\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/pum/v1\n    description: PeopleSoft Update Manager API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: updates\n      path: /updates\n      description: Update and patch management operations\n      operations:\n      - name: list-updates\n        method: GET\n        description: Retrieve a list of available updates and change packages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: apply-update\n        method: POST\n        description:\
  \ Initiate application of a specific update or change package.\n        inputParameters:\n        - name: updateId\n          in: path\n          type: string\n          required: true\n          description: The update identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: process-scheduler\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/scheduler/v1\n    description: PeopleSoft Process Scheduler API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: processes\n      path: /processes\n      description: Process scheduling and monitoring operations\n      operations:\n      - name: list-processes\n        method: GET\n        description: Retrieve a list of process requests and their run status.\n        inputParameters:\n        - name: status\n   \
  \       in: query\n          type: string\n          required: false\n          description: Filter by process status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-process\n        method: POST\n        description: Submit a new process request for scheduling.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            processName: '{{tools.processName}}'\n            processType: '{{tools.processType}}'\n            serverName: '{{tools.serverName}}'\n            runDateTime: '{{tools.runDateTime}}'\n            parameters: '{{tools.parameters}}'\n      - name: get-process-status\n        method: GET\n        description: Retrieve the status and details of a specific process instance.\n        inputParameters:\n        - name: processInstance\n       \
  \   in: path\n          type: integer\n          required: true\n          description: The process instance number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: integration-broker\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/PSIGW/RESTListeningConnector\n    description: PeopleSoft Integration Broker\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: service-operations\n      path: /\n      description: Integration Broker service operations\n      operations:\n      - name: get-service-operation\n        method: GET\n        description: Invoke a synchronous Integration Broker REST service operation using GET.\n        inputParameters:\n        - name: serviceOperation\n          in: path\n          type: string\n          required: true\n          description:\
  \ The service operation name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-service-operation\n        method: POST\n        description: Invoke a synchronous or asynchronous Integration Broker REST service operation using POST.\n        inputParameters:\n        - name: serviceOperation\n          in: path\n          type: string\n          required: true\n          description: The service operation name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payload: '{{tools.payload}}'\n  - type: http\n    namespace: rest-api\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/v1\n    description: PeopleSoft REST API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n\
  \    resources:\n    - name: resources\n      path: /\n      description: PeopleSoft REST resource operations\n      operations:\n      - name: get-resource\n        method: GET\n        description: Retrieve PeopleSoft resource data via REST.\n        inputParameters:\n        - name: resource\n          in: path\n          type: string\n          required: true\n          description: The PeopleSoft resource name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-resource\n        method: POST\n        description: Create a new PeopleSoft resource via REST.\n        inputParameters:\n        - name: resource\n          in: path\n          type: string\n          required: true\n          description: The PeopleSoft resource name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            resource: '{{tools.resource}}'\n  - type: http\n    namespace: asf\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/asf/v1\n    description: PeopleSoft Application Services Framework API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: services\n      path: /\n      description: ASF service operations\n      operations:\n      - name: get-service-resource\n        method: GET\n        description: Retrieve data from an ASF-defined service with OpenAPI-compliant response.\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: The ASF service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service-resource\n        method: POST\n        description:\
  \ Create a resource via an ASF-defined service.\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: The ASF service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            serviceName: '{{tools.serviceName}}'\n  - type: http\n    namespace: component-interface\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/componentinterface/v1\n    description: PeopleSoft Component Interface API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: component-interfaces\n      path: /\n      description: Component interface operations\n      operations:\n      - name: get-component-data\n        method: GET\n        description: Retrieve data from\
  \ a PeopleSoft component interface.\n        inputParameters:\n        - name: componentInterface\n          in: path\n          type: string\n          required: true\n          description: The component interface name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-component-data\n        method: POST\n        description: Create a new record via a PeopleSoft component interface.\n        inputParameters:\n        - name: componentInterface\n          in: path\n          type: string\n          required: true\n          description: The component interface name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            componentInterface: '{{tools.componentInterface}}'\n      - name: update-component-data\n        method: PUT\n        description: Update\
  \ an existing record via a PeopleSoft component interface.\n        inputParameters:\n        - name: componentInterface\n          in: path\n          type: string\n          required: true\n          description: The component interface name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            componentInterface: '{{tools.componentInterface}}'\n  exposes:\n  - type: rest\n    port: 8085\n    namespace: platform-admin-api\n    description: Unified REST API for PeopleSoft platform administration workflows.\n    resources:\n    - path: /v1/environments\n      name: environments\n      description: PeopleSoft environments\n      operations:\n      - method: GET\n        name: list-environments\n        description: Retrieve provisioned environments.\n        call: cloud-manager.list-environments\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n      - method: POST\n        name: provision-environment\n        description: Provision a new environment.\n        call: cloud-manager.provision-environment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/templates\n      name: templates\n      description: Provisioning templates\n      operations:\n      - method: GET\n        name: list-templates\n        description: Retrieve available provisioning templates.\n        call: cloud-manager.list-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/updates\n      name: updates\n      description: Available updates and change packages\n      operations:\n      - method: GET\n        name: list-updates\n        description: Retrieve available updates.\n        call: update-manager.list-updates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/updates/{updateId}/apply\n      name: update-apply\n\
  \      description: Apply updates\n      operations:\n      - method: POST\n        name: apply-update\n        description: Initiate application of a specific update.\n        call: update-manager.apply-update\n        with:\n          updateId: rest.updateId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/processes\n      name: processes\n      description: Process requests\n      operations:\n      - method: GET\n        name: list-processes\n        description: Retrieve process requests and their run status.\n        call: process-scheduler.list-processes\n        with:\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-process\n        description: Submit a new process request.\n        call: process-scheduler.submit-process\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/processes/{processInstance}\n\
  \      name: process-detail\n      description: Process instance details\n      operations:\n      - method: GET\n        name: get-process-status\n        description: Retrieve the status of a specific process instance.\n        call: process-scheduler.get-process-status\n        with:\n          processInstance: rest.processInstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/service-operations/{serviceOperation}\n      name: service-operations\n      description: Integration Broker service operations\n      operations:\n      - method: GET\n        name: get-service-operation\n        description: Invoke a service operation using GET.\n        call: integration-broker.get-service-operation\n        with:\n          serviceOperation: rest.serviceOperation\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: post-service-operation\n        description: Invoke a service operation using\
  \ POST.\n        call: integration-broker.post-service-operation\n        with:\n          serviceOperation: rest.serviceOperation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/resources/{resource}\n      name: resources\n      description: PeopleSoft REST resources\n      operations:\n      - method: GET\n        name: get-resource\n        description: Retrieve PeopleSoft resource data.\n        call: rest-api.get-resource\n        with:\n          resource: rest.resource\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-resource\n        description: Create a new PeopleSoft resource.\n        call: rest-api.create-resource\n        with:\n          resource: rest.resource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceName}\n      name: services\n      description: ASF service resources\n      operations:\n    \
  \  - method: GET\n        name: get-service-resource\n        description: Retrieve data from an ASF-defined service.\n        call: asf.get-service-resource\n        with:\n          serviceName: rest.serviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-service-resource\n        description: Create a resource via an ASF-defined service.\n        call: asf.create-service-resource\n        with:\n          serviceName: rest.serviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/component-interfaces/{componentInterface}\n      name: component-interfaces\n      description: Component interface resources\n      operations:\n      - method: GET\n        name: get-component-data\n        description: Retrieve data from a component interface.\n        call: component-interface.get-component-data\n        with:\n          componentInterface: rest.componentInterface\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-component-data\n        description: Create a new record via a component interface.\n        call: component-interface.create-component-data\n        with:\n          componentInterface: rest.componentInterface\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-component-data\n        description: Update an existing record via a component interface.\n        call: component-interface.update-component-data\n        with:\n          componentInterface: rest.componentInterface\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9095\n    namespace: platform-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted PeopleSoft platform administration workflows.\n    tools:\n    - name: list-environments\n      description: Retrieve provisioned PeopleSoft\
  \ environments.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-manager.list-environments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provision-environment\n      description: Provision a new PeopleSoft environment on OCI.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cloud-manager.provision-environment\n      with:\n        templateId: tools.templateId\n        environmentName: tools.environmentName\n        configuration: tools.configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-templates\n      description: Retrieve available provisioning templates.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-manager.list-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-updates\n      description: Retrieve available updates and change packages.\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: update-manager.list-updates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: apply-update\n      description: Initiate application of a specific update or change package.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: false\n      call: update-manager.apply-update\n      with:\n        updateId: tools.updateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-processes\n      description: Retrieve process requests and their run status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: process-scheduler.list-processes\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-process\n      description: Submit a new process request for scheduling.\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: process-scheduler.submit-process\n      with:\n        processName: tools.processName\n        processType: tools.processType\n        serverName: tools.serverName\n        runDateTime: tools.runDateTime\n        parameters: tools.parameters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-process-status\n      description: Retrieve the status of a specific process instance.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: process-scheduler.get-process-status\n      with:\n        processInstance: tools.processInstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service-operation\n      description: Invoke a synchronous Integration Broker service operation using GET.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: integration-broker.get-service-operation\n      with:\n        serviceOperation: tools.serviceOperation\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-service-operation\n      description: Invoke an Integration Broker service operation using POST.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: integration-broker.post-service-operation\n      with:\n        serviceOperation: tools.serviceOperation\n        payload: tools.payload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-resource\n      description: Retrieve PeopleSoft resource data via REST.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-resource\n      with:\n        resource: tools.resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-resource\n      description: Create a new PeopleSoft resource via REST.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: rest-api.create-resource\n\
  \      with:\n        resource: tools.resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service-resource\n      description: Retrieve data from an ASF-defined service.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: asf.get-service-resource\n      with:\n        serviceName: tools.serviceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-service-resource\n      description: Create a resource via an ASF-defined service.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: asf.create-service-resource\n      with:\n        serviceName: tools.serviceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-component-data\n      description: Retrieve data from a PeopleSoft component interface.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: component-interface.get-component-data\n\
  \      with:\n        componentInterface: tools.componentInterface\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-component-data\n      description: Create a new record via a PeopleSoft component interface.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: component-interface.create-component-data\n      with:\n        componentInterface: tools.componentInterface\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-component-data\n      description: Update an existing record via a PeopleSoft component interface.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: component-interface.update-component-data\n      with:\n        componentInterface: tools.componentInterface\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/capabilities/platform-administration.yaml
tags:
- PeopleSoft
- Platform Administration
- Cloud Manager
- Integration
- DevOps
- PeopleTools
tools:
- description: Retrieve provisioned PeopleSoft environments.
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: Provision a new PeopleSoft environment on OCI.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provision-environment
- description: Retrieve available provisioning templates.
  hints:
    openWorld: true
    readOnly: true
  name: list-templates
- description: Retrieve available updates and change packages.
  hints:
    openWorld: true
    readOnly: true
  name: list-updates
- description: Initiate application of a specific update or change package.
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: apply-update
- description: Retrieve process requests and their run status.
  hints:
    openWorld: true
    readOnly: true
  name: list-processes
- description: Submit a new process request for scheduling.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-process
- description: Retrieve the status of a specific process instance.
  hints:
    openWorld: true
    readOnly: true
  name: get-process-status
- description: Invoke a synchronous Integration Broker service operation using GET.
  hints:
    openWorld: true
    readOnly: true
  name: get-service-operation
- description: Invoke an Integration Broker service operation using POST.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-service-operation
- description: Retrieve PeopleSoft resource data via REST.
  hints:
    openWorld: true
    readOnly: true
  name: get-resource
- description: Create a new PeopleSoft resource via REST.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-resource
- description: Retrieve data from an ASF-defined service.
  hints:
    openWorld: true
    readOnly: true
  name: get-service-resource
- description: Create a resource via an ASF-defined service.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-service-resource
- description: Retrieve data from a PeopleSoft component interface.
  hints:
    openWorld: true
    readOnly: true
  name: get-component-data
- description: Create a new record via a PeopleSoft component interface.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-component-data
- description: Update an existing record via a PeopleSoft component interface.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-component-data
---
