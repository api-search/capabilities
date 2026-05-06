---
categories: []
consumed_apis: []
description: The Camunda 8 REST API provides endpoints for managing process instances, jobs, decisions, deployments, messages, signals, and other resources in the Camunda 8 process orchestration platform.
layout: capability
name: Camunda 8 REST API
operations:
- description: Get cluster topology
  method: GET
  name: gettopology
  path: /topology
- description: Search process definitions
  method: POST
  name: searchprocessdefinitions
  path: /process-definitions/search
- description: Get process definition
  method: GET
  name: getprocessdefinition
  path: /process-definitions/{processDefinitionKey}
- description: Get process definition XML
  method: GET
  name: getprocessdefinitionxml
  path: /process-definitions/{processDefinitionKey}/xml
- description: Create a process instance
  method: POST
  name: createprocessinstance
  path: /process-instances
- description: Search process instances
  method: POST
  name: searchprocessinstances
  path: /process-instances/search
- description: Get process instance
  method: GET
  name: getprocessinstance
  path: /process-instances/{processInstanceKey}
- description: Cancel a process instance
  method: DELETE
  name: cancelprocessinstance
  path: /process-instances/{processInstanceKey}
- description: Activate jobs
  method: POST
  name: activatejobs
  path: /jobs/activation
- description: Complete a job
  method: POST
  name: completejob
  path: /jobs/{jobKey}/completion
- description: Fail a job
  method: POST
  name: failjob
  path: /jobs/{jobKey}/failure
- description: Throw error for a job
  method: POST
  name: throwerror
  path: /jobs/{jobKey}/error
- description: Deploy resources
  method: POST
  name: createdeployment
  path: /deployments
- description: Search deployments
  method: POST
  name: searchdeployments
  path: /deployments/search
- description: Search decision definitions
  method: POST
  name: searchdecisiondefinitions
  path: /decision-definitions/search
- description: Evaluate a decision
  method: POST
  name: evaluatedecision
  path: /decision-definitions/{decisionKey}/evaluation
- description: Search user tasks
  method: POST
  name: searchusertasks
  path: /user-tasks/search
- description: Assign a user task
  method: POST
  name: assignusertask
  path: /user-tasks/{userTaskKey}/assignment
- description: Complete a user task
  method: POST
  name: completeusertask
  path: /user-tasks/{userTaskKey}/completion
- description: Publish a message
  method: POST
  name: publishmessage
  path: /messages/publication
- description: Broadcast a signal
  method: POST
  name: broadcastsignal
  path: /signals/broadcast
- description: Search incidents
  method: POST
  name: searchincidents
  path: /incidents/search
- description: Resolve an incident
  method: POST
  name: resolveincident
  path: /incidents/{incidentKey}/resolution
