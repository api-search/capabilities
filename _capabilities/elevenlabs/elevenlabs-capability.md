---
categories: []
consumed_apis: []
description: The ElevenLabs Audio Isolation API removes background noise from audio recordings, isolating vocal tracks from ambient sounds and interference. This is useful for cleaning up recordings, improving audio quality for podcasts and interviews, and preparing audio files for further processing such as voice cloning or transcription.
layout: capability
name: ElevenLabs Audio Isolation API
operations:
- description: Isolate audio
  method: POST
  name: isolateaudio
  path: /v1/audio-isolation
- description: Isolate audio with streaming
  method: POST
  name: isolateaudiostream
  path: /v1/audio-isolation/stream
personas: []
provider_name: elevenlabs
provider_slug: elevenlabs
search_terms:
- isolate audio with streaming
- isolateaudiostream
- isolateaudio
- isolate audio
- api
- elevenlabs
slug: elevenlabs-capability
source_filename: elevenlabs-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ElevenLabs Audio Isolation API\n  description: The ElevenLabs Audio Isolation API removes background noise from audio recordings, isolating vocal tracks from\n    ambient sounds and interference. This is useful for cleaning up recordings, improving audio quality for podcasts and interviews,\n    and preparing audio files for further processing such as voice cloning or transcription.\n  tags:\n  - Elevenlabs\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: elevenlabs\n    baseUri: https://api.elevenlabs.io\n    description: ElevenLabs Audio Isolation API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: xi-api-key\n      value: '{{ELEVENLABS_TOKEN}}'\n    resources:\n    - name: v1-audio-isolation\n      path: /v1/audio-isolation\n      operations:\n      - name: isolateaudio\n        method: POST\n        description: Isolate audio\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-audio-isolation-stream\n      path: /v1/audio-isolation/stream\n      operations:\n      - name: isolateaudiostream\n        method: POST\n        description: Isolate audio with streaming\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: elevenlabs-rest\n    description: REST adapter for ElevenLabs Audio Isolation API.\n    resources:\n    - path: /v1/audio-isolation\n      name: isolateaudio\n      operations:\n      - method: POST\n        name: isolateaudio\n        description: Isolate audio\n        call: elevenlabs.isolateaudio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audio-isolation/stream\n      name: isolateaudiostream\n      operations:\n      - method:\
  \ POST\n        name: isolateaudiostream\n        description: Isolate audio with streaming\n        call: elevenlabs.isolateaudiostream\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: elevenlabs-mcp\n    transport: http\n    description: MCP adapter for ElevenLabs Audio Isolation API for AI agent use.\n    tools:\n    - name: isolateaudio\n      description: Isolate audio\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: elevenlabs.isolateaudio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isolateaudiostream\n      description: Isolate audio with streaming\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: elevenlabs.isolateaudiostream\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ELEVENLABS_TOKEN: ELEVENLABS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/elevenlabs/refs/heads/main/capabilities/elevenlabs-capability.yaml
tags:
- Elevenlabs
- API
tools:
- description: Isolate audio
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: isolateaudio
- description: Isolate audio with streaming
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: isolateaudiostream
---
