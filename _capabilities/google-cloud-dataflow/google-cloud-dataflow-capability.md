---
categories: []
consumed_apis: []
description: Manages Google Cloud Dataflow projects on Google Cloud Platform for creating and managing data processing pipelines, including job submission, monitoring, and resource management for both batch and streaming workloads.
layout: capability
name: Google Cloud Dataflow API
operations:
- description: Google Cloud Dataflow List aggregated jobs across all regions
  method: GET
  name: listaggregatedjobs
  path: /v1b3/projects/{projectId}/jobs:aggregated
- description: Google Cloud Dataflow List jobs in a project
  method: GET
  name: listprojectjobs
  path: /v1b3/projects/{projectId}/jobs
- description: Google Cloud Dataflow Create a Dataflow job in a project
  method: POST
  name: createprojectjob
  path: /v1b3/projects/{projectId}/jobs
- description: Google Cloud Dataflow Get a Dataflow job in a project
  method: GET
  name: getprojectjob
  path: /v1b3/projects/{projectId}/jobs/{jobId}
- description: Google Cloud Dataflow Update a Dataflow job in a project
  method: PUT
  name: updateprojectjob
  path: /v1b3/projects/{projectId}/jobs/{jobId}
- description: Google Cloud Dataflow Snapshot a Dataflow job in a project
  method: POST
  name: snapshotprojectjob
  path: /v1b3/projects/{projectId}/jobs/{jobId}:snapshot
- description: Google Cloud Dataflow Get metrics for a Dataflow job in a project
  method: GET
  name: getprojectjobmetrics
  path: /v1b3/projects/{projectId}/jobs/{jobId}/metrics
- description: Google Cloud Dataflow List messages for a Dataflow job in a project
  method: GET
  name: listprojectjobmessages
  path: /v1b3/projects/{projectId}/jobs/{jobId}/messages
- description: Google Cloud Dataflow List jobs in a specific location
  method: GET
  name: listlocationjobs
  path: /v1b3/projects/{projectId}/locations/{location}/jobs
- description: Google Cloud Dataflow Create a Dataflow job in a specific location
  method: POST
  name: createlocationjob
  path: /v1b3/projects/{projectId}/locations/{location}/jobs
- description: Google Cloud Dataflow Get a Dataflow job in a specific location
  method: GET
  name: getlocationjob
  path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}
- description: Google Cloud Dataflow Update a Dataflow job in a specific location
  method: PUT
  name: updatelocationjob
  path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}
- description: Google Cloud Dataflow Snapshot a Dataflow job in a specific location
  method: POST
  name: snapshotlocationjob
  path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}:snapshot
- description: Google Cloud Dataflow Get metrics for a Dataflow job in a specific location
  method: GET
  name: getlocationjobmetrics
  path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/metrics
- description: Google Cloud Dataflow List messages for a Dataflow job in a specific location
  method: GET
  name: listlocationjobmessages
  path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/messages
- description: Google Cloud Dataflow Get execution details for a Dataflow job
  method: GET
  name: getlocationjobexecutiondetails
  path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/executionDetails
- description: Google Cloud Dataflow Get stage execution details for a Dataflow job
  method: GET
  name: getlocationjobstageexecutiondetails
  path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/stages/{stageId}/executionDetails
- description: Google Cloud Dataflow Get a snapshot in a specific location
  method: GET
  name: getlocationsnapshot
  path: /v1b3/projects/{projectId}/locations/{location}/snapshots/{snapshotId}
- description: Google Cloud Dataflow Delete a snapshot in a specific location
  method: DELETE
  name: deletelocationsnapshot
  path: /v1b3/projects/{projectId}/locations/{location}/snapshots/{snapshotId}
- description: Google Cloud Dataflow List snapshots in a specific location
  method: GET
  name: listlocationsnapshots
  path: /v1b3/projects/{projectId}/locations/{location}/snapshots
- description: Google Cloud Dataflow Get debug configuration for a job component
  method: POST
  name: getlocationjobdebugconfig
  path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/debug/getConfig
