---
categories: []
consumed_apis: []
description: The Cloud Scheduler API enables creation and management of scheduled jobs that run on a recurring basis. Jobs can target HTTP endpoints, Pub/Sub topics, or App Engine applications.
layout: capability
name: Google Cloud Scheduler API
operations:
- description: Google Cloud Scheduler List jobs
  method: GET
  name: listjobs
  path: /v1/projects/{project}/locations/{location}/jobs
- description: Google Cloud Scheduler Create a job
  method: POST
  name: createjob
  path: /v1/projects/{project}/locations/{location}/jobs
- description: Google Cloud Scheduler Get a job
  method: GET
  name: getjob
  path: /v1/projects/{project}/locations/{location}/jobs/{job}
- description: Google Cloud Scheduler Update a job
  method: PATCH
  name: updatejob
  path: /v1/projects/{project}/locations/{location}/jobs/{job}
- description: Google Cloud Scheduler Delete a job
  method: DELETE
  name: deletejob
  path: /v1/projects/{project}/locations/{location}/jobs/{job}
- description: Google Cloud Scheduler Pause a job
  method: POST
  name: pausejob
  path: /v1/projects/{project}/locations/{location}/jobs/{job}:pause
- description: Google Cloud Scheduler Resume a job
  method: POST
  name: resumejob
  path: /v1/projects/{project}/locations/{location}/jobs/{job}:resume
- description: Google Cloud Scheduler Run a job
  method: POST
  name: runjob
  path: /v1/projects/{project}/locations/{location}/jobs/{job}:run
