---
categories: []
consumed_apis: []
description: Synthesizes natural-sounding speech from text or SSML input using Google's AI-powered voice synthesis technology.
layout: capability
name: Google Cloud Text-to-Speech API
operations:
- description: Google Cloud Text-To-Speech List available voices
  method: GET
  name: listvoices
  path: /voices
- description: Google Cloud Text-To-Speech Synthesize speech
  method: POST
  name: synthesizespeech
  path: /text:synthesize
personas: []
provider_name: Google Cloud Text-To-Speech
provider_slug: google-cloud-text-to-speech
search_terms:
- text
- synthesizespeech
- machine learning
- google
- speech synthesis
- to
- google cloud text-to-speech list available voices
- google cloud
- text-to-speech
- speech
- api
- cloud
- listvoices
- google cloud text-to-speech synthesize speech
- audio
slug: google-cloud-text-to-speech-capability
source_filename: google-cloud-text-to-speech-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Text-to-Speech API\n  description: Synthesizes natural-sounding speech from text or SSML input using Google's AI-powered voice synthesis technology.\n  tags:\n  - Google\n  - Cloud\n  - Text\n  - To\n  - Speech\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-text-to-speech\n    baseUri: https://texttospeech.googleapis.com/v1\n    description: Google Cloud Text-to-Speech API HTTP API.\n    resources:\n    - name: voices\n      path: /voices\n      operations:\n      - name: listvoices\n        method: GET\n        description: Google Cloud Text-To-Speech List available voices\n        inputParameters:\n        - name: languageCode\n          in: query\n          type: string\n          description: BCP-47 language tag to filter voices.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: text-synthesize\n      path: /text:synthesize\n      operations:\n      - name: synthesizespeech\n        method: POST\n        description: Google Cloud Text-To-Speech Synthesize speech\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-text-to-speech-rest\n    description: REST adapter for Google Cloud Text-to-Speech API.\n    resources:\n    - path: /voices\n      name: listvoices\n      operations:\n      - method: GET\n        name: listvoices\n        description: Google Cloud Text-To-Speech List available voices\n        call: google-cloud-text-to-speech.listvoices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /text:synthesize\n      name: synthesizespeech\n      operations:\n      - method: POST\n        name: synthesizespeech\n        description: Google Cloud\
  \ Text-To-Speech Synthesize speech\n        call: google-cloud-text-to-speech.synthesizespeech\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-text-to-speech-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Text-to-Speech API for AI agent use.\n    tools:\n    - name: listvoices\n      description: Google Cloud Text-To-Speech List available voices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-text-to-speech.listvoices\n      with:\n        languageCode: tools.languageCode\n      inputParameters:\n      - name: languageCode\n        type: string\n        description: BCP-47 language tag to filter voices.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: synthesizespeech\n      description: Google Cloud Text-To-Speech Synthesize speech\n      hints:\n        readOnly: false\n   \
  \     destructive: false\n        idempotent: false\n      call: google-cloud-text-to-speech.synthesizespeech\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-text-to-speech/refs/heads/main/capabilities/google-cloud-text-to-speech-capability.yaml
tags:
- Google
- Cloud
- Text
- To
- Speech
- API
tools:
- description: Google Cloud Text-To-Speech List available voices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvoices
- description: Google Cloud Text-To-Speech Synthesize speech
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: synthesizespeech
---
