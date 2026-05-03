---
categories: []
consumed_apis:
- api
description: Unified workflow capability composing Zeebe APIs.
layout: capability
name: Zeebe Workflow
operations:
- description: Zeebe Get Cluster Topology
  method: GET
  name: get-topology
  path: /v1/api
- description: Zeebe Deploy Resources
  method: POST
  name: deploy-resources
  path: /v1/api
- description: Zeebe Create a Process Instance
  method: POST
  name: create-process-instance
  path: /v1/api
- description: Zeebe Cancel a Process Instance
  method: DELETE
  name: cancel-process-instance
  path: /v1/api
- description: Zeebe Migrate a Process Instance
  method: POST
  name: migrate-process-instance
  path: /v1/api
- description: Zeebe Activate Jobs
  method: POST
  name: activate-jobs
  path: /v1/api
- description: Zeebe Complete a Job
  method: POST
  name: complete-job
  path: /v1/api
- description: Zeebe Fail a Job
  method: POST
  name: fail-job
  path: /v1/api
- description: Zeebe Throw Error for a Job
  method: POST
  name: throw-error
  path: /v1/api
- description: Zeebe Update Job Retries
  method: PATCH
  name: update-job-retries
  path: /v1/api
- description: Zeebe Publish a Message
  method: POST
  name: publish-message
  path: /v1/api
- description: Zeebe Broadcast a Signal
  method: POST
  name: broadcast-signal
  path: /v1/api
- description: Zeebe Resolve an Incident
  method: POST
  name: resolve-incident
  path: /v1/api
- description: Zeebe Delete a Resource
  method: POST
  name: delete-resource
  path: /v1/api
- description: Zeebe Assign a User Task
  method: POST
  name: assign-user-task
  path: /v1/api
- description: Zeebe Complete a User Task
  method: POST
  name: complete-user-task
  path: /v1/api
personas: []
provider_name: Zeebe
provider_slug: zeebe
search_terms:
- zeebe migrate a process instance
- fail job
- api publish message
- api deploy resources
- java
- zeebe throw error for a job
- migrate process instance
- api throw error
- delete resource
- zeebe fail a job
- api get topology
- workflow orchestration
- api cancel process instance
- deploy resources
- cloud native
- api fail job
- create process instance
- zeebe publish a message
- zeebe deploy resources
- activate jobs
- throw error
- api complete job
- api delete resource
- zeebe broadcast a signal
- get topology
- assign user task
- zeebe delete a resource
- api broadcast signal
- operations for api
- zeebe resolve an incident
- zeebe update job retries
- distributed systems
- zeebe complete a job
- complete user task
- complete job
- bpmn
- process automation
- api assign user task
- update job retries
- zeebe assign a user task
- microservices
- camunda
- api activate jobs
- zeebe create a process instance
- zeebe activate jobs
- zeebe
- api complete user task
- api create process instance
- zeebe get cluster topology
- broadcast signal
- resolve incident
- cancel process instance
- api update job retries
- api resolve incident
- zeebe complete a user task
- api migrate process instance
- zeebe cancel a process instance
- publish message
slug: zeebe-workflow
source_filename: zeebe-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Zeebe Workflow\n  description: Unified workflow capability composing Zeebe APIs.\n  tags:\n    - Zeebe\n  created: '2026-05-03'\n  modified: '2026-05-03'\ncapability:\n  consumes:\n    - import: api\n      location: ./shared/api.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: zeebe-api\n      description: Unified REST API for Zeebe\n      resources:\n        - path: /v1/api\n          name: api\n          description: Operations for api\n          operations:\n            - method: GET\n              name: get-topology\n              description: Zeebe Get Cluster Topology\n              call: api.get-topology\n            - method: POST\n              name: deploy-resources\n              description: Zeebe Deploy Resources\n              call: api.deploy-resources\n            - method: POST\n              name: create-process-instance\n              description: Zeebe Create a Process Instance\n              call:\
  \ api.create-process-instance\n            - method: DELETE\n              name: cancel-process-instance\n              description: Zeebe Cancel a Process Instance\n              call: api.cancel-process-instance\n            - method: POST\n              name: migrate-process-instance\n              description: Zeebe Migrate a Process Instance\n              call: api.migrate-process-instance\n            - method: POST\n              name: activate-jobs\n              description: Zeebe Activate Jobs\n              call: api.activate-jobs\n            - method: POST\n              name: complete-job\n              description: Zeebe Complete a Job\n              call: api.complete-job\n            - method: POST\n              name: fail-job\n              description: Zeebe Fail a Job\n              call: api.fail-job\n            - method: POST\n              name: throw-error\n              description: Zeebe Throw Error for a Job\n              call: api.throw-error\n         \
  \   - method: PATCH\n              name: update-job-retries\n              description: Zeebe Update Job Retries\n              call: api.update-job-retries\n            - method: POST\n              name: publish-message\n              description: Zeebe Publish a Message\n              call: api.publish-message\n            - method: POST\n              name: broadcast-signal\n              description: Zeebe Broadcast a Signal\n              call: api.broadcast-signal\n            - method: POST\n              name: resolve-incident\n              description: Zeebe Resolve an Incident\n              call: api.resolve-incident\n            - method: POST\n              name: delete-resource\n              description: Zeebe Delete a Resource\n              call: api.delete-resource\n            - method: POST\n              name: assign-user-task\n              description: Zeebe Assign a User Task\n              call: api.assign-user-task\n            - method: POST\n             \
  \ name: complete-user-task\n              description: Zeebe Complete a User Task\n              call: api.complete-user-task\n    - type: mcp\n      port: 9090\n      namespace: zeebe-mcp\n      transport: http\n      description: MCP server for Zeebe\n      tools:\n        - name: api-get-topology\n          description: Zeebe Get Cluster Topology\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-topology\n        - name: api-deploy-resources\n          description: Zeebe Deploy Resources\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.deploy-resources\n        - name: api-create-process-instance\n          description: Zeebe Create a Process Instance\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.create-process-instance\n        - name: api-cancel-process-instance\n          description: Zeebe Cancel a Process Instance\n          hints:\n\
  \            readOnly: false\n            openWorld: true\n          call: api.cancel-process-instance\n        - name: api-migrate-process-instance\n          description: Zeebe Migrate a Process Instance\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.migrate-process-instance\n        - name: api-activate-jobs\n          description: Zeebe Activate Jobs\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.activate-jobs\n        - name: api-complete-job\n          description: Zeebe Complete a Job\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.complete-job\n        - name: api-fail-job\n          description: Zeebe Fail a Job\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.fail-job\n        - name: api-throw-error\n          description: Zeebe Throw Error for a Job\n          hints:\n           \
  \ readOnly: false\n            openWorld: true\n          call: api.throw-error\n        - name: api-update-job-retries\n          description: Zeebe Update Job Retries\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.update-job-retries\n        - name: api-publish-message\n          description: Zeebe Publish a Message\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.publish-message\n        - name: api-broadcast-signal\n          description: Zeebe Broadcast a Signal\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.broadcast-signal\n        - name: api-resolve-incident\n          description: Zeebe Resolve an Incident\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.resolve-incident\n        - name: api-delete-resource\n          description: Zeebe Delete a Resource\n          hints:\n         \
  \   readOnly: false\n            openWorld: true\n          call: api.delete-resource\n        - name: api-assign-user-task\n          description: Zeebe Assign a User Task\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.assign-user-task\n        - name: api-complete-user-task\n          description: Zeebe Complete a User Task\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.complete-user-task\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zeebe/refs/heads/main/capabilities/zeebe-workflow.yaml
