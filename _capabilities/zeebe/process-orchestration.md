---
api_specs:
- filename: zeebe-api.yml
  format: yaml
  label: zeebe
  slug: zeebe
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/zeebe/refs/heads/main/openapi/zeebe-api.yml
categories: []
consumed_apis:
- zeebe
description: Unified workflow capability for process orchestration with Zeebe, combining deployment, instance management, job handling, message correlation, signal broadcasting, incident resolution, and user task management for BPMN-based process automation.
layout: capability
name: Zeebe Process Orchestration
operations:
- description: Get current cluster topology
  method: GET
  name: get-topology
  path: /v1/topology
- description: Deploy BPMN, DMN, or form resources
  method: POST
  name: deploy-resources
  path: /v1/deployments
- description: Create and start a new process instance
  method: POST
  name: create-process-instance
  path: /v1/process-instances
- description: Cancel a running process instance
  method: DELETE
  name: cancel-process-instance
  path: /v1/process-instances/{processInstanceKey}
- description: Migrate a process instance
  method: POST
  name: migrate-process-instance
  path: /v1/process-instances/{processInstanceKey}/migration
- description: Activate available jobs for a worker
  method: POST
  name: activate-jobs
  path: /v1/jobs/activation
- description: Complete a job
  method: POST
  name: complete-job
  path: /v1/jobs/{jobKey}/completion
- description: Report a job failure
  method: POST
  name: fail-job
  path: /v1/jobs/{jobKey}/failure
- description: Throw a BPMN error for boundary event handling
  method: POST
  name: throw-error
  path: /v1/jobs/{jobKey}/error
- description: Update the retry count for a job
  method: PATCH
  name: update-job-retries
  path: /v1/jobs/{jobKey}/retries
- description: Publish a message for correlation
  method: POST
  name: publish-message
  path: /v1/messages
- description: Broadcast a signal
  method: POST
  name: broadcast-signal
  path: /v1/signals
- description: Resolve an incident to retry the failed operation
  method: POST
  name: resolve-incident
  path: /v1/incidents/{incidentKey}/resolution
- description: Assign a user task to a specific user
  method: POST
  name: assign-user-task
  path: /v1/user-tasks/{userTaskKey}/assignment
- description: Complete a user task
  method: POST
  name: complete-user-task
  path: /v1/user-tasks/{userTaskKey}/completion
