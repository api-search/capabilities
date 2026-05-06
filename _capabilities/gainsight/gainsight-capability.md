---
categories: []
consumed_apis: []
description: The Gainsight Bulk API is an asynchronous connector that automates insert or update of large data volumes from CSV files into Gainsight standard and custom objects, with rate limits of 10 calls per hour and 100 per day.
layout: capability
name: Gainsight CS Bulk API
operations:
- description: Gainsight Create a bulk job
  method: POST
  name: createbulkjob
  path: /bulk/jobs
- description: Gainsight List bulk jobs
  method: GET
  name: listbulkjobs
  path: /bulk/jobs
- description: Gainsight Get bulk job status
  method: GET
  name: getbulkjob
  path: /bulk/jobs/{jobId}
- description: Gainsight Get bulk job errors
  method: GET
  name: getbulkjoberrors
  path: /bulk/jobs/{jobId}/errors
personas: []
provider_name: Gainsight
provider_slug: gainsight
search_terms:
- getbulkjob
- gainsight list bulk jobs
- gainsight get bulk job status
- api
- gainsight create a bulk job
- getbulkjoberrors
- gainsight get bulk job errors
- createbulkjob
- listbulkjobs
- gainsight
slug: gainsight-capability
source_filename: gainsight-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Gainsight CS Bulk API\n  description: The Gainsight Bulk API is an asynchronous connector that automates insert or update of large data volumes from\n    CSV files into Gainsight standard and custom objects, with rate limits of 10 calls per hour and 100 per day.\n  tags:\n  - Gainsight\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: gainsight\n    baseUri: https://customer.gainsightcloud.com/v1\n    description: Gainsight CS Bulk API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: accessKey\n      value: '{{GAINSIGHT_TOKEN}}'\n    resources:\n    - name: bulk-jobs\n      path: /bulk/jobs\n      operations:\n      - name: createbulkjob\n        method: POST\n        description: Gainsight Create a bulk job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: listbulkjobs\n        method: GET\n        description: Gainsight List bulk jobs\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by job status\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of jobs to return\n        - name: offset\n          in: query\n          type: integer\n          description: Offset for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bulk-jobs-jobid\n      path: /bulk/jobs/{jobId}\n      operations:\n      - name: getbulkjob\n        method: GET\n        description: Gainsight Get bulk job status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bulk-jobs-jobid-errors\n      path: /bulk/jobs/{jobId}/errors\n      operations:\n\
  \      - name: getbulkjoberrors\n        method: GET\n        description: Gainsight Get bulk job errors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gainsight-rest\n    description: REST adapter for Gainsight CS Bulk API.\n    resources:\n    - path: /bulk/jobs\n      name: createbulkjob\n      operations:\n      - method: POST\n        name: createbulkjob\n        description: Gainsight Create a bulk job\n        call: gainsight.createbulkjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bulk/jobs\n      name: listbulkjobs\n      operations:\n      - method: GET\n        name: listbulkjobs\n        description: Gainsight List bulk jobs\n        call: gainsight.listbulkjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bulk/jobs/{jobId}\n      name: getbulkjob\n\
  \      operations:\n      - method: GET\n        name: getbulkjob\n        description: Gainsight Get bulk job status\n        call: gainsight.getbulkjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bulk/jobs/{jobId}/errors\n      name: getbulkjoberrors\n      operations:\n      - method: GET\n        name: getbulkjoberrors\n        description: Gainsight Get bulk job errors\n        call: gainsight.getbulkjoberrors\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gainsight-mcp\n    transport: http\n    description: MCP adapter for Gainsight CS Bulk API for AI agent use.\n    tools:\n    - name: createbulkjob\n      description: Gainsight Create a bulk job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: gainsight.createbulkjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbulkjobs\n\
  \      description: Gainsight List bulk jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gainsight.listbulkjobs\n      with:\n        status: tools.status\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by job status\n      - name: limit\n        type: integer\n        description: Maximum number of jobs to return\n      - name: offset\n        type: integer\n        description: Offset for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbulkjob\n      description: Gainsight Get bulk job status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gainsight.getbulkjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbulkjoberrors\n      description: Gainsight Get bulk job errors\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gainsight.getbulkjoberrors\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GAINSIGHT_TOKEN: GAINSIGHT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gainsight/refs/heads/main/capabilities/gainsight-capability.yaml
tags:
- Gainsight
- API
tools:
- description: Gainsight Create a bulk job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbulkjob
- description: Gainsight List bulk jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbulkjobs
- description: Gainsight Get bulk job status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbulkjob
- description: Gainsight Get bulk job errors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbulkjoberrors
---
