---
categories: []
consumed_apis: []
description: The Cloud Monitoring API provides programmatic access to time series data, alert policies, notification channels, uptime checks, dashboards, metric descriptors, monitored resource descriptors, and service level objectives for comprehensive infrastructure and application monitoring.
layout: capability
name: Google Cloud Monitoring API
operations:
- description: Google Cloud Monitoring List Time Series
  method: GET
  name: listtimeseries
  path: /v3/projects/{projectId}/timeSeries
- description: Google Cloud Monitoring Create Time Series
  method: POST
  name: createtimeseries
  path: /v3/projects/{projectId}/timeSeries
- description: Google Cloud Monitoring List Alert Policies
  method: GET
  name: listalertpolicies
  path: /v3/projects/{projectId}/alertPolicies
- description: Google Cloud Monitoring Create Alert Policy
  method: POST
  name: createalertpolicy
  path: /v3/projects/{projectId}/alertPolicies
- description: Google Cloud Monitoring Get Alert Policy
  method: GET
  name: getalertpolicy
  path: /v3/projects/{projectId}/alertPolicies/{alertPolicyId}
- description: Google Cloud Monitoring Update Alert Policy
  method: PATCH
  name: updatealertpolicy
  path: /v3/projects/{projectId}/alertPolicies/{alertPolicyId}
- description: Google Cloud Monitoring Delete Alert Policy
  method: DELETE
  name: deletealertpolicy
  path: /v3/projects/{projectId}/alertPolicies/{alertPolicyId}
- description: Google Cloud Monitoring List Uptime Check Configs
  method: GET
  name: listuptimecheckconfigs
  path: /v3/projects/{projectId}/uptimeCheckConfigs
- description: Google Cloud Monitoring Create Uptime Check Config
  method: POST
  name: createuptimecheckconfig
  path: /v3/projects/{projectId}/uptimeCheckConfigs
- description: Google Cloud Monitoring List Notification Channels
  method: GET
  name: listnotificationchannels
  path: /v3/projects/{projectId}/notificationChannels
- description: Google Cloud Monitoring Create Notification Channel
  method: POST
  name: createnotificationchannel
  path: /v3/projects/{projectId}/notificationChannels
- description: Google Cloud Monitoring List Metric Descriptors
  method: GET
  name: listmetricdescriptors
  path: /v3/projects/{projectId}/metricDescriptors
- description: Google Cloud Monitoring Create Metric Descriptor
  method: POST
  name: createmetricdescriptor
  path: /v3/projects/{projectId}/metricDescriptors
- description: Google Cloud Monitoring List Groups
  method: GET
  name: listgroups
  path: /v3/projects/{projectId}/groups
