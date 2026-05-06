---
categories: []
consumed_apis: []
description: The Midjourney Image Generation API provides programmatic access to Midjourney's AI-powered image generation capabilities. Developers can submit text prompts to generate images, upscale selected outputs to higher resolutions, create variations of generated images, describe existing images to generate prompts, and blend multiple images together. The API uses an asynchronous job-based workflow where image generation requests return a job identifier that can be polled for status and results. Webhook callbacks are supported for real-time job status notifications. Enterprise API access is available
layout: capability
name: Midjourney Image Generation API
operations:
- description: Generate images from a text prompt
  method: POST
  name: createimaginejob
  path: /v1/imagine
- description: Upscale a generated image to higher resolution
  method: POST
  name: createupscalejob
  path: /v1/upscale
- description: Create variations of a generated image
  method: POST
  name: createvariationjob
  path: /v1/variations
- description: Generate text prompts from an image
  method: POST
  name: createdescribejob
  path: /v1/describe
- description: Blend multiple images together
  method: POST
  name: createblendjob
  path: /v1/blend
- description: Get the status and results of a job
  method: GET
  name: getjobstatus
  path: /v1/jobs/{jobId}
- description: List image generation jobs
  method: GET
  name: listjobs
  path: /v1/jobs
- description: Cancel a pending or in-progress job
  method: POST
  name: canceljob
  path: /v1/jobs/{jobId}/cancel
personas: []
provider_name: midjourney
provider_slug: midjourney
search_terms:
- generate text prompts from an image
- createvariationjob
- get the status and results of a job
- midjourney
- canceljob
- generate images from a text prompt
- api
- createdescribejob
- blend multiple images together
- getjobstatus
- list image generation jobs
- cancel a pending or in-progress job
- upscale a generated image to higher resolution
- listjobs
- createblendjob
- createupscalejob
- create variations of a generated image
- createimaginejob
slug: midjourney-capability
source_filename: midjourney-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Midjourney Image Generation API\n  description: The Midjourney Image Generation API provides programmatic access to Midjourney's AI-powered image generation\n    capabilities. Developers can submit text prompts to generate images, upscale selected outputs to higher resolutions, create\n    variations of generated images, describe existing images to generate prompts, and blend multiple images together. The\n    API uses an asynchronous job-based workflow where image generation requests return a job identifier that can be polled\n    for status and results. Webhook callbacks are supported for real-time job status notifications. Enterprise API access\n    is available\n  tags:\n  - Midjourney\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: midjourney\n    baseUri: https://api.midjourney.com\n    description: Midjourney Image Generation API HTTP API.\n    authentication:\n\
  \      type: bearer\n      token: '{{MIDJOURNEY_TOKEN}}'\n    resources:\n    - name: v1-imagine\n      path: /v1/imagine\n      operations:\n      - name: createimaginejob\n        method: POST\n        description: Generate images from a text prompt\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-upscale\n      path: /v1/upscale\n      operations:\n      - name: createupscalejob\n        method: POST\n        description: Upscale a generated image to higher resolution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-variations\n      path: /v1/variations\n      operations:\n      - name: createvariationjob\n        method: POST\n        description: Create variations of a generated image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: v1-describe\n      path: /v1/describe\n      operations:\n      - name: createdescribejob\n        method: POST\n        description: Generate text prompts from an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blend\n      path: /v1/blend\n      operations:\n      - name: createblendjob\n        method: POST\n        description: Blend multiple images together\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-jobs-jobid\n      path: /v1/jobs/{jobId}\n      operations:\n      - name: getjobstatus\n        method: GET\n        description: Get the status and results of a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-jobs\n      path: /v1/jobs\n      operations:\n   \
  \   - name: listjobs\n        method: GET\n        description: List image generation jobs\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter jobs by their current status.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of jobs to return per page.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of jobs to skip for pagination.\n        - name: sort\n          in: query\n          type: string\n          description: Sort order for the returned jobs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-jobs-jobid-cancel\n      path: /v1/jobs/{jobId}/cancel\n      operations:\n      - name: canceljob\n        method: POST\n        description: Cancel a pending or in-progress job\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: midjourney-rest\n    description: REST adapter for Midjourney Image Generation API.\n    resources:\n    - path: /v1/imagine\n      name: createimaginejob\n      operations:\n      - method: POST\n        name: createimaginejob\n        description: Generate images from a text prompt\n        call: midjourney.createimaginejob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/upscale\n      name: createupscalejob\n      operations:\n      - method: POST\n        name: createupscalejob\n        description: Upscale a generated image to higher resolution\n        call: midjourney.createupscalejob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/variations\n      name: createvariationjob\n      operations:\n      - method: POST\n        name: createvariationjob\n\
  \        description: Create variations of a generated image\n        call: midjourney.createvariationjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/describe\n      name: createdescribejob\n      operations:\n      - method: POST\n        name: createdescribejob\n        description: Generate text prompts from an image\n        call: midjourney.createdescribejob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blend\n      name: createblendjob\n      operations:\n      - method: POST\n        name: createblendjob\n        description: Blend multiple images together\n        call: midjourney.createblendjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobId}\n      name: getjobstatus\n      operations:\n      - method: GET\n        name: getjobstatus\n        description: Get the status and results of a job\n        call: midjourney.getjobstatus\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: List image generation jobs\n        call: midjourney.listjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobId}/cancel\n      name: canceljob\n      operations:\n      - method: POST\n        name: canceljob\n        description: Cancel a pending or in-progress job\n        call: midjourney.canceljob\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: midjourney-mcp\n    transport: http\n    description: MCP adapter for Midjourney Image Generation API for AI agent use.\n    tools:\n    - name: createimaginejob\n      description: Generate images from a text prompt\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ midjourney.createimaginejob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createupscalejob\n      description: Upscale a generated image to higher resolution\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: midjourney.createupscalejob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvariationjob\n      description: Create variations of a generated image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: midjourney.createvariationjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdescribejob\n      description: Generate text prompts from an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: midjourney.createdescribejob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createblendjob\n\
  \      description: Blend multiple images together\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: midjourney.createblendjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobstatus\n      description: Get the status and results of a job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: midjourney.getjobstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobs\n      description: List image generation jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: midjourney.listjobs\n      with:\n        status: tools.status\n        limit: tools.limit\n        offset: tools.offset\n        sort: tools.sort\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter jobs by their current status.\n      - name: limit\n\
  \        type: integer\n        description: Maximum number of jobs to return per page.\n      - name: offset\n        type: integer\n        description: Number of jobs to skip for pagination.\n      - name: sort\n        type: string\n        description: Sort order for the returned jobs.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: canceljob\n      description: Cancel a pending or in-progress job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: midjourney.canceljob\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MIDJOURNEY_TOKEN: MIDJOURNEY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/midjourney/refs/heads/main/capabilities/midjourney-capability.yaml
tags:
- Midjourney
- API
tools:
- description: Generate images from a text prompt
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimaginejob
- description: Upscale a generated image to higher resolution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createupscalejob
- description: Create variations of a generated image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvariationjob
- description: Generate text prompts from an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdescribejob
- description: Blend multiple images together
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createblendjob
- description: Get the status and results of a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobstatus
- description: List image generation jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Cancel a pending or in-progress job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: canceljob
---
