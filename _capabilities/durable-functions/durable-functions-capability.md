---
categories: []
consumed_apis: []
description: The Azure Durable Functions extension exposes built-in HTTP APIs for managing orchestrations, entities, and task hubs. These HTTP APIs are extensibility webhooks authorized by the Azure Functions host and handled by the Durable Functions extension. Use them to start orchestrations, query status, raise events, terminate, suspend, resume, rewind, signal entities, and purge history.
layout: capability
name: Azure Durable Functions HTTP API
operations:
- description: Start orchestration
  method: POST
  name: startorchestration
  path: /runtime/webhooks/durabletask/orchestrators/{functionName}
- description: Start orchestration with explicit instance ID
  method: POST
  name: startorchestrationwithid
  path: /runtime/webhooks/durabletask/orchestrators/{functionName}/{instanceId}
- description: List instances
  method: GET
  name: listinstances
  path: /runtime/webhooks/durabletask/instances
- description: Purge multiple instance histories
  method: DELETE
  name: purgeinstances
  path: /runtime/webhooks/durabletask/instances
- description: Get instance status
  method: GET
  name: getinstancestatus
  path: /runtime/webhooks/durabletask/instances/{instanceId}
- description: Purge single instance history
  method: DELETE
  name: purgeinstance
  path: /runtime/webhooks/durabletask/instances/{instanceId}
- description: Raise event
  method: POST
  name: raiseevent
  path: /runtime/webhooks/durabletask/instances/{instanceId}/raiseEvent/{eventName}
- description: Terminate instance
  method: POST
  name: terminateinstance
  path: /runtime/webhooks/durabletask/instances/{instanceId}/terminate
- description: Suspend instance
  method: POST
  name: suspendinstance
  path: /runtime/webhooks/durabletask/instances/{instanceId}/suspend
- description: Resume instance
  method: POST
  name: resumeinstance
  path: /runtime/webhooks/durabletask/instances/{instanceId}/resume
- description: Rewind instance (preview)
  method: POST
  name: rewindinstance
  path: /runtime/webhooks/durabletask/instances/{instanceId}/rewind
- description: Get entity
  method: GET
  name: getentity
  path: /runtime/webhooks/durabletask/entities/{entityName}/{entityKey}
- description: Signal entity
  method: POST
  name: signalentity
  path: /runtime/webhooks/durabletask/entities/{entityName}/{entityKey}
- description: List entities
  method: GET
  name: listentities
  path: /runtime/webhooks/durabletask/entities/{entityName}