personas: []
provider_name: Camunda
provider_slug: camunda
search_terms:
- evaluatedecision
- search user tasks
- completeusertask
- getprocessdefinitionxml
- get cluster topology
- complete a job
- searchprocessdefinitions
- getprocessinstance
- workflow
- cancel a process instance
- get process instance
- camunda
- search process instances
- searchdecisiondefinitions
- evaluate a decision
- completejob
- activatejobs
- business process management
- cancelprocessinstance
- getprocessdefinition
- searchincidents
- search incidents
- bpmn
- throw error for a job
- searchusertasks
- throwerror
- search decision definitions
- search process definitions
- resolveincident
- broadcast a signal
- resolve an incident
- process automation
- api
- createdeployment
- gettopology
- complete a user task
- searchprocessinstances
- get process definition xml
- failjob
- searchdeployments
- activate jobs
- deploy resources
- get process definition
- search deployments
- createprocessinstance
- create a process instance
- publish a message
- fail a job
- broadcastsignal
- publishmessage
- assignusertask
- assign a user task
slug: camunda-capability
source_filename: camunda-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Camunda 8 REST API\n  description: The Camunda 8 REST API provides endpoints for managing process instances, jobs, decisions, deployments, messages,\n    signals, and other resources in the Camunda 8 process orchestration platform.\n  tags:\n  - Camunda\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: camunda\n    baseUri: http://localhost:8080/v2\n    description: Camunda 8 REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CAMUNDA_TOKEN}}'\n    resources:\n    - name: topology\n      path: /topology\n      operations:\n      - name: gettopology\n        method: GET\n        description: Get cluster topology\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-definitions-search\n      path: /process-definitions/search\n      operations:\n      - name:\
  \ searchprocessdefinitions\n        method: POST\n        description: Search process definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-definitions-processdefinitionkey\n      path: /process-definitions/{processDefinitionKey}\n      operations:\n      - name: getprocessdefinition\n        method: GET\n        description: Get process definition\n        inputParameters:\n        - name: processDefinitionKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-definitions-processdefinitionkey-xml\n      path: /process-definitions/{processDefinitionKey}/xml\n      operations:\n      - name: getprocessdefinitionxml\n        method: GET\n        description: Get process definition XML\n        inputParameters:\n      \
  \  - name: processDefinitionKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-instances\n      path: /process-instances\n      operations:\n      - name: createprocessinstance\n        method: POST\n        description: Create a process instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-instances-search\n      path: /process-instances/search\n      operations:\n      - name: searchprocessinstances\n        method: POST\n        description: Search process instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-instances-processinstancekey\n      path: /process-instances/{processInstanceKey}\n      operations:\n\
  \      - name: getprocessinstance\n        method: GET\n        description: Get process instance\n        inputParameters:\n        - name: processInstanceKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancelprocessinstance\n        method: DELETE\n        description: Cancel a process instance\n        inputParameters:\n        - name: processInstanceKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-activation\n      path: /jobs/activation\n      operations:\n      - name: activatejobs\n        method: POST\n        description: Activate jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: jobs-jobkey-completion\n      path: /jobs/{jobKey}/completion\n      operations:\n      - name: completejob\n        method: POST\n        description: Complete a job\n        inputParameters:\n        - name: jobKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobkey-failure\n      path: /jobs/{jobKey}/failure\n      operations:\n      - name: failjob\n        method: POST\n        description: Fail a job\n        inputParameters:\n        - name: jobKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobkey-error\n      path: /jobs/{jobKey}/error\n      operations:\n      - name: throwerror\n        method: POST\n    \
  \    description: Throw error for a job\n        inputParameters:\n        - name: jobKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /deployments\n      operations:\n      - name: createdeployment\n        method: POST\n        description: Deploy resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments-search\n      path: /deployments/search\n      operations:\n      - name: searchdeployments\n        method: POST\n        description: Search deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: decision-definitions-search\n      path: /decision-definitions/search\n      operations:\n      - name:\
  \ searchdecisiondefinitions\n        method: POST\n        description: Search decision definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: decision-definitions-decisionkey-evaluation\n      path: /decision-definitions/{decisionKey}/evaluation\n      operations:\n      - name: evaluatedecision\n        method: POST\n        description: Evaluate a decision\n        inputParameters:\n        - name: decisionKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-tasks-search\n      path: /user-tasks/search\n      operations:\n      - name: searchusertasks\n        method: POST\n        description: Search user tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: user-tasks-usertaskkey-assignment\n      path: /user-tasks/{userTaskKey}/assignment\n      operations:\n      - name: assignusertask\n        method: POST\n        description: Assign a user task\n        inputParameters:\n        - name: userTaskKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-tasks-usertaskkey-completion\n      path: /user-tasks/{userTaskKey}/completion\n      operations:\n      - name: completeusertask\n        method: POST\n        description: Complete a user task\n        inputParameters:\n        - name: userTaskKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages-publication\n      path: /messages/publication\n\
  \      operations:\n      - name: publishmessage\n        method: POST\n        description: Publish a message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signals-broadcast\n      path: /signals/broadcast\n      operations:\n      - name: broadcastsignal\n        method: POST\n        description: Broadcast a signal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incidents-search\n      path: /incidents/search\n      operations:\n      - name: searchincidents\n        method: POST\n        description: Search incidents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incidents-incidentkey-resolution\n      path: /incidents/{incidentKey}/resolution\n      operations:\n      - name: resolveincident\n        method:\
  \ POST\n        description: Resolve an incident\n        inputParameters:\n        - name: incidentKey\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: camunda-rest\n    description: REST adapter for Camunda 8 REST API.\n    resources:\n    - path: /topology\n      name: gettopology\n      operations:\n      - method: GET\n        name: gettopology\n        description: Get cluster topology\n        call: camunda.gettopology\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /process-definitions/search\n      name: searchprocessdefinitions\n      operations:\n      - method: POST\n        name: searchprocessdefinitions\n        description: Search process definitions\n        call: camunda.searchprocessdefinitions\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /process-definitions/{processDefinitionKey}\n      name: getprocessdefinition\n      operations:\n      - method: GET\n        name: getprocessdefinition\n        description: Get process definition\n        call: camunda.getprocessdefinition\n        with:\n          processDefinitionKey: rest.processDefinitionKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /process-definitions/{processDefinitionKey}/xml\n      name: getprocessdefinitionxml\n      operations:\n      - method: GET\n        name: getprocessdefinitionxml\n        description: Get process definition XML\n        call: camunda.getprocessdefinitionxml\n        with:\n          processDefinitionKey: rest.processDefinitionKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /process-instances\n      name: createprocessinstance\n      operations:\n      - method: POST\n        name: createprocessinstance\n\
  \        description: Create a process instance\n        call: camunda.createprocessinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /process-instances/search\n      name: searchprocessinstances\n      operations:\n      - method: POST\n        name: searchprocessinstances\n        description: Search process instances\n        call: camunda.searchprocessinstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /process-instances/{processInstanceKey}\n      name: getprocessinstance\n      operations:\n      - method: GET\n        name: getprocessinstance\n        description: Get process instance\n        call: camunda.getprocessinstance\n        with:\n          processInstanceKey: rest.processInstanceKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /process-instances/{processInstanceKey}\n      name: cancelprocessinstance\n      operations:\n      - method:\
  \ DELETE\n        name: cancelprocessinstance\n        description: Cancel a process instance\n        call: camunda.cancelprocessinstance\n        with:\n          processInstanceKey: rest.processInstanceKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/activation\n      name: activatejobs\n      operations:\n      - method: POST\n        name: activatejobs\n        description: Activate jobs\n        call: camunda.activatejobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobKey}/completion\n      name: completejob\n      operations:\n      - method: POST\n        name: completejob\n        description: Complete a job\n        call: camunda.completejob\n        with:\n          jobKey: rest.jobKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobKey}/failure\n      name: failjob\n      operations:\n      - method: POST\n        name: failjob\n\
  \        description: Fail a job\n        call: camunda.failjob\n        with:\n          jobKey: rest.jobKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobKey}/error\n      name: throwerror\n      operations:\n      - method: POST\n        name: throwerror\n        description: Throw error for a job\n        call: camunda.throwerror\n        with:\n          jobKey: rest.jobKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments\n      name: createdeployment\n      operations:\n      - method: POST\n        name: createdeployment\n        description: Deploy resources\n        call: camunda.createdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments/search\n      name: searchdeployments\n      operations:\n      - method: POST\n        name: searchdeployments\n        description: Search deployments\n        call: camunda.searchdeployments\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /decision-definitions/search\n      name: searchdecisiondefinitions\n      operations:\n      - method: POST\n        name: searchdecisiondefinitions\n        description: Search decision definitions\n        call: camunda.searchdecisiondefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /decision-definitions/{decisionKey}/evaluation\n      name: evaluatedecision\n      operations:\n      - method: POST\n        name: evaluatedecision\n        description: Evaluate a decision\n        call: camunda.evaluatedecision\n        with:\n          decisionKey: rest.decisionKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user-tasks/search\n      name: searchusertasks\n      operations:\n      - method: POST\n        name: searchusertasks\n        description: Search user tasks\n        call: camunda.searchusertasks\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user-tasks/{userTaskKey}/assignment\n      name: assignusertask\n      operations:\n      - method: POST\n        name: assignusertask\n        description: Assign a user task\n        call: camunda.assignusertask\n        with:\n          userTaskKey: rest.userTaskKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user-tasks/{userTaskKey}/completion\n      name: completeusertask\n      operations:\n      - method: POST\n        name: completeusertask\n        description: Complete a user task\n        call: camunda.completeusertask\n        with:\n          userTaskKey: rest.userTaskKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages/publication\n      name: publishmessage\n      operations:\n      - method: POST\n        name: publishmessage\n        description: Publish a message\n        call: camunda.publishmessage\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /signals/broadcast\n      name: broadcastsignal\n      operations:\n      - method: POST\n        name: broadcastsignal\n        description: Broadcast a signal\n        call: camunda.broadcastsignal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /incidents/search\n      name: searchincidents\n      operations:\n      - method: POST\n        name: searchincidents\n        description: Search incidents\n        call: camunda.searchincidents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /incidents/{incidentKey}/resolution\n      name: resolveincident\n      operations:\n      - method: POST\n        name: resolveincident\n        description: Resolve an incident\n        call: camunda.resolveincident\n        with:\n          incidentKey: rest.incidentKey\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: camunda-mcp\n    transport: http\n    description: MCP adapter for Camunda 8 REST API for AI agent use.\n    tools:\n    - name: gettopology\n      description: Get cluster topology\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camunda.gettopology\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchprocessdefinitions\n      description: Search process definitions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.searchprocessdefinitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprocessdefinition\n      description: Get process definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camunda.getprocessdefinition\n      with:\n        processDefinitionKey: tools.processDefinitionKey\n\
  \      inputParameters:\n      - name: processDefinitionKey\n        type: integer\n        description: processDefinitionKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprocessdefinitionxml\n      description: Get process definition XML\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camunda.getprocessdefinitionxml\n      with:\n        processDefinitionKey: tools.processDefinitionKey\n      inputParameters:\n      - name: processDefinitionKey\n        type: integer\n        description: processDefinitionKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createprocessinstance\n      description: Create a process instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.createprocessinstance\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: searchprocessinstances\n      description: Search process instances\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.searchprocessinstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprocessinstance\n      description: Get process instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camunda.getprocessinstance\n      with:\n        processInstanceKey: tools.processInstanceKey\n      inputParameters:\n      - name: processInstanceKey\n        type: integer\n        description: processInstanceKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelprocessinstance\n      description: Cancel a process instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: camunda.cancelprocessinstance\n\
  \      with:\n        processInstanceKey: tools.processInstanceKey\n      inputParameters:\n      - name: processInstanceKey\n        type: integer\n        description: processInstanceKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activatejobs\n      description: Activate jobs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.activatejobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: completejob\n      description: Complete a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.completejob\n      with:\n        jobKey: tools.jobKey\n      inputParameters:\n      - name: jobKey\n        type: integer\n        description: jobKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: failjob\n      description: Fail\
  \ a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.failjob\n      with:\n        jobKey: tools.jobKey\n      inputParameters:\n      - name: jobKey\n        type: integer\n        description: jobKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: throwerror\n      description: Throw error for a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.throwerror\n      with:\n        jobKey: tools.jobKey\n      inputParameters:\n      - name: jobKey\n        type: integer\n        description: jobKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdeployment\n      description: Deploy resources\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.createdeployment\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: searchdeployments\n      description: Search deployments\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.searchdeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchdecisiondefinitions\n      description: Search decision definitions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.searchdecisiondefinitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: evaluatedecision\n      description: Evaluate a decision\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.evaluatedecision\n      with:\n        decisionKey: tools.decisionKey\n      inputParameters:\n      - name: decisionKey\n        type: integer\n        description: decisionKey\n        required: true\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchusertasks\n      description: Search user tasks\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.searchusertasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assignusertask\n      description: Assign a user task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.assignusertask\n      with:\n        userTaskKey: tools.userTaskKey\n      inputParameters:\n      - name: userTaskKey\n        type: integer\n        description: userTaskKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: completeusertask\n      description: Complete a user task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.completeusertask\n      with:\n\
  \        userTaskKey: tools.userTaskKey\n      inputParameters:\n      - name: userTaskKey\n        type: integer\n        description: userTaskKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publishmessage\n      description: Publish a message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.publishmessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: broadcastsignal\n      description: Broadcast a signal\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.broadcastsignal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchincidents\n      description: Search incidents\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.searchincidents\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: resolveincident\n      description: Resolve an incident\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camunda.resolveincident\n      with:\n        incidentKey: tools.incidentKey\n      inputParameters:\n      - name: incidentKey\n        type: integer\n        description: incidentKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CAMUNDA_TOKEN: CAMUNDA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/camunda/refs/heads/main/capabilities/camunda-capability.yaml
tags:
- Camunda
- API
tools:
- description: Get cluster topology
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopology
- description: Search process definitions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchprocessdefinitions
- description: Get process definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprocessdefinition
- description: Get process definition XML
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprocessdefinitionxml
- description: Create a process instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprocessinstance
- description: Search process instances
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchprocessinstances
- description: Get process instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprocessinstance
- description: Cancel a process instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancelprocessinstance
- description: Activate jobs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activatejobs
- description: Complete a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completejob
- description: Fail a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: failjob
- description: Throw error for a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: throwerror
- description: Deploy resources
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeployment
- description: Search deployments
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchdeployments
- description: Search decision definitions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchdecisiondefinitions
- description: Evaluate a decision
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluatedecision
- description: Search user tasks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchusertasks
- description: Assign a user task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assignusertask
- description: Complete a user task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completeusertask
- description: Publish a message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishmessage
- description: Broadcast a signal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: broadcastsignal
- description: Search incidents
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchincidents
- description: Resolve an incident
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resolveincident
---
