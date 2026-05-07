---
categories:
- incident-management
consumed_apis: []
description: Unified incident response workflow combining problems, events, and entity data for SREs investigating service degradations detected by Davis AI.
layout: capability
name: Dynatrace Incident Response
operations:
- description: List problems detected by Davis AI
  method: GET
  name: list-problems
  path: /v1/problems
- description: Get full problem details with root cause analysis
  method: GET
  name: get-problem
  path: /v1/problems/{problemId}
- description: Close a problem with an optional message
  method: POST
  name: close-problem
  path: /v1/problems/{problemId}/close
- description: List comments on a problem
  method: GET
  name: list-problem-comments
  path: /v1/problems/{problemId}/comments
- description: Add an investigation comment
  method: POST
  name: create-problem-comment
  path: /v1/problems/{problemId}/comments
- description: Get a comment
  method: GET
  name: get-problem-comment
  path: /v1/problems/{problemId}/comments/{commentId}
- description: Update a comment
  method: PUT
  name: update-problem-comment
  path: /v1/problems/{problemId}/comments/{commentId}
- description: Delete a comment
  method: DELETE
  name: delete-problem-comment
  path: /v1/problems/{problemId}/comments/{commentId}
- description: List events matching filters
  method: GET
  name: list-events
  path: /v1/events
- description: Get a specific event
  method: GET
  name: get-event
  path: /v1/events/{eventId}
- description: Ingest a custom event to annotate the timeline
  method: POST
  name: ingest-event
  path: /v1/events/ingest
- description: List entities matching a selector
  method: GET
  name: list-entities
  path: /v1/entities
- description: Get entity details for root cause investigation
  method: GET
  name: get-entity
  path: /v1/entities/{entityId}
