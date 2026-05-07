---
categories: []
consumed_apis: []
description: The Axon Server REST API provides HTTP endpoints for managing the Axon Server event store, command routing, query handling, application contexts, users, and cluster configuration.
layout: capability
name: Axon Server REST API
operations:
- description: Axon Framework - List Events
  method: GET
  name: listevents
  path: /events
- description: Axon Framework - Append an Event
  method: POST
  name: appendevent
  path: /events
- description: Axon Framework - Get Events for an Aggregate
  method: GET
  name: getaggregateevents
  path: /events/aggregates/{aggregateId}
- description: Axon Framework - Get Snapshots for an Aggregate
  method: GET
  name: getsnapshots
  path: /snapshots/{aggregateId}
- description: Axon Framework - Append a Snapshot
  method: POST
  name: appendsnapshot
  path: /snapshots/{aggregateId}
- description: Axon Framework - List Command Handlers
  method: GET
  name: listcommandhandlers
  path: /commands
- description: Axon Framework - List Query Handlers
  method: GET
  name: listqueryhandlers
  path: /queries
- description: Axon Framework - List Contexts
  method: GET
  name: listcontexts
  path: /context
- description: Axon Framework - Create a Context
  method: POST
  name: createcontext
  path: /context
- description: Axon Framework - Get a Context
  method: GET
  name: getcontext
  path: /context/{contextName}
- description: Axon Framework - Delete a Context
  method: DELETE
  name: deletecontext
  path: /context/{contextName}
- description: Axon Framework - List Applications
  method: GET
  name: listapplications
  path: /applications
- description: Axon Framework - List Users
  method: GET
  name: listusers
  path: /users
- description: Axon Framework - Create a User
  method: POST
  name: createuser
  path: /users
- description: Axon Framework - Delete a User
  method: DELETE
  name: deleteuser
  path: /users/{username}
- description: Axon Framework - Get Cluster Information
  method: GET
  name: getclusterinfo
  path: /cluster
- description: Axon Framework - Remove a Node from the Cluster
  method: DELETE
  name: removenode
  path: /cluster/{nodeName}
- description: Axon Framework - List Event Processors
  method: GET
  name: listeventprocessors
  path: /processors
- description: Axon Framework - Pause an Event Processor
  method: PATCH
  name: pauseeventprocessor
  path: /processors/{processorName}/pause
- description: Axon Framework - Start an Event Processor
  method: PATCH
  name: starteventprocessor
  path: /processors/{processorName}/start
