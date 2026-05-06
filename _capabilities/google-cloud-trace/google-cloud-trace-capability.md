---
categories: []
consumed_apis: []
description: The Cloud Trace API enables sending and retrieving latency data for distributed applications. It supports writing trace spans, batch writing traces, listing traces, and retrieving individual traces to analyze request latency across microservices.
layout: capability
name: Google Cloud Trace API
operations:
- description: Google Cloud Trace Batch Write Spans
  method: POST
  name: batchwritespans
  path: /v2/projects/{projectId}/traces:batchWrite
- description: Google Cloud Trace Create Span
  method: POST
  name: createspan
  path: /v2/projects/{projectId}/traces/{traceId}/spans
- description: Google Cloud Trace List Traces
  method: GET
  name: listtraces
  path: /v1/projects/{projectId}/traces
- description: Google Cloud Trace Patch Traces
  method: PATCH
  name: patchtraces
  path: /v1/projects/{projectId}/traces
- description: Google Cloud Trace Get Trace
  method: GET
  name: gettrace
  path: /v1/projects/{projectId}/traces/{traceId}
personas: []
provider_name: Google Cloud Trace
provider_slug: google-cloud-trace
search_terms:
- patchtraces
- tracing
- google cloud trace list traces
- google cloud trace create span
- cloud
- google cloud trace batch write spans
- google
- spans
- api
- observability
- google cloud trace patch traces
- gettrace
- trace
- performance
- google cloud trace get trace
- createspan
- listtraces
- latency
- distributed tracing
- batchwritespans
- google cloud
slug: google-cloud-trace-capability
source_filename: google-cloud-trace-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Trace API\n  description: The Cloud Trace API enables sending and retrieving latency data for distributed applications. It supports writing\n    trace spans, batch writing traces, listing traces, and retrieving individual traces to analyze request latency across\n    microservices.\n  tags:\n  - Google\n  - Cloud\n  - Trace\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-trace\n    baseUri: https://cloudtrace.googleapis.com\n    description: Google Cloud Trace API HTTP API.\n    resources:\n    - name: v2-projects-projectid-traces-batchwrite\n      path: /v2/projects/{projectId}/traces:batchWrite\n      operations:\n      - name: batchwritespans\n        method: POST\n        description: Google Cloud Trace Batch Write Spans\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-projects-projectid-traces-traceid-spans\n      path: /v2/projects/{projectId}/traces/{traceId}/spans\n      operations:\n      - name: createspan\n        method: POST\n        description: Google Cloud Trace Create Span\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: traceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-traces\n      path: /v1/projects/{projectId}/traces\n      operations:\n      - name: listtraces\n        method: GET\n        description: Google Cloud Trace List Traces\n        inputParameters:\n        - name: projectId\n          in: path\n   \
  \       type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          description: Optional filter for the traces.\n        - name: startTime\n          in: query\n          type: string\n        - name: endTime\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchtraces\n        method: PATCH\n        description: Google Cloud Trace Patch Traces\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-traces-traceid\n      path:\
  \ /v1/projects/{projectId}/traces/{traceId}\n      operations:\n      - name: gettrace\n        method: GET\n        description: Google Cloud Trace Get Trace\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: traceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-trace-rest\n    description: REST adapter for Google Cloud Trace API.\n    resources:\n    - path: /v2/projects/{projectId}/traces:batchWrite\n      name: batchwritespans\n      operations:\n      - method: POST\n        name: batchwritespans\n        description: Google Cloud Trace Batch Write Spans\n        call: google-cloud-trace.batchwritespans\n        with:\n          projectId: rest.projectId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v2/projects/{projectId}/traces/{traceId}/spans\n      name: createspan\n      operations:\n      - method: POST\n        name: createspan\n        description: Google Cloud Trace Create Span\n        call: google-cloud-trace.createspan\n        with:\n          projectId: rest.projectId\n          traceId: rest.traceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/traces\n      name: listtraces\n      operations:\n      - method: GET\n        name: listtraces\n        description: Google Cloud Trace List Traces\n        call: google-cloud-trace.listtraces\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/traces\n      name: patchtraces\n      operations:\n      - method: PATCH\n        name: patchtraces\n        description: Google Cloud Trace Patch\
  \ Traces\n        call: google-cloud-trace.patchtraces\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/traces/{traceId}\n      name: gettrace\n      operations:\n      - method: GET\n        name: gettrace\n        description: Google Cloud Trace Get Trace\n        call: google-cloud-trace.gettrace\n        with:\n          projectId: rest.projectId\n          traceId: rest.traceId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-trace-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Trace API for AI agent use.\n    tools:\n    - name: batchwritespans\n      description: Google Cloud Trace Batch Write Spans\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-trace.batchwritespans\n      with:\n    \
  \    projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createspan\n      description: Google Cloud Trace Create Span\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-trace.createspan\n      with:\n        projectId: tools.projectId\n        traceId: tools.traceId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: traceId\n        type: string\n        description: traceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtraces\n      description: Google Cloud Trace List Traces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-trace.listtraces\n\
  \      with:\n        projectId: tools.projectId\n        filter: tools.filter\n        startTime: tools.startTime\n        endTime: tools.endTime\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: filter\n        type: string\n        description: Optional filter for the traces.\n      - name: startTime\n        type: string\n        description: startTime\n      - name: endTime\n        type: string\n        description: endTime\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchtraces\n      description: Google Cloud Trace Patch Traces\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ google-cloud-trace.patchtraces\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettrace\n      description: Google Cloud Trace Get Trace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-trace.gettrace\n      with:\n        projectId: tools.projectId\n        traceId: tools.traceId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: traceId\n        type: string\n        description: traceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-trace/refs/heads/main/capabilities/google-cloud-trace-capability.yaml
tags:
- Google
- Cloud
- Trace
- API
tools:
- description: Google Cloud Trace Batch Write Spans
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchwritespans
- description: Google Cloud Trace Create Span
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspan
- description: Google Cloud Trace List Traces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtraces
- description: Google Cloud Trace Patch Traces
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchtraces
- description: Google Cloud Trace Get Trace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettrace
---
