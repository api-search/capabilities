---
categories: []
consumed_apis: []
description: The Zeebe REST API provides endpoints for interacting with the Zeebe workflow engine that powers Camunda 8, including process deployment, instance management, job handling, and cluster topology queries.
layout: capability
name: Zeebe REST API
operations:
- description: Zeebe Get Cluster Topology
  method: GET
  name: gettopology
  path: /topology
- description: Zeebe Deploy Resources
  method: POST
  name: deployresources
  path: /deployments
- description: Zeebe Create a Process Instance
  method: POST
  name: createprocessinstance
  path: /process-instances
- description: Zeebe Cancel a Process Instance
  method: DELETE
  name: cancelprocessinstance
  path: /process-instances/{processInstanceKey}
- description: Zeebe Migrate a Process Instance
  method: POST
  name: migrateprocessinstance
  path: /process-instances/{processInstanceKey}/migration
- description: Zeebe Activate Jobs
  method: POST
  name: activatejobs
  path: /jobs/activation
- description: Zeebe Complete a Job
  method: POST
  name: completejob
  path: /jobs/{jobKey}/completion
- description: Zeebe Fail a Job
  method: POST
  name: failjob
  path: /jobs/{jobKey}/failure
- description: Zeebe Throw Error for a Job
  method: POST
  name: throwerror
  path: /jobs/{jobKey}/error
- description: Zeebe Update Job Retries
  method: PATCH
  name: updatejobretries
  path: /jobs/{jobKey}/retries
- description: Zeebe Publish a Message
  method: POST
  name: publishmessage
  path: /messages/publication
- description: Zeebe Broadcast a Signal
  method: POST
  name: broadcastsignal
  path: /signals/broadcast
- description: Zeebe Resolve an Incident
  method: POST
  name: resolveincident
  path: /incidents/{incidentKey}/resolution
- description: Zeebe Delete a Resource
  method: POST
  name: deleteresource
  path: /resources/deletion
- description: Zeebe Assign a User Task
  method: POST
  name: assignusertask
  path: /user-tasks/{userTaskKey}/assignment
- description: Zeebe Complete a User Task
  method: POST
  name: completeusertask
  path: /user-tasks/{userTaskKey}/completion
