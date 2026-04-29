---
categories:
- collaboration
consumed_apis:
- pluralsight-flow-coding-metrics
- pluralsight-flow-collaboration-metrics
- pluralsight-flow-dora-metrics
- pluralsight-flow-commits
- pluralsight-flow-pull-requests
- pluralsight-flow-tickets
description: Unified workflow for engineering managers to track developer productivity, code quality, collaboration, and delivery performance through Flow metrics. Combines coding metrics, collaboration metrics, DORA metrics, commits, pull requests, and tickets APIs.
layout: capability
name: Pluralsight Engineering Metrics
operations:
- description: Retrieve code-level engineering metrics
  method: GET
  name: get-coding-metrics
  path: /v1/coding-metrics
- description: Retrieve collaboration metrics for engineering teams
  method: GET
  name: get-collaboration-metrics
  path: /v1/collaboration-metrics
- description: Retrieve DORA engineering metrics
  method: GET
  name: get-dora-metrics
  path: /v1/dora-metrics
- description: Retrieve commit data and metrics
  method: GET
  name: get-commits
  path: /v1/commits
- description: Retrieve pull request data and events
  method: GET
  name: get-pull-requests
  path: /v1/pull-requests
- description: Retrieve ticket data and events
  method: GET
  name: get-tickets
  path: /v1/tickets
