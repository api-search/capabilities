---
categories: []
consumed_apis:
- mediaconvert
description: Workflow capability for Amazon MediaConvert media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MediaConvert Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MediaConvert
provider_slug: amazon-mediaconvert
search_terms:
- aws
- aws media processing and delivery
- createjobtemplate
- canceljob
- list jobs
- list presets
- manage media processing jobs
- list job templates
- create job
- workflow
- associate certificate
- listjobtemplates
- Media Developer
- createjob
- media
- cancel job
- amazon mediaconvert media processing workflow
- listpresets
- media processing
- get job
- engineer managing broadcast media workflows
- Broadcast Engineer
- listjobs
- broadcasting
- getjob
- developer building media processing applications
- associatecertificate
- create job template
slug: amazon-mediaconvert-media-workflow
source_filename: amazon-mediaconvert-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon MediaConvert Workflow\n  description: Workflow capability for Amazon MediaConvert media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: mediaconvert\n    location: ./shared/mediaconvert.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mediaconvert-workflow-api\n    description: Unified REST API for Amazon MediaConvert workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: mediaconvert.list-jobs\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mediaconvert-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MediaConvert workflow management.\n    tools:\n    - name: associate-certificate\n      description: AssociateCertificate\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediaconvert.associate-certificate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job\n      description: GetJob\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediaconvert.get-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-job\n      description: CancelJob\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediaconvert.cancel-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: ListJobs\n      hints:\n \
  \       readOnly: true\n        openWorld: true\n      call: mediaconvert.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-job\n      description: CreateJob\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediaconvert.create-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-job-templates\n      description: ListJobTemplates\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediaconvert.list-job-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-job-template\n      description: CreateJobTemplate\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediaconvert.create-job-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-presets\n      description: ListPresets\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ mediaconvert.list-presets\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mediaconvert/refs/heads/main/capabilities/amazon-mediaconvert-media-workflow.yaml
tags:
- Media
- Broadcasting
- Workflow
tools:
- description: AssociateCertificate
  hints:
    openWorld: true
    readOnly: false
  name: associate-certificate
- description: GetJob
  hints:
    openWorld: true
    readOnly: true
  name: get-job
- description: CancelJob
  hints:
    openWorld: true
    readOnly: false
  name: cancel-job
- description: ListJobs
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: CreateJob
  hints:
    openWorld: true
    readOnly: false
  name: create-job
- description: ListJobTemplates
  hints:
    openWorld: true
    readOnly: true
  name: list-job-templates
- description: CreateJobTemplate
  hints:
    openWorld: true
    readOnly: false
  name: create-job-template
- description: ListPresets
  hints:
    openWorld: true
    readOnly: true
  name: list-presets
---