personas: []
provider_name: Zeebe
provider_slug: zeebe
search_terms:
- update job retries
- delete a deployed resource (process, decision, or form) from zeebe
- complete a user task
- resolve incident
- report a job failure to trigger retry logic or incident creation
- bpmn
- cancel a running process instance
- broadcast signal
- assign user tasks
- assign user task
- deploy process definitions and resources
- fail job
- process automation
- deploy resources
- update the retry count for a job
- resolve process incidents
- deploy bpmn process definitions, dmn decisions, or forms to the zeebe engine
- broadcast signals to process subscriptions
- complete user task
- broadcast a signal
- activate and lock jobs of a given type for a worker to process
- complete a job with output variables after worker processing
- broadcast a named signal to all matching signal catch events in running processes
- complete a job
- mark a job as completed
- assign a user task to a specific user for completion
- publish a message for correlation with waiting process subscriptions
- create and start a new bpmn process instance with optional input variables
- cancel a running process instance and all its subprocesses
- update the remaining retry count for a job
- cluster topology and health
- throw a bpmn error from a job
- publish a message for correlation
- delete resource
- activate jobs for worker processing
- get topology
- cancel a specific process instance
- update job retry count
- complete a user task with optional output variables
- cloud native
- distributed systems
- publish message
- report a job failure
- throw a bpmn error for boundary event handling
- microservices
- cancel process instance
- publish messages for process correlation
- migrate process instance
- create and start a new process instance
- create process instance
- complete user tasks
- get the current zeebe cluster topology showing brokers, partitions, and health
- complete job
- migrate a running process instance to a newer version of the process definition
- resolve an incident to allow the failed operation to be retried
- get current cluster topology
- throw error
- activate available jobs for a worker
- workflow orchestration
- process instance lifecycle management
- assign a user task to a specific user
- activate jobs
- migrate a process instance
- deploy bpmn, dmn, or form resources
- resolve an incident to retry the failed operation
- throw a bpmn error from a job to trigger error boundary event handling
- camunda
- migrate a process instance to a new version
- java
slug: process-orchestration
source_filename: process-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Zeebe Process Orchestration\"\n  description: \"Unified workflow capability for process orchestration with Zeebe, combining deployment, instance management, job handling, message correlation, signal broadcasting, incident resolution, and user task management for BPMN-based process automation.\"\n  tags:\n    - BPMN\n    - Camunda\n    - Cloud Native\n    - Process Automation\n    - Workflow Orchestration\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      ZEEBE_BEARER_TOKEN: ZEEBE_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: zeebe\n      location: ./shared/zeebe-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: zeebe-orchestration-api\n      description: \"Unified REST API for Zeebe process orchestration workflows.\"\n      resources:\n        - path: /v1/topology\n          name: topology\n          description: \"Cluster topology and health\"\
  \n          operations:\n            - method: GET\n              name: get-topology\n              description: \"Get current cluster topology\"\n              call: \"zeebe.get-topology\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments\n          name: deployments\n          description: \"Deploy process definitions and resources\"\n          operations:\n            - method: POST\n              name: deploy-resources\n              description: \"Deploy BPMN, DMN, or form resources\"\n              call: \"zeebe.deploy-resources\"\n              with:\n                resources: \"rest.resources\"\n                tenantId: \"rest.tenantId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/process-instances\n          name: process-instances\n          description: \"Process instance lifecycle management\"\n          operations:\n\
  \            - method: POST\n              name: create-process-instance\n              description: \"Create and start a new process instance\"\n              call: \"zeebe.create-process-instance\"\n              with:\n                bpmnProcessId: \"rest.bpmnProcessId\"\n                processDefinitionKey: \"rest.processDefinitionKey\"\n                variables: \"rest.variables\"\n                tenantId: \"rest.tenantId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/process-instances/{processInstanceKey}\n          name: process-instance\n          description: \"Cancel a specific process instance\"\n          operations:\n            - method: DELETE\n              name: cancel-process-instance\n              description: \"Cancel a running process instance\"\n              call: \"zeebe.cancel-process-instance\"\n              with:\n                processInstanceKey: \"rest.processInstanceKey\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/process-instances/{processInstanceKey}/migration\n          name: process-instance-migration\n          description: \"Migrate a process instance to a new version\"\n          operations:\n            - method: POST\n              name: migrate-process-instance\n              description: \"Migrate a process instance\"\n              call: \"zeebe.migrate-process-instance\"\n              with:\n                processInstanceKey: \"rest.processInstanceKey\"\n                targetProcessDefinitionKey: \"rest.targetProcessDefinitionKey\"\n                mappingInstructions: \"rest.mappingInstructions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/activation\n          name: jobs-activation\n          description: \"Activate jobs for worker processing\"\n          operations:\n    \
  \        - method: POST\n              name: activate-jobs\n              description: \"Activate available jobs for a worker\"\n              call: \"zeebe.activate-jobs\"\n              with:\n                type: \"rest.type\"\n                timeout: \"rest.timeout\"\n                maxJobsToActivate: \"rest.maxJobsToActivate\"\n                worker: \"rest.worker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{jobKey}/completion\n          name: job-completion\n          description: \"Mark a job as completed\"\n          operations:\n            - method: POST\n              name: complete-job\n              description: \"Complete a job\"\n              call: \"zeebe.complete-job\"\n              with:\n                jobKey: \"rest.jobKey\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n \
  \       - path: /v1/jobs/{jobKey}/failure\n          name: job-failure\n          description: \"Report a job failure\"\n          operations:\n            - method: POST\n              name: fail-job\n              description: \"Report a job failure\"\n              call: \"zeebe.fail-job\"\n              with:\n                jobKey: \"rest.jobKey\"\n                retries: \"rest.retries\"\n                errorMessage: \"rest.errorMessage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{jobKey}/error\n          name: job-error\n          description: \"Throw a BPMN error from a job\"\n          operations:\n            - method: POST\n              name: throw-error\n              description: \"Throw a BPMN error for boundary event handling\"\n              call: \"zeebe.throw-error\"\n              with:\n                jobKey: \"rest.jobKey\"\n                errorCode: \"rest.errorCode\"\n   \
  \             errorMessage: \"rest.errorMessage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{jobKey}/retries\n          name: job-retries\n          description: \"Update job retry count\"\n          operations:\n            - method: PATCH\n              name: update-job-retries\n              description: \"Update the retry count for a job\"\n              call: \"zeebe.update-job-retries\"\n              with:\n                jobKey: \"rest.jobKey\"\n                retries: \"rest.retries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/messages\n          name: messages\n          description: \"Publish messages for process correlation\"\n          operations:\n            - method: POST\n              name: publish-message\n              description: \"Publish a message for correlation\"\n              call: \"zeebe.publish-message\"\
  \n              with:\n                name: \"rest.name\"\n                correlationKey: \"rest.correlationKey\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/signals\n          name: signals\n          description: \"Broadcast signals to process subscriptions\"\n          operations:\n            - method: POST\n              name: broadcast-signal\n              description: \"Broadcast a signal\"\n              call: \"zeebe.broadcast-signal\"\n              with:\n                signalName: \"rest.signalName\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/incidents/{incidentKey}/resolution\n          name: incident-resolution\n          description: \"Resolve process incidents\"\n          operations:\n            - method: POST\n   \
  \           name: resolve-incident\n              description: \"Resolve an incident to retry the failed operation\"\n              call: \"zeebe.resolve-incident\"\n              with:\n                incidentKey: \"rest.incidentKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/user-tasks/{userTaskKey}/assignment\n          name: user-task-assignment\n          description: \"Assign user tasks\"\n          operations:\n            - method: POST\n              name: assign-user-task\n              description: \"Assign a user task to a specific user\"\n              call: \"zeebe.assign-user-task\"\n              with:\n                userTaskKey: \"rest.userTaskKey\"\n                assignee: \"rest.assignee\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/user-tasks/{userTaskKey}/completion\n          name: user-task-completion\n\
  \          description: \"Complete user tasks\"\n          operations:\n            - method: POST\n              name: complete-user-task\n              description: \"Complete a user task\"\n              call: \"zeebe.complete-user-task\"\n              with:\n                userTaskKey: \"rest.userTaskKey\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: zeebe-orchestration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Zeebe process orchestration and workflow automation.\"\n      tools:\n        - name: get-topology\n          description: \"Get the current Zeebe cluster topology showing brokers, partitions, and health\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zeebe.get-topology\"\n          outputParameters:\n            - type: object\n       \
  \       mapping: \"$.\"\n\n        - name: deploy-resources\n          description: \"Deploy BPMN process definitions, DMN decisions, or forms to the Zeebe engine\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zeebe.deploy-resources\"\n          with:\n            resources: \"tools.resources\"\n            tenantId: \"tools.tenantId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-process-instance\n          description: \"Create and start a new BPMN process instance with optional input variables\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zeebe.create-process-instance\"\n          with:\n            bpmnProcessId: \"tools.bpmnProcessId\"\n            processDefinitionKey: \"tools.processDefinitionKey\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n\n        - name: cancel-process-instance\n          description: \"Cancel a running process instance and all its subprocesses\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"zeebe.cancel-process-instance\"\n          with:\n            processInstanceKey: \"tools.processInstanceKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: migrate-process-instance\n          description: \"Migrate a running process instance to a newer version of the process definition\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zeebe.migrate-process-instance\"\n          with:\n            processInstanceKey: \"tools.processInstanceKey\"\n            targetProcessDefinitionKey: \"tools.targetProcessDefinitionKey\"\n            mappingInstructions: \"tools.mappingInstructions\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: activate-jobs\n          description: \"Activate and lock jobs of a given type for a worker to process\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zeebe.activate-jobs\"\n          with:\n            type: \"tools.type\"\n            timeout: \"tools.timeout\"\n            maxJobsToActivate: \"tools.maxJobsToActivate\"\n            worker: \"tools.worker\"\n            fetchVariable: \"tools.fetchVariable\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: complete-job\n          description: \"Complete a job with output variables after worker processing\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"zeebe.complete-job\"\n          with:\n            jobKey: \"tools.jobKey\"\n            variables: \"tools.variables\"\n          outputParameters:\n \
  \           - type: object\n              mapping: \"$.\"\n\n        - name: fail-job\n          description: \"Report a job failure to trigger retry logic or incident creation\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zeebe.fail-job\"\n          with:\n            jobKey: \"tools.jobKey\"\n            retries: \"tools.retries\"\n            errorMessage: \"tools.errorMessage\"\n            retryBackOff: \"tools.retryBackOff\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: throw-error\n          description: \"Throw a BPMN error from a job to trigger error boundary event handling\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"zeebe.throw-error\"\n          with:\n            jobKey: \"tools.jobKey\"\n            errorCode: \"tools.errorCode\"\n            errorMessage: \"tools.errorMessage\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-job-retries\n          description: \"Update the remaining retry count for a job\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"zeebe.update-job-retries\"\n          with:\n            jobKey: \"tools.jobKey\"\n            retries: \"tools.retries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: publish-message\n          description: \"Publish a message for correlation with waiting process subscriptions\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zeebe.publish-message\"\n          with:\n            name: \"tools.name\"\n            correlationKey: \"tools.correlationKey\"\n            variables: \"tools.variables\"\n            timeToLive: \"tools.timeToLive\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: broadcast-signal\n          description: \"Broadcast a named signal to all matching signal catch events in running processes\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zeebe.broadcast-signal\"\n          with:\n            signalName: \"tools.signalName\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: resolve-incident\n          description: \"Resolve an incident to allow the failed operation to be retried\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"zeebe.resolve-incident\"\n          with:\n            incidentKey: \"tools.incidentKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-resource\n          description: \"Delete a deployed resource (process,\
  \ decision, or form) from Zeebe\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"zeebe.delete-resource\"\n          with:\n            resourceKey: \"tools.resourceKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: assign-user-task\n          description: \"Assign a user task to a specific user for completion\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"zeebe.assign-user-task\"\n          with:\n            userTaskKey: \"tools.userTaskKey\"\n            assignee: \"tools.assignee\"\n            allowOverride: \"tools.allowOverride\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: complete-user-task\n          description: \"Complete a user task with optional output variables\"\n          hints:\n            readOnly: false\n          \
  \  idempotent: true\n          call: \"zeebe.complete-user-task\"\n          with:\n            userTaskKey: \"tools.userTaskKey\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zeebe/refs/heads/main/capabilities/process-orchestration.yaml
