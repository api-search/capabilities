---
categories:
- incident-management
consumed_apis:
- problems-v2
- events-v2
- entities-v2
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
- automation
- list problems detected by davis ai
- delete problem comment
- cloud monitoring
- close a problem with an optional message
- list investigation comments on a problem
- application security
- list entities
- incident response
- problems
- get entity
- apm
- analytics
- get a specific event
- list comments on a problem
- close a problem
- get entity details for root cause investigation
- dynatrace
- get full problem details with root cause analysis
- ingest a custom event to annotate the timeline
- ingest custom events
- list events
- delete a comment from a problem
- get event
- list entities matching a selector
- close problem
- get entity details
- query and manage ai-detected problems
- ai operations
- list events in the dynatrace environment
- list problems
- get event details
- ingest event
- sre
- manage a specific comment
- get a comment
- get details of a specific monitored entity
- get a specific comment on a problem
- update a comment
- events
- list problem comments
- update an investigation comment
- get details of a specific event
- get problem comment
- delete a comment
- observability
- manage investigation comments
- update problem comment
- get full details of a specific problem including root cause analysis
- query affected entities
- get problem
- list problems detected by davis ai in the dynatrace environment
- list events matching filters
- get problem details including root cause
- close an open problem with an optional closing message
- application performance monitoring
- digital experience management
- add an investigation comment to a problem
- list monitored entities matching a selector
- add an investigation comment
- create problem comment
- query events related to incidents
- intelligence
slug: incident-response
source_filename: incident-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Dynatrace Incident Response\"\n  description: \"Unified incident response workflow combining problems, events, and entity data for SREs investigating service degradations detected by Davis AI.\"\n  tags:\n    - Dynatrace\n    - Incident Response\n    - SRE\n    - Problems\n    - Events\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      DYNATRACE_API_TOKEN: DYNATRACE_API_TOKEN\n      DYNATRACE_ENVIRONMENT_ID: DYNATRACE_ENVIRONMENT_ID\n\ncapability:\n  consumes:\n    - import: problems-v2\n      location: ./shared/problems-v2.yaml\n    - import: events-v2\n      location: ./shared/events-v2.yaml\n    - import: entities-v2\n      location: ./shared/entities-v2.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: incident-response-api\n      description: \"Unified REST API for Dynatrace incident response workflows.\"\n      resources:\n        - path: /v1/problems\n\
  \          name: problems\n          description: \"Query and manage AI-detected problems\"\n          operations:\n            - method: GET\n              name: list-problems\n              description: \"List problems detected by Davis AI\"\n              call: \"problems-v2.list-problems\"\n              with:\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n                problemSelector: \"rest.problemSelector\"\n                entitySelector: \"rest.entitySelector\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                sort: \"rest.sort\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/problems/{problemId}\n          name: problem-detail\n          description: \"Get problem details including root cause\"\n          operations:\n            - method: GET\n              name: get-problem\n\
  \              description: \"Get full problem details with root cause analysis\"\n              call: \"problems-v2.get-problem\"\n              with:\n                problemId: \"rest.problemId\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/problems/{problemId}/close\n          name: problem-close\n          description: \"Close a problem\"\n          operations:\n            - method: POST\n              name: close-problem\n              description: \"Close a problem with an optional message\"\n              call: \"problems-v2.close-problem\"\n              with:\n                problemId: \"rest.problemId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/problems/{problemId}/comments\n          name: problem-comments\n          description: \"Manage investigation comments\"\n          operations:\n\
  \            - method: GET\n              name: list-problem-comments\n              description: \"List comments on a problem\"\n              call: \"problems-v2.list-problem-comments\"\n              with:\n                problemId: \"rest.problemId\"\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-problem-comment\n              description: \"Add an investigation comment\"\n              call: \"problems-v2.create-problem-comment\"\n              with:\n                problemId: \"rest.problemId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/problems/{problemId}/comments/{commentId}\n          name: problem-comment-detail\n          description: \"Manage a specific comment\"\n          operations:\n     \
  \       - method: GET\n              name: get-problem-comment\n              description: \"Get a comment\"\n              call: \"problems-v2.get-problem-comment\"\n              with:\n                problemId: \"rest.problemId\"\n                commentId: \"rest.commentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-problem-comment\n              description: \"Update a comment\"\n              call: \"problems-v2.update-problem-comment\"\n              with:\n                problemId: \"rest.problemId\"\n                commentId: \"rest.commentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-problem-comment\n              description: \"Delete a comment\"\n              call: \"problems-v2.delete-problem-comment\"\n              with:\n                problemId:\
  \ \"rest.problemId\"\n                commentId: \"rest.commentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Query events related to incidents\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List events matching filters\"\n              call: \"events-v2.list-events\"\n              with:\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                eventSelector: \"rest.eventSelector\"\n                entitySelector: \"rest.entitySelector\"\n                eventType: \"rest.eventType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events/{eventId}\n          name: event-detail\n          description:\
  \ \"Get event details\"\n          operations:\n            - method: GET\n              name: get-event\n              description: \"Get a specific event\"\n              call: \"events-v2.get-event\"\n              with:\n                eventId: \"rest.eventId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events/ingest\n          name: event-ingest\n          description: \"Ingest custom events\"\n          operations:\n            - method: POST\n              name: ingest-event\n              description: \"Ingest a custom event to annotate the timeline\"\n              call: \"events-v2.ingest-event\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities\n          name: entities\n          description: \"Query affected entities\"\n          operations:\n            - method: GET\n              name: list-entities\n            \
  \  description: \"List entities matching a selector\"\n              call: \"entities-v2.list-entities\"\n              with:\n                entitySelector: \"rest.entitySelector\"\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n                fields: \"rest.fields\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities/{entityId}\n          name: entity-detail\n          description: \"Get entity details\"\n          operations:\n            - method: GET\n              name: get-entity\n              description: \"Get entity details for root cause investigation\"\n              call: \"entities-v2.get-entity\"\n              with:\n                entityId: \"rest.entityId\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n       \
  \           mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: incident-response-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Dynatrace incident response.\"\n      tools:\n        - name: list-problems\n          description: \"List problems detected by Davis AI in the Dynatrace environment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"problems-v2.list-problems\"\n          with:\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n            problemSelector: \"tools.problemSelector\"\n            entitySelector: \"tools.entitySelector\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            sort: \"tools.sort\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-problem\n          description: \"Get full details of a specific problem\
  \ including root cause analysis\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"problems-v2.get-problem\"\n          with:\n            problemId: \"tools.problemId\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: close-problem\n          description: \"Close an open problem with an optional closing message\"\n          hints:\n            readOnly: false\n            destructive: true\n            openWorld: true\n          call: \"problems-v2.close-problem\"\n          with:\n            problemId: \"tools.problemId\"\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-problem-comments\n          description: \"List investigation comments on a problem\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"\
  problems-v2.list-problem-comments\"\n          with:\n            problemId: \"tools.problemId\"\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-problem-comment\n          description: \"Add an investigation comment to a problem\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"problems-v2.create-problem-comment\"\n          with:\n            problemId: \"tools.problemId\"\n            message: \"tools.message\"\n            context: \"tools.context\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-problem-comment\n          description: \"Get a specific comment on a problem\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"problems-v2.get-problem-comment\"\n          with:\n      \
  \      problemId: \"tools.problemId\"\n            commentId: \"tools.commentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-problem-comment\n          description: \"Update an investigation comment\"\n          hints:\n            readOnly: false\n            idempotent: true\n            openWorld: true\n          call: \"problems-v2.update-problem-comment\"\n          with:\n            problemId: \"tools.problemId\"\n            commentId: \"tools.commentId\"\n            message: \"tools.message\"\n            context: \"tools.context\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-problem-comment\n          description: \"Delete a comment from a problem\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          call: \"problems-v2.delete-problem-comment\"\n\
  \          with:\n            problemId: \"tools.problemId\"\n            commentId: \"tools.commentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-events\n          description: \"List events in the Dynatrace environment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"events-v2.list-events\"\n          with:\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            eventSelector: \"tools.eventSelector\"\n            entitySelector: \"tools.entitySelector\"\n            eventType: \"tools.eventType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-event\n          description: \"Get details of a specific event\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"\
  events-v2.get-event\"\n          with:\n            eventId: \"tools.eventId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ingest-event\n          description: \"Ingest a custom event to annotate the timeline\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"events-v2.ingest-event\"\n          with:\n            event_type: \"tools.event_type\"\n            title: \"tools.title\"\n            entity_selector: \"tools.entity_selector\"\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n            properties: \"tools.properties\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-entities\n          description: \"List monitored entities matching a selector\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entities-v2.list-entities\"\n    \
  \      with:\n            entitySelector: \"tools.entitySelector\"\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n            fields: \"tools.fields\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-entity\n          description: \"Get details of a specific monitored entity\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entities-v2.get-entity\"\n          with:\n            entityId: \"tools.entityId\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
