---
categories:
- collaboration
consumed_apis: []
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
- courses
- video training
- get commits
- pull request data, comments, and events across repositories
- ticket data from connected project management tools
- commit data and aggregated metrics across repositories
- developer productivity
- skills assessment
- get coding metrics
- get dora metrics
- collaboration
- learning
- retrieve pull request data, comments, and events across repositories.
- engineering metrics
- pull request and collaboration metrics for engineering teams
- retrieve collaboration metrics for engineering teams
- retrieve pull request data and events
- get tickets
- technology
- dora
- retrieve ticket data including comments, events, and project associations from connected project management tools.
- retrieve code-level engineering metrics
- code-level engineering metrics and developer productivity data
- dora engineering metrics including deployment frequency and lead time
- education
- retrieve pull request and collaboration metrics for engineering teams with date range filtering.
- retrieve commit data and aggregated commit metrics across repositories.
- retrieve commit data and metrics
- flow
- retrieve ticket data and events
- retrieve dora engineering metrics
- get pull requests
- retrieve dora engineering metrics including deployment frequency, lead time for changes, change failure rate, and time to restore service.
- pluralsight
- get collaboration metrics
- retrieve code-level engineering metrics and developer productivity data with date range filtering.
slug: engineering-metrics
source_filename: engineering-metrics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pluralsight Engineering Metrics\n  description: Unified workflow for engineering managers to track developer productivity, code quality, collaboration, and\n    delivery performance through Flow metrics. Combines coding metrics, collaboration metrics, DORA metrics, commits, pull\n    requests, and tickets APIs.\n  tags:\n  - Pluralsight\n  - Flow\n  - Engineering Metrics\n  - Developer Productivity\n  - DORA\n  - Collaboration\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PLURALSIGHT_FLOW_BEARER_TOKEN: PLURALSIGHT_FLOW_BEARER_TOKEN\n    PLURALSIGHT_FLOW_WORKSPACE: PLURALSIGHT_FLOW_WORKSPACE\ncapability:\n  consumes:\n  - type: http\n    namespace: pluralsight-flow-coding-metrics\n    baseUri: https://flow-api.pluralsight.com\n    description: REST API for accessing code-level engineering metrics and developer productivity data.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n\
  \    resources:\n    - name: coding-metrics\n      path: /collaboration/code/metrics\n      description: Code-level engineering metrics\n      operations:\n      - name: get-coding-metrics\n        method: GET\n        description: Retrieve code-level engineering metrics and developer productivity data with date range filtering.\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date for the metrics period\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date for the metrics period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pluralsight-flow-collaboration-metrics\n    baseUri: https://api.appfireflow.com\n    description: REST API for accessing pull request and collaboration metrics for engineering\
  \ teams.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n    resources:\n    - name: collaboration-metrics\n      path: /collaboration/pullrequest/metrics\n      description: Pull request and collaboration metrics\n      operations:\n      - name: get-collaboration-metrics\n        method: GET\n        description: Retrieve pull request and collaboration metrics for engineering teams with date range filtering.\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date for the metrics period\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date for the metrics period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pluralsight-flow-dora-metrics\n    baseUri: https://flow-api.pluralsight.com\n\
  \    description: REST API for accessing DORA engineering metrics including deployment frequency, lead time for changes, change\n      failure rate, and time to restore service.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n    resources:\n    - name: dora-metrics\n      path: /dora/build-release\n      description: DORA engineering metrics\n      operations:\n      - name: get-dora-metrics\n        method: GET\n        description: Retrieve DORA engineering metrics including deployment frequency, lead time for changes, change failure\n          rate, and time to restore service.\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date for the metrics period\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date for the metrics period\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pluralsight-flow-commits\n    baseUri: https://{{PLURALSIGHT_FLOW_WORKSPACE}}.appfireflow.com/v3/customer/core\n    description: REST API for accessing commit data and aggregated commit metrics across repositories.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n    resources:\n    - name: commits\n      path: /commits\n      description: Commit data and metrics\n      operations:\n      - name: get-commits\n        method: GET\n        description: Retrieve commit data and aggregated commit metrics across repositories.\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date for the query period\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description:\
  \ End date for the query period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pluralsight-flow-pull-requests\n    baseUri: https://{{PLURALSIGHT_FLOW_WORKSPACE}}.appfireflow.com/v3/customer/core\n    description: REST API for accessing pull request data, comments, and events across repositories.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n    resources:\n    - name: pull-requests\n      path: /pull-requests\n      description: Pull request data and events\n      operations:\n      - name: get-pull-requests\n        method: GET\n        description: Retrieve pull request data, comments, and events across repositories.\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date for the query period\n        - name: end_date\n    \
  \      in: query\n          type: string\n          required: false\n          description: End date for the query period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pluralsight-flow-tickets\n    baseUri: https://{{PLURALSIGHT_FLOW_WORKSPACE}}.appfireflow.com/v3/customer/core\n    description: REST API for accessing ticket data including comments, events, and project associations from connected project\n      management tools.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n    resources:\n    - name: tickets\n      path: /tickets\n      description: Ticket data and events\n      operations:\n      - name: get-tickets\n        method: GET\n        description: Retrieve ticket data including comments, events, and project associations from connected project management\n          tools.\n        inputParameters:\n        - name: start_date\n\
  \          in: query\n          type: string\n          required: false\n          description: Start date for the query period\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date for the query period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: engineering-metrics-api\n    description: Unified REST API for Pluralsight Flow engineering metrics including coding, collaboration, DORA, commits,\n      pull requests, and tickets.\n    resources:\n    - path: /v1/coding-metrics\n      name: coding-metrics\n      description: Code-level engineering metrics and developer productivity data\n      operations:\n      - method: GET\n        name: get-coding-metrics\n        description: Retrieve code-level engineering metrics\n        call: pluralsight-flow-coding-metrics.get-coding-metrics\n\
  \        with:\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/collaboration-metrics\n      name: collaboration-metrics\n      description: Pull request and collaboration metrics for engineering teams\n      operations:\n      - method: GET\n        name: get-collaboration-metrics\n        description: Retrieve collaboration metrics for engineering teams\n        call: pluralsight-flow-collaboration-metrics.get-collaboration-metrics\n        with:\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dora-metrics\n      name: dora-metrics\n      description: DORA engineering metrics including deployment frequency and lead time\n      operations:\n      - method: GET\n        name: get-dora-metrics\n        description: Retrieve DORA engineering metrics\n       \
  \ call: pluralsight-flow-dora-metrics.get-dora-metrics\n        with:\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commits\n      name: commits\n      description: Commit data and aggregated metrics across repositories\n      operations:\n      - method: GET\n        name: get-commits\n        description: Retrieve commit data and metrics\n        call: pluralsight-flow-commits.get-commits\n        with:\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pull-requests\n      name: pull-requests\n      description: Pull request data, comments, and events across repositories\n      operations:\n      - method: GET\n        name: get-pull-requests\n        description: Retrieve pull request data and events\n        call: pluralsight-flow-pull-requests.get-pull-requests\n\
  \        with:\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tickets\n      name: tickets\n      description: Ticket data from connected project management tools\n      operations:\n      - method: GET\n        name: get-tickets\n        description: Retrieve ticket data and events\n        call: pluralsight-flow-tickets.get-tickets\n        with:\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: engineering-metrics-mcp\n    transport: http\n    description: MCP server for AI-assisted engineering metrics analysis across coding, collaboration, DORA, and delivery\n      data.\n    tools:\n    - name: get-coding-metrics\n      description: Retrieve code-level engineering metrics and developer productivity data with date range filtering.\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-flow-coding-metrics.get-coding-metrics\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-collaboration-metrics\n      description: Retrieve pull request and collaboration metrics for engineering teams with date range filtering.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-flow-collaboration-metrics.get-collaboration-metrics\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dora-metrics\n      description: Retrieve DORA engineering metrics including deployment frequency, lead time for changes, change failure\n      \
  \  rate, and time to restore service.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-flow-dora-metrics.get-dora-metrics\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commits\n      description: Retrieve commit data and aggregated commit metrics across repositories.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-flow-commits.get-commits\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pull-requests\n      description: Retrieve pull request data, comments, and events across repositories.\n      hints:\n        readOnly: true\n        destructive: false\n      \
  \  idempotent: true\n        openWorld: true\n      call: pluralsight-flow-pull-requests.get-pull-requests\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tickets\n      description: Retrieve ticket data including comments, events, and project associations from connected project management\n        tools.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-flow-tickets.get-tickets\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
