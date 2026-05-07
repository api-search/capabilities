---
categories: []
consumed_apis: []
description: REST API for working with Workday Prism Analytics tables, datasets, and data change tasks. Enables programmatic loading of external data into Prism Analytics for advanced reporting and analytics that combines internal Workday data with external sources. Supports creating tables with schema definitions, uploading compressed data files via buckets, and executing data change tasks to apply inserts, updates, upserts, and deletes.
layout: capability
name: Workday Report Writer Workday Prism Analytics API
operations:
- description: Workday Report Writer List Prism Analytics Tables
  method: GET
  name: listtables
  path: /tables
- description: Workday Report Writer Create a Prism Analytics Table
  method: POST
  name: createtable
  path: /tables
- description: Workday Report Writer Get a Prism Analytics Table
  method: GET
  name: gettable
  path: /tables/{tableId}
- description: Workday Report Writer Update a Prism Analytics Table
  method: PATCH
  name: updatetable
  path: /tables/{tableId}
- description: Workday Report Writer List Prism Analytics Datasets
  method: GET
  name: listdatasets
  path: /datasets
- description: Workday Report Writer Get a Prism Analytics Dataset
  method: GET
  name: getdataset
  path: /datasets/{datasetId}
- description: Workday Report Writer List File Upload Buckets
  method: GET
  name: listbuckets
  path: /buckets
- description: Workday Report Writer Create a File Upload Bucket
  method: POST
  name: createbucket
  path: /buckets
- description: Workday Report Writer Get a File Upload Bucket
  method: GET
  name: getbucket
  path: /buckets/{bucketId}
- description: Workday Report Writer Upload a File to a Bucket
  method: POST
  name: uploadfiletobucket
  path: /buckets/{bucketId}/files
- description: Workday Report Writer Complete a Bucket and Trigger Data Change Task
  method: POST
  name: completebucket
  path: /buckets/{bucketId}/complete
- description: Workday Report Writer List Data Change Tasks
  method: GET
  name: listdatachangetasks
  path: /dataChangeTasks
- description: Workday Report Writer Get a Data Change Task
  method: GET
  name: getdatachangetask
  path: /dataChangeTasks/{taskId}
