---
categories: []
consumed_apis: []
description: Manages batch processing workloads on Google Cloud, including job creation, scheduling, task execution, and resource provisioning.
layout: capability
name: Google Cloud Batch API
operations:
- description: Google Cloud Batch List Jobs
  method: GET
  name: listjobs
  path: /projects/{project}/locations/{location}/jobs
- description: Google Cloud Batch Create Job
  method: POST
  name: createjob
  path: /projects/{project}/locations/{location}/jobs
- description: Google Cloud Batch Get Job
  method: GET
  name: getjob
  path: /projects/{project}/locations/{location}/jobs/{jobId}
- description: Google Cloud Batch Delete Job
  method: DELETE
  name: deletejob
  path: /projects/{project}/locations/{location}/jobs/{jobId}
- description: Google Cloud Batch List Tasks
  method: GET
  name: listtasks
  path: /projects/{project}/locations/{location}/jobs/{jobId}/taskGroups/{taskGroupId}/tasks
- description: Google Cloud Batch Get Task
  method: GET
  name: gettask
  path: /projects/{project}/locations/{location}/jobs/{jobId}/taskGroups/{taskGroupId}/tasks/{taskId}
personas: []
provider_name: Google Cloud Batch
provider_slug: google-cloud-batch
search_terms:
- listtasks
- api
- google cloud batch delete job
- batch
- hpc
- gettask
- listjobs
- google
- google cloud batch create job
- google cloud batch get job
- cloud
- google cloud batch list tasks
- deletejob
- compute
- getjob
- jobs
- google cloud batch get task
- google cloud batch list jobs
- google cloud
- createjob
- batch processing
slug: google-cloud-batch-capability
source_filename: google-cloud-batch-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Batch API\n  description: Manages batch processing workloads on Google Cloud, including job creation, scheduling, task execution, and\n    resource provisioning.\n  tags:\n  - Google\n  - Cloud\n  - Batch\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-batch\n    baseUri: https://batch.googleapis.com/v1\n    description: Google Cloud Batch API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_BATCH_TOKEN}}'\n    resources:\n    - name: projects-project-locations-location-jobs\n      path: /projects/{project}/locations/{location}/jobs\n      operations:\n      - name: listjobs\n        method: GET\n        description: Google Cloud Batch List Jobs\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n\
  \          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createjob\n        method: POST\n        description: Google Cloud Batch Create Job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-jobs-jobid\n      path: /projects/{project}/locations/{location}/jobs/{jobId}\n      operations:\n      - name: getjob\n\
  \        method: GET\n        description: Google Cloud Batch Get Job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletejob\n        method: DELETE\n        description: Google Cloud Batch Delete Job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: projects-project-locations-location-jobs-jobid-t\n      path: /projects/{project}/locations/{location}/jobs/{jobId}/taskGroups/{taskGroupId}/tasks\n      operations:\n      - name: listtasks\n        method: GET\n        description: Google Cloud Batch List Tasks\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        - name: taskGroupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-jobs-jobid-t\n      path: /projects/{project}/locations/{location}/jobs/{jobId}/taskGroups/{taskGroupId}/tasks/{taskId}\n\
  \      operations:\n      - name: gettask\n        method: GET\n        description: Google Cloud Batch Get Task\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        - name: taskGroupId\n          in: path\n          type: string\n          required: true\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-batch-rest\n    description: REST adapter for Google Cloud Batch API.\n    resources:\n    - path: /projects/{project}/locations/{location}/jobs\n      name: listjobs\n      operations:\n\
  \      - method: GET\n        name: listjobs\n        description: Google Cloud Batch List Jobs\n        call: google-cloud-batch.listjobs\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/jobs\n      name: createjob\n      operations:\n      - method: POST\n        name: createjob\n        description: Google Cloud Batch Create Job\n        call: google-cloud-batch.createjob\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/jobs/{jobId}\n      name: getjob\n      operations:\n      - method: GET\n        name: getjob\n        description: Google Cloud Batch Get Job\n        call: google-cloud-batch.getjob\n        with:\n          project: rest.project\n          location:\
  \ rest.location\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/jobs/{jobId}\n      name: deletejob\n      operations:\n      - method: DELETE\n        name: deletejob\n        description: Google Cloud Batch Delete Job\n        call: google-cloud-batch.deletejob\n        with:\n          project: rest.project\n          location: rest.location\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/jobs/{jobId}/taskGroups/{taskGroupId}/tasks\n      name: listtasks\n      operations:\n      - method: GET\n        name: listtasks\n        description: Google Cloud Batch List Tasks\n        call: google-cloud-batch.listtasks\n        with:\n          project: rest.project\n          location: rest.location\n          jobId: rest.jobId\n          taskGroupId: rest.taskGroupId\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/jobs/{jobId}/taskGroups/{taskGroupId}/tasks/{taskId}\n      name: gettask\n      operations:\n      - method: GET\n        name: gettask\n        description: Google Cloud Batch Get Task\n        call: google-cloud-batch.gettask\n        with:\n          project: rest.project\n          location: rest.location\n          jobId: rest.jobId\n          taskGroupId: rest.taskGroupId\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-batch-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Batch API for AI agent use.\n    tools:\n    - name: listjobs\n      description: Google Cloud Batch List Jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-batch.listjobs\n     \
  \ with:\n        project: tools.project\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createjob\n      description: Google Cloud Batch Create Job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-batch.createjob\n      with:\n        project: tools.project\n        location: tools.location\n        jobId: tools.jobId\n      inputParameters:\n      - name: project\n        type: string\n        description:\
  \ project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjob\n      description: Google Cloud Batch Get Job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-batch.getjob\n      with:\n        project: tools.project\n        location: tools.location\n        jobId: tools.jobId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletejob\n      description:\
  \ Google Cloud Batch Delete Job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-batch.deletejob\n      with:\n        project: tools.project\n        location: tools.location\n        jobId: tools.jobId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtasks\n      description: Google Cloud Batch List Tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-batch.listtasks\n      with:\n        project: tools.project\n        location: tools.location\n        jobId: tools.jobId\n        taskGroupId: tools.taskGroupId\n\
  \      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      - name: taskGroupId\n        type: string\n        description: taskGroupId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettask\n      description: Google Cloud Batch Get Task\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-batch.gettask\n      with:\n        project: tools.project\n        location: tools.location\n        jobId: tools.jobId\n        taskGroupId: tools.taskGroupId\n        taskId: tools.taskId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n   \
  \   - name: location\n        type: string\n        description: location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      - name: taskGroupId\n        type: string\n        description: taskGroupId\n        required: true\n      - name: taskId\n        type: string\n        description: taskId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_BATCH_TOKEN: GOOGLE_CLOUD_BATCH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-batch/refs/heads/main/capabilities/google-cloud-batch-capability.yaml
tags:
- Google
- Cloud
- Batch
- API
tools:
- description: Google Cloud Batch List Jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Google Cloud Batch Create Job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createjob
- description: Google Cloud Batch Get Job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: Google Cloud Batch Delete Job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejob
- description: Google Cloud Batch List Tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtasks
- description: Google Cloud Batch Get Task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettask
---
