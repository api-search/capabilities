---
api_specs:
- filename: salad-transcription-api-openapi.yml
  format: yaml
  label: salad-transcription
  slug: salad-transcription
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/salad-transcription-api/refs/heads/main/openapi/salad-transcription-api-openapi.yml
categories: []
consumed_apis:
- salad-transcription
description: Workflow capability for speech-to-text transcription using Salad's distributed GPU inference network. Supports multi-language transcription, speaker diarization, word-level timestamps, and SRT caption generation for audio and video content.
layout: capability
name: Salad Speech-to-Text
operations:
- description: Submit a media URL for transcription with language and output options.
  method: POST
  name: transcribe-media
  path: /v1/transcriptions
- description: Retrieve the full transcript, segments, and optional SRT output.
  method: GET
  name: get-transcript
  path: /v1/transcriptions/{jobId}
personas: []
provider_name: Salad Transcription API
provider_slug: salad-transcription-api
search_terms:
- get transcript
- retrieve the full transcript, segments, and optional srt output.
- retrieve transcription results for a completed job.
- speech recognition
- captions
- video transcription
- retrieve the completed transcription for a job by id. returns segments, word timestamps, speaker labels, and optional srt caption content.
- get transcription result
- submit an audio or video file url to salad for speech-to-text transcription. supports 97 languages, speaker diarization, word-level timestamps, and srt output. returns a job id to retrieve results.
- salad
- subtitles
- gpu
- diarization
- media processing
- submit audio and video files for transcription.
- transcribe audio video
- transcription
- submit a media url for transcription with language and output options.
- audio transcription
- video processing
- transcribe media
slug: speech-to-text
source_filename: speech-to-text.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salad Speech-to-Text\"\n  description: >-\n    Workflow capability for speech-to-text transcription using Salad's distributed\n    GPU inference network. Supports multi-language transcription, speaker diarization,\n    word-level timestamps, and SRT caption generation for audio and video content.\n  tags:\n    - Audio Transcription\n    - Captions\n    - Diarization\n    - Media Processing\n    - Salad\n    - Speech Recognition\n    - Subtitles\n    - Video Transcription\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALAD_API_KEY: SALAD_API_KEY\n      SALAD_API_URL: SALAD_API_URL\n\ncapability:\n  consumes:\n    - import: salad-transcription\n      location: ./shared/salad-transcription-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: salad-speech-to-text-api\n      description: \"Unified REST API for Salad speech-to-text transcription workflows.\"\
  \n      resources:\n        - path: /v1/transcriptions\n          name: transcriptions\n          description: \"Submit audio and video files for transcription.\"\n          operations:\n            - method: POST\n              name: transcribe-media\n              description: \"Submit a media URL for transcription with language and output options.\"\n              call: \"salad-transcription.transcribe-media\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transcriptions/{jobId}\n          name: transcription-by-id\n          description: \"Retrieve transcription results for a completed job.\"\n          operations:\n            - method: GET\n              name: get-transcript\n              description: \"Retrieve the full transcript, segments, and optional SRT output.\"\n              call: \"salad-transcription.get-transcript\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: salad-speech-to-text-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salad speech-to-text transcription.\"\n      tools:\n        - name: transcribe-audio-video\n          description: >-\n            Submit an audio or video file URL to Salad for speech-to-text transcription.\n            Supports 97 languages, speaker diarization, word-level timestamps, and SRT output.\n            Returns a job ID to retrieve results.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salad-transcription.transcribe-media\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-transcription-result\n          description: >-\n            Retrieve the completed transcription for a job by ID. Returns segments,\n            word timestamps, speaker labels,\
  \ and optional SRT caption content.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salad-transcription.get-transcript\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salad-transcription-api/refs/heads/main/capabilities/speech-to-text.yaml
tags:
- Audio Transcription
- Captions
- Diarization
- Media Processing
- Salad
- Speech Recognition
- Subtitles
- Video Transcription
tools:
- description: Submit an audio or video file URL to Salad for speech-to-text transcription. Supports 97 languages, speaker diarization, word-level timestamps, and SRT output. Returns a job ID to retrieve results.
  hints:
    destructive: false
    readOnly: false
  name: transcribe-audio-video
- description: Retrieve the completed transcription for a job by ID. Returns segments, word timestamps, speaker labels, and optional SRT caption content.
  hints:
    idempotent: true
    readOnly: true
  name: get-transcription-result
---
