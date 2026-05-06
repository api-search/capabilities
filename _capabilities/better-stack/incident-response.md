---
categories:
- incident-management
consumed_apis: []
description: Unified incident response workflow combining Better Stack uptime monitoring, heartbeat monitoring, and incident management. Used by SRE teams and on-call engineers to detect, acknowledge, and resolve infrastructure incidents.
layout: capability
name: Better Stack Incident Response
operations:
- description: List all uptime monitors
  method: GET
  name: list-monitors
  path: /v1/monitors
- description: Create a new uptime monitor
  method: POST
  name: create-monitor
  path: /v1/monitors
- description: Get monitor details
  method: GET
  name: get-monitor
  path: /v1/monitors/{id}
- description: Update a monitor
  method: PATCH
  name: update-monitor
  path: /v1/monitors/{id}
- description: Delete a monitor
  method: DELETE
  name: delete-monitor
  path: /v1/monitors/{id}
- description: Get monitor availability summary
  method: GET
  name: get-monitor-availability
  path: /v1/monitors/{id}/availability
- description: List all heartbeats
  method: GET
  name: list-heartbeats
  path: /v1/heartbeats
- description: Create a heartbeat monitor
  method: POST
  name: create-heartbeat
  path: /v1/heartbeats
- description: List all incidents
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: Create a manual incident
  method: POST
  name: create-incident
  path: /v1/incidents
- description: Get incident details
  method: GET
  name: get-incident
  path: /v1/incidents/{id}
- description: Delete an incident
  method: DELETE
  name: delete-incident
  path: /v1/incidents/{id}
- description: Acknowledge an active incident
  method: POST
  name: acknowledge-incident
  path: /v1/incidents/{id}/acknowledge
- description: Resolve an active incident
  method: POST
  name: resolve-incident
  path: /v1/incidents/{id}/resolve
personas:
- description: Site Reliability Engineer managing infrastructure uptime and incident response
  id: sre-engineer
  name: SRE Engineer
- description: Engineer on-call rotation responsible for responding to incidents
  id: on-call-engineer
  name: On-Call Engineer
