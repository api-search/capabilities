---
categories:
- machine-learning
consumed_apis: []
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
- Content Creator
- text-to-speech
- ai
- list synthesis tasks
- speech synthesis
- amazon
- Application Developer
- list voices
- tts
- list available amazon polly voices filterable by language and engine type
- list tasks
- get lexicon
- machine learning
- convert text to speech audio
- create lexicon
- start an asynchronous speech synthesis task
- speech synthesis from text
- convert text to lifelike speech audio using amazon polly
- multi-channel text-to-speech synthesis workflow
- ssml
- custom pronunciation lexicons
- list pronunciation lexicons
- list and monitor asynchronous speech synthesis tasks
- create or update a custom pronunciation lexicon
- start task
- creates audio content from written text using polly
- generative ai
- start synthesis task
- create or update a pronunciation lexicon
- list available voices by language and engine
- available synthesis voices
- neural engine
- start an asynchronous synthesis task for long text with s3 output
- list custom pronunciation lexicons for controlling how words are spoken
- voice applications
- aws
- synthesize speech
- asynchronous synthesis tasks
- voice
- list lexicons
- get the content of a pronunciation lexicon
- builds voice-enabled applications using polly speech synthesis
slug: text-to-speech
source_filename: text-to-speech.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Polly Text-to-Speech\n  description: Workflow capability for converting text to lifelike speech using Amazon Polly. Combines speech synthesis, voice\n    discovery, and lexicon management for developers building voice-enabled applications.\n  tags:\n  - Amazon\n  - AWS\n  - Text-To-Speech\n  - Speech Synthesis\n  - AI\n  - Voice Applications\n  - Machine Learning\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-polly\n    baseUri: https://polly.{region}.amazonaws.com\n    description: Amazon Polly text-to-speech API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: speech\n      path: /v1/speech\n      description:\
  \ Synthesize speech from text\n      operations:\n      - name: synthesize-speech\n        method: POST\n        description: Synthesizes UTF-8 input, plain text or SSML, to a stream of bytes\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Text: '{{tools.text}}'\n            VoiceId: '{{tools.voice_id}}'\n            OutputFormat: '{{tools.output_format}}'\n    - name: voices\n      path: /v1/voices\n      description: List available voices\n      operations:\n      - name: describe-voices\n        method: GET\n        description: Returns the list of voices that are available for use when requesting speech synthesis\n        inputParameters:\n        - name: Engine\n          in: query\n          type: string\n          required: false\n          description: Specifies the engine for Amazon Polly to use (standard, neural, long-form, generative)\n\
  \        - name: LanguageCode\n          in: query\n          type: string\n          required: false\n          description: The language identification tag for filtering voices\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lexicons\n      path: /v1/lexicons\n      description: Manage pronunciation lexicons\n      operations:\n      - name: list-lexicons\n        method: GET\n        description: Returns a list of pronunciation lexicons stored in an AWS Region\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lexicon\n      path: /v1/lexicons/{LexiconName}\n      description: Get or manage a specific lexicon\n      operations:\n      - name: get-lexicon\n        method:\
  \ GET\n        description: Returns the content of the specified pronunciation lexicon\n        inputParameters:\n        - name: LexiconName\n          in: path\n          type: string\n          required: true\n          description: Name of the lexicon\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-lexicon\n        method: PUT\n        description: Stores a pronunciation lexicon in an AWS Region\n        inputParameters:\n        - name: LexiconName\n          in: path\n          type: string\n          required: true\n          description: Name of the lexicon\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Content: '{{tools.content}}'\n    - name: synthesis-tasks\n      path: /v1/synthesisTasks\n      description: Manage asynchronous speech\
  \ synthesis tasks\n      operations:\n      - name: start-speech-synthesis-task\n        method: POST\n        description: Allows the creation of an asynchronous synthesis task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Text: '{{tools.text}}'\n            VoiceId: '{{tools.voice_id}}'\n            OutputFormat: '{{tools.output_format}}'\n            OutputS3BucketName: '{{tools.bucket}}'\n      - name: list-speech-synthesis-tasks\n        method: GET\n        description: Returns a list of SpeechSynthesisTask objects ordered by creation date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: text-to-speech-api\n    description: Unified REST API for Amazon Polly text-to-speech workflows.\n    resources:\n\
  \    - path: /v1/speech\n      name: speech\n      description: Speech synthesis from text\n      operations:\n      - method: POST\n        name: synthesize-speech\n        description: Convert text to speech audio\n        call: amazon-polly.synthesize-speech\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/voices\n      name: voices\n      description: Available synthesis voices\n      operations:\n      - method: GET\n        name: list-voices\n        description: List available voices by language and engine\n        call: amazon-polly.describe-voices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lexicons\n      name: lexicons\n      description: Custom pronunciation lexicons\n      operations:\n      - method: GET\n        name: list-lexicons\n        description: List pronunciation lexicons\n        call: amazon-polly.list-lexicons\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n      - method: PUT\n        name: create-lexicon\n        description: Create or update a pronunciation lexicon\n        call: amazon-polly.put-lexicon\n        with:\n          LexiconName: rest.lexicon_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Asynchronous synthesis tasks\n      operations:\n      - method: POST\n        name: start-task\n        description: Start an asynchronous speech synthesis task\n        call: amazon-polly.start-speech-synthesis-task\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-tasks\n        description: List synthesis tasks\n        call: amazon-polly.list-speech-synthesis-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: text-to-speech-mcp\n    transport: http\n    description: MCP server for AI-assisted\
  \ text-to-speech workflows with Amazon Polly.\n    tools:\n    - name: synthesize-speech\n      description: Convert text to lifelike speech audio using Amazon Polly\n      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-polly.synthesize-speech\n      with:\n        text: tools.text\n        voice_id: tools.voice_id\n        output_format: tools.output_format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-voices\n      description: List available Amazon Polly voices filterable by language and engine type\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-polly.describe-voices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-lexicons\n      description: List custom pronunciation lexicons for controlling how words are spoken\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-polly.list-lexicons\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-lexicon\n      description: Get the content of a pronunciation lexicon\n      hints:\n        readOnly: true\n        openWorld: false\n      call: amazon-polly.get-lexicon\n      with:\n        LexiconName: tools.lexicon_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-lexicon\n      description: Create or update a custom pronunciation lexicon\n      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-polly.put-lexicon\n      with:\n        LexiconName: tools.lexicon_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-synthesis-task\n      description: Start an asynchronous synthesis task for long text with S3 output\n      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-polly.start-speech-synthesis-task\n      with:\n        text: tools.text\n        voice_id: tools.voice_id\n      \
  \  output_format: tools.output_format\n        bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-synthesis-tasks\n      description: List and monitor asynchronous speech synthesis tasks\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-polly.list-speech-synthesis-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