tags:
- BPMN
- Camunda
- Cloud Native
- Process Automation
- Workflow Orchestration
tools:
- description: Get the current Zeebe cluster topology showing brokers, partitions, and health
  hints:
    idempotent: true
    readOnly: true
  name: get-topology
- description: Deploy BPMN process definitions, DMN decisions, or forms to the Zeebe engine
  hints:
    idempotent: false
    readOnly: false
  name: deploy-resources
- description: Create and start a new BPMN process instance with optional input variables
  hints:
    idempotent: false
    readOnly: false
  name: create-process-instance
- description: Cancel a running process instance and all its subprocesses
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-process-instance
- description: Migrate a running process instance to a newer version of the process definition
  hints:
    idempotent: false
    readOnly: false
  name: migrate-process-instance
- description: Activate and lock jobs of a given type for a worker to process
  hints:
    idempotent: false
    readOnly: false
  name: activate-jobs
- description: Complete a job with output variables after worker processing
  hints:
    idempotent: true
    readOnly: false
  name: complete-job
- description: Report a job failure to trigger retry logic or incident creation
  hints:
    idempotent: false
    readOnly: false
  name: fail-job
- description: Throw a BPMN error from a job to trigger error boundary event handling
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: throw-error
- description: Update the remaining retry count for a job
  hints:
    idempotent: true
    readOnly: false
  name: update-job-retries
- description: Publish a message for correlation with waiting process subscriptions
  hints:
    idempotent: false
    readOnly: false
  name: publish-message
- description: Broadcast a named signal to all matching signal catch events in running processes
  hints:
    idempotent: false
    readOnly: false
  name: broadcast-signal
- description: Resolve an incident to allow the failed operation to be retried
  hints:
    idempotent: true
    readOnly: false
  name: resolve-incident
- description: Delete a deployed resource (process, decision, or form) from Zeebe
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-resource
- description: Assign a user task to a specific user for completion
  hints:
    idempotent: true
    readOnly: false
  name: assign-user-task
- description: Complete a user task with optional output variables
  hints:
    idempotent: true
    readOnly: false
  name: complete-user-task
---