personas: []
provider_name: Axon Framework
provider_slug: axon-framework
search_terms:
- pauseeventprocessor
- removenode
- axon framework - list applications
- event-driven
- axon framework - append an event
- axon framework - append a snapshot
- getcontext
- getsnapshots
- getclusterinfo
- axon framework - list event processors
- axon framework - pause an event processor
- axon framework - delete a context
- api
- axon framework - get snapshots for an aggregate
- java
- createcontext
- listeventprocessors
- axon framework - list contexts
- appendevent
- axon framework - delete a user
- axon
- event sourcing
- deletecontext
- deleteuser
- listqueryhandlers
- cqrs
- axon framework - create a user
- axon framework - start an event processor
- framework
- axon framework - get events for an aggregate
- starteventprocessor
- listevents
- axon framework - get a context
- createuser
- listapplications
- axon framework - list users
- listusers
- axon framework - create a context
- appendsnapshot
- axon framework - remove a node from the cluster
- axon framework - list command handlers
- listcommandhandlers
- messaging
- getaggregateevents
- axon framework - list query handlers
- listcontexts
- microservices
- axon framework - list events
- axon framework - get cluster information
slug: axon-framework-capability
source_filename: axon-framework-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Axon Server REST API\n  description: The Axon Server REST API provides HTTP endpoints for managing the Axon Server event store, command routing,\n    query handling, application contexts, users, and cluster configuration.\n  tags:\n  - Axon\n  - Framework\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: axon-framework\n    baseUri: http://localhost:8024/v1\n    description: Axon Server REST API HTTP API.\n    resources:\n    - name: events\n      path: /events\n      operations:\n      - name: listevents\n        method: GET\n        description: Axon Framework - List Events\n        inputParameters:\n        - name: context\n          in: query\n          type: string\n        - name: trackingToken\n          in: query\n          type: integer\n        - name: numberOfEvents\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: appendevent\n        method: POST\n        description: Axon Framework - Append an Event\n        inputParameters:\n        - name: context\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-aggregates-aggregateid\n      path: /events/aggregates/{aggregateId}\n      operations:\n      - name: getaggregateevents\n        method: GET\n        description: Axon Framework - Get Events for an Aggregate\n        inputParameters:\n        - name: aggregateId\n          in: path\n          type: string\n          required: true\n        - name: context\n          in: query\n          type: string\n        - name: initialSequence\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: snapshots-aggregateid\n      path: /snapshots/{aggregateId}\n      operations:\n      - name: getsnapshots\n        method: GET\n        description: Axon Framework - Get Snapshots for an Aggregate\n        inputParameters:\n        - name: aggregateId\n          in: path\n          type: string\n          required: true\n        - name: context\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: appendsnapshot\n        method: POST\n        description: Axon Framework - Append a Snapshot\n        inputParameters:\n        - name: aggregateId\n          in: path\n          type: string\n          required: true\n        - name: context\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commands\n\
  \      path: /commands\n      operations:\n      - name: listcommandhandlers\n        method: GET\n        description: Axon Framework - List Command Handlers\n        inputParameters:\n        - name: context\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queries\n      path: /queries\n      operations:\n      - name: listqueryhandlers\n        method: GET\n        description: Axon Framework - List Query Handlers\n        inputParameters:\n        - name: context\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: context\n      path: /context\n      operations:\n      - name: listcontexts\n        method: GET\n        description: Axon Framework - List Contexts\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createcontext\n        method: POST\n        description: Axon Framework - Create a Context\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: context-contextname\n      path: /context/{contextName}\n      operations:\n      - name: getcontext\n        method: GET\n        description: Axon Framework - Get a Context\n        inputParameters:\n        - name: contextName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontext\n        method: DELETE\n        description: Axon Framework - Delete a Context\n        inputParameters:\n        - name: contextName\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      operations:\n      - name: listapplications\n        method: GET\n        description: Axon Framework - List Applications\n        inputParameters:\n        - name: context\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: Axon Framework - List Users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Axon Framework - Create a User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: users-username\n      path: /users/{username}\n      operations:\n      - name: deleteuser\n        method: DELETE\n        description: Axon Framework - Delete a User\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster\n      path: /cluster\n      operations:\n      - name: getclusterinfo\n        method: GET\n        description: Axon Framework - Get Cluster Information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-nodename\n      path: /cluster/{nodeName}\n      operations:\n      - name: removenode\n        method: DELETE\n        description: Axon Framework - Remove a Node from the Cluster\n        inputParameters:\n        - name: nodeName\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: processors\n      path: /processors\n      operations:\n      - name: listeventprocessors\n        method: GET\n        description: Axon Framework - List Event Processors\n        inputParameters:\n        - name: context\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: processors-processorname-pause\n      path: /processors/{processorName}/pause\n      operations:\n      - name: pauseeventprocessor\n        method: PATCH\n        description: Axon Framework - Pause an Event Processor\n        inputParameters:\n        - name: processorName\n          in: path\n          type: string\n          required: true\n        - name: context\n         \
  \ in: query\n          type: string\n        - name: tokenStoreIdentifier\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: processors-processorname-start\n      path: /processors/{processorName}/start\n      operations:\n      - name: starteventprocessor\n        method: PATCH\n        description: Axon Framework - Start an Event Processor\n        inputParameters:\n        - name: processorName\n          in: path\n          type: string\n          required: true\n        - name: context\n          in: query\n          type: string\n        - name: tokenStoreIdentifier\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: axon-framework-rest\n    description: REST adapter for\
  \ Axon Server REST API.\n    resources:\n    - path: /events\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: Axon Framework - List Events\n        call: axon-framework.listevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: appendevent\n      operations:\n      - method: POST\n        name: appendevent\n        description: Axon Framework - Append an Event\n        call: axon-framework.appendevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events/aggregates/{aggregateId}\n      name: getaggregateevents\n      operations:\n      - method: GET\n        name: getaggregateevents\n        description: Axon Framework - Get Events for an Aggregate\n        call: axon-framework.getaggregateevents\n        with:\n          aggregateId: rest.aggregateId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /snapshots/{aggregateId}\n      name: getsnapshots\n      operations:\n      - method: GET\n        name: getsnapshots\n        description: Axon Framework - Get Snapshots for an Aggregate\n        call: axon-framework.getsnapshots\n        with:\n          aggregateId: rest.aggregateId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /snapshots/{aggregateId}\n      name: appendsnapshot\n      operations:\n      - method: POST\n        name: appendsnapshot\n        description: Axon Framework - Append a Snapshot\n        call: axon-framework.appendsnapshot\n        with:\n          aggregateId: rest.aggregateId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /commands\n      name: listcommandhandlers\n      operations:\n      - method: GET\n        name: listcommandhandlers\n        description: Axon Framework - List Command Handlers\n        call: axon-framework.listcommandhandlers\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /queries\n      name: listqueryhandlers\n      operations:\n      - method: GET\n        name: listqueryhandlers\n        description: Axon Framework - List Query Handlers\n        call: axon-framework.listqueryhandlers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /context\n      name: listcontexts\n      operations:\n      - method: GET\n        name: listcontexts\n        description: Axon Framework - List Contexts\n        call: axon-framework.listcontexts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /context\n      name: createcontext\n      operations:\n      - method: POST\n        name: createcontext\n        description: Axon Framework - Create a Context\n        call: axon-framework.createcontext\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /context/{contextName}\n      name: getcontext\n     \
  \ operations:\n      - method: GET\n        name: getcontext\n        description: Axon Framework - Get a Context\n        call: axon-framework.getcontext\n        with:\n          contextName: rest.contextName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /context/{contextName}\n      name: deletecontext\n      operations:\n      - method: DELETE\n        name: deletecontext\n        description: Axon Framework - Delete a Context\n        call: axon-framework.deletecontext\n        with:\n          contextName: rest.contextName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications\n      name: listapplications\n      operations:\n      - method: GET\n        name: listapplications\n        description: Axon Framework - List Applications\n        call: axon-framework.listapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: listusers\n\
  \      operations:\n      - method: GET\n        name: listusers\n        description: Axon Framework - List Users\n        call: axon-framework.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Axon Framework - Create a User\n        call: axon-framework.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{username}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Axon Framework - Delete a User\n        call: axon-framework.deleteuser\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cluster\n      name: getclusterinfo\n      operations:\n      - method: GET\n        name: getclusterinfo\n        description: Axon Framework\
  \ - Get Cluster Information\n        call: axon-framework.getclusterinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cluster/{nodeName}\n      name: removenode\n      operations:\n      - method: DELETE\n        name: removenode\n        description: Axon Framework - Remove a Node from the Cluster\n        call: axon-framework.removenode\n        with:\n          nodeName: rest.nodeName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /processors\n      name: listeventprocessors\n      operations:\n      - method: GET\n        name: listeventprocessors\n        description: Axon Framework - List Event Processors\n        call: axon-framework.listeventprocessors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /processors/{processorName}/pause\n      name: pauseeventprocessor\n      operations:\n      - method: PATCH\n        name: pauseeventprocessor\n        description:\
  \ Axon Framework - Pause an Event Processor\n        call: axon-framework.pauseeventprocessor\n        with:\n          processorName: rest.processorName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /processors/{processorName}/start\n      name: starteventprocessor\n      operations:\n      - method: PATCH\n        name: starteventprocessor\n        description: Axon Framework - Start an Event Processor\n        call: axon-framework.starteventprocessor\n        with:\n          processorName: rest.processorName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: axon-framework-mcp\n    transport: http\n    description: MCP adapter for Axon Server REST API for AI agent use.\n    tools:\n    - name: listevents\n      description: Axon Framework - List Events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.listevents\n\
  \      with:\n        context: tools.context\n        trackingToken: tools.trackingToken\n        numberOfEvents: tools.numberOfEvents\n      inputParameters:\n      - name: context\n        type: string\n        description: context\n      - name: trackingToken\n        type: integer\n        description: trackingToken\n      - name: numberOfEvents\n        type: integer\n        description: numberOfEvents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: appendevent\n      description: Axon Framework - Append an Event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: axon-framework.appendevent\n      with:\n        context: tools.context\n      inputParameters:\n      - name: context\n        type: string\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaggregateevents\n      description: Axon Framework - Get Events for an Aggregate\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.getaggregateevents\n      with:\n        aggregateId: tools.aggregateId\n        context: tools.context\n        initialSequence: tools.initialSequence\n      inputParameters:\n      - name: aggregateId\n        type: string\n        description: aggregateId\n        required: true\n      - name: context\n        type: string\n        description: context\n      - name: initialSequence\n        type: integer\n        description: initialSequence\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsnapshots\n      description: Axon Framework - Get Snapshots for an Aggregate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.getsnapshots\n      with:\n        aggregateId: tools.aggregateId\n        context: tools.context\n      inputParameters:\n      - name: aggregateId\n\
  \        type: string\n        description: aggregateId\n        required: true\n      - name: context\n        type: string\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: appendsnapshot\n      description: Axon Framework - Append a Snapshot\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: axon-framework.appendsnapshot\n      with:\n        aggregateId: tools.aggregateId\n        context: tools.context\n      inputParameters:\n      - name: aggregateId\n        type: string\n        description: aggregateId\n        required: true\n      - name: context\n        type: string\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcommandhandlers\n      description: Axon Framework - List Command Handlers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.listcommandhandlers\n\
  \      with:\n        context: tools.context\n      inputParameters:\n      - name: context\n        type: string\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listqueryhandlers\n      description: Axon Framework - List Query Handlers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.listqueryhandlers\n      with:\n        context: tools.context\n      inputParameters:\n      - name: context\n        type: string\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontexts\n      description: Axon Framework - List Contexts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.listcontexts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontext\n      description: Axon Framework - Create a\
  \ Context\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: axon-framework.createcontext\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontext\n      description: Axon Framework - Get a Context\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.getcontext\n      with:\n        contextName: tools.contextName\n      inputParameters:\n      - name: contextName\n        type: string\n        description: contextName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontext\n      description: Axon Framework - Delete a Context\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: axon-framework.deletecontext\n      with:\n        contextName: tools.contextName\n      inputParameters:\n      - name: contextName\n       \
  \ type: string\n        description: contextName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapplications\n      description: Axon Framework - List Applications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.listapplications\n      with:\n        context: tools.context\n      inputParameters:\n      - name: context\n        type: string\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: Axon Framework - List Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.listusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: Axon Framework - Create a User\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: axon-framework.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Axon Framework - Delete a User\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: axon-framework.deleteuser\n      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusterinfo\n      description: Axon Framework - Get Cluster Information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.getclusterinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removenode\n      description: Axon Framework - Remove a Node from the Cluster\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: axon-framework.removenode\n      with:\n        nodeName: tools.nodeName\n      inputParameters:\n      - name: nodeName\n        type: string\n        description: nodeName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listeventprocessors\n      description: Axon Framework - List Event Processors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: axon-framework.listeventprocessors\n      with:\n        context: tools.context\n      inputParameters:\n      - name: context\n        type: string\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pauseeventprocessor\n      description: Axon Framework - Pause an Event Processor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: axon-framework.pauseeventprocessor\n     \
  \ with:\n        processorName: tools.processorName\n        context: tools.context\n        tokenStoreIdentifier: tools.tokenStoreIdentifier\n      inputParameters:\n      - name: processorName\n        type: string\n        description: processorName\n        required: true\n      - name: context\n        type: string\n        description: context\n      - name: tokenStoreIdentifier\n        type: string\n        description: tokenStoreIdentifier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: starteventprocessor\n      description: Axon Framework - Start an Event Processor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: axon-framework.starteventprocessor\n      with:\n        processorName: tools.processorName\n        context: tools.context\n        tokenStoreIdentifier: tools.tokenStoreIdentifier\n      inputParameters:\n      - name: processorName\n        type: string\n        description:\
  \ processorName\n        required: true\n      - name: context\n        type: string\n        description: context\n      - name: tokenStoreIdentifier\n        type: string\n        description: tokenStoreIdentifier\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/axon-framework/refs/heads/main/capabilities/axon-framework-capability.yaml
tags:
- Axon
- Framework
- API
tools:
- description: Axon Framework - List Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: Axon Framework - Append an Event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: appendevent
- description: Axon Framework - Get Events for an Aggregate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaggregateevents
- description: Axon Framework - Get Snapshots for an Aggregate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsnapshots
- description: Axon Framework - Append a Snapshot
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: appendsnapshot
- description: Axon Framework - List Command Handlers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcommandhandlers
- description: Axon Framework - List Query Handlers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listqueryhandlers
- description: Axon Framework - List Contexts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontexts
- description: Axon Framework - Create a Context
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontext
- description: Axon Framework - Get a Context
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontext
- description: Axon Framework - Delete a Context
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontext
- description: Axon Framework - List Applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplications
- description: Axon Framework - List Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Axon Framework - Create a User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Axon Framework - Delete a User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Axon Framework - Get Cluster Information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusterinfo
- description: Axon Framework - Remove a Node from the Cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removenode
- description: Axon Framework - List Event Processors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventprocessors
- description: Axon Framework - Pause an Event Processor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pauseeventprocessor
- description: Axon Framework - Start an Event Processor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: starteventprocessor
---
