---
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
- devops
- retrieve available updates.
- get service operation
- retrieve available updates and change packages.
- update an existing record via a peoplesoft component interface.
- get component data
- peoplesoft environments
- retrieve the status of a specific process instance.
- initiate application of a specific update.
- financial and supply chain management.
- integration broker service operations
- retrieve provisioned environments.
- submit a new process request.
- human capital management.
- asf service resources
- retrieve provisioned peoplesoft environments.
- peoplesoft
- retrieve process requests and their run status.
- retrieve data from an asf-defined service.
- cloud manager
- get process status
- invoke a service operation using get.
- apply update
- retrieve peoplesoft resource data via rest.
- create resource
- invoke a service operation using post.
- peopletools
- integration
- get resource
- campus solutions.
- list processes
- retrieve available provisioning templates.
- platform administration
- submit process
- list updates
- peoplesoft rest resources
- submit a new process request for scheduling.
- campus solutions
- get service resource
- hcm
- provision a new environment.
- provisioning templates
- create component data
- initiate application of a specific update or change package.
- component interface resources
- supply chain management
- enterprise software
- retrieve peoplesoft resource data.
- update component data
- create a new peoplesoft resource.
- invoke a synchronous integration broker service operation using get.
- process requests
- retrieve data from a peoplesoft component interface.
- crm
- financial management
- process instance details
- create a new record via a component interface.
- post service operation
- create a resource via an asf-defined service.
- create a new record via a peoplesoft component interface.
- invoke an integration broker service operation using post.
- available updates and change packages
- list templates
- provision a new peoplesoft environment on oci.
- erp
- update an existing record via a component interface.
- apply updates
- create service resource
- list environments
- create a new peoplesoft resource via rest.
- peopletools platform services.
- retrieve data from a component interface.
- provision environment
slug: platform-administration
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