personas: []
provider_name: Pluralsight
provider_slug: pluralsight
search_terms:
- retrieve code-level engineering metrics and developer productivity data with date range filtering.
- retrieve pull request and collaboration metrics for engineering teams with date range filtering.
- retrieve commit data and aggregated commit metrics across repositories.
- get collaboration metrics
- get pull requests
- code-level engineering metrics and developer productivity data
- retrieve commit data and metrics
- retrieve pull request data and events
- get dora metrics
- collaboration
- education
- get coding metrics
- retrieve dora engineering metrics including deployment frequency, lead time for changes, change failure rate, and time to restore service.
- retrieve ticket data and events
- pluralsight
- courses
- flow
- developer productivity
- technology
- pull request and collaboration metrics for engineering teams
- video training
- get tickets
- commit data and aggregated metrics across repositories
- retrieve ticket data including comments, events, and project associations from connected project management tools.
- get commits
- pull request data, comments, and events across repositories
- ticket data from connected project management tools
- learning
- retrieve collaboration metrics for engineering teams
- engineering metrics
- dora
- retrieve code-level engineering metrics
- skills assessment
- retrieve dora engineering metrics
- retrieve pull request data, comments, and events across repositories.
- dora engineering metrics including deployment frequency and lead time
slug: engineering-metrics
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Pluralsight Engineering Metrics\"\n  description: \"Unified workflow for engineering managers to track developer productivity, code quality, collaboration, and delivery performance through Flow metrics. Combines coding metrics, collaboration metrics, DORA metrics, commits, pull requests, and tickets APIs.\"\n  tags:\n    - Pluralsight\n    - Flow\n    - Engineering Metrics\n    - Developer Productivity\n    - DORA\n    - Collaboration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PLURALSIGHT_FLOW_BEARER_TOKEN: PLURALSIGHT_FLOW_BEARER_TOKEN\n      PLURALSIGHT_FLOW_WORKSPACE: PLURALSIGHT_FLOW_WORKSPACE\n\ncapability:\n  consumes:\n    - import: pluralsight-flow-coding-metrics\n      location: ./shared/flow-coding-metrics.yaml\n    - import: pluralsight-flow-collaboration-metrics\n      location: ./shared/flow-collaboration-metrics.yaml\n    - import: pluralsight-flow-dora-metrics\n\
  \      location: ./shared/flow-dora-metrics.yaml\n    - import: pluralsight-flow-commits\n      location: ./shared/flow-commits.yaml\n    - import: pluralsight-flow-pull-requests\n      location: ./shared/flow-pull-requests.yaml\n    - import: pluralsight-flow-tickets\n      location: ./shared/flow-tickets.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: engineering-metrics-api\n      description: \"Unified REST API for Pluralsight Flow engineering metrics including coding, collaboration, DORA, commits, pull requests, and tickets.\"\n      resources:\n        - path: /v1/coding-metrics\n          name: coding-metrics\n          description: \"Code-level engineering metrics and developer productivity data\"\n          operations:\n            - method: GET\n              name: get-coding-metrics\n              description: \"Retrieve code-level engineering metrics\"\n              call: \"pluralsight-flow-coding-metrics.get-coding-metrics\"\n              with:\n\
  \                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/collaboration-metrics\n          name: collaboration-metrics\n          description: \"Pull request and collaboration metrics for engineering teams\"\n          operations:\n            - method: GET\n              name: get-collaboration-metrics\n              description: \"Retrieve collaboration metrics for engineering teams\"\n              call: \"pluralsight-flow-collaboration-metrics.get-collaboration-metrics\"\n              with:\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dora-metrics\n          name: dora-metrics\n          description: \"DORA engineering metrics including deployment frequency and\
  \ lead time\"\n          operations:\n            - method: GET\n              name: get-dora-metrics\n              description: \"Retrieve DORA engineering metrics\"\n              call: \"pluralsight-flow-dora-metrics.get-dora-metrics\"\n              with:\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/commits\n          name: commits\n          description: \"Commit data and aggregated metrics across repositories\"\n          operations:\n            - method: GET\n              name: get-commits\n              description: \"Retrieve commit data and metrics\"\n              call: \"pluralsight-flow-commits.get-commits\"\n              with:\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                \
  \  mapping: \"$.\"\n        - path: /v1/pull-requests\n          name: pull-requests\n          description: \"Pull request data, comments, and events across repositories\"\n          operations:\n            - method: GET\n              name: get-pull-requests\n              description: \"Retrieve pull request data and events\"\n              call: \"pluralsight-flow-pull-requests.get-pull-requests\"\n              with:\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tickets\n          name: tickets\n          description: \"Ticket data from connected project management tools\"\n          operations:\n            - method: GET\n              name: get-tickets\n              description: \"Retrieve ticket data and events\"\n              call: \"pluralsight-flow-tickets.get-tickets\"\n              with:\n             \
  \   start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: engineering-metrics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted engineering metrics analysis across coding, collaboration, DORA, and delivery data.\"\n      tools:\n        - name: get-coding-metrics\n          description: \"Retrieve code-level engineering metrics and developer productivity data with date range filtering.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-coding-metrics.get-coding-metrics\"\n          with:\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: get-collaboration-metrics\n          description: \"Retrieve pull request and collaboration metrics for engineering teams with date range filtering.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-collaboration-metrics.get-collaboration-metrics\"\n          with:\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dora-metrics\n          description: \"Retrieve DORA engineering metrics including deployment frequency, lead time for changes, change failure rate, and time to restore service.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-dora-metrics.get-dora-metrics\"\n         \
  \ with:\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-commits\n          description: \"Retrieve commit data and aggregated commit metrics across repositories.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-commits.get-commits\"\n          with:\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pull-requests\n          description: \"Retrieve pull request data, comments, and events across repositories.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-pull-requests.get-pull-requests\"\
  \n          with:\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-tickets\n          description: \"Retrieve ticket data including comments, events, and project associations from connected project management tools.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-tickets.get-tickets\"\n          with:\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/capabilities/engineering-metrics.yaml
tags:
- Pluralsight
- Flow
- Engineering Metrics
- Developer Productivity
- DORA
- Collaboration
tools:
- description: Retrieve code-level engineering metrics and developer productivity data with date range filtering.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-coding-metrics
- description: Retrieve pull request and collaboration metrics for engineering teams with date range filtering.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-collaboration-metrics
- description: Retrieve DORA engineering metrics including deployment frequency, lead time for changes, change failure rate, and time to restore service.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-dora-metrics
- description: Retrieve commit data and aggregated commit metrics across repositories.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-commits
- description: Retrieve pull request data, comments, and events across repositories.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-pull-requests
- description: Retrieve ticket data including comments, events, and project associations from connected project management tools.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-tickets
---