personas: []
provider_name: Google Cloud Monitoring
provider_slug: google-cloud-monitoring
search_terms:
- updatealertpolicy
- google cloud monitoring create notification channel
- getalertpolicy
- google cloud monitoring list uptime check configs
- createuptimecheckconfig
- deletealertpolicy
- google cloud monitoring list groups
- listtimeseries
- uptime
- google cloud monitoring list time series
- google cloud monitoring create alert policy
- google cloud monitoring list notification channels
- cloud
- dashboards
- metrics
- google
- alerting
- google cloud monitoring create uptime check config
- monitoring
- createmetricdescriptor
- listnotificationchannels
- google cloud monitoring create time series
- listgroups
- slo
- google cloud monitoring delete alert policy
- listmetricdescriptors
- api
- createnotificationchannel
- observability
- google cloud monitoring update alert policy
- createtimeseries
- google cloud monitoring create metric descriptor
- listalertpolicies
- google cloud monitoring list alert policies
- google cloud monitoring get alert policy
- createalertpolicy
- google cloud monitoring list metric descriptors
- google cloud
- listuptimecheckconfigs
slug: google-cloud-monitoring-capability
source_filename: google-cloud-monitoring-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Monitoring API\n  description: The Cloud Monitoring API provides programmatic access to time series data, alert policies, notification channels,\n    uptime checks, dashboards, metric descriptors, monitored resource descriptors, and service level objectives for comprehensive\n    infrastructure and application monitoring.\n  tags:\n  - Google\n  - Cloud\n  - Monitoring\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-monitoring\n    baseUri: https://monitoring.googleapis.com\n    description: Google Cloud Monitoring API HTTP API.\n    resources:\n    - name: v3-projects-projectid-timeseries\n      path: /v3/projects/{projectId}/timeSeries\n      operations:\n      - name: listtimeseries\n        method: GET\n        description: Google Cloud Monitoring List Time Series\n        inputParameters:\n        - name: projectId\n          in: path\n\
  \          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          description: Monitoring filter specifying the time series to return.\n        - name: interval.startTime\n          in: query\n          type: string\n        - name: interval.endTime\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtimeseries\n        method: POST\n        description: Google Cloud Monitoring Create Time Series\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-projects-projectid-alertpolicies\n      path: /v3/projects/{projectId}/alertPolicies\n      operations:\n      - name: listalertpolicies\n\
  \        method: GET\n        description: Google Cloud Monitoring List Alert Policies\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createalertpolicy\n        method: POST\n        description: Google Cloud Monitoring Create Alert Policy\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-projects-projectid-alertpolicies-alertpolicyi\n      path: /v3/projects/{projectId}/alertPolicies/{alertPolicyId}\n      operations:\n      - name: getalertpolicy\n        method: GET\n        description: Google Cloud Monitoring Get Alert Policy\n        inputParameters:\n \
  \       - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: alertPolicyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatealertpolicy\n        method: PATCH\n        description: Google Cloud Monitoring Update Alert Policy\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: alertPolicyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletealertpolicy\n        method: DELETE\n        description: Google Cloud Monitoring Delete Alert Policy\n        inputParameters:\n        - name: projectId\n          in: path\n     \
  \     type: string\n          required: true\n        - name: alertPolicyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-projects-projectid-uptimecheckconfigs\n      path: /v3/projects/{projectId}/uptimeCheckConfigs\n      operations:\n      - name: listuptimecheckconfigs\n        method: GET\n        description: Google Cloud Monitoring List Uptime Check Configs\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuptimecheckconfig\n        method: POST\n        description: Google Cloud Monitoring Create Uptime Check Config\n        inputParameters:\n        - name: projectId\n          in: path\n       \
  \   type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-projects-projectid-notificationchannels\n      path: /v3/projects/{projectId}/notificationChannels\n      operations:\n      - name: listnotificationchannels\n        method: GET\n        description: Google Cloud Monitoring List Notification Channels\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnotificationchannel\n        method: POST\n        description: Google Cloud Monitoring Create Notification Channel\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v3-projects-projectid-metricdescriptors\n      path: /v3/projects/{projectId}/metricDescriptors\n      operations:\n      - name: listmetricdescriptors\n        method: GET\n        description: Google Cloud Monitoring List Metric Descriptors\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmetricdescriptor\n        method: POST\n        description: Google Cloud Monitoring Create Metric Descriptor\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-projects-projectid-groups\n\
  \      path: /v3/projects/{projectId}/groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: Google Cloud Monitoring List Groups\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-monitoring-rest\n    description: REST adapter for Google Cloud Monitoring API.\n    resources:\n    - path: /v3/projects/{projectId}/timeSeries\n      name: listtimeseries\n      operations:\n      - method: GET\n        name: listtimeseries\n        description: Google Cloud Monitoring List Time Series\n        call: google-cloud-monitoring.listtimeseries\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/timeSeries\n\
  \      name: createtimeseries\n      operations:\n      - method: POST\n        name: createtimeseries\n        description: Google Cloud Monitoring Create Time Series\n        call: google-cloud-monitoring.createtimeseries\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/alertPolicies\n      name: listalertpolicies\n      operations:\n      - method: GET\n        name: listalertpolicies\n        description: Google Cloud Monitoring List Alert Policies\n        call: google-cloud-monitoring.listalertpolicies\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/alertPolicies\n      name: createalertpolicy\n      operations:\n      - method: POST\n        name: createalertpolicy\n        description: Google Cloud Monitoring Create Alert Policy\n        call: google-cloud-monitoring.createalertpolicy\n\
  \        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/alertPolicies/{alertPolicyId}\n      name: getalertpolicy\n      operations:\n      - method: GET\n        name: getalertpolicy\n        description: Google Cloud Monitoring Get Alert Policy\n        call: google-cloud-monitoring.getalertpolicy\n        with:\n          projectId: rest.projectId\n          alertPolicyId: rest.alertPolicyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/alertPolicies/{alertPolicyId}\n      name: updatealertpolicy\n      operations:\n      - method: PATCH\n        name: updatealertpolicy\n        description: Google Cloud Monitoring Update Alert Policy\n        call: google-cloud-monitoring.updatealertpolicy\n        with:\n          projectId: rest.projectId\n          alertPolicyId: rest.alertPolicyId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/alertPolicies/{alertPolicyId}\n      name: deletealertpolicy\n      operations:\n      - method: DELETE\n        name: deletealertpolicy\n        description: Google Cloud Monitoring Delete Alert Policy\n        call: google-cloud-monitoring.deletealertpolicy\n        with:\n          projectId: rest.projectId\n          alertPolicyId: rest.alertPolicyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/uptimeCheckConfigs\n      name: listuptimecheckconfigs\n      operations:\n      - method: GET\n        name: listuptimecheckconfigs\n        description: Google Cloud Monitoring List Uptime Check Configs\n        call: google-cloud-monitoring.listuptimecheckconfigs\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/uptimeCheckConfigs\n\
  \      name: createuptimecheckconfig\n      operations:\n      - method: POST\n        name: createuptimecheckconfig\n        description: Google Cloud Monitoring Create Uptime Check Config\n        call: google-cloud-monitoring.createuptimecheckconfig\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/notificationChannels\n      name: listnotificationchannels\n      operations:\n      - method: GET\n        name: listnotificationchannels\n        description: Google Cloud Monitoring List Notification Channels\n        call: google-cloud-monitoring.listnotificationchannels\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/notificationChannels\n      name: createnotificationchannel\n      operations:\n      - method: POST\n        name: createnotificationchannel\n\
  \        description: Google Cloud Monitoring Create Notification Channel\n        call: google-cloud-monitoring.createnotificationchannel\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/metricDescriptors\n      name: listmetricdescriptors\n      operations:\n      - method: GET\n        name: listmetricdescriptors\n        description: Google Cloud Monitoring List Metric Descriptors\n        call: google-cloud-monitoring.listmetricdescriptors\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/metricDescriptors\n      name: createmetricdescriptor\n      operations:\n      - method: POST\n        name: createmetricdescriptor\n        description: Google Cloud Monitoring Create Metric Descriptor\n        call: google-cloud-monitoring.createmetricdescriptor\n    \
  \    with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/projects/{projectId}/groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: Google Cloud Monitoring List Groups\n        call: google-cloud-monitoring.listgroups\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-monitoring-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Monitoring API for AI agent use.\n    tools:\n    - name: listtimeseries\n      description: Google Cloud Monitoring List Time Series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-monitoring.listtimeseries\n      with:\n        projectId: tools.projectId\n        filter: tools.filter\n       \
  \ interval.startTime: tools.interval.startTime\n        interval.endTime: tools.interval.endTime\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: filter\n        type: string\n        description: Monitoring filter specifying the time series to return.\n      - name: interval.startTime\n        type: string\n        description: interval.startTime\n      - name: interval.endTime\n        type: string\n        description: interval.endTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtimeseries\n      description: Google Cloud Monitoring Create Time Series\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-monitoring.createtimeseries\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n \
  \       required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalertpolicies\n      description: Google Cloud Monitoring List Alert Policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-monitoring.listalertpolicies\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createalertpolicy\n      description: Google Cloud Monitoring Create Alert Policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-monitoring.createalertpolicy\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: getalertpolicy\n      description: Google Cloud Monitoring Get Alert Policy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-monitoring.getalertpolicy\n      with:\n        projectId: tools.projectId\n        alertPolicyId: tools.alertPolicyId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: alertPolicyId\n        type: string\n        description: alertPolicyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatealertpolicy\n      description: Google Cloud Monitoring Update Alert Policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-monitoring.updatealertpolicy\n      with:\n        projectId: tools.projectId\n      \
  \  alertPolicyId: tools.alertPolicyId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: alertPolicyId\n        type: string\n        description: alertPolicyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletealertpolicy\n      description: Google Cloud Monitoring Delete Alert Policy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-monitoring.deletealertpolicy\n      with:\n        projectId: tools.projectId\n        alertPolicyId: tools.alertPolicyId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: alertPolicyId\n        type: string\n        description: alertPolicyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listuptimecheckconfigs\n\
  \      description: Google Cloud Monitoring List Uptime Check Configs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-monitoring.listuptimecheckconfigs\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuptimecheckconfig\n      description: Google Cloud Monitoring Create Uptime Check Config\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-monitoring.createuptimecheckconfig\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnotificationchannels\n\
  \      description: Google Cloud Monitoring List Notification Channels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-monitoring.listnotificationchannels\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnotificationchannel\n      description: Google Cloud Monitoring Create Notification Channel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-monitoring.createnotificationchannel\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmetricdescriptors\n\
  \      description: Google Cloud Monitoring List Metric Descriptors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-monitoring.listmetricdescriptors\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmetricdescriptor\n      description: Google Cloud Monitoring Create Metric Descriptor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-monitoring.createmetricdescriptor\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description:\
  \ Google Cloud Monitoring List Groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-monitoring.listgroups\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-monitoring/refs/heads/main/capabilities/google-cloud-monitoring-capability.yaml
tags:
- Google
- Cloud
- Monitoring
- API
tools:
- description: Google Cloud Monitoring List Time Series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtimeseries
- description: Google Cloud Monitoring Create Time Series
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtimeseries
- description: Google Cloud Monitoring List Alert Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalertpolicies
- description: Google Cloud Monitoring Create Alert Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createalertpolicy
- description: Google Cloud Monitoring Get Alert Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalertpolicy
- description: Google Cloud Monitoring Update Alert Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatealertpolicy
- description: Google Cloud Monitoring Delete Alert Policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletealertpolicy
- description: Google Cloud Monitoring List Uptime Check Configs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuptimecheckconfigs
- description: Google Cloud Monitoring Create Uptime Check Config
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuptimecheckconfig
- description: Google Cloud Monitoring List Notification Channels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnotificationchannels
- description: Google Cloud Monitoring Create Notification Channel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnotificationchannel
- description: Google Cloud Monitoring List Metric Descriptors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmetricdescriptors
- description: Google Cloud Monitoring Create Metric Descriptor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmetricdescriptor
- description: Google Cloud Monitoring List Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
---