personas: []
provider_name: Google Cloud Scheduler
provider_slug: google-cloud-scheduler
search_terms:
- google cloud scheduler update a job
- pausejob
- automation
- scheduler
- google cloud scheduler pause a job
- api
- google cloud scheduler delete a job
- listjobs
- google cloud scheduler create a job
- google
- updatejob
- resumejob
- runjob
- cloud
- deletejob
- google cloud scheduler list jobs
- google cloud scheduler get a job
- getjob
- google cloud scheduler resume a job
- google cloud scheduler run a job
- cron
- jobs
- scheduling
- google cloud
- createjob
slug: google-cloud-scheduler-capability
source_filename: google-cloud-scheduler-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Scheduler API\n  description: The Cloud Scheduler API enables creation and management of scheduled jobs that run on a recurring basis. Jobs\n    can target HTTP endpoints, Pub/Sub topics, or App Engine applications.\n  tags:\n  - Google\n  - Cloud\n  - Scheduler\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-scheduler\n    baseUri: https://cloudscheduler.googleapis.com\n    description: Google Cloud Scheduler API HTTP API.\n    resources:\n    - name: v1-projects-project-locations-location-jobs\n      path: /v1/projects/{project}/locations/{location}/jobs\n      operations:\n      - name: listjobs\n        method: GET\n        description: Google Cloud Scheduler List jobs\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n  \
  \        type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createjob\n        method: POST\n        description: Google Cloud Scheduler Create a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-jobs-job\n      path: /v1/projects/{project}/locations/{location}/jobs/{job}\n      operations:\n      - name: getjob\n        method: GET\n        description: Google Cloud Scheduler Get a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n       \
  \ - name: location\n          in: path\n          type: string\n          required: true\n        - name: job\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatejob\n        method: PATCH\n        description: Google Cloud Scheduler Update a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: job\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletejob\n        method: DELETE\n        description: Google Cloud Scheduler Delete a job\n        inputParameters:\n        - name: project\n\
  \          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: job\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-jobs-job-\n      path: /v1/projects/{project}/locations/{location}/jobs/{job}:pause\n      operations:\n      - name: pausejob\n        method: POST\n        description: Google Cloud Scheduler Pause a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: job\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-jobs-job-\n      path: /v1/projects/{project}/locations/{location}/jobs/{job}:resume\n      operations:\n      - name: resumejob\n        method: POST\n        description: Google Cloud Scheduler Resume a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: job\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-jobs-job-\n      path: /v1/projects/{project}/locations/{location}/jobs/{job}:run\n      operations:\n      - name: runjob\n        method: POST\n        description: Google Cloud Scheduler\
  \ Run a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: job\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-scheduler-rest\n    description: REST adapter for Google Cloud Scheduler API.\n    resources:\n    - path: /v1/projects/{project}/locations/{location}/jobs\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: Google Cloud Scheduler List jobs\n        call: google-cloud-scheduler.listjobs\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/jobs\n      name: createjob\n      operations:\n      - method: POST\n        name: createjob\n        description: Google Cloud Scheduler Create a job\n        call: google-cloud-scheduler.createjob\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/jobs/{job}\n      name: getjob\n      operations:\n      - method: GET\n        name: getjob\n        description: Google Cloud Scheduler Get a job\n        call: google-cloud-scheduler.getjob\n        with:\n          project: rest.project\n          location: rest.location\n          job: rest.job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/jobs/{job}\n      name: updatejob\n      operations:\n      - method: PATCH\n\
  \        name: updatejob\n        description: Google Cloud Scheduler Update a job\n        call: google-cloud-scheduler.updatejob\n        with:\n          project: rest.project\n          location: rest.location\n          job: rest.job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/jobs/{job}\n      name: deletejob\n      operations:\n      - method: DELETE\n        name: deletejob\n        description: Google Cloud Scheduler Delete a job\n        call: google-cloud-scheduler.deletejob\n        with:\n          project: rest.project\n          location: rest.location\n          job: rest.job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/jobs/{job}:pause\n      name: pausejob\n      operations:\n      - method: POST\n        name: pausejob\n        description: Google Cloud Scheduler Pause a job\n        call: google-cloud-scheduler.pausejob\n\
  \        with:\n          project: rest.project\n          location: rest.location\n          job: rest.job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/jobs/{job}:resume\n      name: resumejob\n      operations:\n      - method: POST\n        name: resumejob\n        description: Google Cloud Scheduler Resume a job\n        call: google-cloud-scheduler.resumejob\n        with:\n          project: rest.project\n          location: rest.location\n          job: rest.job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/jobs/{job}:run\n      name: runjob\n      operations:\n      - method: POST\n        name: runjob\n        description: Google Cloud Scheduler Run a job\n        call: google-cloud-scheduler.runjob\n        with:\n          project: rest.project\n          location: rest.location\n          job: rest.job\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-scheduler-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Scheduler API for AI agent use.\n    tools:\n    - name: listjobs\n      description: Google Cloud Scheduler List jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-scheduler.listjobs\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createjob\n      description: Google Cloud Scheduler Create a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: google-cloud-scheduler.createjob\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjob\n      description: Google Cloud Scheduler Get a job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-scheduler.getjob\n      with:\n        project: tools.project\n        location: tools.location\n        job: tools.job\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: job\n        type: string\n\
  \        description: job\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatejob\n      description: Google Cloud Scheduler Update a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-scheduler.updatejob\n      with:\n        project: tools.project\n        location: tools.location\n        job: tools.job\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: job\n        type: string\n        description: job\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletejob\n      description: Google Cloud Scheduler Delete a job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n    \
  \  call: google-cloud-scheduler.deletejob\n      with:\n        project: tools.project\n        location: tools.location\n        job: tools.job\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: job\n        type: string\n        description: job\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pausejob\n      description: Google Cloud Scheduler Pause a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-scheduler.pausejob\n      with:\n        project: tools.project\n        location: tools.location\n        job: tools.job\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n    \
  \    type: string\n        description: location\n        required: true\n      - name: job\n        type: string\n        description: job\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resumejob\n      description: Google Cloud Scheduler Resume a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-scheduler.resumejob\n      with:\n        project: tools.project\n        location: tools.location\n        job: tools.job\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: job\n        type: string\n        description: job\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runjob\n      description: Google Cloud Scheduler\
  \ Run a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-scheduler.runjob\n      with:\n        project: tools.project\n        location: tools.location\n        job: tools.job\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: job\n        type: string\n        description: job\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-scheduler/refs/heads/main/capabilities/google-cloud-scheduler-capability.yaml
tags:
- Google
- Cloud
- Scheduler
- API
tools:
- description: Google Cloud Scheduler List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Google Cloud Scheduler Create a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createjob
- description: Google Cloud Scheduler Get a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: Google Cloud Scheduler Update a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatejob
- description: Google Cloud Scheduler Delete a job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejob
- description: Google Cloud Scheduler Pause a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pausejob
- description: Google Cloud Scheduler Resume a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resumejob
- description: Google Cloud Scheduler Run a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runjob
---