tags:
- Zeebe
tools:
- description: Zeebe Get Cluster Topology
  hints:
    openWorld: true
    readOnly: true
  name: api-get-topology
- description: Zeebe Deploy Resources
  hints:
    openWorld: true
    readOnly: false
  name: api-deploy-resources
- description: Zeebe Create a Process Instance
  hints:
    openWorld: true
    readOnly: false
  name: api-create-process-instance
- description: Zeebe Cancel a Process Instance
  hints:
    openWorld: true
    readOnly: false
  name: api-cancel-process-instance
- description: Zeebe Migrate a Process Instance
  hints:
    openWorld: true
    readOnly: false
  name: api-migrate-process-instance
- description: Zeebe Activate Jobs
  hints:
    openWorld: true
    readOnly: false
  name: api-activate-jobs
- description: Zeebe Complete a Job
  hints:
    openWorld: true
    readOnly: false
  name: api-complete-job
- description: Zeebe Fail a Job
  hints:
    openWorld: true
    readOnly: false
  name: api-fail-job
- description: Zeebe Throw Error for a Job
  hints:
    openWorld: true
    readOnly: false
  name: api-throw-error
- description: Zeebe Update Job Retries
  hints:
    openWorld: true
    readOnly: false
  name: api-update-job-retries
- description: Zeebe Publish a Message
  hints:
    openWorld: true
    readOnly: false
  name: api-publish-message
- description: Zeebe Broadcast a Signal
  hints:
    openWorld: true
    readOnly: false
  name: api-broadcast-signal
- description: Zeebe Resolve an Incident
  hints:
    openWorld: true
    readOnly: false
  name: api-resolve-incident
- description: Zeebe Delete a Resource
  hints:
    openWorld: true
    readOnly: false
  name: api-delete-resource
- description: Zeebe Assign a User Task
  hints:
    openWorld: true
    readOnly: false
  name: api-assign-user-task
- description: Zeebe Complete a User Task
  hints:
    openWorld: true
    readOnly: false
  name: api-complete-user-task
---