personas: []
provider_name: Dynatrace
provider_slug: dynatrace
search_terms:
- close a problem
- list problem comments
- get entity details
- analytics
- observability
- list events
- list entities
- manage a specific comment
- incident response
- get problem details including root cause
- application security
- automation
- query and manage ai-detected problems
- close an open problem with an optional closing message
- delete a comment from a problem
- get entity details for root cause investigation
- ai operations
- update a comment
- get a specific comment on a problem
- apm
- create problem comment
- get a specific event
- close problem
- cloud monitoring
- manage investigation comments
- add an investigation comment to a problem
- application performance monitoring
- get full problem details with root cause analysis
- get full details of a specific problem including root cause analysis
- list entities matching a selector
- list events matching filters
- delete problem comment
- ingest custom events
- get details of a specific event
- events
- list problems
- list problems detected by davis ai
- get problem
- close a problem with an optional message
- sre
- delete a comment
- update problem comment
- query events related to incidents
- get entity
- list events in the dynatrace environment
- list monitored entities matching a selector
- intelligence
- ingest a custom event to annotate the timeline
- add an investigation comment
- get event details
- get details of a specific monitored entity
- get problem comment
- dynatrace
- list problems detected by davis ai in the dynatrace environment
- get event
- digital experience management
- ingest event
- query affected entities
- update an investigation comment
- list comments on a problem
- get a comment
- problems
- list investigation comments on a problem
slug: incident-response
source_filename: incident-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Dynatrace Incident Response\n  description: Unified incident response workflow combining problems, events, and entity data for SREs investigating service\n    degradations detected by Davis AI.\n  tags:\n  - Dynatrace\n  - Incident Response\n  - SRE\n  - Problems\n  - Events\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DYNATRACE_API_TOKEN: DYNATRACE_API_TOKEN\n    DYNATRACE_ENVIRONMENT_ID: DYNATRACE_ENVIRONMENT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: problems-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Problems API v2 for querying and managing AI-detected problems.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: problems\n      path: /problems\n      description: Query problems\n      operations:\n\
  \      - name: list-problems\n        method: GET\n        description: Returns a list of problems from the Dynatrace environment.\n        inputParameters:\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of problems to return per page.\n        - name: problemSelector\n          in: query\n          type: string\n          required: false\n          description: Problem selector expression.\n        - name: entitySelector\n          in: query\n          type: string\n          required: false\n          description: Entity selector to filter by affected entities.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the queried time range.\n        - name: to\n          in:\
  \ query\n          type: string\n          required: false\n          description: End of the queried time range.\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort order for results.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Additional fields to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: problem-detail\n      path: /problems/{problemId}\n      description: Get a specific problem\n      operations:\n      - name: get-problem\n        method: GET\n        description: Returns the full details of a specific problem.\n        inputParameters:\n        - name: problemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the problem.\n        - name: fields\n          in:\
  \ query\n          type: string\n          required: false\n          description: Additional fields to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: problem-close\n      path: /problems/{problemId}/close\n      description: Close a problem\n      operations:\n      - name: close-problem\n        method: POST\n        description: Closes the specified problem with an optional closing message.\n        inputParameters:\n        - name: problemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the problem.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n    - name: problem-comments\n      path: /problems/{problemId}/comments\n      description:\
  \ Manage problem comments\n      operations:\n      - name: list-problem-comments\n        method: GET\n        description: Returns a list of all comments attached to the specified problem.\n        inputParameters:\n        - name: problemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the problem.\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of comments to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-problem-comment\n        method: POST\n        description: Creates a new comment on the specified problem.\n        inputParameters:\n        - name:\
  \ problemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the problem.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n            context: '{{tools.context}}'\n    - name: problem-comment-detail\n      path: /problems/{problemId}/comments/{commentId}\n      description: Get, update, or delete a specific comment\n      operations:\n      - name: get-problem-comment\n        method: GET\n        description: Returns the details of a specific comment.\n        inputParameters:\n        - name: problemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the problem.\n        - name: commentId\n          in: path\n          type: string\n          required: true\n          description:\
  \ The unique identifier of the comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-problem-comment\n        method: PUT\n        description: Updates the content or context of an existing comment.\n        inputParameters:\n        - name: problemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the problem.\n        - name: commentId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n            context: '{{tools.context}}'\n      - name: delete-problem-comment\n        method: DELETE\n        description: Permanently\
  \ deletes a specific comment from a problem.\n        inputParameters:\n        - name: problemId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the problem.\n        - name: commentId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: events-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Events API v2 for querying and ingesting custom events.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name: events\n      path: /events\n      description: Query events\n      operations:\n      - name: list-events\n    \
  \    method: GET\n        description: Returns a list of events matching the specified filters.\n        inputParameters:\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of events to return per page.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the queried time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the queried time range.\n        - name: eventSelector\n          in: query\n          type: string\n          required: false\n          description: Event selector expression.\n        - name: entitySelector\n          in: query\n          type: string\n          required: false\n\
  \          description: Entity selector to filter events by affected entities.\n        - name: eventType\n          in: query\n          type: string\n          required: false\n          description: Filter by event type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-detail\n      path: /events/{eventId}\n      description: Get a specific event\n      operations:\n      - name: get-event\n        method: GET\n        description: Returns the details of a specific event by ID.\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-ingest\n      path: /events/ingest\n      description: Ingest custom events\n      operations:\n\
  \      - name: ingest-event\n        method: POST\n        description: Ingests a custom event into the Dynatrace environment.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            eventType: '{{tools.event_type}}'\n            title: '{{tools.title}}'\n            entitySelector: '{{tools.entity_selector}}'\n            startTime: '{{tools.start_time}}'\n            endTime: '{{tools.end_time}}'\n            properties: '{{tools.properties}}'\n  - type: http\n    namespace: entities-v2\n    baseUri: https://${DYNATRACE_ENVIRONMENT_ID}.live.dynatrace.com/api/v2\n    description: Dynatrace Entities API v2 for querying monitored entities and entity types.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Api-Token {{DYNATRACE_API_TOKEN}}\n      placement: header\n    resources:\n    - name:\
  \ entities\n      path: /entities\n      description: Query monitored entities\n      operations:\n      - name: list-entities\n        method: GET\n        description: Returns a list of monitored entities matching the specified entity selector.\n        inputParameters:\n        - name: entitySelector\n          in: query\n          type: string\n          required: true\n          description: Entity selector expression, e.g., type(SERVICE).\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of entities to return per page.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Additional fields to include, e.g., +properties,+tags.\n        - name: from\n          in: query\n       \
  \   type: string\n          required: false\n          description: Start of the time range for entity discovery.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the time range for entity discovery.\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort order, e.g., +displayName or -lastSeenTms.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-detail\n      path: /entities/{entityId}\n      description: Get a specific entity by ID\n      operations:\n      - name: get-entity\n        method: GET\n        description: Returns the details of a specific monitored entity by its entity ID.\n        inputParameters:\n        - name: entityId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier\
  \ of the entity.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Additional fields to include.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of the time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the time range.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-types\n      path: /entityTypes\n      description: Query entity type definitions\n      operations:\n      - name: list-entity-types\n        method: GET\n        description: Returns a list of all entity types available in the environment.\n        inputParameters:\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for\
  \ the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of entity types to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-type-detail\n      path: /entityTypes/{type}\n      description: Get a specific entity type definition\n      operations:\n      - name: get-entity-type\n        method: GET\n        description: Returns the definition of a specific entity type.\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: The entity type identifier, e.g., SERVICE, HOST.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-lookup\n      path: /entities/lookup\n      description: Look up entity by\
  \ name\n      operations:\n      - name: lookup-entity\n        method: POST\n        description: Looks up a specific entity by its display name and type.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: incident-response-api\n    description: Unified REST API for Dynatrace incident response workflows.\n    resources:\n    - path: /v1/problems\n      name: problems\n      description: Query and manage AI-detected problems\n      operations:\n      - method: GET\n        name: list-problems\n        description: List problems detected by Davis AI\n        call: problems-v2.list-problems\n        with:\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n          problemSelector:\
  \ rest.problemSelector\n          entitySelector: rest.entitySelector\n          from: rest.from\n          to: rest.to\n          sort: rest.sort\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/problems/{problemId}\n      name: problem-detail\n      description: Get problem details including root cause\n      operations:\n      - method: GET\n        name: get-problem\n        description: Get full problem details with root cause analysis\n        call: problems-v2.get-problem\n        with:\n          problemId: rest.problemId\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/problems/{problemId}/close\n      name: problem-close\n      description: Close a problem\n      operations:\n      - method: POST\n        name: close-problem\n        description: Close a problem with an optional message\n        call: problems-v2.close-problem\n   \
  \     with:\n          problemId: rest.problemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/problems/{problemId}/comments\n      name: problem-comments\n      description: Manage investigation comments\n      operations:\n      - method: GET\n        name: list-problem-comments\n        description: List comments on a problem\n        call: problems-v2.list-problem-comments\n        with:\n          problemId: rest.problemId\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-problem-comment\n        description: Add an investigation comment\n        call: problems-v2.create-problem-comment\n        with:\n          problemId: rest.problemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/problems/{problemId}/comments/{commentId}\n      name: problem-comment-detail\n\
  \      description: Manage a specific comment\n      operations:\n      - method: GET\n        name: get-problem-comment\n        description: Get a comment\n        call: problems-v2.get-problem-comment\n        with:\n          problemId: rest.problemId\n          commentId: rest.commentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-problem-comment\n        description: Update a comment\n        call: problems-v2.update-problem-comment\n        with:\n          problemId: rest.problemId\n          commentId: rest.commentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-problem-comment\n        description: Delete a comment\n        call: problems-v2.delete-problem-comment\n        with:\n          problemId: rest.problemId\n          commentId: rest.commentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/events\n      name: events\n      description: Query events related to incidents\n      operations:\n      - method: GET\n        name: list-events\n        description: List events matching filters\n        call: events-v2.list-events\n        with:\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n          from: rest.from\n          to: rest.to\n          eventSelector: rest.eventSelector\n          entitySelector: rest.entitySelector\n          eventType: rest.eventType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{eventId}\n      name: event-detail\n      description: Get event details\n      operations:\n      - method: GET\n        name: get-event\n        description: Get a specific event\n        call: events-v2.get-event\n        with:\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/ingest\n      name: event-ingest\n\
  \      description: Ingest custom events\n      operations:\n      - method: POST\n        name: ingest-event\n        description: Ingest a custom event to annotate the timeline\n        call: events-v2.ingest-event\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities\n      name: entities\n      description: Query affected entities\n      operations:\n      - method: GET\n        name: list-entities\n        description: List entities matching a selector\n        call: entities-v2.list-entities\n        with:\n          entitySelector: rest.entitySelector\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n          fields: rest.fields\n          from: rest.from\n          to: rest.to\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/{entityId}\n      name: entity-detail\n      description: Get entity details\n      operations:\n      - method: GET\n        name:\
  \ get-entity\n        description: Get entity details for root cause investigation\n        call: entities-v2.get-entity\n        with:\n          entityId: rest.entityId\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: incident-response-mcp\n    transport: http\n    description: MCP server for AI-assisted Dynatrace incident response.\n    tools:\n    - name: list-problems\n      description: List problems detected by Davis AI in the Dynatrace environment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: problems-v2.list-problems\n      with:\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n        problemSelector: tools.problemSelector\n        entitySelector: tools.entitySelector\n        from: tools.from\n        to: tools.to\n        sort: tools.sort\n        fields: tools.fields\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: get-problem\n      description: Get full details of a specific problem including root cause analysis\n      hints:\n        readOnly: true\n        openWorld: true\n      call: problems-v2.get-problem\n      with:\n        problemId: tools.problemId\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: close-problem\n      description: Close an open problem with an optional closing message\n      hints:\n        readOnly: false\n        destructive: true\n        openWorld: true\n      call: problems-v2.close-problem\n      with:\n        problemId: tools.problemId\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-problem-comments\n      description: List investigation comments on a problem\n      hints:\n        readOnly: true\n        openWorld: true\n      call: problems-v2.list-problem-comments\n      with:\n        problemId:\
  \ tools.problemId\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-problem-comment\n      description: Add an investigation comment to a problem\n      hints:\n        readOnly: false\n        openWorld: true\n      call: problems-v2.create-problem-comment\n      with:\n        problemId: tools.problemId\n        message: tools.message\n        context: tools.context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-problem-comment\n      description: Get a specific comment on a problem\n      hints:\n        readOnly: true\n        openWorld: true\n      call: problems-v2.get-problem-comment\n      with:\n        problemId: tools.problemId\n        commentId: tools.commentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-problem-comment\n      description: Update an investigation comment\n      hints:\n\
  \        readOnly: false\n        idempotent: true\n        openWorld: true\n      call: problems-v2.update-problem-comment\n      with:\n        problemId: tools.problemId\n        commentId: tools.commentId\n        message: tools.message\n        context: tools.context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-problem-comment\n      description: Delete a comment from a problem\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n        openWorld: true\n      call: problems-v2.delete-problem-comment\n      with:\n        problemId: tools.problemId\n        commentId: tools.commentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-events\n      description: List events in the Dynatrace environment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: events-v2.list-events\n      with:\n        nextPageKey: tools.nextPageKey\n        pageSize:\
  \ tools.pageSize\n        from: tools.from\n        to: tools.to\n        eventSelector: tools.eventSelector\n        entitySelector: tools.entitySelector\n        eventType: tools.eventType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event\n      description: Get details of a specific event\n      hints:\n        readOnly: true\n        openWorld: true\n      call: events-v2.get-event\n      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ingest-event\n      description: Ingest a custom event to annotate the timeline\n      hints:\n        readOnly: false\n        openWorld: true\n      call: events-v2.ingest-event\n      with:\n        event_type: tools.event_type\n        title: tools.title\n        entity_selector: tools.entity_selector\n        start_time: tools.start_time\n        end_time: tools.end_time\n        properties: tools.properties\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-entities\n      description: List monitored entities matching a selector\n      hints:\n        readOnly: true\n        openWorld: true\n      call: entities-v2.list-entities\n      with:\n        entitySelector: tools.entitySelector\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n        fields: tools.fields\n        from: tools.from\n        to: tools.to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity\n      description: Get details of a specific monitored entity\n      hints:\n        readOnly: true\n        openWorld: true\n      call: entities-v2.get-entity\n      with:\n        entityId: tools.entityId\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/dynatrace/refs/heads/main/capabilities/incident-response.yaml
