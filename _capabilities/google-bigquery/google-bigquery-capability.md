---
categories: []
consumed_apis: []
description: The BigQuery API provides programmatic access to Google BigQuery for creating, managing, and querying datasets, tables, jobs, models, and routines. It enables developers to run SQL queries over petabytes of data, load and export data, manage access control, and orchestrate analytics workloads using serverless infrastructure.
layout: capability
name: Google BigQuery API
operations:
- description: Google BigQuery List projects
  method: GET
  name: listprojects
  path: /projects
- description: Google BigQuery List datasets
  method: GET
  name: listdatasets
  path: /projects/{projectId}/datasets
- description: Google BigQuery Create a dataset
  method: POST
  name: insertdataset
  path: /projects/{projectId}/datasets
- description: Google BigQuery Get dataset
  method: GET
  name: getdataset
  path: /projects/{projectId}/datasets/{datasetId}
- description: Google BigQuery Partially update dataset
  method: PATCH
  name: patchdataset
  path: /projects/{projectId}/datasets/{datasetId}
- description: Google BigQuery Update dataset
  method: PUT
  name: updatedataset
  path: /projects/{projectId}/datasets/{datasetId}
- description: Google BigQuery Delete dataset
  method: DELETE
  name: deletedataset
  path: /projects/{projectId}/datasets/{datasetId}
- description: Google BigQuery List tables
  method: GET
  name: listtables
  path: /projects/{projectId}/datasets/{datasetId}/tables
- description: Google BigQuery Create a table
  method: POST
  name: inserttable
  path: /projects/{projectId}/datasets/{datasetId}/tables
- description: Google BigQuery Get table
  method: GET
  name: gettable
  path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}
- description: Google BigQuery Partially update table
  method: PATCH
  name: patchtable
  path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}
- description: Google BigQuery Delete table
  method: DELETE
  name: deletetable
  path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}
- description: Google BigQuery List table rows
  method: GET
  name: listtabledata
  path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}/data
- description: Google BigQuery Insert rows
  method: POST
  name: insertalltabledata
  path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}/insertAll
- description: Google BigQuery List jobs
  method: GET
  name: listjobs
  path: /projects/{projectId}/jobs
- description: Google BigQuery Submit a job
  method: POST
  name: insertjob
  path: /projects/{projectId}/jobs
- description: Google BigQuery Get job
  method: GET
  name: getjob
  path: /projects/{projectId}/jobs/{jobId}
- description: Google BigQuery Delete job
  method: DELETE
  name: deletejob
  path: /projects/{projectId}/jobs/{jobId}
- description: Google BigQuery Cancel job
  method: POST
  name: canceljob
  path: /projects/{projectId}/jobs/{jobId}/cancel
- description: Google BigQuery Execute query
  method: POST
  name: queryjobs
  path: /projects/{projectId}/queries
- description: Google BigQuery Get query results
  method: GET
  name: getqueryresults
  path: /projects/{projectId}/queries/{jobId}
- description: Google BigQuery List models
  method: GET
  name: listmodels
  path: /projects/{projectId}/datasets/{datasetId}/models
- description: Google BigQuery Get model
  method: GET
  name: getmodel
  path: /projects/{projectId}/datasets/{datasetId}/models/{modelId}
- description: Google BigQuery Update model
  method: PATCH
  name: patchmodel
  path: /projects/{projectId}/datasets/{datasetId}/models/{modelId}
- description: Google BigQuery Delete model
  method: DELETE
  name: deletemodel
  path: /projects/{projectId}/datasets/{datasetId}/models/{modelId}
- description: Google BigQuery List routines
  method: GET
  name: listroutines
  path: /projects/{projectId}/datasets/{datasetId}/routines
- description: Google BigQuery Create a routine
  method: POST
  name: insertroutine
  path: /projects/{projectId}/datasets/{datasetId}/routines
- description: Google BigQuery Get routine
  method: GET
  name: getroutine
  path: /projects/{projectId}/datasets/{datasetId}/routines/{routineId}
- description: Google BigQuery Update routine
  method: PUT
  name: updateroutine
  path: /projects/{projectId}/datasets/{datasetId}/routines/{routineId}
- description: Google BigQuery Delete routine
  method: DELETE
  name: deleteroutine
  path: /projects/{projectId}/datasets/{datasetId}/routines/{routineId}
