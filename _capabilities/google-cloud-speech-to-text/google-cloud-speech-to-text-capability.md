---
categories: []
consumed_apis: []
description: Provides speech recognition capabilities to convert audio to text, supporting synchronous recognition, asynchronous batch processing, and real-time streaming transcription across 125+ languages.
layout: capability
name: Google Cloud Speech-to-Text API
operations:
- description: Google Cloud Speech-To-Text Synchronous speech recognition
  method: POST
  name: recognize
  path: /speech:recognize
- description: Google Cloud Speech-To-Text Asynchronous speech recognition
  method: POST
  name: longrunningrecognize
  path: /speech:longrunningrecognize
- description: Google Cloud Speech-To-Text Get operation status
  method: GET
  name: getoperation
  path: /operations/{operationId}
- description: Google Cloud Speech-To-Text List recognizers
  method: GET
  name: listrecognizers
  path: /projects/{project}/locations/{location}/recognizers
- description: Google Cloud Speech-To-Text Create a recognizer
  method: POST
  name: createrecognizer
  path: /projects/{project}/locations/{location}/recognizers
personas: []
provider_name: Google Cloud Speech-To-Text
provider_slug: google-cloud-speech-to-text
search_terms:
- google cloud speech-to-text asynchronous speech recognition
- google cloud speech-to-text create a recognizer
- google cloud speech-to-text list recognizers
- cloud
- google
- longrunningrecognize
- speech
- recognize
- google cloud speech-to-text synchronous speech recognition
- listrecognizers
- text
- createrecognizer
- machine learning
- api
- getoperation
- transcription
- google cloud speech-to-text get operation status
- audio processing
- to
- speech recognition
- google cloud
slug: google-cloud-speech-to-text-capability
source_filename: google-cloud-speech-to-text-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Speech-to-Text API\n  description: Provides speech recognition capabilities to convert audio to text, supporting synchronous recognition, asynchronous\n    batch processing, and real-time streaming transcription across 125+ languages.\n  tags:\n  - Google\n  - Cloud\n  - Speech\n  - To\n  - Text\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-speech-to-text\n    baseUri: https://speech.googleapis.com/v1\n    description: Google Cloud Speech-to-Text API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_SPEECH_TO_TEXT_TOKEN}}'\n    resources:\n    - name: speech-recognize\n      path: /speech:recognize\n      operations:\n      - name: recognize\n        method: POST\n        description: Google Cloud Speech-To-Text Synchronous speech recognition\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: speech-longrunningrecognize\n      path: /speech:longrunningrecognize\n      operations:\n      - name: longrunningrecognize\n        method: POST\n        description: Google Cloud Speech-To-Text Asynchronous speech recognition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-operationid\n      path: /operations/{operationId}\n      operations:\n      - name: getoperation\n        method: GET\n        description: Google Cloud Speech-To-Text Get operation status\n        inputParameters:\n        - name: operationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-recognizers\n      path: /projects/{project}/locations/{location}/recognizers\n\
  \      operations:\n      - name: listrecognizers\n        method: GET\n        description: Google Cloud Speech-To-Text List recognizers\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrecognizer\n        method: POST\n        description: Google Cloud Speech-To-Text Create a recognizer\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ google-cloud-speech-to-text-rest\n    description: REST adapter for Google Cloud Speech-to-Text API.\n    resources:\n    - path: /speech:recognize\n      name: recognize\n      operations:\n      - method: POST\n        name: recognize\n        description: Google Cloud Speech-To-Text Synchronous speech recognition\n        call: google-cloud-speech-to-text.recognize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /speech:longrunningrecognize\n      name: longrunningrecognize\n      operations:\n      - method: POST\n        name: longrunningrecognize\n        description: Google Cloud Speech-To-Text Asynchronous speech recognition\n        call: google-cloud-speech-to-text.longrunningrecognize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/{operationId}\n      name: getoperation\n      operations:\n      - method: GET\n        name: getoperation\n        description: Google Cloud Speech-To-Text\
  \ Get operation status\n        call: google-cloud-speech-to-text.getoperation\n        with:\n          operationId: rest.operationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/recognizers\n      name: listrecognizers\n      operations:\n      - method: GET\n        name: listrecognizers\n        description: Google Cloud Speech-To-Text List recognizers\n        call: google-cloud-speech-to-text.listrecognizers\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/recognizers\n      name: createrecognizer\n      operations:\n      - method: POST\n        name: createrecognizer\n        description: Google Cloud Speech-To-Text Create a recognizer\n        call: google-cloud-speech-to-text.createrecognizer\n        with:\n          project: rest.project\n\
  \          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-speech-to-text-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Speech-to-Text API for AI agent use.\n    tools:\n    - name: recognize\n      description: Google Cloud Speech-To-Text Synchronous speech recognition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-speech-to-text.recognize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: longrunningrecognize\n      description: Google Cloud Speech-To-Text Asynchronous speech recognition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-speech-to-text.longrunningrecognize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperation\n      description:\
  \ Google Cloud Speech-To-Text Get operation status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-speech-to-text.getoperation\n      with:\n        operationId: tools.operationId\n      inputParameters:\n      - name: operationId\n        type: string\n        description: operationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecognizers\n      description: Google Cloud Speech-To-Text List recognizers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-speech-to-text.listrecognizers\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrecognizer\n      description: Google Cloud Speech-To-Text Create a recognizer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-speech-to-text.createrecognizer\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_SPEECH_TO_TEXT_TOKEN: GOOGLE_CLOUD_SPEECH_TO_TEXT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-speech-to-text/refs/heads/main/capabilities/google-cloud-speech-to-text-capability.yaml
tags:
- Google
- Cloud
- Speech
- To
- Text
- API
tools:
- description: Google Cloud Speech-To-Text Synchronous speech recognition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: recognize
- description: Google Cloud Speech-To-Text Asynchronous speech recognition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: longrunningrecognize
- description: Google Cloud Speech-To-Text Get operation status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperation
- description: Google Cloud Speech-To-Text List recognizers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecognizers
- description: Google Cloud Speech-To-Text Create a recognizer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrecognizer
---