tags:
- Dynatrace
- Incident Response
- SRE
- Problems
- Events
tools:
- description: List problems detected by Davis AI in the Dynatrace environment
  hints:
    openWorld: true
    readOnly: true
  name: list-problems
- description: Get full details of a specific problem including root cause analysis
  hints:
    openWorld: true
    readOnly: true
  name: get-problem
- description: Close an open problem with an optional closing message
  hints:
    destructive: true
    openWorld: true
    readOnly: false
  name: close-problem
- description: List investigation comments on a problem
  hints:
    openWorld: true
    readOnly: true
  name: list-problem-comments
- description: Add an investigation comment to a problem
  hints:
    openWorld: true
    readOnly: false
  name: create-problem-comment
- description: Get a specific comment on a problem
  hints:
    openWorld: true
    readOnly: true
  name: get-problem-comment
- description: Update an investigation comment
  hints:
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-problem-comment
- description: Delete a comment from a problem
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-problem-comment
- description: List events in the Dynatrace environment
  hints:
    openWorld: true
    readOnly: true
  name: list-events
- description: Get details of a specific event
  hints:
    openWorld: true
    readOnly: true
  name: get-event
- description: Ingest a custom event to annotate the timeline
  hints:
    openWorld: true
    readOnly: false
  name: ingest-event
- description: List monitored entities matching a selector
  hints:
    openWorld: true
    readOnly: true
  name: list-entities
- description: Get details of a specific monitored entity
  hints:
    openWorld: true
    readOnly: true
  name: get-entity
---