personas: []
provider_name: Google BigQuery
provider_slug: google-bigquery
search_terms:
- google bigquery partially update table
- analytics
- listdatasets
- google bigquery list projects
- google bigquery get query results
- patchdataset
- google bigquery delete dataset
- updateroutine
- google bigquery delete table
- google bigquery execute query
- data warehouse
- google bigquery create a routine
- insertjob
- api
- getqueryresults
- deleteroutine
- google bigquery get table
- google bigquery update routine
- google bigquery update model
- listjobs
- getdataset
- google bigquery list table rows
- listtabledata
- updatedataset
- google bigquery get dataset
- canceljob
- google
- google bigquery get job
- google bigquery list models
- deletemodel
- google bigquery delete model
- getmodel
- serverless
- google bigquery cancel job
- google bigquery list datasets
- listmodels
- big data
- google bigquery list tables
- listtables
- google bigquery delete job
- sql
- inserttable
- google bigquery delete routine
- bigquery
- getroutine
- google bigquery get routine
- google bigquery list routines
- google bigquery create a table
- insertalltabledata
- google bigquery insert rows
- google bigquery partially update dataset
- patchmodel
- cloud
- deletejob
- deletetable
- google bigquery list jobs
- getjob
- listroutines
- insertroutine
- patchtable
- queryjobs
- listprojects
- google bigquery create a dataset
- insertdataset
- deletedataset
- gettable
- google bigquery get model
- google bigquery submit a job
- google bigquery update dataset
slug: google-bigquery-capability
source_filename: google-bigquery-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google BigQuery API\n  description: The BigQuery API provides programmatic access to Google BigQuery for creating, managing, and querying datasets,\n    tables, jobs, models, and routines. It enables developers to run SQL queries over petabytes of data, load and export data,\n    manage access control, and orchestrate analytics workloads using serverless infrastructure.\n  tags:\n  - Google\n  - Bigquery\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-bigquery\n    baseUri: https://bigquery.googleapis.com/bigquery/v2\n    description: Google BigQuery API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_BIGQUERY_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: Google BigQuery List projects\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets\n      path: /projects/{projectId}/datasets\n      operations:\n      - name: listdatasets\n        method: GET\n        description: Google BigQuery List datasets\n        inputParameters:\n        - name: all\n          in: query\n          type: boolean\n          description: Whether to list all datasets, including hidden ones\n        - name: filter\n          in: query\n          type: string\n          description: Filter expression for filtering datasets by label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertdataset\n        method: POST\n        description: Google BigQuery Create a dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets-datasetid\n\
  \      path: /projects/{projectId}/datasets/{datasetId}\n      operations:\n      - name: getdataset\n        method: GET\n        description: Google BigQuery Get dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchdataset\n        method: PATCH\n        description: Google BigQuery Partially update dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedataset\n        method: PUT\n        description: Google BigQuery Update dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedataset\n        method: DELETE\n        description: Google BigQuery Delete dataset\n        inputParameters:\n        - name: deleteContents\n          in: query\n          type: boolean\n          description:\
  \ If true, delete all the tables in the dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets-datasetid-tables\n      path: /projects/{projectId}/datasets/{datasetId}/tables\n      operations:\n      - name: listtables\n        method: GET\n        description: Google BigQuery List tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: inserttable\n        method: POST\n        description: Google BigQuery Create a table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets-datasetid-tables-tab\n      path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}\n      operations:\n      - name: gettable\n        method: GET\n        description: Google BigQuery\
  \ Get table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchtable\n        method: PATCH\n        description: Google BigQuery Partially update table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetable\n        method: DELETE\n        description: Google BigQuery Delete table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets-datasetid-tables-tab\n      path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}/data\n      operations:\n      - name: listtabledata\n        method: GET\n        description: Google BigQuery List table rows\n        inputParameters:\n        - name: startIndex\n          in: query\n          type: integer\n          description: Zero-based\
  \ index of the starting row to read\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets-datasetid-tables-tab\n      path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}/insertAll\n      operations:\n      - name: insertalltabledata\n        method: POST\n        description: Google BigQuery Insert rows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-jobs\n      path: /projects/{projectId}/jobs\n      operations:\n      - name: listjobs\n        method: GET\n        description: Google BigQuery List jobs\n        inputParameters:\n        - name: projection\n          in: query\n          type: string\n          description: Restricts information returned to a set of selected fields\n        - name: stateFilter\n          in: query\n          type: array\n\
  \          description: Filter for job state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertjob\n        method: POST\n        description: Google BigQuery Submit a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-jobs-jobid\n      path: /projects/{projectId}/jobs/{jobId}\n      operations:\n      - name: getjob\n        method: GET\n        description: Google BigQuery Get job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletejob\n        method: DELETE\n        description: Google BigQuery Delete job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-jobs-jobid-cancel\n\
  \      path: /projects/{projectId}/jobs/{jobId}/cancel\n      operations:\n      - name: canceljob\n        method: POST\n        description: Google BigQuery Cancel job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-queries\n      path: /projects/{projectId}/queries\n      operations:\n      - name: queryjobs\n        method: POST\n        description: Google BigQuery Execute query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-queries-jobid\n      path: /projects/{projectId}/queries/{jobId}\n      operations:\n      - name: getqueryresults\n        method: GET\n        description: Google BigQuery Get query results\n        inputParameters:\n        - name: startIndex\n          in: query\n          type: integer\n          description: Zero-based index of the starting\
  \ row\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets-datasetid-models\n      path: /projects/{projectId}/datasets/{datasetId}/models\n      operations:\n      - name: listmodels\n        method: GET\n        description: Google BigQuery List models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets-datasetid-models-mod\n      path: /projects/{projectId}/datasets/{datasetId}/models/{modelId}\n      operations:\n      - name: getmodel\n        method: GET\n        description: Google BigQuery Get model\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: The ID of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n      - name: patchmodel\n        method: PATCH\n        description: Google BigQuery Update model\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: The ID of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemodel\n        method: DELETE\n        description: Google BigQuery Delete model\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: The ID of the model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets-datasetid-routines\n      path: /projects/{projectId}/datasets/{datasetId}/routines\n      operations:\n      - name: listroutines\n  \
  \      method: GET\n        description: Google BigQuery List routines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertroutine\n        method: POST\n        description: Google BigQuery Create a routine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-datasets-datasetid-routines-r\n      path: /projects/{projectId}/datasets/{datasetId}/routines/{routineId}\n      operations:\n      - name: getroutine\n        method: GET\n        description: Google BigQuery Get routine\n        inputParameters:\n        - name: routineId\n          in: path\n          type: string\n          required: true\n          description: The ID of the routine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateroutine\n\
  \        method: PUT\n        description: Google BigQuery Update routine\n        inputParameters:\n        - name: routineId\n          in: path\n          type: string\n          required: true\n          description: The ID of the routine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteroutine\n        method: DELETE\n        description: Google BigQuery Delete routine\n        inputParameters:\n        - name: routineId\n          in: path\n          type: string\n          required: true\n          description: The ID of the routine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-bigquery-rest\n    description: REST adapter for Google BigQuery API.\n    resources:\n    - path: /projects\n      name: listprojects\n      operations:\n     \
  \ - method: GET\n        name: listprojects\n        description: Google BigQuery List projects\n        call: google-bigquery.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets\n      name: listdatasets\n      operations:\n      - method: GET\n        name: listdatasets\n        description: Google BigQuery List datasets\n        call: google-bigquery.listdatasets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets\n      name: insertdataset\n      operations:\n      - method: POST\n        name: insertdataset\n        description: Google BigQuery Create a dataset\n        call: google-bigquery.insertdataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}\n      name: getdataset\n      operations:\n      - method: GET\n        name: getdataset\n        description:\
  \ Google BigQuery Get dataset\n        call: google-bigquery.getdataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}\n      name: patchdataset\n      operations:\n      - method: PATCH\n        name: patchdataset\n        description: Google BigQuery Partially update dataset\n        call: google-bigquery.patchdataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}\n      name: updatedataset\n      operations:\n      - method: PUT\n        name: updatedataset\n        description: Google BigQuery Update dataset\n        call: google-bigquery.updatedataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}\n      name: deletedataset\n      operations:\n      - method: DELETE\n        name: deletedataset\n        description: Google BigQuery Delete\
  \ dataset\n        call: google-bigquery.deletedataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/tables\n      name: listtables\n      operations:\n      - method: GET\n        name: listtables\n        description: Google BigQuery List tables\n        call: google-bigquery.listtables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/tables\n      name: inserttable\n      operations:\n      - method: POST\n        name: inserttable\n        description: Google BigQuery Create a table\n        call: google-bigquery.inserttable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}\n      name: gettable\n      operations:\n      - method: GET\n        name: gettable\n        description: Google BigQuery Get table\n        call: google-bigquery.gettable\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}\n      name: patchtable\n      operations:\n      - method: PATCH\n        name: patchtable\n        description: Google BigQuery Partially update table\n        call: google-bigquery.patchtable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}\n      name: deletetable\n      operations:\n      - method: DELETE\n        name: deletetable\n        description: Google BigQuery Delete table\n        call: google-bigquery.deletetable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}/data\n      name: listtabledata\n      operations:\n      - method: GET\n        name: listtabledata\n        description: Google BigQuery List table rows\n        call: google-bigquery.listtabledata\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/tables/{tableId}/insertAll\n      name: insertalltabledata\n      operations:\n      - method: POST\n        name: insertalltabledata\n        description: Google BigQuery Insert rows\n        call: google-bigquery.insertalltabledata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/jobs\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: Google BigQuery List jobs\n        call: google-bigquery.listjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/jobs\n      name: insertjob\n      operations:\n      - method: POST\n        name: insertjob\n        description: Google BigQuery Submit a job\n        call: google-bigquery.insertjob\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /projects/{projectId}/jobs/{jobId}\n      name: getjob\n      operations:\n      - method: GET\n        name: getjob\n        description: Google BigQuery Get job\n        call: google-bigquery.getjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/jobs/{jobId}\n      name: deletejob\n      operations:\n      - method: DELETE\n        name: deletejob\n        description: Google BigQuery Delete job\n        call: google-bigquery.deletejob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/jobs/{jobId}/cancel\n      name: canceljob\n      operations:\n      - method: POST\n        name: canceljob\n        description: Google BigQuery Cancel job\n        call: google-bigquery.canceljob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/queries\n      name: queryjobs\n      operations:\n\
  \      - method: POST\n        name: queryjobs\n        description: Google BigQuery Execute query\n        call: google-bigquery.queryjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/queries/{jobId}\n      name: getqueryresults\n      operations:\n      - method: GET\n        name: getqueryresults\n        description: Google BigQuery Get query results\n        call: google-bigquery.getqueryresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/models\n      name: listmodels\n      operations:\n      - method: GET\n        name: listmodels\n        description: Google BigQuery List models\n        call: google-bigquery.listmodels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/models/{modelId}\n      name: getmodel\n      operations:\n      - method: GET\n  \
  \      name: getmodel\n        description: Google BigQuery Get model\n        call: google-bigquery.getmodel\n        with:\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/models/{modelId}\n      name: patchmodel\n      operations:\n      - method: PATCH\n        name: patchmodel\n        description: Google BigQuery Update model\n        call: google-bigquery.patchmodel\n        with:\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/models/{modelId}\n      name: deletemodel\n      operations:\n      - method: DELETE\n        name: deletemodel\n        description: Google BigQuery Delete model\n        call: google-bigquery.deletemodel\n        with:\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /projects/{projectId}/datasets/{datasetId}/routines\n      name: listroutines\n      operations:\n      - method: GET\n        name: listroutines\n        description: Google BigQuery List routines\n        call: google-bigquery.listroutines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/routines\n      name: insertroutine\n      operations:\n      - method: POST\n        name: insertroutine\n        description: Google BigQuery Create a routine\n        call: google-bigquery.insertroutine\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/routines/{routineId}\n      name: getroutine\n      operations:\n      - method: GET\n        name: getroutine\n        description: Google BigQuery Get routine\n        call: google-bigquery.getroutine\n        with:\n          routineId: rest.routineId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/routines/{routineId}\n      name: updateroutine\n      operations:\n      - method: PUT\n        name: updateroutine\n        description: Google BigQuery Update routine\n        call: google-bigquery.updateroutine\n        with:\n          routineId: rest.routineId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/datasets/{datasetId}/routines/{routineId}\n      name: deleteroutine\n      operations:\n      - method: DELETE\n        name: deleteroutine\n        description: Google BigQuery Delete routine\n        call: google-bigquery.deleteroutine\n        with:\n          routineId: rest.routineId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-bigquery-mcp\n    transport: http\n    description: MCP adapter for Google BigQuery API for AI agent use.\n\
  \    tools:\n    - name: listprojects\n      description: Google BigQuery List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.listprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatasets\n      description: Google BigQuery List datasets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.listdatasets\n      with:\n        all: tools.all\n        filter: tools.filter\n      inputParameters:\n      - name: all\n        type: boolean\n        description: Whether to list all datasets, including hidden ones\n      - name: filter\n        type: string\n        description: Filter expression for filtering datasets by label\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertdataset\n      description: Google BigQuery Create a dataset\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.insertdataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdataset\n      description: Google BigQuery Get dataset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.getdataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchdataset\n      description: Google BigQuery Partially update dataset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.patchdataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedataset\n      description: Google BigQuery Update dataset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-bigquery.updatedataset\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: deletedataset\n      description: Google BigQuery Delete dataset\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-bigquery.deletedataset\n      with:\n        deleteContents: tools.deleteContents\n      inputParameters:\n      - name: deleteContents\n        type: boolean\n        description: If true, delete all the tables in the dataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtables\n      description: Google BigQuery List tables\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.listtables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inserttable\n      description: Google BigQuery Create a table\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.inserttable\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: gettable\n      description: Google BigQuery Get table\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.gettable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchtable\n      description: Google BigQuery Partially update table\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.patchtable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetable\n      description: Google BigQuery Delete table\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-bigquery.deletetable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtabledata\n      description: Google BigQuery List table rows\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-bigquery.listtabledata\n      with:\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: startIndex\n        type: integer\n        description: Zero-based index of the starting row to read\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertalltabledata\n      description: Google BigQuery Insert rows\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.insertalltabledata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobs\n      description: Google BigQuery List jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.listjobs\n      with:\n        projection: tools.projection\n        stateFilter: tools.stateFilter\n      inputParameters:\n      - name: projection\n        type: string\n        description:\
  \ Restricts information returned to a set of selected fields\n      - name: stateFilter\n        type: array\n        description: Filter for job state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertjob\n      description: Google BigQuery Submit a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.insertjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjob\n      description: Google BigQuery Get job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.getjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletejob\n      description: Google BigQuery Delete job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-bigquery.deletejob\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: canceljob\n      description: Google BigQuery Cancel job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.canceljob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queryjobs\n      description: Google BigQuery Execute query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.queryjobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getqueryresults\n      description: Google BigQuery Get query results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.getqueryresults\n      with:\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: startIndex\n        type: integer\n        description: Zero-based index of the starting row\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: listmodels\n      description: Google BigQuery List models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.listmodels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmodel\n      description: Google BigQuery Get model\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.getmodel\n      with:\n        modelId: tools.modelId\n      inputParameters:\n      - name: modelId\n        type: string\n        description: The ID of the model\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchmodel\n      description: Google BigQuery Update model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.patchmodel\n      with:\n        modelId: tools.modelId\n\
  \      inputParameters:\n      - name: modelId\n        type: string\n        description: The ID of the model\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemodel\n      description: Google BigQuery Delete model\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-bigquery.deletemodel\n      with:\n        modelId: tools.modelId\n      inputParameters:\n      - name: modelId\n        type: string\n        description: The ID of the model\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroutines\n      description: Google BigQuery List routines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.listroutines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertroutine\n      description: Google BigQuery Create\
  \ a routine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-bigquery.insertroutine\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getroutine\n      description: Google BigQuery Get routine\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-bigquery.getroutine\n      with:\n        routineId: tools.routineId\n      inputParameters:\n      - name: routineId\n        type: string\n        description: The ID of the routine\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateroutine\n      description: Google BigQuery Update routine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-bigquery.updateroutine\n      with:\n        routineId: tools.routineId\n      inputParameters:\n      - name: routineId\n        type:\
  \ string\n        description: The ID of the routine\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteroutine\n      description: Google BigQuery Delete routine\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-bigquery.deleteroutine\n      with:\n        routineId: tools.routineId\n      inputParameters:\n      - name: routineId\n        type: string\n        description: The ID of the routine\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_BIGQUERY_TOKEN: GOOGLE_BIGQUERY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-bigquery/refs/heads/main/capabilities/google-bigquery-capability.yaml