- description: Google Cloud Dataflow Send debug capture data for a job component
  method: POST
  name: sendlocationjobdebugcapture
  path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/debug/sendCapture
- description: Google Cloud Dataflow Launch a Flex Template job in a specific location
  method: POST
  name: launchlocationflextemplate
  path: /v1b3/projects/{projectId}/locations/{location}/flexTemplates:launch
- description: Google Cloud Dataflow Create a job from a template in a specific location
  method: POST
  name: createlocationjobfromtemplate
  path: /v1b3/projects/{projectId}/locations/{location}/templates
- description: Google Cloud Dataflow Get template metadata in a specific location
  method: GET
  name: getlocationtemplate
  path: /v1b3/projects/{projectId}/locations/{location}/templates:get
- description: Google Cloud Dataflow Launch a template job in a specific location
  method: POST
  name: launchlocationtemplate
  path: /v1b3/projects/{projectId}/locations/{location}/templates:launch
- description: Google Cloud Dataflow Create a job from a template in a project
  method: POST
  name: createprojectjobfromtemplate
  path: /v1b3/projects/{projectId}/templates
- description: Google Cloud Dataflow Get template metadata in a project
  method: GET
  name: getprojecttemplate
  path: /v1b3/projects/{projectId}/templates:get
- description: Google Cloud Dataflow Launch a template job in a project
  method: POST
  name: launchprojecttemplate
  path: /v1b3/projects/{projectId}/templates:launch
