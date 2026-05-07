---
categories: []
consumed_apis: []
description: The Operations Suite API provides a unified interface for managing observability across Google Cloud services. This specification covers the core monitoring and logging capabilities including time series metrics, alert policies, log entries, dashboards, and service monitoring that form the foundation of the Operations Suite.
layout: capability
name: Google Cloud Operations Suite API
operations:
- description: Google Cloud Operations Suite List Time Series
  method: GET
  name: listtimeseries
  path: /v3/projects/{projectId}/timeSeries
- description: Google Cloud Operations Suite Create Time Series
  method: POST
  name: createtimeseries
  path: /v3/projects/{projectId}/timeSeries
- description: Google Cloud Operations Suite List Alert Policies
  method: GET
  name: listalertpolicies
  path: /v3/projects/{projectId}/alertPolicies
- description: Google Cloud Operations Suite Create Alert Policy
  method: POST
  name: createalertpolicy
  path: /v3/projects/{projectId}/alertPolicies
- description: Google Cloud Operations Suite List Log Entries
  method: POST
  name: listlogentries
  path: /v2/entries:list
- description: Google Cloud Operations Suite Write Log Entries
  method: POST
  name: writelogentries
  path: /v2/entries:write
- description: Google Cloud Operations Suite List Dashboards
  method: GET
  name: listdashboards
  path: /v1/projects/{projectId}/dashboards
- description: Google Cloud Operations Suite Create Dashboard
  method: POST
  name: createdashboard
  path: /v1/projects/{projectId}/dashboards
- description: Google Cloud Operations Suite List Uptime Check Configs
  method: GET
  name: listuptimecheckconfigs
  path: /v3/projects/{projectId}/uptimeCheckConfigs