provider_name: Better Stack
provider_slug: better-stack
search_terms:
- on-call
- single monitor operations
- incidents
- list heartbeats
- delete a monitor
- create a manual incident
- list all heartbeat monitors for scheduled jobs
- acknowledge incident
- resolve an active incident
- list all incidents
- get details for a specific incident
- get monitor details
- heartbeat monitor management
- get monitor availability
- detection, acknowledgement, and resolution of service incidents
- uptime
- create a new uptime monitor for a url or api
- list incidents with optional date and filter parameters
- get availability metrics for a monitor
- create incident
- list all uptime monitors
- acknowledge an active incident
- logs
- monitoring
- delete monitor
- acknowledge an active incident to indicate someone is working on it
- resolve incident
- get availability for a heartbeat monitor
- communicating service health to customers and stakeholders
- create a new uptime monitor
- get heartbeat availability
- on call engineer
- create monitor
- list all heartbeats
- get monitor availability summary
- create a heartbeat monitor
- delete incident
- resolve an incident
- engineer on-call rotation responsible for responding to incidents
- resolve an active incident once the issue is fixed
- delete an incident
- acknowledge an incident
- observability
- heartbeats
- monitor management for uptime checks
- status
- get incident details
- monitor availability metrics
- better stack
- get details for a specific uptime monitor
- list all uptime monitors to check what is being monitored
- site reliability engineer managing infrastructure uptime and incident response
- create heartbeat
- managing team access and membership
- update a monitor
- platform
- get incident
- list incidents
- incident response
- monitor detection, incident acknowledgement, and resolution workflow for sre teams
- sre
- uptime and availability monitoring for services and scheduled jobs
- update monitor
- incident management
- sre engineer
- get monitor
- list monitors
- single incident operations
slug: incident-response
source_filename: incident-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Better Stack Incident Response\n  description: Unified incident response workflow combining Better Stack uptime monitoring, heartbeat monitoring, and incident\n    management. Used by SRE teams and on-call engineers to detect, acknowledge, and resolve infrastructure incidents.\n  tags:\n  - Better Stack\n  - Incident Response\n  - Monitoring\n  - On-Call\n  - Sre\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BETTER_STACK_API_TOKEN: BETTER_STACK_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: better-stack\n    baseUri: https://uptime.betterstack.com/api/v2\n    description: Better Stack uptime monitoring and incident management API\n    authentication:\n      type: bearer\n      token: '{{BETTER_STACK_API_TOKEN}}'\n    resources:\n    - name: monitors\n      path: /monitors\n      description: Uptime monitors for URLs, APIs, and services\n      operations:\n      - name: list-monitors\n\
  \        method: GET\n        description: List all uptime monitors\n        inputParameters:\n        - name: team_name\n          in: query\n          type: string\n          required: false\n          description: Filter by team name\n        - name: url\n          in: query\n          type: string\n          required: false\n          description: Filter by monitored URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-monitor\n        method: POST\n        description: Create a new uptime monitor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            pronounceable_name: '{{tools.pronounceable_name}}'\n            monitor_type: '{{tools.monitor_type}}'\n            check_frequency: '{{tools.check_frequency}}'\n  \
  \    - name: get-monitor\n        method: GET\n        description: Get a single monitor by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Monitor ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-monitor\n        method: PATCH\n        description: Update an existing monitor\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Monitor ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            pronounceable_name: '{{tools.pronounceable_name}}'\n            check_frequency: '{{tools.check_frequency}}'\n      - name: delete-monitor\n        method: DELETE\n        description:\
  \ Delete an existing monitor\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Monitor ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-monitor-response-times\n        method: GET\n        description: Get response time metrics for a monitor\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Monitor ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-monitor-availability\n        method: GET\n        description: Get availability summary for a monitor\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Monitor ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: heartbeats\n      path: /heartbeats\n      description: Heartbeat monitors for scheduled jobs and cron tasks\n      operations:\n      - name: list-heartbeats\n        method: GET\n        description: List all heartbeat monitors\n        inputParameters:\n        - name: team_name\n          in: query\n          type: string\n          required: false\n          description: Filter by team name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-heartbeat\n        method: POST\n        description: Create a new heartbeat monitor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            period: '{{tools.period}}'\n\
  \            grace: '{{tools.grace}}'\n      - name: get-heartbeat\n        method: GET\n        description: Get a single heartbeat by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Heartbeat ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-heartbeat\n        method: PATCH\n        description: Update an existing heartbeat\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Heartbeat ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            grace: '{{tools.grace}}'\n      - name: delete-heartbeat\n        method: DELETE\n        description:\
  \ Delete a heartbeat monitor\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Heartbeat ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-heartbeat-availability\n        method: GET\n        description: Get availability for a heartbeat\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Heartbeat ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incidents\n      path: /incidents\n      description: Incident management and alerting\n      operations:\n      - name: list-incidents\n        method: GET\n        description: List all incidents with optional filters\n        inputParameters:\n        - name: from\n          in:\
  \ query\n          type: string\n          required: false\n          description: Start date filter\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        - name: monitor_id\n          in: query\n          type: integer\n          required: false\n          description: Filter by monitor ID\n        - name: resolved\n          in: query\n          type: boolean\n          required: false\n          description: Filter by resolved status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-incident\n        method: POST\n        description: Create a manual incident\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: get-incident\n\
  \        method: GET\n        description: Get a single incident by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Incident ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: acknowledge-incident\n        method: POST\n        description: Acknowledge an active incident\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Incident ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resolve-incident\n        method: POST\n        description: Resolve an active incident\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Incident ID\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-incident\n        method: DELETE\n        description: Delete an incident\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Incident ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status-pages\n      path: /status-pages\n      description: Public and private status pages\n      operations:\n      - name: list-status-pages\n        method: GET\n        description: List all status pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-status-page\n        method: POST\n        description: Create a new status page\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            company_name: '{{tools.company_name}}'\n            subdomain: '{{tools.subdomain}}'\n      - name: get-status-page\n        method: GET\n        description: Get a single status page\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Status page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-status-page\n        method: PATCH\n        description: Update a status page\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Status page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            company_name: '{{tools.company_name}}'\n      - name: delete-status-page\n        method: DELETE\n        description: Delete a status page\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Status page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /policies\n      description: Escalation policies for on-call alerting\n      operations:\n      - name: list-escalation-policies\n        method: GET\n        description: List all escalation policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-escalation-policy\n        method: POST\n        description: Create a new escalation policy\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            repeat_count: '{{tools.repeat_count}}'\n      - name: get-escalation-policy\n        method: GET\n        description: Get a single escalation policy\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Policy ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-escalation-policy\n        method: PATCH\n        description: Update an escalation policy\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Policy ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-escalation-policy\n        method: DELETE\n        description: Delete an escalation policy\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Policy ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-members\n      path: /team-members\n      description: Team member management and invitations\n      operations:\n      - name: list-team-members\n        method: GET\n        description: List all team members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invite-team-member\n        method: POST\n        description: Invite a new team member\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            role: '{{tools.role}}'\n      - name: get-team-member\n        method: GET\n        description: Get a single team member\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Team member ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-team-member\n        method: DELETE\n        description: Remove a team member\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Team member ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ better-stack-incident-response-api\n    description: Unified REST API for Better Stack incident response workflows.\n    resources:\n    - path: /v1/monitors\n      name: monitors\n      description: Monitor management for uptime checks\n      operations:\n      - method: GET\n        name: list-monitors\n        description: List all uptime monitors\n        call: better-stack.list-monitors\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-monitor\n        description: Create a new uptime monitor\n        call: better-stack.create-monitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors/{id}\n      name: monitor\n      description: Single monitor operations\n      operations:\n      - method: GET\n        name: get-monitor\n        description: Get monitor details\n        call: better-stack.get-monitor\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-monitor\n        description: Update a monitor\n        call: better-stack.update-monitor\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-monitor\n        description: Delete a monitor\n        call: better-stack.delete-monitor\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors/{id}/availability\n      name: monitor-availability\n      description: Monitor availability metrics\n      operations:\n      - method: GET\n        name: get-monitor-availability\n        description: Get monitor availability summary\n        call: better-stack.get-monitor-availability\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/heartbeats\n \
  \     name: heartbeats\n      description: Heartbeat monitor management\n      operations:\n      - method: GET\n        name: list-heartbeats\n        description: List all heartbeats\n        call: better-stack.list-heartbeats\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-heartbeat\n        description: Create a heartbeat monitor\n        call: better-stack.create-heartbeat\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/incidents\n      name: incidents\n      description: Incident management\n      operations:\n      - method: GET\n        name: list-incidents\n        description: List all incidents\n        call: better-stack.list-incidents\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-incident\n        description: Create a manual incident\n        call: better-stack.create-incident\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/incidents/{id}\n      name: incident\n      description: Single incident operations\n      operations:\n      - method: GET\n        name: get-incident\n        description: Get incident details\n        call: better-stack.get-incident\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-incident\n        description: Delete an incident\n        call: better-stack.delete-incident\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/incidents/{id}/acknowledge\n      name: incident-acknowledge\n      description: Acknowledge an incident\n      operations:\n      - method: POST\n        name: acknowledge-incident\n        description: Acknowledge an active incident\n        call: better-stack.acknowledge-incident\n        with:\n          id: rest.id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/incidents/{id}/resolve\n      name: incident-resolve\n      description: Resolve an incident\n      operations:\n      - method: POST\n        name: resolve-incident\n        description: Resolve an active incident\n        call: better-stack.resolve-incident\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: better-stack-incident-response-mcp\n    transport: http\n    description: MCP server for AI-assisted Better Stack incident response.\n    tools:\n    - name: list-monitors\n      description: List all uptime monitors to check what is being monitored\n      hints:\n        readOnly: true\n        openWorld: true\n      call: better-stack.list-monitors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-monitor\n      description: Create a new uptime monitor\
  \ for a URL or API\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: better-stack.create-monitor\n      with:\n        url: tools.url\n        pronounceable_name: tools.pronounceable_name\n        check_frequency: tools.check_frequency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-monitor\n      description: Get details for a specific uptime monitor\n      hints:\n        readOnly: true\n        openWorld: false\n      call: better-stack.get-monitor\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-monitor-availability\n      description: Get availability metrics for a monitor\n      hints:\n        readOnly: true\n        openWorld: false\n      call: better-stack.get-monitor-availability\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-heartbeats\n \
  \     description: List all heartbeat monitors for scheduled jobs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: better-stack.list-heartbeats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-heartbeat-availability\n      description: Get availability for a heartbeat monitor\n      hints:\n        readOnly: true\n        openWorld: false\n      call: better-stack.get-heartbeat-availability\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-incidents\n      description: List incidents with optional date and filter parameters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: better-stack.list-incidents\n      with:\n        from: tools.from\n        to: tools.to\n        resolved: tools.resolved\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-incident\n      description: Get details for a specific\
  \ incident\n      hints:\n        readOnly: true\n        openWorld: false\n      call: better-stack.get-incident\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-incident\n      description: Create a manual incident\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: better-stack.create-incident\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acknowledge-incident\n      description: Acknowledge an active incident to indicate someone is working on it\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: better-stack.acknowledge-incident\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resolve-incident\n      description: Resolve an active incident once the issue is fixed\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: better-stack.resolve-incident\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/better-stack/refs/heads/main/capabilities/incident-response.yaml
tags:
- Better Stack
- Incident Response
- Monitoring
- On-Call
- Sre
tools:
- description: List all uptime monitors to check what is being monitored
  hints:
    openWorld: true
    readOnly: true
  name: list-monitors
- description: Create a new uptime monitor for a URL or API
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-monitor
- description: Get details for a specific uptime monitor
  hints:
    openWorld: false
    readOnly: true
  name: get-monitor
- description: Get availability metrics for a monitor
  hints:
    openWorld: false
    readOnly: true
  name: get-monitor-availability
- description: List all heartbeat monitors for scheduled jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-heartbeats
- description: Get availability for a heartbeat monitor
  hints:
    openWorld: false
    readOnly: true
  name: get-heartbeat-availability
- description: List incidents with optional date and filter parameters
  hints:
    openWorld: true
    readOnly: true
  name: list-incidents
- description: Get details for a specific incident
  hints:
    openWorld: false
    readOnly: true
  name: get-incident
- description: Create a manual incident
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-incident
- description: Acknowledge an active incident to indicate someone is working on it
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: acknowledge-incident
- description: Resolve an active incident once the issue is fixed
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resolve-incident
---