tags:
- Google
- Bigquery
- API
tools:
- description: Google BigQuery List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Google BigQuery List datasets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatasets
- description: Google BigQuery Create a dataset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertdataset
- description: Google BigQuery Get dataset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdataset
- description: Google BigQuery Partially update dataset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdataset
- description: Google BigQuery Update dataset
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedataset
- description: Google BigQuery Delete dataset
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedataset
- description: Google BigQuery List tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtables
- description: Google BigQuery Create a table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: inserttable
- description: Google BigQuery Get table
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettable
- description: Google BigQuery Partially update table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchtable
- description: Google BigQuery Delete table
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetable
- description: Google BigQuery List table rows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtabledata
- description: Google BigQuery Insert rows
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertalltabledata
- description: Google BigQuery List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Google BigQuery Submit a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertjob
- description: Google BigQuery Get job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: Google BigQuery Delete job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejob
- description: Google BigQuery Cancel job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: canceljob
- description: Google BigQuery Execute query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: queryjobs
- description: Google BigQuery Get query results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getqueryresults
- description: Google BigQuery List models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodels
- description: Google BigQuery Get model
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodel
- description: Google BigQuery Update model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchmodel
- description: Google BigQuery Delete model
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemodel
- description: Google BigQuery List routines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutines
- description: Google BigQuery Create a routine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertroutine
- description: Google BigQuery Get routine
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroutine
- description: Google BigQuery Update routine
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateroutine
- description: Google BigQuery Delete routine
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteroutine
---