personas: []
provider_name: Google Cloud Operations Suite
provider_slug: google-cloud-operations-suite
search_terms:
- google cloud operations suite list alert policies
- operations
- google cloud operations suite list dashboards
- google cloud operations suite create alert policy
- api
- writelogentries
- monitoring
- google
- observability
- google cloud operations suite write log entries
- google cloud operations suite list log entries
- listalertpolicies
- stackdriver
- google cloud operations suite list uptime check configs
- cloud
- google cloud operations suite create dashboard
- google cloud operations suite create time series
- tracing
- listtimeseries
- listdashboards
- suite
- google cloud operations suite list time series
- listlogentries
- listuptimecheckconfigs
- profiling
- createdashboard
- google cloud
- createalertpolicy
- error reporting
- createtimeseries
- logging
slug: google-cloud-operations-suite-capability
source_filename: google-cloud-operations-suite-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Operations Suite API\n  description: The Operations Suite API provides a unified interface for managing observability across Google Cloud services.\n    This specification covers the core monitoring and logging capabilities including time series metrics, alert policies,\n    log entries, dashboards, and service monitoring that form the foundation of the Operations Suite.\n  tags:\n  - Google\n  - Cloud\n  - Operations\n  - Suite\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-operations-suite\n    baseUri: https://monitoring.googleapis.com\n    description: Google Cloud Operations Suite API HTTP API.\n    resources:\n    - name: v3-projects-projectid-timeseries\n      path: /v3/projects/{projectId}/timeSeries\n      operations:\n      - name: listtimeseries\n        method: GET\n        description: Google Cloud Operations Suite List Time Series\n\
  \        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n        - name: interval.startTime\n          in: query\n          type: string\n        - name: interval.endTime\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtimeseries\n        method: POST\n        description: Google Cloud Operations Suite Create Time Series\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-projects-projectid-alertpolicies\n      path: /v3/projects/{projectId}/alertPolicies\n      operations:\n      - name: listalertpolicies\n\
  \        method: GET\n        description: Google Cloud Operations Suite List Alert Policies\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createalertpolicy\n        method: POST\n        description: Google Cloud Operations Suite Create Alert Policy\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-entries-list\n      path: /v2/entries:list\n      operations:\n      - name: listlogentries\n        method: POST\n        description: Google Cloud Operations Suite List Log Entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: v2-entries-write\n      path: /v2/entries:write\n      operations:\n      - name: writelogentries\n        method: POST\n        description: Google Cloud Operations Suite Write Log Entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-dashboards\n      path: /v1/projects/{projectId}/dashboards\n      operations:\n      - name: listdashboards\n        method: GET\n        description: Google Cloud Operations Suite List Dashboards\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdashboard\n        method: POST\n        description: Google Cloud Operations Suite Create Dashboard\n        inputParameters:\n\
  \        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-projects-projectid-uptimecheckconfigs\n      path: /v3/projects/{projectId}/uptimeCheckConfigs\n      operations:\n      - name: listuptimecheckconfigs\n        method: GET\n        description: Google Cloud Operations Suite List Uptime Check Configs\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-operations-suite-rest\n    description: REST adapter for Google Cloud Operations Suite API.\n    resources:\n    - path: /v3/projects/{projectId}/timeSeries\n      name: listtimeseries\n\
  \      operations:\n      - method: GET\n        name: listtimeseries\n        description: Google Cloud Operations Suite List Time Series\n        call: google-cloud-operations-suite.listtimeseries\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/timeSeries\n      name: createtimeseries\n      operations:\n      - method: POST\n        name: createtimeseries\n        description: Google Cloud Operations Suite Create Time Series\n        call: google-cloud-operations-suite.createtimeseries\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/alertPolicies\n      name: listalertpolicies\n      operations:\n      - method: GET\n        name: listalertpolicies\n        description: Google Cloud Operations Suite List Alert Policies\n        call: google-cloud-operations-suite.listalertpolicies\n\
  \        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/alertPolicies\n      name: createalertpolicy\n      operations:\n      - method: POST\n        name: createalertpolicy\n        description: Google Cloud Operations Suite Create Alert Policy\n        call: google-cloud-operations-suite.createalertpolicy\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/entries:list\n      name: listlogentries\n      operations:\n      - method: POST\n        name: listlogentries\n        description: Google Cloud Operations Suite List Log Entries\n        call: google-cloud-operations-suite.listlogentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/entries:write\n      name: writelogentries\n      operations:\n      - method: POST\n        name: writelogentries\n\
  \        description: Google Cloud Operations Suite Write Log Entries\n        call: google-cloud-operations-suite.writelogentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/dashboards\n      name: listdashboards\n      operations:\n      - method: GET\n        name: listdashboards\n        description: Google Cloud Operations Suite List Dashboards\n        call: google-cloud-operations-suite.listdashboards\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/dashboards\n      name: createdashboard\n      operations:\n      - method: POST\n        name: createdashboard\n        description: Google Cloud Operations Suite Create Dashboard\n        call: google-cloud-operations-suite.createdashboard\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n    - path: /v3/projects/{projectId}/uptimeCheckConfigs\n      name: listuptimecheckconfigs\n      operations:\n      - method: GET\n        name: listuptimecheckconfigs\n        description: Google Cloud Operations Suite List Uptime Check Configs\n        call: google-cloud-operations-suite.listuptimecheckconfigs\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-operations-suite-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Operations Suite API for AI agent use.\n    tools:\n    - name: listtimeseries\n      description: Google Cloud Operations Suite List Time Series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-operations-suite.listtimeseries\n      with:\n        projectId: tools.projectId\n        filter: tools.filter\n        interval.startTime:\
  \ tools.interval.startTime\n        interval.endTime: tools.interval.endTime\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: filter\n        type: string\n        description: filter\n      - name: interval.startTime\n        type: string\n        description: interval.startTime\n      - name: interval.endTime\n        type: string\n        description: interval.endTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtimeseries\n      description: Google Cloud Operations Suite Create Time Series\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-operations-suite.createtimeseries\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: listalertpolicies\n      description: Google Cloud Operations Suite List Alert Policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-operations-suite.listalertpolicies\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createalertpolicy\n      description: Google Cloud Operations Suite Create Alert Policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-operations-suite.createalertpolicy\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: listlogentries\n      description: Google Cloud Operations Suite List Log Entries\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-operations-suite.listlogentries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: writelogentries\n      description: Google Cloud Operations Suite Write Log Entries\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-operations-suite.writelogentries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdashboards\n      description: Google Cloud Operations Suite List Dashboards\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-operations-suite.listdashboards\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n\
  \        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdashboard\n      description: Google Cloud Operations Suite Create Dashboard\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-operations-suite.createdashboard\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listuptimecheckconfigs\n      description: Google Cloud Operations Suite List Uptime Check Configs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-operations-suite.listuptimecheckconfigs\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n\
  \        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-operations-suite/refs/heads/main/capabilities/google-cloud-operations-suite-capability.yaml
tags:
- Google
- Cloud
- Operations
- Suite
- API
tools:
- description: Google Cloud Operations Suite List Time Series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtimeseries
- description: Google Cloud Operations Suite Create Time Series
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtimeseries
- description: Google Cloud Operations Suite List Alert Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalertpolicies
- description: Google Cloud Operations Suite Create Alert Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createalertpolicy
- description: Google Cloud Operations Suite List Log Entries
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listlogentries
- description: Google Cloud Operations Suite Write Log Entries
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: writelogentries
- description: Google Cloud Operations Suite List Dashboards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdashboards
- description: Google Cloud Operations Suite Create Dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdashboard
- description: Google Cloud Operations Suite List Uptime Check Configs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuptimecheckconfigs
---
