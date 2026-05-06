---
categories: []
consumed_apis: []
description: Workflow capability for AI-powered video dubbing and content localization using Sync Labs. Enables single video generation, batch processing for large-scale dubbing, cost estimation before submission, and asset reuse. Ideal for content creators, studios, educational platforms, and enterprises localizing video content across multiple languages.
layout: capability
name: Sync Labs Video Dubbing and Localization
operations:
- description: Create an AI lip-sync generation
  method: POST
  name: create-generation
  path: /v1/generate
- description: List all generation jobs
  method: GET
  name: list-generations
  path: /v1/generate
- description: Get generation status and output video URL
  method: GET
  name: get-generation
  path: /v1/generate/{id}
- description: Estimate generation cost
  method: GET
  name: estimate-cost
  path: /v1/estimate
- description: Submit a batch of lip-sync generations
  method: POST
  name: create-batch
  path: /v1/batch
- description: List all batch jobs
  method: GET
  name: list-batches
  path: /v1/batch
- description: Get batch status and results
  method: GET
  name: get-batch
  path: /v1/batch/{id}
- description: List available lip-sync AI models
  method: GET
  name: list-models
  path: /v1/models
- description: List uploaded video and audio assets
  method: GET
  name: list-assets
  path: /v1/assets
personas: []
provider_name: Sync Labs
provider_slug: sync-labs
search_terms:
- content localization
- available ai models
- get batch status
- list generations
- dubbing
- visual ai
- single video generation
- list available models
- cost estimation
- check the status of a lip-sync generation and get the output video url when complete
- list available lip-sync ai models
- list uploaded assets
- get a cost estimate before submitting a lip-sync generation to avoid surprises
- create batch
- individual generation status and result
- check the progress and results of a batch dubbing job
- list all batch jobs
- generate a lip-synced video by combining source video with new audio track
- list uploaded video and audio assets
- create batch dubbing
- list previously uploaded video and audio assets available for reuse
- get batch
- sync labs
- create generation
- artificial intelligence
- list all lip-sync generation jobs with their statuses and output urls
- create lipsync video
- estimate generation cost
- get generation
- lip sync
- list all generation jobs
- submit multiple videos for batch lip-sync processing (up to 500 videos)
- video
- batch video generation
- get batch status and results
- media
- list models
- list assets
- get generation status
- submit a batch of lip-sync generations
- batch processing
- list all available sync labs ai models with quality/speed/cost tradeoffs
- uploaded media assets
- get generation status and output video url
- create an ai lip-sync generation
- individual batch status
- estimate cost
- list batches
slug: video-dubbing
source_filename: video-dubbing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sync Labs Video Dubbing and Localization\n  description: Workflow capability for AI-powered video dubbing and content localization using Sync Labs. Enables single video\n    generation, batch processing for large-scale dubbing, cost estimation before submission, and asset reuse. Ideal for content\n    creators, studios, educational platforms, and enterprises localizing video content across multiple languages.\n  tags:\n  - Artificial Intelligence\n  - Batch Processing\n  - Content Localization\n  - Dubbing\n  - Lip Sync\n  - Media\n  - Sync Labs\n  - Video\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SYNC_LABS_API_KEY: SYNC_LABS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sync-labs\n    baseUri: https://api.sync.so/v2\n    description: Sync Labs AI lip-sync API\n    authentication:\n      type: apikey\n      key: x-api-key\n      value: '{{SYNC_LABS_API_KEY}}'\n      placement:\
  \ header\n    resources:\n    - name: generate\n      path: /generate\n      description: Lip-sync video generation\n      operations:\n      - name: create-generation\n        method: POST\n        description: Create a lip-sync generation job\n        body:\n          type: json\n          data:\n            video_url: '{{tools.videoUrl}}'\n            audio_url: '{{tools.audioUrl}}'\n            model: '{{tools.model}}'\n            webhook_url: '{{tools.webhookUrl}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: generationId\n          type: string\n          value: $.id\n        - name: status\n          type: string\n          value: $.status\n      - name: list-generations\n        method: GET\n        description: List all generation jobs\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: status\n          in: query\n\
  \          type: string\n          required: false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-generation\n        method: GET\n        description: Get status and result of a generation job\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Generation job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        - name: status\n          type: string\n          value: $.status\n        - name: videoUrl\n          type: string\n          value: $.video_url\n    - name: estimate-cost\n      path: /generate/estimate-cost\n      description: Cost estimation before generation\n      operations:\n      - name: estimate-cost\n        method: GET\n        description: Estimate cost for\
  \ a generation\n        inputParameters:\n        - name: model\n          in: query\n          type: string\n          required: true\n          description: AI model to use\n        - name: duration\n          in: query\n          type: number\n          required: true\n          description: Video duration in seconds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch\n      path: /batch\n      description: Batch video generation\n      operations:\n      - name: create-batch\n        method: POST\n        description: Create a batch of generation jobs\n        body:\n          type: json\n          data:\n            generations: '{{tools.generations}}'\n            webhook_url: '{{tools.webhookUrl}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: batchId\n          type: string\n          value: $.id\n      - name: list-batches\n        method: GET\n        description:\
  \ List all batch jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-batch\n        method: GET\n        description: Get status of a batch job\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Batch job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /assets\n      description: Uploaded media asset management\n      operations:\n      - name: list-assets\n        method: GET\n        description: List all uploaded assets\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by asset type (video or audio)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: models\n      path: /models\n      description: Available AI model listing\n      operations:\n      - name: list-models\n        method: GET\n        description: List available AI lip-sync models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sync-labs-dubbing-api\n    description: Unified REST API for Sync Labs video dubbing and localization workflows.\n    resources:\n    - path: /v1/generate\n      name: generate\n      description: Single video generation\n      operations:\n      - method: POST\n        name: create-generation\n        description: Create an AI lip-sync generation\n        call: sync-labs.create-generation\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-generations\n        description: List all generation\
  \ jobs\n        call: sync-labs.list-generations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/generate/{id}\n      name: generation\n      description: Individual generation status and result\n      operations:\n      - method: GET\n        name: get-generation\n        description: Get generation status and output video URL\n        call: sync-labs.get-generation\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/estimate\n      name: estimate\n      description: Cost estimation\n      operations:\n      - method: GET\n        name: estimate-cost\n        description: Estimate generation cost\n        call: sync-labs.estimate-cost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batch\n      name: batch\n      description: Batch video generation\n      operations:\n      - method: POST\n        name: create-batch\n      \
  \  description: Submit a batch of lip-sync generations\n        call: sync-labs.create-batch\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-batches\n        description: List all batch jobs\n        call: sync-labs.list-batches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batch/{id}\n      name: batch-item\n      description: Individual batch status\n      operations:\n      - method: GET\n        name: get-batch\n        description: Get batch status and results\n        call: sync-labs.get-batch\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description: Available AI models\n      operations:\n      - method: GET\n        name: list-models\n        description: List available lip-sync AI models\n        call: sync-labs.list-models\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Uploaded media assets\n      operations:\n      - method: GET\n        name: list-assets\n        description: List uploaded video and audio assets\n        call: sync-labs.list-assets\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sync-labs-dubbing-mcp\n    transport: http\n    description: MCP server for AI-assisted video dubbing and content localization workflows.\n    tools:\n    - name: create-lipsync-video\n      description: Generate a lip-synced video by combining source video with new audio track\n      hints:\n        readOnly: false\n        destructive: false\n      call: sync-labs.create-generation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-generation-status\n      description: Check the status of a lip-sync generation and get the output video URL when\
  \ complete\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sync-labs.get-generation\n      with:\n        id: tools.generationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-generations\n      description: List all lip-sync generation jobs with their statuses and output URLs\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sync-labs.list-generations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: estimate-generation-cost\n      description: Get a cost estimate before submitting a lip-sync generation to avoid surprises\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sync-labs.estimate-cost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-batch-dubbing\n      description: Submit multiple videos for batch lip-sync processing (up to 500 videos)\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n      call: sync-labs.create-batch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-batch-status\n      description: Check the progress and results of a batch dubbing job\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sync-labs.get-batch\n      with:\n        id: tools.batchId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-available-models\n      description: List all available Sync Labs AI models with quality/speed/cost tradeoffs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sync-labs.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-uploaded-assets\n      description: List previously uploaded video and audio assets available for reuse\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sync-labs.list-assets\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sync-labs/refs/heads/main/capabilities/video-dubbing.yaml
tags:
- Artificial Intelligence
- Batch Processing
- Content Localization
- Dubbing
- Lip Sync
- Media
- Sync Labs
- Video
tools:
- description: Generate a lip-synced video by combining source video with new audio track
  hints:
    destructive: false
    readOnly: false
  name: create-lipsync-video
- description: Check the status of a lip-sync generation and get the output video URL when complete
  hints:
    openWorld: false
    readOnly: true
  name: get-generation-status
- description: List all lip-sync generation jobs with their statuses and output URLs
  hints:
    openWorld: false
    readOnly: true
  name: list-generations
- description: Get a cost estimate before submitting a lip-sync generation to avoid surprises
  hints:
    openWorld: false
    readOnly: true
  name: estimate-generation-cost
- description: Submit multiple videos for batch lip-sync processing (up to 500 videos)
  hints:
    destructive: false
    readOnly: false
  name: create-batch-dubbing
- description: Check the progress and results of a batch dubbing job
  hints:
    openWorld: false
    readOnly: true
  name: get-batch-status
- description: List all available Sync Labs AI models with quality/speed/cost tradeoffs
  hints:
    openWorld: true
    readOnly: true
  name: list-available-models
- description: List previously uploaded video and audio assets available for reuse
  hints:
    openWorld: false
    readOnly: true
  name: list-uploaded-assets
---