personas: []
provider_name: Google Cloud Dataflow
provider_slug: google-cloud-dataflow
search_terms:
- google cloud dataflow snapshot a dataflow job in a project
- createprojectjob
- google cloud dataflow send debug capture data for a job component
- google cloud dataflow launch a flex template job in a specific location
- google cloud dataflow get debug configuration for a job component
- big data
- google cloud dataflow snapshot a dataflow job in a specific location
- google cloud dataflow create a dataflow job in a specific location
- google cloud dataflow update a dataflow job in a specific location
- apache beam
- snapshotlocationjob
- google cloud dataflow get execution details for a dataflow job
- snapshotprojectjob
- google cloud dataflow get metrics for a dataflow job in a project
- updatelocationjob
- google cloud dataflow get a snapshot in a specific location
- cloud
- launchlocationflextemplate
- google cloud dataflow list snapshots in a specific location
- google
- etl
- listlocationjobs
- sendlocationjobdebugcapture
- listprojectjobmessages
- google cloud dataflow list messages for a dataflow job in a project
- google cloud dataflow get stage execution details for a dataflow job
- google cloud dataflow list messages for a dataflow job in a specific location
- launchlocationtemplate
- listaggregatedjobs
- getlocationjobstageexecutiondetails
- listprojectjobs
- getlocationjobexecutiondetails
- listlocationsnapshots
- google cloud dataflow get a dataflow job in a specific location
- createlocationjob
- listlocationjobmessages
- getlocationjobdebugconfig
- google cloud dataflow create a job from a template in a project
- google cloud dataflow get a dataflow job in a project
- api
- getprojecttemplate
- getlocationtemplate
- google cloud dataflow update a dataflow job in a project
- getprojectjobmetrics
- google cloud dataflow get metrics for a dataflow job in a specific location
- google cloud dataflow launch a template job in a specific location
- google cloud dataflow list jobs in a specific location
- getlocationsnapshot
- google cloud dataflow create a job from a template in a specific location
- updateprojectjob
- stream processing
- getprojectjob
- google cloud dataflow list aggregated jobs across all regions
- google cloud dataflow get template metadata in a specific location
- batch processing
- createprojectjobfromtemplate
- getlocationjobmetrics
- dataflow
- createlocationjobfromtemplate
- getlocationjob
- launchprojecttemplate
- google cloud dataflow launch a template job in a project
- google cloud dataflow create a dataflow job in a project
- google cloud dataflow delete a snapshot in a specific location
- deletelocationsnapshot
- google cloud dataflow list jobs in a project
- google cloud dataflow get template metadata in a project
- data processing
slug: google-cloud-dataflow-capability
source_filename: google-cloud-dataflow-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Dataflow API\n  description: Manages Google Cloud Dataflow projects on Google Cloud Platform for creating and managing data processing pipelines,\n    including job submission, monitoring, and resource management for both batch and streaming workloads.\n  tags:\n  - Google\n  - Cloud\n  - Dataflow\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-dataflow\n    baseUri: https://dataflow.googleapis.com\n    description: Google Cloud Dataflow API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_DATAFLOW_TOKEN}}'\n    resources:\n    - name: v1b3-projects-projectid-jobs-aggregated\n      path: /v1b3/projects/{projectId}/jobs:aggregated\n      operations:\n      - name: listaggregatedjobs\n        method: GET\n        description: Google Cloud Dataflow List aggregated jobs across all regions\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-jobs\n      path: /v1b3/projects/{projectId}/jobs\n      operations:\n      - name: listprojectjobs\n        method: GET\n        description: Google Cloud Dataflow List jobs in a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprojectjob\n        method: POST\n        description: Google Cloud Dataflow Create a Dataflow job in a project\n        inputParameters:\n        - name: replaceJobId\n          in: query\n          type: string\n          description: Deprecated. The ID of the job to replace when updating a pipeline.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-jobs-jobid\n      path: /v1b3/projects/{projectId}/jobs/{jobId}\n\
  \      operations:\n      - name: getprojectjob\n        method: GET\n        description: Google Cloud Dataflow Get a Dataflow job in a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateprojectjob\n        method: PUT\n        description: Google Cloud Dataflow Update a Dataflow job in a project\n        inputParameters:\n        - name: updateMask\n          in: query\n          type: string\n          description: The list of fields to update relative to the job. If empty, only the requestedState field will be considered.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-jobs-jobid-snapshot\n      path: /v1b3/projects/{projectId}/jobs/{jobId}:snapshot\n      operations:\n      - name: snapshotprojectjob\n        method: POST\n        description: Google Cloud Dataflow\
  \ Snapshot a Dataflow job in a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-jobs-jobid-metrics\n      path: /v1b3/projects/{projectId}/jobs/{jobId}/metrics\n      operations:\n      - name: getprojectjobmetrics\n        method: GET\n        description: Google Cloud Dataflow Get metrics for a Dataflow job in a project\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          description: Return only metric data that has changed since this time. Default is to return all information about\n            all metrics for the job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-jobs-jobid-messages\n      path: /v1b3/projects/{projectId}/jobs/{jobId}/messages\n      operations:\n      - name: listprojectjobmessages\n\
  \        method: GET\n        description: Google Cloud Dataflow List messages for a Dataflow job in a project\n        inputParameters:\n        - name: minimumImportance\n          in: query\n          type: string\n          description: Filter to return only messages with at least this importance level.\n        - name: startTime\n          in: query\n          type: string\n          description: Return messages with timestamps greater than or equal to this value.\n        - name: endTime\n          in: query\n          type: string\n          description: Return messages with timestamps less than this value.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-jobs\n      path: /v1b3/projects/{projectId}/locations/{location}/jobs\n      operations:\n      - name: listlocationjobs\n        method: GET\n        description: Google Cloud Dataflow List jobs\
  \ in a specific location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlocationjob\n        method: POST\n        description: Google Cloud Dataflow Create a Dataflow job in a specific location\n        inputParameters:\n        - name: replaceJobId\n          in: query\n          type: string\n          description: Deprecated. The ID of the job to replace when updating a pipeline.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-jobs-\n      path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}\n      operations:\n      - name: getlocationjob\n        method: GET\n        description: Google Cloud Dataflow Get a Dataflow job in a specific location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n      - name: updatelocationjob\n        method: PUT\n        description: Google Cloud Dataflow Update a Dataflow job in a specific location\n        inputParameters:\n        - name: updateMask\n          in: query\n          type: string\n          description: The list of fields to update relative to the job. If empty, only the requestedState field will be considered.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-jobs-\n      path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}:snapshot\n      operations:\n      - name: snapshotlocationjob\n        method: POST\n        description: Google Cloud Dataflow Snapshot a Dataflow job in a specific location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-jobs-\n\
  \      path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/metrics\n      operations:\n      - name: getlocationjobmetrics\n        method: GET\n        description: Google Cloud Dataflow Get metrics for a Dataflow job in a specific location\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          description: Return only metric data that has changed since this time. Default is to return all information about\n            all metrics for the job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-jobs-\n      path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/messages\n      operations:\n      - name: listlocationjobmessages\n        method: GET\n        description: Google Cloud Dataflow List messages for a Dataflow job in a specific location\n        inputParameters:\n   \
  \     - name: minimumImportance\n          in: query\n          type: string\n          description: Filter to return only messages with at least this importance level.\n        - name: startTime\n          in: query\n          type: string\n          description: Return messages with timestamps greater than or equal to this value.\n        - name: endTime\n          in: query\n          type: string\n          description: Return messages with timestamps less than this value.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-jobs-\n      path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/executionDetails\n      operations:\n      - name: getlocationjobexecutiondetails\n        method: GET\n        description: Google Cloud Dataflow Get execution details for a Dataflow job\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-jobs-\n      path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/stages/{stageId}/executionDetails\n      operations:\n      - name: getlocationjobstageexecutiondetails\n        method: GET\n        description: Google Cloud Dataflow Get stage execution details for a Dataflow job\n        inputParameters:\n        - name: stageId\n          in: path\n          type: string\n          required: true\n          description: The stage for which to fetch information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-snaps\n      path: /v1b3/projects/{projectId}/locations/{location}/snapshots/{snapshotId}\n      operations:\n      - name: getlocationsnapshot\n        method: GET\n        description: Google Cloud Dataflow Get a snapshot\
  \ in a specific location\n        inputParameters:\n        - name: snapshotId\n          in: path\n          type: string\n          required: true\n          description: The ID of the snapshot to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelocationsnapshot\n        method: DELETE\n        description: Google Cloud Dataflow Delete a snapshot in a specific location\n        inputParameters:\n        - name: snapshotId\n          in: path\n          type: string\n          required: true\n          description: The ID of the snapshot to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-snaps\n      path: /v1b3/projects/{projectId}/locations/{location}/snapshots\n      operations:\n      - name: listlocationsnapshots\n        method: GET\n\
  \        description: Google Cloud Dataflow List snapshots in a specific location\n        inputParameters:\n        - name: jobId\n          in: query\n          type: string\n          description: If specified, list snapshots created from this job only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-jobs-\n      path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/debug/getConfig\n      operations:\n      - name: getlocationjobdebugconfig\n        method: POST\n        description: Google Cloud Dataflow Get debug configuration for a job component\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-jobs-\n      path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/debug/sendCapture\n      operations:\n\
  \      - name: sendlocationjobdebugcapture\n        method: POST\n        description: Google Cloud Dataflow Send debug capture data for a job component\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-flext\n      path: /v1b3/projects/{projectId}/locations/{location}/flexTemplates:launch\n      operations:\n      - name: launchlocationflextemplate\n        method: POST\n        description: Google Cloud Dataflow Launch a Flex Template job in a specific location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-templ\n      path: /v1b3/projects/{projectId}/locations/{location}/templates\n      operations:\n      - name: createlocationjobfromtemplate\n        method: POST\n        description: Google Cloud Dataflow Create a\
  \ job from a template in a specific location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-templ\n      path: /v1b3/projects/{projectId}/locations/{location}/templates:get\n      operations:\n      - name: getlocationtemplate\n        method: GET\n        description: Google Cloud Dataflow Get template metadata in a specific location\n        inputParameters:\n        - name: gcsPath\n          in: query\n          type: string\n          required: true\n          description: Required. A Cloud Storage path to the template from which to create the job. Must be a valid Cloud\n            Storage URL beginning with gs://.\n        - name: view\n          in: query\n          type: string\n          description: The view to retrieve. Defaults to METADATA_ONLY.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: v1b3-projects-projectid-locations-location-templ\n      path: /v1b3/projects/{projectId}/locations/{location}/templates:launch\n      operations:\n      - name: launchlocationtemplate\n        method: POST\n        description: Google Cloud Dataflow Launch a template job in a specific location\n        inputParameters:\n        - name: gcsPath\n          in: query\n          type: string\n          description: A Cloud Storage path to the template from which to create the job. Must be a valid Cloud Storage URL\n            beginning with gs://.\n        - name: validateOnly\n          in: query\n          type: boolean\n          description: If true, the request is validated but not actually executed. Defaults to false.\n        - name: dynamicTemplate.gcsPath\n          in: query\n          type: string\n          description: Path to the dynamic template spec file on Cloud Storage.\n        - name: dynamicTemplate.stagingLocation\n        \
  \  in: query\n          type: string\n          description: Cloud Storage path for staging dependencies.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-templates\n      path: /v1b3/projects/{projectId}/templates\n      operations:\n      - name: createprojectjobfromtemplate\n        method: POST\n        description: Google Cloud Dataflow Create a job from a template in a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-templates-get\n      path: /v1b3/projects/{projectId}/templates:get\n      operations:\n      - name: getprojecttemplate\n        method: GET\n        description: Google Cloud Dataflow Get template metadata in a project\n        inputParameters:\n        - name: gcsPath\n          in: query\n          type: string\n          required:\
  \ true\n          description: Required. A Cloud Storage path to the template from which to create the job. Must be a valid Cloud\n            Storage URL beginning with gs://.\n        - name: view\n          in: query\n          type: string\n          description: The view to retrieve. Defaults to METADATA_ONLY.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1b3-projects-projectid-templates-launch\n      path: /v1b3/projects/{projectId}/templates:launch\n      operations:\n      - name: launchprojecttemplate\n        method: POST\n        description: Google Cloud Dataflow Launch a template job in a project\n        inputParameters:\n        - name: gcsPath\n          in: query\n          type: string\n          description: A Cloud Storage path to the template from which to create the job. Must be a valid Cloud Storage URL\n            beginning with gs://.\n        - name: validateOnly\n\
  \          in: query\n          type: boolean\n          description: If true, the request is validated but not actually executed. Defaults to false.\n        - name: dynamicTemplate.gcsPath\n          in: query\n          type: string\n          description: Path to the dynamic template spec file on Cloud Storage.\n        - name: dynamicTemplate.stagingLocation\n          in: query\n          type: string\n          description: Cloud Storage path for staging dependencies.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-dataflow-rest\n    description: REST adapter for Google Cloud Dataflow API.\n    resources:\n    - path: /v1b3/projects/{projectId}/jobs:aggregated\n      name: listaggregatedjobs\n      operations:\n      - method: GET\n        name: listaggregatedjobs\n        description: Google Cloud Dataflow List aggregated jobs across\
  \ all regions\n        call: google-cloud-dataflow.listaggregatedjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/jobs\n      name: listprojectjobs\n      operations:\n      - method: GET\n        name: listprojectjobs\n        description: Google Cloud Dataflow List jobs in a project\n        call: google-cloud-dataflow.listprojectjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/jobs\n      name: createprojectjob\n      operations:\n      - method: POST\n        name: createprojectjob\n        description: Google Cloud Dataflow Create a Dataflow job in a project\n        call: google-cloud-dataflow.createprojectjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/jobs/{jobId}\n      name: getprojectjob\n      operations:\n      - method: GET\n        name: getprojectjob\n        description:\
  \ Google Cloud Dataflow Get a Dataflow job in a project\n        call: google-cloud-dataflow.getprojectjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/jobs/{jobId}\n      name: updateprojectjob\n      operations:\n      - method: PUT\n        name: updateprojectjob\n        description: Google Cloud Dataflow Update a Dataflow job in a project\n        call: google-cloud-dataflow.updateprojectjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/jobs/{jobId}:snapshot\n      name: snapshotprojectjob\n      operations:\n      - method: POST\n        name: snapshotprojectjob\n        description: Google Cloud Dataflow Snapshot a Dataflow job in a project\n        call: google-cloud-dataflow.snapshotprojectjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/jobs/{jobId}/metrics\n      name: getprojectjobmetrics\n\
  \      operations:\n      - method: GET\n        name: getprojectjobmetrics\n        description: Google Cloud Dataflow Get metrics for a Dataflow job in a project\n        call: google-cloud-dataflow.getprojectjobmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/jobs/{jobId}/messages\n      name: listprojectjobmessages\n      operations:\n      - method: GET\n        name: listprojectjobmessages\n        description: Google Cloud Dataflow List messages for a Dataflow job in a project\n        call: google-cloud-dataflow.listprojectjobmessages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs\n      name: listlocationjobs\n      operations:\n      - method: GET\n        name: listlocationjobs\n        description: Google Cloud Dataflow List jobs in a specific location\n        call: google-cloud-dataflow.listlocationjobs\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs\n      name: createlocationjob\n      operations:\n      - method: POST\n        name: createlocationjob\n        description: Google Cloud Dataflow Create a Dataflow job in a specific location\n        call: google-cloud-dataflow.createlocationjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}\n      name: getlocationjob\n      operations:\n      - method: GET\n        name: getlocationjob\n        description: Google Cloud Dataflow Get a Dataflow job in a specific location\n        call: google-cloud-dataflow.getlocationjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}\n      name: updatelocationjob\n      operations:\n      - method: PUT\n        name:\
  \ updatelocationjob\n        description: Google Cloud Dataflow Update a Dataflow job in a specific location\n        call: google-cloud-dataflow.updatelocationjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}:snapshot\n      name: snapshotlocationjob\n      operations:\n      - method: POST\n        name: snapshotlocationjob\n        description: Google Cloud Dataflow Snapshot a Dataflow job in a specific location\n        call: google-cloud-dataflow.snapshotlocationjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/metrics\n      name: getlocationjobmetrics\n      operations:\n      - method: GET\n        name: getlocationjobmetrics\n        description: Google Cloud Dataflow Get metrics for a Dataflow job in a specific location\n        call: google-cloud-dataflow.getlocationjobmetrics\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/messages\n      name: listlocationjobmessages\n      operations:\n      - method: GET\n        name: listlocationjobmessages\n        description: Google Cloud Dataflow List messages for a Dataflow job in a specific location\n        call: google-cloud-dataflow.listlocationjobmessages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/executionDetails\n      name: getlocationjobexecutiondetails\n      operations:\n      - method: GET\n        name: getlocationjobexecutiondetails\n        description: Google Cloud Dataflow Get execution details for a Dataflow job\n        call: google-cloud-dataflow.getlocationjobexecutiondetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/stages/{stageId}/executionDetails\n\
  \      name: getlocationjobstageexecutiondetails\n      operations:\n      - method: GET\n        name: getlocationjobstageexecutiondetails\n        description: Google Cloud Dataflow Get stage execution details for a Dataflow job\n        call: google-cloud-dataflow.getlocationjobstageexecutiondetails\n        with:\n          stageId: rest.stageId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/snapshots/{snapshotId}\n      name: getlocationsnapshot\n      operations:\n      - method: GET\n        name: getlocationsnapshot\n        description: Google Cloud Dataflow Get a snapshot in a specific location\n        call: google-cloud-dataflow.getlocationsnapshot\n        with:\n          snapshotId: rest.snapshotId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/snapshots/{snapshotId}\n      name: deletelocationsnapshot\n\
  \      operations:\n      - method: DELETE\n        name: deletelocationsnapshot\n        description: Google Cloud Dataflow Delete a snapshot in a specific location\n        call: google-cloud-dataflow.deletelocationsnapshot\n        with:\n          snapshotId: rest.snapshotId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/snapshots\n      name: listlocationsnapshots\n      operations:\n      - method: GET\n        name: listlocationsnapshots\n        description: Google Cloud Dataflow List snapshots in a specific location\n        call: google-cloud-dataflow.listlocationsnapshots\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/debug/getConfig\n      name: getlocationjobdebugconfig\n      operations:\n      - method: POST\n        name: getlocationjobdebugconfig\n        description: Google Cloud Dataflow\
  \ Get debug configuration for a job component\n        call: google-cloud-dataflow.getlocationjobdebugconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/jobs/{jobId}/debug/sendCapture\n      name: sendlocationjobdebugcapture\n      operations:\n      - method: POST\n        name: sendlocationjobdebugcapture\n        description: Google Cloud Dataflow Send debug capture data for a job component\n        call: google-cloud-dataflow.sendlocationjobdebugcapture\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/flexTemplates:launch\n      name: launchlocationflextemplate\n      operations:\n      - method: POST\n        name: launchlocationflextemplate\n        description: Google Cloud Dataflow Launch a Flex Template job in a specific location\n        call: google-cloud-dataflow.launchlocationflextemplate\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/templates\n      name: createlocationjobfromtemplate\n      operations:\n      - method: POST\n        name: createlocationjobfromtemplate\n        description: Google Cloud Dataflow Create a job from a template in a specific location\n        call: google-cloud-dataflow.createlocationjobfromtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/templates:get\n      name: getlocationtemplate\n      operations:\n      - method: GET\n        name: getlocationtemplate\n        description: Google Cloud Dataflow Get template metadata in a specific location\n        call: google-cloud-dataflow.getlocationtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/locations/{location}/templates:launch\n      name: launchlocationtemplate\n\
  \      operations:\n      - method: POST\n        name: launchlocationtemplate\n        description: Google Cloud Dataflow Launch a template job in a specific location\n        call: google-cloud-dataflow.launchlocationtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/templates\n      name: createprojectjobfromtemplate\n      operations:\n      - method: POST\n        name: createprojectjobfromtemplate\n        description: Google Cloud Dataflow Create a job from a template in a project\n        call: google-cloud-dataflow.createprojectjobfromtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/templates:get\n      name: getprojecttemplate\n      operations:\n      - method: GET\n        name: getprojecttemplate\n        description: Google Cloud Dataflow Get template metadata in a project\n        call: google-cloud-dataflow.getprojecttemplate\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1b3/projects/{projectId}/templates:launch\n      name: launchprojecttemplate\n      operations:\n      - method: POST\n        name: launchprojecttemplate\n        description: Google Cloud Dataflow Launch a template job in a project\n        call: google-cloud-dataflow.launchprojecttemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-dataflow-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Dataflow API for AI agent use.\n    tools:\n    - name: listaggregatedjobs\n      description: Google Cloud Dataflow List aggregated jobs across all regions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dataflow.listaggregatedjobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojectjobs\n \
  \     description: Google Cloud Dataflow List jobs in a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dataflow.listprojectjobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createprojectjob\n      description: Google Cloud Dataflow Create a Dataflow job in a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dataflow.createprojectjob\n      with:\n        replaceJobId: tools.replaceJobId\n      inputParameters:\n      - name: replaceJobId\n        type: string\n        description: Deprecated. The ID of the job to replace when updating a pipeline.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprojectjob\n      description: Google Cloud Dataflow Get a Dataflow job in a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: google-cloud-dataflow.getprojectjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateprojectjob\n      description: Google Cloud Dataflow Update a Dataflow job in a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-cloud-dataflow.updateprojectjob\n      with:\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: updateMask\n        type: string\n        description: The list of fields to update relative to the job. If empty, only the requestedState field will be considered.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: snapshotprojectjob\n      description: Google Cloud Dataflow Snapshot a Dataflow job in a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dataflow.snapshotprojectjob\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getprojectjobmetrics\n      description: Google Cloud Dataflow Get metrics for a Dataflow job in a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dataflow.getprojectjobmetrics\n      with:\n        startTime: tools.startTime\n      inputParameters:\n      - name: startTime\n        type: string\n        description: Return only metric data that has changed since this time. Default is to return all information about\n          all metrics for the job.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojectjobmessages\n      description: Google Cloud Dataflow List messages for a Dataflow job in a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dataflow.listprojectjobmessages\n      with:\n        minimumImportance: tools.minimumImportance\n        startTime: tools.startTime\n\
  \        endTime: tools.endTime\n      inputParameters:\n      - name: minimumImportance\n        type: string\n        description: Filter to return only messages with at least this importance level.\n      - name: startTime\n        type: string\n        description: Return messages with timestamps greater than or equal to this value.\n      - name: endTime\n        type: string\n        description: Return messages with timestamps less than this value.\n \n\n# --- truncated at 32 KB (43 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/google-cloud-dataflow/refs/heads/main/capabilities/google-cloud-dataflow-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-dataflow/refs/heads/main/capabilities/google-cloud-dataflow-capability.yaml
