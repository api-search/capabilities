---
api_specs:
- filename: cloud-manager.yml
  format: yaml
  label: cloud-manager
  slug: cloud-manager
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/cloud-manager.yml
- filename: update-manager.yml
  format: yaml
  label: update-manager
  slug: update-manager
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/update-manager.yml
- filename: process-scheduler.yml
  format: yaml
  label: process-scheduler
  slug: process-scheduler
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/process-scheduler.yml
- filename: integration-broker.yml
  format: yaml
  label: integration-broker
  slug: integration-broker
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/integration-broker.yml
- filename: rest-api.yml
  format: yaml
  label: rest-api
  slug: rest-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/rest-api.yml
- filename: application-services-framework.yml
  format: yaml
  label: asf
  slug: asf
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/application-services-framework.yml
- filename: component-interface.yml
  format: yaml
  label: component-interface
  slug: component-interface
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/component-interface.yml
categories: []
consumed_apis:
- cloud-manager
- update-manager
- process-scheduler
- integration-broker
- rest-api
- asf
- component-interface
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
- list templates
- retrieve available provisioning templates.
- peopletools
- retrieve process requests and their run status.
- retrieve provisioned peoplesoft environments.
- create service resource
- retrieve provisioned environments.
- provision environment
- retrieve available updates.
- list processes
- submit a new process request for scheduling.
- human capital management.
- create a resource via an asf-defined service.
- create a new record via a peoplesoft component interface.
- peoplesoft rest resources
- create a new record via a component interface.
- retrieve peoplesoft resource data.
- initiate application of a specific update or change package.
- enterprise software
- retrieve data from an asf-defined service.
- hcm
- list environments
- provision a new peoplesoft environment on oci.
- campus solutions
- component interface resources
- create a new peoplesoft resource via rest.
- integration broker service operations
- devops
- erp
- platform administration
- crm
- retrieve the status of a specific process instance.
- submit process
- financial and supply chain management.
- update an existing record via a component interface.
- apply updates
- retrieve available updates and change packages.
- post service operation
- create resource
- create component data
- supply chain management
- list updates
- integration
- process requests
- get process status
- get component data
- invoke an integration broker service operation using post.
- financial management
- peopletools platform services.
- process instance details
- asf service resources
- get service operation
- invoke a service operation using post.
- peoplesoft
- provision a new environment.
- apply update
- retrieve data from a component interface.
- update component data
- cloud manager
- invoke a synchronous integration broker service operation using get.
- retrieve peoplesoft resource data via rest.
- retrieve data from a peoplesoft component interface.
- provisioning templates
- update an existing record via a peoplesoft component interface.
- get resource
- initiate application of a specific update.
- peoplesoft environments
- available updates and change packages
- invoke a service operation using get.
- get service resource
- submit a new process request.
- create a new peoplesoft resource.
- campus solutions.
slug: platform-administration
source_filename: platform-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"PeopleSoft Platform Administration\"\n  description: \"Unified workflow for IT administrators combining environment provisioning, update management, process scheduling, integration broker, REST API management, application services framework, and component interface operations across PeopleSoft platform APIs.\"\n  tags:\n    - PeopleSoft\n    - Platform Administration\n    - Cloud Manager\n    - Integration\n    - DevOps\n    - PeopleTools\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n      PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\n\ncapability:\n  consumes:\n    - import: cloud-manager\n      location: ./shared/cloud-manager.yaml\n    - import: update-manager\n      location: ./shared/update-manager.yaml\n    - import: process-scheduler\n      location: ./shared/process-scheduler.yaml\n    - import: integration-broker\n      location:\
  \ ./shared/integration-broker.yaml\n    - import: rest-api\n      location: ./shared/rest-api.yaml\n    - import: asf\n      location: ./shared/application-services-framework.yaml\n    - import: component-interface\n      location: ./shared/component-interface.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: platform-admin-api\n      description: \"Unified REST API for PeopleSoft platform administration workflows.\"\n      resources:\n        - path: /v1/environments\n          name: environments\n          description: \"PeopleSoft environments\"\n          operations:\n            - method: GET\n              name: list-environments\n              description: \"Retrieve provisioned environments.\"\n              call: \"cloud-manager.list-environments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: provision-environment\n              description: \"Provision\
  \ a new environment.\"\n              call: \"cloud-manager.provision-environment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/templates\n          name: templates\n          description: \"Provisioning templates\"\n          operations:\n            - method: GET\n              name: list-templates\n              description: \"Retrieve available provisioning templates.\"\n              call: \"cloud-manager.list-templates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/updates\n          name: updates\n          description: \"Available updates and change packages\"\n          operations:\n            - method: GET\n              name: list-updates\n              description: \"Retrieve available updates.\"\n              call: \"update-manager.list-updates\"\n              outputParameters:\n                - type: object\n        \
  \          mapping: \"$.\"\n        - path: /v1/updates/{updateId}/apply\n          name: update-apply\n          description: \"Apply updates\"\n          operations:\n            - method: POST\n              name: apply-update\n              description: \"Initiate application of a specific update.\"\n              call: \"update-manager.apply-update\"\n              with:\n                updateId: \"rest.updateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/processes\n          name: processes\n          description: \"Process requests\"\n          operations:\n            - method: GET\n              name: list-processes\n              description: \"Retrieve process requests and their run status.\"\n              call: \"process-scheduler.list-processes\"\n              with:\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n            - method: POST\n              name: submit-process\n              description: \"Submit a new process request.\"\n              call: \"process-scheduler.submit-process\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/processes/{processInstance}\n          name: process-detail\n          description: \"Process instance details\"\n          operations:\n            - method: GET\n              name: get-process-status\n              description: \"Retrieve the status of a specific process instance.\"\n              call: \"process-scheduler.get-process-status\"\n              with:\n                processInstance: \"rest.processInstance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/service-operations/{serviceOperation}\n          name: service-operations\n          description: \"Integration Broker service operations\"\
  \n          operations:\n            - method: GET\n              name: get-service-operation\n              description: \"Invoke a service operation using GET.\"\n              call: \"integration-broker.get-service-operation\"\n              with:\n                serviceOperation: \"rest.serviceOperation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: post-service-operation\n              description: \"Invoke a service operation using POST.\"\n              call: \"integration-broker.post-service-operation\"\n              with:\n                serviceOperation: \"rest.serviceOperation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resources/{resource}\n          name: resources\n          description: \"PeopleSoft REST resources\"\n          operations:\n            - method: GET\n              name: get-resource\n\
  \              description: \"Retrieve PeopleSoft resource data.\"\n              call: \"rest-api.get-resource\"\n              with:\n                resource: \"rest.resource\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-resource\n              description: \"Create a new PeopleSoft resource.\"\n              call: \"rest-api.create-resource\"\n              with:\n                resource: \"rest.resource\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/services/{serviceName}\n          name: services\n          description: \"ASF service resources\"\n          operations:\n            - method: GET\n              name: get-service-resource\n              description: \"Retrieve data from an ASF-defined service.\"\n              call: \"asf.get-service-resource\"\n              with:\n             \
  \   serviceName: \"rest.serviceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-service-resource\n              description: \"Create a resource via an ASF-defined service.\"\n              call: \"asf.create-service-resource\"\n              with:\n                serviceName: \"rest.serviceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/component-interfaces/{componentInterface}\n          name: component-interfaces\n          description: \"Component interface resources\"\n          operations:\n            - method: GET\n              name: get-component-data\n              description: \"Retrieve data from a component interface.\"\n              call: \"component-interface.get-component-data\"\n              with:\n                componentInterface: \"rest.componentInterface\"\n           \
  \   outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-component-data\n              description: \"Create a new record via a component interface.\"\n              call: \"component-interface.create-component-data\"\n              with:\n                componentInterface: \"rest.componentInterface\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-component-data\n              description: \"Update an existing record via a component interface.\"\n              call: \"component-interface.update-component-data\"\n              with:\n                componentInterface: \"rest.componentInterface\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9095\n      namespace: platform-admin-mcp\n      transport: http\n \
  \     description: \"MCP server for AI-assisted PeopleSoft platform administration workflows.\"\n      tools:\n        - name: list-environments\n          description: \"Retrieve provisioned PeopleSoft environments.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-manager.list-environments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: provision-environment\n          description: \"Provision a new PeopleSoft environment on OCI.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"cloud-manager.provision-environment\"\n          with:\n            templateId: \"tools.templateId\"\n            environmentName: \"tools.environmentName\"\n            configuration: \"tools.configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-templates\n\
  \          description: \"Retrieve available provisioning templates.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-manager.list-templates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-updates\n          description: \"Retrieve available updates and change packages.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"update-manager.list-updates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: apply-update\n          description: \"Initiate application of a specific update or change package.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"update-manager.apply-update\"\n          with:\n            updateId: \"tools.updateId\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n        - name: list-processes\n          description: \"Retrieve process requests and their run status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"process-scheduler.list-processes\"\n          with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-process\n          description: \"Submit a new process request for scheduling.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"process-scheduler.submit-process\"\n          with:\n            processName: \"tools.processName\"\n            processType: \"tools.processType\"\n            serverName: \"tools.serverName\"\n            runDateTime: \"tools.runDateTime\"\n            parameters: \"tools.parameters\"\n          outputParameters:\n            - type: object\n           \
  \   mapping: \"$.\"\n        - name: get-process-status\n          description: \"Retrieve the status of a specific process instance.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"process-scheduler.get-process-status\"\n          with:\n            processInstance: \"tools.processInstance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service-operation\n          description: \"Invoke a synchronous Integration Broker service operation using GET.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"integration-broker.get-service-operation\"\n          with:\n            serviceOperation: \"tools.serviceOperation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post-service-operation\n          description: \"Invoke an Integration Broker service operation using POST.\"\n     \
  \     hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"integration-broker.post-service-operation\"\n          with:\n            serviceOperation: \"tools.serviceOperation\"\n            payload: \"tools.payload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-resource\n          description: \"Retrieve PeopleSoft resource data via REST.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-resource\"\n          with:\n            resource: \"tools.resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-resource\n          description: \"Create a new PeopleSoft resource via REST.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"rest-api.create-resource\"\n\
  \          with:\n            resource: \"tools.resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service-resource\n          description: \"Retrieve data from an ASF-defined service.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"asf.get-service-resource\"\n          with:\n            serviceName: \"tools.serviceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-service-resource\n          description: \"Create a resource via an ASF-defined service.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"asf.create-service-resource\"\n          with:\n            serviceName: \"tools.serviceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-component-data\n     \
  \     description: \"Retrieve data from a PeopleSoft component interface.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"component-interface.get-component-data\"\n          with:\n            componentInterface: \"tools.componentInterface\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-component-data\n          description: \"Create a new record via a PeopleSoft component interface.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"component-interface.create-component-data\"\n          with:\n            componentInterface: \"tools.componentInterface\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-component-data\n          description: \"Update an existing record via a PeopleSoft component interface.\"\n          hints:\n      \
  \      readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"component-interface.update-component-data\"\n          with:\n            componentInterface: \"tools.componentInterface\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