personas: []
provider_name: Workday Report Writer
provider_slug: workday-report-writer
search_terms:
- workday report writer list prism analytics datasets
- analytics
- listdatasets
- writer
- workday report writer get a data change task
- api
- workday
- workday report writer list prism analytics tables
- listbuckets
- saas
- getdataset
- workday report writer get a prism analytics table
- workday report writer get a prism analytics dataset
- createtable
- workday report writer list file upload buckets
- workday report writer complete a bucket and trigger data change task
- workday report writer list data change tasks
- hrms
- workday report writer update a prism analytics table
- getbucket
- workday report writer upload a file to a bucket
- workday report writer get a file upload bucket
- listtables
- workday report writer create a file upload bucket
- createbucket
- updatetable
- enterprise
- report
- listdatachangetasks
- completebucket
- workday report writer create a prism analytics table
- erp
- reporting
- uploadfiletobucket
- getdatachangetask
- gettable
- financials
slug: workday-report-writer-capability
source_filename: workday-report-writer-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Report Writer Workday Prism Analytics API\n  description: REST API for working with Workday Prism Analytics tables, datasets, and data change tasks. Enables programmatic\n    loading of external data into Prism Analytics for advanced reporting and analytics that combines internal Workday data\n    with external sources. Supports creating tables with schema definitions, uploading compressed data files via buckets,\n    and executing data change tasks to apply inserts, updates, upserts, and deletes.\n  tags:\n  - Workday\n  - Report\n  - Writer\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-report-writer\n    baseUri: https://wd2-impl-services1.workday.com/api/prismAnalytics/v3/your-tenant\n    description: Workday Report Writer Workday Prism Analytics API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_REPORT_WRITER_TOKEN}}'\n\
  \    resources:\n    - name: tables\n      path: /tables\n      operations:\n      - name: listtables\n        method: GET\n        description: Workday Report Writer List Prism Analytics Tables\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter tables by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtable\n        method: POST\n        description: Workday Report Writer Create a Prism Analytics Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tables-tableid\n      path: /tables/{tableId}\n      operations:\n      - name: gettable\n        method: GET\n        description: Workday Report Writer Get a Prism Analytics Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n      - name: updatetable\n        method: PATCH\n        description: Workday Report Writer Update a Prism Analytics Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets\n      path: /datasets\n      operations:\n      - name: listdatasets\n        method: GET\n        description: Workday Report Writer List Prism Analytics Datasets\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter datasets by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets-datasetid\n      path: /datasets/{datasetId}\n      operations:\n      - name: getdataset\n        method: GET\n        description: Workday Report Writer Get a Prism Analytics Dataset\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: buckets\n      path: /buckets\n      operations:\n      - name: listbuckets\n        method: GET\n        description: Workday Report Writer List File Upload Buckets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbucket\n        method: POST\n        description: Workday Report Writer Create a File Upload Bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: buckets-bucketid\n      path: /buckets/{bucketId}\n      operations:\n      - name: getbucket\n        method: GET\n        description: Workday Report Writer Get a File Upload Bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: buckets-bucketid-files\n      path: /buckets/{bucketId}/files\n\
  \      operations:\n      - name: uploadfiletobucket\n        method: POST\n        description: Workday Report Writer Upload a File to a Bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: buckets-bucketid-complete\n      path: /buckets/{bucketId}/complete\n      operations:\n      - name: completebucket\n        method: POST\n        description: Workday Report Writer Complete a Bucket and Trigger Data Change Task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datachangetasks\n      path: /dataChangeTasks\n      operations:\n      - name: listdatachangetasks\n        method: GET\n        description: Workday Report Writer List Data Change Tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datachangetasks-taskid\n\
  \      path: /dataChangeTasks/{taskId}\n      operations:\n      - name: getdatachangetask\n        method: GET\n        description: Workday Report Writer Get a Data Change Task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workday-report-writer-rest\n    description: REST adapter for Workday Report Writer Workday Prism Analytics API.\n    resources:\n    - path: /tables\n      name: listtables\n      operations:\n      - method: GET\n        name: listtables\n        description: Workday Report Writer List Prism Analytics Tables\n        call: workday-report-writer.listtables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tables\n      name: createtable\n      operations:\n      - method: POST\n        name: createtable\n        description: Workday Report Writer Create a Prism Analytics Table\n        call:\
  \ workday-report-writer.createtable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tables/{tableId}\n      name: gettable\n      operations:\n      - method: GET\n        name: gettable\n        description: Workday Report Writer Get a Prism Analytics Table\n        call: workday-report-writer.gettable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tables/{tableId}\n      name: updatetable\n      operations:\n      - method: PATCH\n        name: updatetable\n        description: Workday Report Writer Update a Prism Analytics Table\n        call: workday-report-writer.updatetable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasets\n      name: listdatasets\n      operations:\n      - method: GET\n        name: listdatasets\n        description: Workday Report Writer List Prism Analytics Datasets\n        call: workday-report-writer.listdatasets\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /datasets/{datasetId}\n      name: getdataset\n      operations:\n      - method: GET\n        name: getdataset\n        description: Workday Report Writer Get a Prism Analytics Dataset\n        call: workday-report-writer.getdataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /buckets\n      name: listbuckets\n      operations:\n      - method: GET\n        name: listbuckets\n        description: Workday Report Writer List File Upload Buckets\n        call: workday-report-writer.listbuckets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /buckets\n      name: createbucket\n      operations:\n      - method: POST\n        name: createbucket\n        description: Workday Report Writer Create a File Upload Bucket\n        call: workday-report-writer.createbucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /buckets/{bucketId}\n      name: getbucket\n      operations:\n      - method: GET\n        name: getbucket\n        description: Workday Report Writer Get a File Upload Bucket\n        call: workday-report-writer.getbucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /buckets/{bucketId}/files\n      name: uploadfiletobucket\n      operations:\n      - method: POST\n        name: uploadfiletobucket\n        description: Workday Report Writer Upload a File to a Bucket\n        call: workday-report-writer.uploadfiletobucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /buckets/{bucketId}/complete\n      name: completebucket\n      operations:\n      - method: POST\n        name: completebucket\n        description: Workday Report Writer Complete a Bucket and Trigger Data Change Task\n        call: workday-report-writer.completebucket\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /dataChangeTasks\n      name: listdatachangetasks\n      operations:\n      - method: GET\n        name: listdatachangetasks\n        description: Workday Report Writer List Data Change Tasks\n        call: workday-report-writer.listdatachangetasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dataChangeTasks/{taskId}\n      name: getdatachangetask\n      operations:\n      - method: GET\n        name: getdatachangetask\n        description: Workday Report Writer Get a Data Change Task\n        call: workday-report-writer.getdatachangetask\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workday-report-writer-mcp\n    transport: http\n    description: MCP adapter for Workday Report Writer Workday Prism Analytics API for AI agent use.\n    tools:\n    - name: listtables\n      description: Workday Report Writer List Prism Analytics Tables\n      hints:\n  \
  \      readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-report-writer.listtables\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter tables by name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtable\n      description: Workday Report Writer Create a Prism Analytics Table\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: workday-report-writer.createtable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettable\n      description: Workday Report Writer Get a Prism Analytics Table\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-report-writer.gettable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetable\n      description: Workday Report\
  \ Writer Update a Prism Analytics Table\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: workday-report-writer.updatetable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatasets\n      description: Workday Report Writer List Prism Analytics Datasets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-report-writer.listdatasets\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter datasets by name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdataset\n      description: Workday Report Writer Get a Prism Analytics Dataset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-report-writer.getdataset\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listbuckets\n      description: Workday Report Writer List File Upload Buckets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-report-writer.listbuckets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbucket\n      description: Workday Report Writer Create a File Upload Bucket\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: workday-report-writer.createbucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbucket\n      description: Workday Report Writer Get a File Upload Bucket\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-report-writer.getbucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadfiletobucket\n      description: Workday Report Writer Upload a File to a Bucket\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: workday-report-writer.uploadfiletobucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: completebucket\n      description: Workday Report Writer Complete a Bucket and Trigger Data Change Task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: workday-report-writer.completebucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatachangetasks\n      description: Workday Report Writer List Data Change Tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-report-writer.listdatachangetasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatachangetask\n      description: Workday Report Writer Get a Data Change Task\n      hints:\n        readOnly: true\n      \
  \  destructive: false\n        idempotent: true\n      call: workday-report-writer.getdatachangetask\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_REPORT_WRITER_TOKEN: WORKDAY_REPORT_WRITER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-report-writer/refs/heads/main/capabilities/workday-report-writer-capability.yaml
tags:
- Workday
- Report
- Writer
- API
tools:
- description: Workday Report Writer List Prism Analytics Tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtables
- description: Workday Report Writer Create a Prism Analytics Table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtable
- description: Workday Report Writer Get a Prism Analytics Table
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettable
- description: Workday Report Writer Update a Prism Analytics Table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetable
- description: Workday Report Writer List Prism Analytics Datasets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatasets
- description: Workday Report Writer Get a Prism Analytics Dataset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdataset
- description: Workday Report Writer List File Upload Buckets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuckets
- description: Workday Report Writer Create a File Upload Bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbucket
- description: Workday Report Writer Get a File Upload Bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucket
- description: Workday Report Writer Upload a File to a Bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadfiletobucket
- description: Workday Report Writer Complete a Bucket and Trigger Data Change Task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completebucket
- description: Workday Report Writer List Data Change Tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatachangetasks
- description: Workday Report Writer Get a Data Change Task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatachangetask
---