tags:
- Google
- Cloud
- Dataflow
- API
tools:
- description: Google Cloud Dataflow List aggregated jobs across all regions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaggregatedjobs
- description: Google Cloud Dataflow List jobs in a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectjobs
- description: Google Cloud Dataflow Create a Dataflow job in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectjob
- description: Google Cloud Dataflow Get a Dataflow job in a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectjob
- description: Google Cloud Dataflow Update a Dataflow job in a project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprojectjob
- description: Google Cloud Dataflow Snapshot a Dataflow job in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: snapshotprojectjob
- description: Google Cloud Dataflow Get metrics for a Dataflow job in a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectjobmetrics
- description: Google Cloud Dataflow List messages for a Dataflow job in a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectjobmessages
- description: Google Cloud Dataflow List jobs in a specific location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocationjobs
- description: Google Cloud Dataflow Create a Dataflow job in a specific location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlocationjob
- description: Google Cloud Dataflow Get a Dataflow job in a specific location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationjob
- description: Google Cloud Dataflow Update a Dataflow job in a specific location
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelocationjob
- description: Google Cloud Dataflow Snapshot a Dataflow job in a specific location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: snapshotlocationjob
- description: Google Cloud Dataflow Get metrics for a Dataflow job in a specific location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationjobmetrics
- description: Google Cloud Dataflow List messages for a Dataflow job in a specific location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocationjobmessages
- description: Google Cloud Dataflow Get execution details for a Dataflow job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationjobexecutiondetails
- description: Google Cloud Dataflow Get stage execution details for a Dataflow job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationjobstageexecutiondetails
- description: Google Cloud Dataflow Get a snapshot in a specific location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationsnapshot
- description: Google Cloud Dataflow Delete a snapshot in a specific location
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelocationsnapshot
- description: Google Cloud Dataflow List snapshots in a specific location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocationsnapshots
- description: Google Cloud Dataflow Get debug configuration for a job component
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getlocationjobdebugconfig
- description: Google Cloud Dataflow Send debug capture data for a job component
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendlocationjobdebugcapture
- description: Google Cloud Dataflow Launch a Flex Template job in a specific location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: launchlocationflextemplate
- description: Google Cloud Dataflow Create a job from a template in a specific location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlocationjobfromtemplate
- description: Google Cloud Dataflow Get template metadata in a specific location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationtemplate
- description: Google Cloud Dataflow Launch a template job in a specific location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: launchlocationtemplate
- description: Google Cloud Dataflow Create a job from a template in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectjobfromtemplate
- description: Google Cloud Dataflow Get template metadata in a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojecttemplate
- description: Google Cloud Dataflow Launch a template job in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: launchprojecttemplate
---
