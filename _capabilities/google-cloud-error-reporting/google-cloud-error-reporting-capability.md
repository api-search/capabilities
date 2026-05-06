---
categories: []
consumed_apis: []
description: The Error Reporting API enables listing error events, retrieving error group statistics, reporting new errors, and managing error groups. It groups and counts similar errors from cloud services and applications and provides programmatic access to error data and statistics.
layout: capability
name: Google Cloud Error Reporting API
operations:
- description: Google Cloud Error Reporting List Error Events
  method: GET
  name: listevents
  path: /v1beta1/projects/{projectId}/events
- description: Google Cloud Error Reporting Report Error Event
  method: POST
  name: reportevent
  path: /v1beta1/projects/{projectId}/events:report
- description: Google Cloud Error Reporting List Group Stats
  method: GET
  name: listgroupstats
  path: /v1beta1/projects/{projectId}/groupStats
- description: Google Cloud Error Reporting Get Error Group
  method: GET
  name: getgroup
  path: /v1beta1/projects/{projectId}/groups/{groupId}
- description: Google Cloud Error Reporting Update Error Group
  method: PUT
  name: updategroup
  path: /v1beta1/projects/{projectId}/groups/{groupId}
- description: Google Cloud Error Reporting Delete All Events
  method: DELETE
  name: deleteevents
  path: /v1beta1/projects/{projectId}/events:deleteAll
personas: []
provider_name: Google Cloud Error Reporting
provider_slug: google-cloud-error-reporting
search_terms:
- error
- google cloud error reporting get error group
- listevents
- reliability
- google cloud error reporting update error group
- reporting
- error reporting
- errors
- cloud
- google
- deleteevents
- google cloud
- reportevent
- google cloud error reporting report error event
- api
- observability
- google cloud error reporting list group stats
- listgroupstats
- exceptions
- getgroup
- google cloud error reporting list error events
- debugging
- updategroup
- google cloud error reporting delete all events
slug: google-cloud-error-reporting-capability
source_filename: google-cloud-error-reporting-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Error Reporting API\n  description: The Error Reporting API enables listing error events, retrieving error group statistics, reporting new errors,\n    and managing error groups. It groups and counts similar errors from cloud services and applications and provides programmatic\n    access to error data and statistics.\n  tags:\n  - Google\n  - Cloud\n  - Error\n  - Reporting\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-error-reporting\n    baseUri: https://clouderrorreporting.googleapis.com\n    description: Google Cloud Error Reporting API HTTP API.\n    resources:\n    - name: v1beta1-projects-projectid-events\n      path: /v1beta1/projects/{projectId}/events\n      operations:\n      - name: listevents\n        method: GET\n        description: Google Cloud Error Reporting List Error Events\n        inputParameters:\n        - name: projectId\n\
  \          in: path\n          type: string\n          required: true\n        - name: groupId\n          in: query\n          type: string\n          required: true\n          description: The group for which events are returned.\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1beta1-projects-projectid-events-report\n      path: /v1beta1/projects/{projectId}/events:report\n      operations:\n      - name: reportevent\n        method: POST\n        description: Google Cloud Error Reporting Report Error Event\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: v1beta1-projects-projectid-groupstats\n      path: /v1beta1/projects/{projectId}/groupStats\n      operations:\n      - name: listgroupstats\n        method: GET\n        description: Google Cloud Error Reporting List Group Stats\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: timeRange.period\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1beta1-projects-projectid-groups-groupid\n      path: /v1beta1/projects/{projectId}/groups/{groupId}\n      operations:\n      - name: getgroup\n        method: GET\n        description: Google Cloud Error Reporting Get Error Group\n        inputParameters:\n        - name:\
  \ projectId\n          in: path\n          type: string\n          required: true\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n        method: PUT\n        description: Google Cloud Error Reporting Update Error Group\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1beta1-projects-projectid-events-deleteall\n      path: /v1beta1/projects/{projectId}/events:deleteAll\n      operations:\n      - name: deleteevents\n        method: DELETE\n        description: Google Cloud Error Reporting\
  \ Delete All Events\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-error-reporting-rest\n    description: REST adapter for Google Cloud Error Reporting API.\n    resources:\n    - path: /v1beta1/projects/{projectId}/events\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: Google Cloud Error Reporting List Error Events\n        call: google-cloud-error-reporting.listevents\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1beta1/projects/{projectId}/events:report\n      name: reportevent\n      operations:\n      - method: POST\n        name: reportevent\n        description:\
  \ Google Cloud Error Reporting Report Error Event\n        call: google-cloud-error-reporting.reportevent\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1beta1/projects/{projectId}/groupStats\n      name: listgroupstats\n      operations:\n      - method: GET\n        name: listgroupstats\n        description: Google Cloud Error Reporting List Group Stats\n        call: google-cloud-error-reporting.listgroupstats\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1beta1/projects/{projectId}/groups/{groupId}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n        description: Google Cloud Error Reporting Get Error Group\n        call: google-cloud-error-reporting.getgroup\n        with:\n          projectId: rest.projectId\n          groupId: rest.groupId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1beta1/projects/{projectId}/groups/{groupId}\n      name: updategroup\n      operations:\n      - method: PUT\n        name: updategroup\n        description: Google Cloud Error Reporting Update Error Group\n        call: google-cloud-error-reporting.updategroup\n        with:\n          projectId: rest.projectId\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1beta1/projects/{projectId}/events:deleteAll\n      name: deleteevents\n      operations:\n      - method: DELETE\n        name: deleteevents\n        description: Google Cloud Error Reporting Delete All Events\n        call: google-cloud-error-reporting.deleteevents\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-error-reporting-mcp\n    transport: http\n    description:\
  \ MCP adapter for Google Cloud Error Reporting API for AI agent use.\n    tools:\n    - name: listevents\n      description: Google Cloud Error Reporting List Error Events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-error-reporting.listevents\n      with:\n        projectId: tools.projectId\n        groupId: tools.groupId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: groupId\n        type: string\n        description: The group for which events are returned.\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reportevent\n      description: Google\
  \ Cloud Error Reporting Report Error Event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-error-reporting.reportevent\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroupstats\n      description: Google Cloud Error Reporting List Group Stats\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-error-reporting.listgroupstats\n      with:\n        projectId: tools.projectId\n        timeRange.period: tools.timeRange.period\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: timeRange.period\n\
  \        type: string\n        description: timeRange.period\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgroup\n      description: Google Cloud Error Reporting Get Error Group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-error-reporting.getgroup\n      with:\n        projectId: tools.projectId\n        groupId: tools.groupId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: groupId\n        type: string\n        description: groupId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updategroup\n      description: Google Cloud Error Reporting Update Error Group\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-cloud-error-reporting.updategroup\n      with:\n        projectId: tools.projectId\n        groupId: tools.groupId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: groupId\n        type: string\n        description: groupId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteevents\n      description: Google Cloud Error Reporting Delete All Events\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-error-reporting.deleteevents\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-error-reporting/refs/heads/main/capabilities/google-cloud-error-reporting-capability.yaml
tags:
- Google
- Cloud
- Error
- Reporting
- API
tools:
- description: Google Cloud Error Reporting List Error Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: Google Cloud Error Reporting Report Error Event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reportevent
- description: Google Cloud Error Reporting List Group Stats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupstats
- description: Google Cloud Error Reporting Get Error Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: Google Cloud Error Reporting Update Error Group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroup
- description: Google Cloud Error Reporting Delete All Events
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteevents
---
