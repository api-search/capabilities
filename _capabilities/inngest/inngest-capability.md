---
categories: []
consumed_apis: []
description: The Inngest REST API provides programmatic access to manage and interact with Inngest resources including events, functions, and runs. It enables developers to send events to trigger functions, fetch run status and output, and inspect function activity for event-driven, background, and durable workflows.
layout: capability
name: Inngest REST API
operations:
- description: Send event(s) to Inngest
  method: POST
  name: sendevents
  path: /e/{eventKey}
- description: List recent events
  method: GET
  name: listevents
  path: /v1/events
- description: Get an event by ID
  method: GET
  name: getevent
  path: /v1/events/{eventId}
- description: List runs triggered by an event
  method: GET
  name: listeventruns
  path: /v1/events/{eventId}/runs
- description: Get function run status
  method: GET
  name: getrun
  path: /v1/runs/{runId}
- description: List the jobs (steps) for a run
  method: GET
  name: listrunjobs
  path: /v1/runs/{runId}/jobs
- description: Cancel a function run
  method: POST
  name: cancelrun
  path: /v1/runs/{runId}/cancel
- description: List functions
  method: GET
  name: listfunctions
  path: /v1/functions
personas: []
provider_name: Inngest
provider_slug: inngest
search_terms:
- event-driven
- cron jobs
- ai agents
- background jobs
- get function run status
- api
- listrunjobs
- getrun
- step functions
- send event(s) to inngest
- sendevents
- getevent
- list the jobs (steps) for a run
- orchestration
- listfunctions
- serverless
- cancel a function run
- listeventruns
- get an event by id
- inngest
- durable execution
- listevents
- cancelrun
- queues
- workflows
- list functions
- list runs triggered by an event
- list recent events
slug: inngest-capability
source_filename: inngest-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Inngest REST API\n  description: The Inngest REST API provides programmatic access to manage and interact with Inngest resources including events,\n    functions, and runs. It enables developers to send events to trigger functions, fetch run status and output, and inspect\n    function activity for event-driven, background, and durable workflows.\n  tags:\n  - Inngest\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: inngest\n    baseUri: https://api.inngest.com\n    description: Inngest REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{INNGEST_TOKEN}}'\n    resources:\n    - name: e-eventkey\n      path: /e/{eventKey}\n      operations:\n      - name: sendevents\n        method: POST\n        description: Send event(s) to Inngest\n        inputParameters:\n        - name: eventKey\n          in: path\n          type: string\n          required:\
  \ true\n          description: Your environment-specific Inngest event key.\n        - name: x-inngest-env\n          in: header\n          type: string\n          description: Branch environment to target.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-events\n      path: /v1/events\n      operations:\n      - name: listevents\n        method: GET\n        description: List recent events\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter events by event name.\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-events-eventid\n      path: /v1/events/{eventId}\n      operations:\n      - name: getevent\n        method: GET\n        description: Get an event by ID\n\
  \        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-events-eventid-runs\n      path: /v1/events/{eventId}/runs\n      operations:\n      - name: listeventruns\n        method: GET\n        description: List runs triggered by an event\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-runs-runid\n      path: /v1/runs/{runId}\n      operations:\n      - name: getrun\n        method: GET\n        description: Get function run status\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-runs-runid-jobs\n      path: /v1/runs/{runId}/jobs\n      operations:\n      - name: listrunjobs\n        method: GET\n        description: List the jobs (steps) for a run\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-runs-runid-cancel\n      path: /v1/runs/{runId}/cancel\n      operations:\n      - name: cancelrun\n        method: POST\n        description: Cancel a function run\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-functions\n      path:\
  \ /v1/functions\n      operations:\n      - name: listfunctions\n        method: GET\n        description: List functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: inngest-rest\n    description: REST adapter for Inngest REST API.\n    resources:\n    - path: /e/{eventKey}\n      name: sendevents\n      operations:\n      - method: POST\n        name: sendevents\n        description: Send event(s) to Inngest\n        call: inngest.sendevents\n        with:\n          eventKey: rest.eventKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: List recent events\n        call: inngest.listevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{eventId}\n\
  \      name: getevent\n      operations:\n      - method: GET\n        name: getevent\n        description: Get an event by ID\n        call: inngest.getevent\n        with:\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{eventId}/runs\n      name: listeventruns\n      operations:\n      - method: GET\n        name: listeventruns\n        description: List runs triggered by an event\n        call: inngest.listeventruns\n        with:\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}\n      name: getrun\n      operations:\n      - method: GET\n        name: getrun\n        description: Get function run status\n        call: inngest.getrun\n        with:\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}/jobs\n      name: listrunjobs\n   \
  \   operations:\n      - method: GET\n        name: listrunjobs\n        description: List the jobs (steps) for a run\n        call: inngest.listrunjobs\n        with:\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}/cancel\n      name: cancelrun\n      operations:\n      - method: POST\n        name: cancelrun\n        description: Cancel a function run\n        call: inngest.cancelrun\n        with:\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/functions\n      name: listfunctions\n      operations:\n      - method: GET\n        name: listfunctions\n        description: List functions\n        call: inngest.listfunctions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: inngest-mcp\n    transport: http\n    description: MCP adapter for Inngest REST API for AI\
  \ agent use.\n    tools:\n    - name: sendevents\n      description: Send event(s) to Inngest\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: inngest.sendevents\n      with:\n        eventKey: tools.eventKey\n      inputParameters:\n      - name: eventKey\n        type: string\n        description: Your environment-specific Inngest event key.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listevents\n      description: List recent events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: inngest.listevents\n      with:\n        name: tools.name\n        limit: tools.limit\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter events by event name.\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getevent\n      description: Get an event by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: inngest.getevent\n      with:\n        eventId: tools.eventId\n      inputParameters:\n      - name: eventId\n        type: string\n        description: eventId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listeventruns\n      description: List runs triggered by an event\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: inngest.listeventruns\n      with:\n        eventId: tools.eventId\n      inputParameters:\n      - name: eventId\n        type: string\n        description: eventId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrun\n      description: Get function run status\n      hints:\n        readOnly: true\n        destructive: false\n  \
  \      idempotent: true\n      call: inngest.getrun\n      with:\n        runId: tools.runId\n      inputParameters:\n      - name: runId\n        type: string\n        description: runId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrunjobs\n      description: List the jobs (steps) for a run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: inngest.listrunjobs\n      with:\n        runId: tools.runId\n      inputParameters:\n      - name: runId\n        type: string\n        description: runId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelrun\n      description: Cancel a function run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: inngest.cancelrun\n      with:\n        runId: tools.runId\n      inputParameters:\n      - name: runId\n        type:\
  \ string\n        description: runId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfunctions\n      description: List functions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: inngest.listfunctions\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INNGEST_TOKEN: INNGEST_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/inngest/refs/heads/main/capabilities/inngest-capability.yaml
tags:
- Inngest
- API
tools:
- description: Send event(s) to Inngest
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendevents
- description: List recent events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: Get an event by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevent
- description: List runs triggered by an event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventruns
- description: Get function run status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrun
- description: List the jobs (steps) for a run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrunjobs
- description: Cancel a function run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelrun
- description: List functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfunctions
---