personas: []
provider_name: Azure Durable Functions
provider_slug: durable-functions
search_terms:
- api composition
- purge multiple instance histories
- resume instance
- startorchestration
- resumeinstance
- getinstancestatus
- startorchestrationwithid
- purge single instance history
- start orchestration
- rewindinstance
- getentity
- durable execution
- workflow
- purgeinstance
- suspend instance
- serverless orchestration
- listentities
- list entities
- terminate instance
- list instances
- raiseevent
- start orchestration with explicit instance id
- functions
- raise event
- rewind instance (preview)
- api
- get instance status
- get entity
- durable
- listinstances
- signalentity
- terminateinstance
- signal entity
- purgeinstances
- suspendinstance
slug: durable-functions-capability
source_filename: durable-functions-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Durable Functions HTTP API\n  description: The Azure Durable Functions extension exposes built-in HTTP APIs for managing orchestrations, entities, and\n    task hubs. These HTTP APIs are extensibility webhooks authorized by the Azure Functions host and handled by the Durable\n    Functions extension. Use them to start orchestrations, query status, raise events, terminate, suspend, resume, rewind,\n    signal entities, and purge history.\n  tags:\n  - Durable\n  - Functions\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: durable-functions\n    baseUri: https://myfuncapp.azurewebsites.net\n    description: Azure Durable Functions HTTP API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: code\n      value: '{{DURABLE_FUNCTIONS_TOKEN}}'\n    resources:\n    - name: runtime-webhooks-durabletask-orchestrators-funct\n      path: /runtime/webhooks/durabletask/orchestrators/{functionName}\n\
  \      operations:\n      - name: startorchestration\n        method: POST\n        description: Start orchestration\n        inputParameters:\n        - name: functionName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime-webhooks-durabletask-orchestrators-funct\n      path: /runtime/webhooks/durabletask/orchestrators/{functionName}/{instanceId}\n      operations:\n      - name: startorchestrationwithid\n        method: POST\n        description: Start orchestration with explicit instance ID\n        inputParameters:\n        - name: functionName\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: runtime-webhooks-durabletask-instances\n      path: /runtime/webhooks/durabletask/instances\n      operations:\n      - name: listinstances\n        method: GET\n        description: List instances\n        inputParameters:\n        - name: createdTimeFrom\n          in: query\n          type: string\n        - name: createdTimeTo\n          in: query\n          type: string\n        - name: runtimeStatus\n          in: query\n          type: string\n        - name: instanceIdPrefix\n          in: query\n          type: string\n        - name: showInput\n          in: query\n          type: boolean\n        - name: top\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: purgeinstances\n        method: DELETE\n        description: Purge multiple instance histories\n        inputParameters:\n        - name: createdTimeFrom\n\
  \          in: query\n          type: string\n        - name: createdTimeTo\n          in: query\n          type: string\n        - name: runtimeStatus\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime-webhooks-durabletask-instances-instancei\n      path: /runtime/webhooks/durabletask/instances/{instanceId}\n      operations:\n      - name: getinstancestatus\n        method: GET\n        description: Get instance status\n        inputParameters:\n        - name: showHistory\n          in: query\n          type: boolean\n        - name: showHistoryOutput\n          in: query\n          type: boolean\n        - name: showInput\n          in: query\n          type: boolean\n        - name: returnInternalServerErrorOnFailure\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: purgeinstance\n        method: DELETE\n        description: Purge single instance history\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime-webhooks-durabletask-instances-instancei\n      path: /runtime/webhooks/durabletask/instances/{instanceId}/raiseEvent/{eventName}\n      operations:\n      - name: raiseevent\n        method: POST\n        description: Raise event\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        - name: eventName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime-webhooks-durabletask-instances-instancei\n      path: /runtime/webhooks/durabletask/instances/{instanceId}/terminate\n\
  \      operations:\n      - name: terminateinstance\n        method: POST\n        description: Terminate instance\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        - name: reason\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime-webhooks-durabletask-instances-instancei\n      path: /runtime/webhooks/durabletask/instances/{instanceId}/suspend\n      operations:\n      - name: suspendinstance\n        method: POST\n        description: Suspend instance\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        - name: reason\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: runtime-webhooks-durabletask-instances-instancei\n      path: /runtime/webhooks/durabletask/instances/{instanceId}/resume\n      operations:\n      - name: resumeinstance\n        method: POST\n        description: Resume instance\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        - name: reason\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime-webhooks-durabletask-instances-instancei\n      path: /runtime/webhooks/durabletask/instances/{instanceId}/rewind\n      operations:\n      - name: rewindinstance\n        method: POST\n        description: Rewind instance (preview)\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        - name: reason\n          in: query\n          type:\
  \ string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime-webhooks-durabletask-entities-entityname\n      path: /runtime/webhooks/durabletask/entities/{entityName}/{entityKey}\n      operations:\n      - name: getentity\n        method: GET\n        description: Get entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: signalentity\n        method: POST\n        description: Signal entity\n        inputParameters:\n        - name: op\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime-webhooks-durabletask-entities-entityname\n      path: /runtime/webhooks/durabletask/entities/{entityName}\n      operations:\n      - name: listentities\n        method: GET\n\
  \        description: List entities\n        inputParameters:\n        - name: entityName\n          in: path\n          type: string\n          required: true\n        - name: lastOperationTimeFrom\n          in: query\n          type: string\n        - name: lastOperationTimeTo\n          in: query\n          type: string\n        - name: fetchState\n          in: query\n          type: boolean\n        - name: top\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: durable-functions-rest\n    description: REST adapter for Azure Durable Functions HTTP API.\n    resources:\n    - path: /runtime/webhooks/durabletask/orchestrators/{functionName}\n      name: startorchestration\n      operations:\n      - method: POST\n        name: startorchestration\n        description: Start orchestration\n        call: durable-functions.startorchestration\n\
  \        with:\n          functionName: rest.functionName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/orchestrators/{functionName}/{instanceId}\n      name: startorchestrationwithid\n      operations:\n      - method: POST\n        name: startorchestrationwithid\n        description: Start orchestration with explicit instance ID\n        call: durable-functions.startorchestrationwithid\n        with:\n          functionName: rest.functionName\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/instances\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n        description: List instances\n        call: durable-functions.listinstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/instances\n     \
  \ name: purgeinstances\n      operations:\n      - method: DELETE\n        name: purgeinstances\n        description: Purge multiple instance histories\n        call: durable-functions.purgeinstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/instances/{instanceId}\n      name: getinstancestatus\n      operations:\n      - method: GET\n        name: getinstancestatus\n        description: Get instance status\n        call: durable-functions.getinstancestatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/instances/{instanceId}\n      name: purgeinstance\n      operations:\n      - method: DELETE\n        name: purgeinstance\n        description: Purge single instance history\n        call: durable-functions.purgeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/instances/{instanceId}/raiseEvent/{eventName}\n\
  \      name: raiseevent\n      operations:\n      - method: POST\n        name: raiseevent\n        description: Raise event\n        call: durable-functions.raiseevent\n        with:\n          instanceId: rest.instanceId\n          eventName: rest.eventName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/instances/{instanceId}/terminate\n      name: terminateinstance\n      operations:\n      - method: POST\n        name: terminateinstance\n        description: Terminate instance\n        call: durable-functions.terminateinstance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/instances/{instanceId}/suspend\n      name: suspendinstance\n      operations:\n      - method: POST\n        name: suspendinstance\n        description: Suspend instance\n        call: durable-functions.suspendinstance\n\
  \        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/instances/{instanceId}/resume\n      name: resumeinstance\n      operations:\n      - method: POST\n        name: resumeinstance\n        description: Resume instance\n        call: durable-functions.resumeinstance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/instances/{instanceId}/rewind\n      name: rewindinstance\n      operations:\n      - method: POST\n        name: rewindinstance\n        description: Rewind instance (preview)\n        call: durable-functions.rewindinstance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/entities/{entityName}/{entityKey}\n      name:\
  \ getentity\n      operations:\n      - method: GET\n        name: getentity\n        description: Get entity\n        call: durable-functions.getentity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/entities/{entityName}/{entityKey}\n      name: signalentity\n      operations:\n      - method: POST\n        name: signalentity\n        description: Signal entity\n        call: durable-functions.signalentity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime/webhooks/durabletask/entities/{entityName}\n      name: listentities\n      operations:\n      - method: GET\n        name: listentities\n        description: List entities\n        call: durable-functions.listentities\n        with:\n          entityName: rest.entityName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: durable-functions-mcp\n    transport:\
  \ http\n    description: MCP adapter for Azure Durable Functions HTTP API for AI agent use.\n    tools:\n    - name: startorchestration\n      description: Start orchestration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: durable-functions.startorchestration\n      with:\n        functionName: tools.functionName\n      inputParameters:\n      - name: functionName\n        type: string\n        description: functionName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startorchestrationwithid\n      description: Start orchestration with explicit instance ID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: durable-functions.startorchestrationwithid\n      with:\n        functionName: tools.functionName\n        instanceId: tools.instanceId\n      inputParameters:\n      - name: functionName\n        type: string\n \
  \       description: functionName\n        required: true\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinstances\n      description: List instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: durable-functions.listinstances\n      with:\n        createdTimeFrom: tools.createdTimeFrom\n        createdTimeTo: tools.createdTimeTo\n        runtimeStatus: tools.runtimeStatus\n        instanceIdPrefix: tools.instanceIdPrefix\n        showInput: tools.showInput\n        top: tools.top\n      inputParameters:\n      - name: createdTimeFrom\n        type: string\n        description: createdTimeFrom\n      - name: createdTimeTo\n        type: string\n        description: createdTimeTo\n      - name: runtimeStatus\n        type: string\n        description: runtimeStatus\n      - name: instanceIdPrefix\n\
  \        type: string\n        description: instanceIdPrefix\n      - name: showInput\n        type: boolean\n        description: showInput\n      - name: top\n        type: integer\n        description: top\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: purgeinstances\n      description: Purge multiple instance histories\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: durable-functions.purgeinstances\n      with:\n        createdTimeFrom: tools.createdTimeFrom\n        createdTimeTo: tools.createdTimeTo\n        runtimeStatus: tools.runtimeStatus\n      inputParameters:\n      - name: createdTimeFrom\n        type: string\n        description: createdTimeFrom\n      - name: createdTimeTo\n        type: string\n        description: createdTimeTo\n      - name: runtimeStatus\n        type: string\n        description: runtimeStatus\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getinstancestatus\n      description: Get instance status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: durable-functions.getinstancestatus\n      with:\n        showHistory: tools.showHistory\n        showHistoryOutput: tools.showHistoryOutput\n        showInput: tools.showInput\n        returnInternalServerErrorOnFailure: tools.returnInternalServerErrorOnFailure\n      inputParameters:\n      - name: showHistory\n        type: boolean\n        description: showHistory\n      - name: showHistoryOutput\n        type: boolean\n        description: showHistoryOutput\n      - name: showInput\n        type: boolean\n        description: showInput\n      - name: returnInternalServerErrorOnFailure\n        type: boolean\n        description: returnInternalServerErrorOnFailure\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: purgeinstance\n      description: Purge single instance history\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: durable-functions.purgeinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: raiseevent\n      description: Raise event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: durable-functions.raiseevent\n      with:\n        instanceId: tools.instanceId\n        eventName: tools.eventName\n      inputParameters:\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      - name: eventName\n        type: string\n        description: eventName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminateinstance\n      description: Terminate instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: durable-functions.terminateinstance\n \
  \     with:\n        instanceId: tools.instanceId\n        reason: tools.reason\n      inputParameters:\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      - name: reason\n        type: string\n        description: reason\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: suspendinstance\n      description: Suspend instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: durable-functions.suspendinstance\n      with:\n        instanceId: tools.instanceId\n        reason: tools.reason\n      inputParameters:\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      - name: reason\n        type: string\n        description: reason\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resumeinstance\n      description: Resume instance\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: durable-functions.resumeinstance\n      with:\n        instanceId: tools.instanceId\n        reason: tools.reason\n      inputParameters:\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      - name: reason\n        type: string\n        description: reason\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rewindinstance\n      description: Rewind instance (preview)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: durable-functions.rewindinstance\n      with:\n        instanceId: tools.instanceId\n        reason: tools.reason\n      inputParameters:\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      - name: reason\n        type: string\n        description: reason\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getentity\n      description: Get entity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: durable-functions.getentity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: signalentity\n      description: Signal entity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: durable-functions.signalentity\n      with:\n        op: tools.op\n      inputParameters:\n      - name: op\n        type: string\n        description: op\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listentities\n      description: List entities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: durable-functions.listentities\n      with:\n        entityName: tools.entityName\n        lastOperationTimeFrom: tools.lastOperationTimeFrom\n        lastOperationTimeTo:\
  \ tools.lastOperationTimeTo\n        fetchState: tools.fetchState\n        top: tools.top\n      inputParameters:\n      - name: entityName\n        type: string\n        description: entityName\n        required: true\n      - name: lastOperationTimeFrom\n        type: string\n        description: lastOperationTimeFrom\n      - name: lastOperationTimeTo\n        type: string\n        description: lastOperationTimeTo\n      - name: fetchState\n        type: boolean\n        description: fetchState\n      - name: top\n        type: integer\n        description: top\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DURABLE_FUNCTIONS_TOKEN: DURABLE_FUNCTIONS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/durable-functions/refs/heads/main/capabilities/durable-functions-capability.yaml
tags:
- Durable
- Functions
- API
tools:
- description: Start orchestration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startorchestration
- description: Start orchestration with explicit instance ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startorchestrationwithid
- description: List instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Purge multiple instance histories
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: purgeinstances
- description: Get instance status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstancestatus
- description: Purge single instance history
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: purgeinstance
- description: Raise event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: raiseevent
- description: Terminate instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: terminateinstance
- description: Suspend instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: suspendinstance
- description: Resume instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resumeinstance
- description: Rewind instance (preview)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rewindinstance
- description: Get entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getentity
- description: Signal entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: signalentity
- description: List entities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listentities
---