personas: []
provider_name: Zeebe
provider_slug: zeebe
search_terms:
- zeebe create a process instance
- zeebe migrate a process instance
- migrateprocessinstance
- zeebe broadcast a signal
- completeusertask
- distributed systems
- zeebe assign a user task
- java
- camunda
- zeebe complete a job
- completejob
- activatejobs
- zeebe deploy resources
- zeebe fail a job
- cancelprocessinstance
- deployresources
- deleteresource
- zeebe resolve an incident
- cloud native
- bpmn
- workflow orchestration
- throwerror
- zeebe throw error for a job
- resolveincident
- zeebe complete a user task
- process automation
- api
- zeebe delete a resource
- zeebe get cluster topology
- zeebe publish a message
- gettopology
- failjob
- zeebe
- updatejobretries
- createprocessinstance
- zeebe cancel a process instance
- zeebe activate jobs
- broadcastsignal
- publishmessage
- microservices
- assignusertask
- zeebe update job retries
slug: zeebe-capability
source_filename: zeebe-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Zeebe REST API\n  description: The Zeebe REST API provides endpoints for interacting with the Zeebe workflow engine that powers Camunda 8,\n    including process deployment, instance management, job handling, and cluster topology queries.\n  tags:\n  - Zeebe\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: zeebe\n    baseUri: http://localhost:8080/v2\n    description: Zeebe REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ZEEBE_TOKEN}}'\n    resources:\n    - name: topology\n      path: /topology\n      operations:\n      - name: gettopology\n        method: GET\n        description: Zeebe Get Cluster Topology\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /deployments\n      operations:\n      - name: deployresources\n    \
  \    method: POST\n        description: Zeebe Deploy Resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-instances\n      path: /process-instances\n      operations:\n      - name: createprocessinstance\n        method: POST\n        description: Zeebe Create a Process Instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-instances-processinstancekey\n      path: /process-instances/{processInstanceKey}\n      operations:\n      - name: cancelprocessinstance\n        method: DELETE\n        description: Zeebe Cancel a Process Instance\n        inputParameters:\n        - name: processInstanceKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: process-instances-processinstancekey-migration\n      path: /process-instances/{processInstanceKey}/migration\n      operations:\n      - name: migrateprocessinstance\n        method: POST\n        description: Zeebe Migrate a Process Instance\n        inputParameters:\n        - name: processInstanceKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-activation\n      path: /jobs/activation\n      operations:\n      - name: activatejobs\n        method: POST\n        description: Zeebe Activate Jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobkey-completion\n      path: /jobs/{jobKey}/completion\n      operations:\n      - name: completejob\n        method: POST\n        description: Zeebe Complete a\
  \ Job\n        inputParameters:\n        - name: jobKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobkey-failure\n      path: /jobs/{jobKey}/failure\n      operations:\n      - name: failjob\n        method: POST\n        description: Zeebe Fail a Job\n        inputParameters:\n        - name: jobKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobkey-error\n      path: /jobs/{jobKey}/error\n      operations:\n      - name: throwerror\n        method: POST\n        description: Zeebe Throw Error for a Job\n        inputParameters:\n        - name: jobKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobkey-retries\n      path: /jobs/{jobKey}/retries\n      operations:\n      - name: updatejobretries\n        method: PATCH\n        description: Zeebe Update Job Retries\n        inputParameters:\n        - name: jobKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages-publication\n      path: /messages/publication\n      operations:\n      - name: publishmessage\n        method: POST\n        description: Zeebe Publish a Message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signals-broadcast\n      path: /signals/broadcast\n      operations:\n      - name: broadcastsignal\n        method: POST\n        description:\
  \ Zeebe Broadcast a Signal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incidents-incidentkey-resolution\n      path: /incidents/{incidentKey}/resolution\n      operations:\n      - name: resolveincident\n        method: POST\n        description: Zeebe Resolve an Incident\n        inputParameters:\n        - name: incidentKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources-deletion\n      path: /resources/deletion\n      operations:\n      - name: deleteresource\n        method: POST\n        description: Zeebe Delete a Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-tasks-usertaskkey-assignment\n      path: /user-tasks/{userTaskKey}/assignment\n\
  \      operations:\n      - name: assignusertask\n        method: POST\n        description: Zeebe Assign a User Task\n        inputParameters:\n        - name: userTaskKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-tasks-usertaskkey-completion\n      path: /user-tasks/{userTaskKey}/completion\n      operations:\n      - name: completeusertask\n        method: POST\n        description: Zeebe Complete a User Task\n        inputParameters:\n        - name: userTaskKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: zeebe-rest\n    description: REST adapter for Zeebe REST API.\n    resources:\n    - path: /topology\n\
  \      name: gettopology\n      operations:\n      - method: GET\n        name: gettopology\n        description: Zeebe Get Cluster Topology\n        call: zeebe.gettopology\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments\n      name: deployresources\n      operations:\n      - method: POST\n        name: deployresources\n        description: Zeebe Deploy Resources\n        call: zeebe.deployresources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /process-instances\n      name: createprocessinstance\n      operations:\n      - method: POST\n        name: createprocessinstance\n        description: Zeebe Create a Process Instance\n        call: zeebe.createprocessinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /process-instances/{processInstanceKey}\n      name: cancelprocessinstance\n      operations:\n      - method: DELETE\n        name: cancelprocessinstance\n\
  \        description: Zeebe Cancel a Process Instance\n        call: zeebe.cancelprocessinstance\n        with:\n          processInstanceKey: rest.processInstanceKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /process-instances/{processInstanceKey}/migration\n      name: migrateprocessinstance\n      operations:\n      - method: POST\n        name: migrateprocessinstance\n        description: Zeebe Migrate a Process Instance\n        call: zeebe.migrateprocessinstance\n        with:\n          processInstanceKey: rest.processInstanceKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/activation\n      name: activatejobs\n      operations:\n      - method: POST\n        name: activatejobs\n        description: Zeebe Activate Jobs\n        call: zeebe.activatejobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobKey}/completion\n      name: completejob\n\
  \      operations:\n      - method: POST\n        name: completejob\n        description: Zeebe Complete a Job\n        call: zeebe.completejob\n        with:\n          jobKey: rest.jobKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobKey}/failure\n      name: failjob\n      operations:\n      - method: POST\n        name: failjob\n        description: Zeebe Fail a Job\n        call: zeebe.failjob\n        with:\n          jobKey: rest.jobKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobKey}/error\n      name: throwerror\n      operations:\n      - method: POST\n        name: throwerror\n        description: Zeebe Throw Error for a Job\n        call: zeebe.throwerror\n        with:\n          jobKey: rest.jobKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobKey}/retries\n      name: updatejobretries\n      operations:\n      - method:\
  \ PATCH\n        name: updatejobretries\n        description: Zeebe Update Job Retries\n        call: zeebe.updatejobretries\n        with:\n          jobKey: rest.jobKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages/publication\n      name: publishmessage\n      operations:\n      - method: POST\n        name: publishmessage\n        description: Zeebe Publish a Message\n        call: zeebe.publishmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /signals/broadcast\n      name: broadcastsignal\n      operations:\n      - method: POST\n        name: broadcastsignal\n        description: Zeebe Broadcast a Signal\n        call: zeebe.broadcastsignal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /incidents/{incidentKey}/resolution\n      name: resolveincident\n      operations:\n      - method: POST\n        name: resolveincident\n        description: Zeebe\
  \ Resolve an Incident\n        call: zeebe.resolveincident\n        with:\n          incidentKey: rest.incidentKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/deletion\n      name: deleteresource\n      operations:\n      - method: POST\n        name: deleteresource\n        description: Zeebe Delete a Resource\n        call: zeebe.deleteresource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user-tasks/{userTaskKey}/assignment\n      name: assignusertask\n      operations:\n      - method: POST\n        name: assignusertask\n        description: Zeebe Assign a User Task\n        call: zeebe.assignusertask\n        with:\n          userTaskKey: rest.userTaskKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user-tasks/{userTaskKey}/completion\n      name: completeusertask\n      operations:\n      - method: POST\n        name: completeusertask\n      \
  \  description: Zeebe Complete a User Task\n        call: zeebe.completeusertask\n        with:\n          userTaskKey: rest.userTaskKey\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: zeebe-mcp\n    transport: http\n    description: MCP adapter for Zeebe REST API for AI agent use.\n    tools:\n    - name: gettopology\n      description: Zeebe Get Cluster Topology\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zeebe.gettopology\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployresources\n      description: Zeebe Deploy Resources\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.deployresources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createprocessinstance\n      description: Zeebe Create a Process Instance\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.createprocessinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelprocessinstance\n      description: Zeebe Cancel a Process Instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: zeebe.cancelprocessinstance\n      with:\n        processInstanceKey: tools.processInstanceKey\n      inputParameters:\n      - name: processInstanceKey\n        type: integer\n        description: processInstanceKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: migrateprocessinstance\n      description: Zeebe Migrate a Process Instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.migrateprocessinstance\n      with:\n        processInstanceKey: tools.processInstanceKey\n      inputParameters:\n\
  \      - name: processInstanceKey\n        type: integer\n        description: processInstanceKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activatejobs\n      description: Zeebe Activate Jobs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.activatejobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: completejob\n      description: Zeebe Complete a Job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.completejob\n      with:\n        jobKey: tools.jobKey\n      inputParameters:\n      - name: jobKey\n        type: integer\n        description: jobKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: failjob\n      description: Zeebe Fail a Job\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: zeebe.failjob\n      with:\n        jobKey: tools.jobKey\n      inputParameters:\n      - name: jobKey\n        type: integer\n        description: jobKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: throwerror\n      description: Zeebe Throw Error for a Job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.throwerror\n      with:\n        jobKey: tools.jobKey\n      inputParameters:\n      - name: jobKey\n        type: integer\n        description: jobKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatejobretries\n      description: Zeebe Update Job Retries\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.updatejobretries\n      with:\n        jobKey: tools.jobKey\n      inputParameters:\n      - name:\
  \ jobKey\n        type: integer\n        description: jobKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publishmessage\n      description: Zeebe Publish a Message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.publishmessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: broadcastsignal\n      description: Zeebe Broadcast a Signal\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.broadcastsignal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resolveincident\n      description: Zeebe Resolve an Incident\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.resolveincident\n      with:\n        incidentKey: tools.incidentKey\n      inputParameters:\n      - name: incidentKey\n\
  \        type: integer\n        description: incidentKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteresource\n      description: Zeebe Delete a Resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.deleteresource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assignusertask\n      description: Zeebe Assign a User Task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zeebe.assignusertask\n      with:\n        userTaskKey: tools.userTaskKey\n      inputParameters:\n      - name: userTaskKey\n        type: integer\n        description: userTaskKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: completeusertask\n      description: Zeebe Complete a User Task\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: zeebe.completeusertask\n      with:\n        userTaskKey: tools.userTaskKey\n      inputParameters:\n      - name: userTaskKey\n        type: integer\n        description: userTaskKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ZEEBE_TOKEN: ZEEBE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zeebe/refs/heads/main/capabilities/zeebe-capability.yaml
tags:
- Zeebe
- API
tools:
- description: Zeebe Get Cluster Topology
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopology
- description: Zeebe Deploy Resources
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployresources
- description: Zeebe Create a Process Instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprocessinstance
- description: Zeebe Cancel a Process Instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancelprocessinstance
- description: Zeebe Migrate a Process Instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: migrateprocessinstance
- description: Zeebe Activate Jobs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activatejobs
- description: Zeebe Complete a Job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completejob
- description: Zeebe Fail a Job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: failjob
- description: Zeebe Throw Error for a Job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: throwerror
- description: Zeebe Update Job Retries
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatejobretries
- description: Zeebe Publish a Message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishmessage
- description: Zeebe Broadcast a Signal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: broadcastsignal
- description: Zeebe Resolve an Incident
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resolveincident
- description: Zeebe Delete a Resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteresource
- description: Zeebe Assign a User Task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assignusertask
- description: Zeebe Complete a User Task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completeusertask
---
