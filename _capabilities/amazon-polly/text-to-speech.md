---
api_specs:
- filename: amazon-polly-openapi.yml
  format: yaml
  label: amazon-polly
  slug: amazon-polly
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-polly/refs/heads/main/openapi/amazon-polly-openapi.yml
categories:
- machine-learning
consumed_apis:
- amazon-polly
description: Workflow capability for converting text to lifelike speech using Amazon Polly. Combines speech synthesis, voice discovery, and lexicon management for developers building voice-enabled applications.
layout: capability
name: Amazon Polly Text-to-Speech
operations:
- description: Convert text to speech audio
  method: POST
  name: synthesize-speech
  path: /v1/speech
- description: List available voices by language and engine
  method: GET
  name: list-voices
  path: /v1/voices
- description: List pronunciation lexicons
  method: GET
  name: list-lexicons
  path: /v1/lexicons
- description: Create or update a pronunciation lexicon
  method: PUT
  name: create-lexicon
  path: /v1/lexicons
- description: Start an asynchronous speech synthesis task
  method: POST
  name: start-task
  path: /v1/tasks
- description: List synthesis tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
personas: []
provider_name: Amazon Polly
provider_slug: amazon-polly
search_terms:
- start an asynchronous speech synthesis task
- text-to-speech
- list lexicons
- start an asynchronous synthesis task for long text with s3 output
- start synthesis task
- list available voices by language and engine
- Application Developer
- list tasks
- amazon
- voice
- get the content of a pronunciation lexicon
- generative ai
- list pronunciation lexicons
- convert text to lifelike speech audio using amazon polly
- list voices
- list available amazon polly voices filterable by language and engine type
- list and monitor asynchronous speech synthesis tasks
- machine learning
- neural engine
- get lexicon
- synthesize speech
- start task
- speech synthesis
- create or update a custom pronunciation lexicon
- ai
- available synthesis voices
- create lexicon
- custom pronunciation lexicons
- builds voice-enabled applications using polly speech synthesis
- creates audio content from written text using polly
- Content Creator
- asynchronous synthesis tasks
- list synthesis tasks
- convert text to speech audio
- create or update a pronunciation lexicon
- ssml
- voice applications
- speech synthesis from text
- list custom pronunciation lexicons for controlling how words are spoken
- aws
- tts
- multi-channel text-to-speech synthesis workflow
slug: text-to-speech
source_filename: text-to-speech.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Polly Text-to-Speech\n  description: Workflow capability for converting text to lifelike speech using Amazon Polly. Combines speech synthesis, voice discovery, and lexicon management for developers building voice-enabled applications.\n  tags:\n    - Amazon\n    - AWS\n    - Text-To-Speech\n    - Speech Synthesis\n    - AI\n    - Voice Applications\n    - Machine Learning\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-polly\n      location: ./shared/amazon-polly.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: text-to-speech-api\n      description: Unified REST API for Amazon Polly text-to-speech workflows.\n      resources:\n        - path: /v1/speech\n          name: speech\n\
  \          description: Speech synthesis from text\n          operations:\n            - method: POST\n              name: synthesize-speech\n              description: Convert text to speech audio\n              call: \"amazon-polly.synthesize-speech\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/voices\n          name: voices\n          description: Available synthesis voices\n          operations:\n            - method: GET\n              name: list-voices\n              description: List available voices by language and engine\n              call: \"amazon-polly.describe-voices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/lexicons\n          name: lexicons\n          description: Custom pronunciation lexicons\n          operations:\n            - method: GET\n              name: list-lexicons\n              description: List pronunciation\
  \ lexicons\n              call: \"amazon-polly.list-lexicons\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: create-lexicon\n              description: Create or update a pronunciation lexicon\n              call: \"amazon-polly.put-lexicon\"\n              with:\n                LexiconName: \"rest.lexicon_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tasks\n          name: tasks\n          description: Asynchronous synthesis tasks\n          operations:\n            - method: POST\n              name: start-task\n              description: Start an asynchronous speech synthesis task\n              call: \"amazon-polly.start-speech-synthesis-task\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-tasks\n\
  \              description: List synthesis tasks\n              call: \"amazon-polly.list-speech-synthesis-tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: text-to-speech-mcp\n      transport: http\n      description: MCP server for AI-assisted text-to-speech workflows with Amazon Polly.\n      tools:\n        - name: synthesize-speech\n          description: Convert text to lifelike speech audio using Amazon Polly\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-polly.synthesize-speech\"\n          with:\n            text: \"tools.text\"\n            voice_id: \"tools.voice_id\"\n            output_format: \"tools.output_format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-voices\n          description: List available Amazon Polly voices filterable by\
  \ language and engine type\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-polly.describe-voices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-lexicons\n          description: List custom pronunciation lexicons for controlling how words are spoken\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-polly.list-lexicons\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-lexicon\n          description: Get the content of a pronunciation lexicon\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"amazon-polly.get-lexicon\"\n          with:\n            LexiconName: \"tools.lexicon_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-lexicon\n          description:\
  \ Create or update a custom pronunciation lexicon\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-polly.put-lexicon\"\n          with:\n            LexiconName: \"tools.lexicon_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-synthesis-task\n          description: Start an asynchronous synthesis task for long text with S3 output\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-polly.start-speech-synthesis-task\"\n          with:\n            text: \"tools.text\"\n            voice_id: \"tools.voice_id\"\n            output_format: \"tools.output_format\"\n            bucket: \"tools.bucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-synthesis-tasks\n          description: List and monitor asynchronous speech synthesis tasks\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"amazon-polly.list-speech-synthesis-tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-polly/refs/heads/main/capabilities/text-to-speech.yaml
tags:
- Amazon
- Text-To-Speech
- Speech Synthesis
- AI
- Voice Applications
- Machine Learning
tools:
- description: Convert text to lifelike speech audio using Amazon Polly
  hints:
    destructive: false
    readOnly: false
  name: synthesize-speech
- description: List available Amazon Polly voices filterable by language and engine type
  hints:
    openWorld: true
    readOnly: true
  name: list-voices
- description: List custom pronunciation lexicons for controlling how words are spoken
  hints:
    openWorld: true
    readOnly: true
  name: list-lexicons
- description: Get the content of a pronunciation lexicon
  hints:
    openWorld: false
    readOnly: true
  name: get-lexicon
- description: Create or update a custom pronunciation lexicon
  hints:
    destructive: false
    readOnly: false
  name: create-lexicon
- description: Start an asynchronous synthesis task for long text with S3 output
  hints:
    destructive: false
    readOnly: false
  name: start-synthesis-task
- description: List and monitor asynchronous speech synthesis tasks
  hints:
    openWorld: true
    readOnly: true
  name: list-synthesis-tasks
---
