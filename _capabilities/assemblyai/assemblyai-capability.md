---
categories: []
consumed_apis: []
description: AssemblyAI API
layout: capability
name: AssemblyAI API
operations:
- description: AssemblyAI Upload a media file
  method: POST
  name: uploadfile
  path: /v2/upload
- description: AssemblyAI Transcribe audio
  method: POST
  name: createtranscript
  path: /v2/transcript
- description: AssemblyAI List transcripts
  method: GET
  name: listtranscripts
  path: /v2/transcript
- description: AssemblyAI Get transcript
  method: GET
  name: gettranscript
  path: /v2/transcript/{transcript_id}
- description: AssemblyAI Delete transcript
  method: DELETE
  name: deletetranscript
  path: /v2/transcript/{transcript_id}
- description: AssemblyAI Get subtitles for transcript
  method: GET
  name: getsubtitles
  path: /v2/transcript/{transcript_id}/{subtitle_format}
- description: AssemblyAI Get sentences in transcript
  method: GET
  name: gettranscriptsentences
  path: /v2/transcript/{transcript_id}/sentences
- description: AssemblyAI Get paragraphs in transcript
  method: GET
  name: gettranscriptparagraphs
  path: /v2/transcript/{transcript_id}/paragraphs
- description: AssemblyAI Search words in transcript
  method: GET
  name: wordsearch
  path: /v2/transcript/{transcript_id}/word-search
- description: AssemblyAI Get redacted audio
  method: GET
  name: getredactedaudio
  path: /v2/transcript/{transcript_id}/redacted-audio
- description: AssemblyAI Create temporary authentication token for Streaming STT
  method: POST
  name: createtemporarytoken
  path: /v2/realtime/token
- description: AssemblyAI Run a task using LeMUR
  method: POST
  name: lemurtask
  path: /lemur/v3/generate/task
- description: AssemblyAI Summarize a transcript using LeMUR
  method: POST
  name: lemursummary
  path: /lemur/v3/generate/summary
- description: AssemblyAI Ask questions using LeMUR
  method: POST
  name: lemurquestionanswer
  path: /lemur/v3/generate/question-answer
- description: AssemblyAI Extract action items
  method: POST
  name: lemuractionitems
  path: /lemur/v3/generate/action-items
- description: AssemblyAI Purge LeMUR request data
  method: DELETE
  name: purgelemurrequestdata
  path: /lemur/v3/{request_id}
personas: []
provider_name: AssemblyAI
provider_slug: assemblyai
search_terms:
- wordsearch
- assemblyai
- lemurtask
- assemblyai list transcripts
- getsubtitles
- assemblyai get subtitles for transcript
- assemblyai get sentences in transcript
- lemursummary
- deletetranscript
- assemblyai create temporary authentication token for streaming stt
- assemblyai purge lemur request data
- assemblyai get paragraphs in transcript
- ai
- assemblyai get redacted audio
- gettranscriptsentences
- api
- transcription
- lemuractionitems
- lemurquestionanswer
- artificial intelligence
- getredactedaudio
- uploadfile
- assemblyai get transcript
- assemblyai ask questions using lemur
- assemblyai transcribe audio
- createtranscript
- audio
- createtemporarytoken
- gettranscript
- assemblyai extract action items
- assemblyai summarize a transcript using lemur
- assemblyai search words in transcript
- assemblyai run a task using lemur
- assemblyai upload a media file
- speech to text
- purgelemurrequestdata
- speech
- listtranscripts
- assemblyai delete transcript
- gettranscriptparagraphs
slug: assemblyai-capability
source_filename: assemblyai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AssemblyAI API\n  description: AssemblyAI API\n  tags:\n  - Assemblyai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: assemblyai\n    baseUri: https://api.assemblyai.com\n    description: AssemblyAI API HTTP API.\n    resources:\n    - name: v2-upload\n      path: /v2/upload\n      operations:\n      - name: uploadfile\n        method: POST\n        description: AssemblyAI Upload a media file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-transcript\n      path: /v2/transcript\n      operations:\n      - name: createtranscript\n        method: POST\n        description: AssemblyAI Transcribe audio\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listtranscripts\n        method: GET\n\
  \        description: AssemblyAI List transcripts\n        inputParameters:\n        - name: limit\n          in: query\n          type: string\n          description: Maximum amount of transcripts to retrieve\n        - name: status\n          in: query\n          type: string\n          description: Filter by transcript status\n        - name: created_on\n          in: query\n          type: string\n          description: Only get transcripts created on this date\n        - name: before_id\n          in: query\n          type: string\n          description: Get transcripts that were created before this transcript ID\n        - name: after_id\n          in: query\n          type: string\n          description: Get transcripts that were created after this transcript ID\n        - name: throttled_only\n          in: query\n          type: string\n          description: Only get throttled transcripts, overrides the status filter\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v2-transcript-transcript-id\n      path: /v2/transcript/{transcript_id}\n      operations:\n      - name: gettranscript\n        method: GET\n        description: AssemblyAI Get transcript\n        inputParameters:\n        - name: transcript_id\n          in: path\n          type: string\n          required: true\n          description: ID of the transcript\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetranscript\n        method: DELETE\n        description: AssemblyAI Delete transcript\n        inputParameters:\n        - name: transcript_id\n          in: path\n          type: string\n          required: true\n          description: ID of the transcript\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-transcript-transcript-id-subtitle-format\n\
  \      path: /v2/transcript/{transcript_id}/{subtitle_format}\n      operations:\n      - name: getsubtitles\n        method: GET\n        description: AssemblyAI Get subtitles for transcript\n        inputParameters:\n        - name: transcript_id\n          in: path\n          type: string\n          required: true\n          description: ID of the transcript\n        - name: subtitle_format\n          in: path\n          type: string\n          required: true\n          description: The format of the captions\n        - name: chars_per_caption\n          in: query\n          type: integer\n          description: The maximum number of characters per caption\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-transcript-transcript-id-sentences\n      path: /v2/transcript/{transcript_id}/sentences\n      operations:\n      - name: gettranscriptsentences\n        method: GET\n        description:\
  \ AssemblyAI Get sentences in transcript\n        inputParameters:\n        - name: transcript_id\n          in: path\n          type: string\n          required: true\n          description: ID of the transcript\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-transcript-transcript-id-paragraphs\n      path: /v2/transcript/{transcript_id}/paragraphs\n      operations:\n      - name: gettranscriptparagraphs\n        method: GET\n        description: AssemblyAI Get paragraphs in transcript\n        inputParameters:\n        - name: transcript_id\n          in: path\n          type: string\n          required: true\n          description: ID of the transcript\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-transcript-transcript-id-word-search\n      path: /v2/transcript/{transcript_id}/word-search\n  \
  \    operations:\n      - name: wordsearch\n        method: GET\n        description: AssemblyAI Search words in transcript\n        inputParameters:\n        - name: transcript_id\n          in: path\n          type: string\n          required: true\n          description: ID of the transcript\n        - name: words\n          in: query\n          type: array\n          required: true\n          description: Keywords to search for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-transcript-transcript-id-redacted-audio\n      path: /v2/transcript/{transcript_id}/redacted-audio\n      operations:\n      - name: getredactedaudio\n        method: GET\n        description: AssemblyAI Get redacted audio\n        inputParameters:\n        - name: transcript_id\n          in: path\n          type: string\n          required: true\n          description: ID of the transcript\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-realtime-token\n      path: /v2/realtime/token\n      operations:\n      - name: createtemporarytoken\n        method: POST\n        description: AssemblyAI Create temporary authentication token for Streaming STT\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lemur-v3-generate-task\n      path: /lemur/v3/generate/task\n      operations:\n      - name: lemurtask\n        method: POST\n        description: AssemblyAI Run a task using LeMUR\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lemur-v3-generate-summary\n      path: /lemur/v3/generate/summary\n      operations:\n      - name: lemursummary\n        method: POST\n        description: AssemblyAI Summarize a transcript using LeMUR\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lemur-v3-generate-question-answer\n      path: /lemur/v3/generate/question-answer\n      operations:\n      - name: lemurquestionanswer\n        method: POST\n        description: AssemblyAI Ask questions using LeMUR\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lemur-v3-generate-action-items\n      path: /lemur/v3/generate/action-items\n      operations:\n      - name: lemuractionitems\n        method: POST\n        description: AssemblyAI Extract action items\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lemur-v3-request-id\n      path: /lemur/v3/{request_id}\n      operations:\n      - name: purgelemurrequestdata\n        method: DELETE\n        description: AssemblyAI\
  \ Purge LeMUR request data\n        inputParameters:\n        - name: request_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the LeMUR request whose data you want to delete. This would be found in the response of the\n            original request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: assemblyai-rest\n    description: REST adapter for AssemblyAI API.\n    resources:\n    - path: /v2/upload\n      name: uploadfile\n      operations:\n      - method: POST\n        name: uploadfile\n        description: AssemblyAI Upload a media file\n        call: assemblyai.uploadfile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/transcript\n      name: createtranscript\n      operations:\n      - method: POST\n        name: createtranscript\n        description:\
  \ AssemblyAI Transcribe audio\n        call: assemblyai.createtranscript\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/transcript\n      name: listtranscripts\n      operations:\n      - method: GET\n        name: listtranscripts\n        description: AssemblyAI List transcripts\n        call: assemblyai.listtranscripts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/transcript/{transcript_id}\n      name: gettranscript\n      operations:\n      - method: GET\n        name: gettranscript\n        description: AssemblyAI Get transcript\n        call: assemblyai.gettranscript\n        with:\n          transcript_id: rest.transcript_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/transcript/{transcript_id}\n      name: deletetranscript\n      operations:\n      - method: DELETE\n        name: deletetranscript\n        description: AssemblyAI Delete transcript\n\
  \        call: assemblyai.deletetranscript\n        with:\n          transcript_id: rest.transcript_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/transcript/{transcript_id}/{subtitle_format}\n      name: getsubtitles\n      operations:\n      - method: GET\n        name: getsubtitles\n        description: AssemblyAI Get subtitles for transcript\n        call: assemblyai.getsubtitles\n        with:\n          transcript_id: rest.transcript_id\n          subtitle_format: rest.subtitle_format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/transcript/{transcript_id}/sentences\n      name: gettranscriptsentences\n      operations:\n      - method: GET\n        name: gettranscriptsentences\n        description: AssemblyAI Get sentences in transcript\n        call: assemblyai.gettranscriptsentences\n        with:\n          transcript_id: rest.transcript_id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v2/transcript/{transcript_id}/paragraphs\n      name: gettranscriptparagraphs\n      operations:\n      - method: GET\n        name: gettranscriptparagraphs\n        description: AssemblyAI Get paragraphs in transcript\n        call: assemblyai.gettranscriptparagraphs\n        with:\n          transcript_id: rest.transcript_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/transcript/{transcript_id}/word-search\n      name: wordsearch\n      operations:\n      - method: GET\n        name: wordsearch\n        description: AssemblyAI Search words in transcript\n        call: assemblyai.wordsearch\n        with:\n          transcript_id: rest.transcript_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/transcript/{transcript_id}/redacted-audio\n      name: getredactedaudio\n      operations:\n      - method: GET\n        name: getredactedaudio\n        description:\
  \ AssemblyAI Get redacted audio\n        call: assemblyai.getredactedaudio\n        with:\n          transcript_id: rest.transcript_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/realtime/token\n      name: createtemporarytoken\n      operations:\n      - method: POST\n        name: createtemporarytoken\n        description: AssemblyAI Create temporary authentication token for Streaming STT\n        call: assemblyai.createtemporarytoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lemur/v3/generate/task\n      name: lemurtask\n      operations:\n      - method: POST\n        name: lemurtask\n        description: AssemblyAI Run a task using LeMUR\n        call: assemblyai.lemurtask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lemur/v3/generate/summary\n      name: lemursummary\n      operations:\n      - method: POST\n        name: lemursummary\n        description:\
  \ AssemblyAI Summarize a transcript using LeMUR\n        call: assemblyai.lemursummary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lemur/v3/generate/question-answer\n      name: lemurquestionanswer\n      operations:\n      - method: POST\n        name: lemurquestionanswer\n        description: AssemblyAI Ask questions using LeMUR\n        call: assemblyai.lemurquestionanswer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lemur/v3/generate/action-items\n      name: lemuractionitems\n      operations:\n      - method: POST\n        name: lemuractionitems\n        description: AssemblyAI Extract action items\n        call: assemblyai.lemuractionitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lemur/v3/{request_id}\n      name: purgelemurrequestdata\n      operations:\n      - method: DELETE\n        name: purgelemurrequestdata\n        description: AssemblyAI\
  \ Purge LeMUR request data\n        call: assemblyai.purgelemurrequestdata\n        with:\n          request_id: rest.request_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: assemblyai-mcp\n    transport: http\n    description: MCP adapter for AssemblyAI API for AI agent use.\n    tools:\n    - name: uploadfile\n      description: AssemblyAI Upload a media file\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: assemblyai.uploadfile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtranscript\n      description: AssemblyAI Transcribe audio\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: assemblyai.createtranscript\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtranscripts\n      description: AssemblyAI List transcripts\n   \
  \   hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assemblyai.listtranscripts\n      with:\n        limit: tools.limit\n        status: tools.status\n        created_on: tools.created_on\n        before_id: tools.before_id\n        after_id: tools.after_id\n        throttled_only: tools.throttled_only\n      inputParameters:\n      - name: limit\n        type: string\n        description: Maximum amount of transcripts to retrieve\n      - name: status\n        type: string\n        description: Filter by transcript status\n      - name: created_on\n        type: string\n        description: Only get transcripts created on this date\n      - name: before_id\n        type: string\n        description: Get transcripts that were created before this transcript ID\n      - name: after_id\n        type: string\n        description: Get transcripts that were created after this transcript ID\n      - name: throttled_only\n        type: string\n\
  \        description: Only get throttled transcripts, overrides the status filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettranscript\n      description: AssemblyAI Get transcript\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assemblyai.gettranscript\n      with:\n        transcript_id: tools.transcript_id\n      inputParameters:\n      - name: transcript_id\n        type: string\n        description: ID of the transcript\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetranscript\n      description: AssemblyAI Delete transcript\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: assemblyai.deletetranscript\n      with:\n        transcript_id: tools.transcript_id\n      inputParameters:\n      - name: transcript_id\n        type: string\n        description: ID of the transcript\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubtitles\n      description: AssemblyAI Get subtitles for transcript\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assemblyai.getsubtitles\n      with:\n        transcript_id: tools.transcript_id\n        subtitle_format: tools.subtitle_format\n        chars_per_caption: tools.chars_per_caption\n      inputParameters:\n      - name: transcript_id\n        type: string\n        description: ID of the transcript\n        required: true\n      - name: subtitle_format\n        type: string\n        description: The format of the captions\n        required: true\n      - name: chars_per_caption\n        type: integer\n        description: The maximum number of characters per caption\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettranscriptsentences\n      description: AssemblyAI Get sentences\
  \ in transcript\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assemblyai.gettranscriptsentences\n      with:\n        transcript_id: tools.transcript_id\n      inputParameters:\n      - name: transcript_id\n        type: string\n        description: ID of the transcript\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettranscriptparagraphs\n      description: AssemblyAI Get paragraphs in transcript\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assemblyai.gettranscriptparagraphs\n      with:\n        transcript_id: tools.transcript_id\n      inputParameters:\n      - name: transcript_id\n        type: string\n        description: ID of the transcript\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wordsearch\n      description: AssemblyAI Search words in transcript\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assemblyai.wordsearch\n      with:\n        transcript_id: tools.transcript_id\n        words: tools.words\n      inputParameters:\n      - name: transcript_id\n        type: string\n        description: ID of the transcript\n        required: true\n      - name: words\n        type: array\n        description: Keywords to search for\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getredactedaudio\n      description: AssemblyAI Get redacted audio\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assemblyai.getredactedaudio\n      with:\n        transcript_id: tools.transcript_id\n      inputParameters:\n      - name: transcript_id\n        type: string\n        description: ID of the transcript\n        required: true\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: createtemporarytoken\n      description: AssemblyAI Create temporary authentication token for Streaming STT\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: assemblyai.createtemporarytoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lemurtask\n      description: AssemblyAI Run a task using LeMUR\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: assemblyai.lemurtask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lemursummary\n      description: AssemblyAI Summarize a transcript using LeMUR\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: assemblyai.lemursummary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lemurquestionanswer\n      description: AssemblyAI Ask questions using LeMUR\n \
  \     hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: assemblyai.lemurquestionanswer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lemuractionitems\n      description: AssemblyAI Extract action items\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: assemblyai.lemuractionitems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: purgelemurrequestdata\n      description: AssemblyAI Purge LeMUR request data\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: assemblyai.purgelemurrequestdata\n      with:\n        request_id: tools.request_id\n      inputParameters:\n      - name: request_id\n        type: string\n        description: The ID of the LeMUR request whose data you want to delete. This would be found in the response of the\n          original request.\n   \
  \     required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/assemblyai/refs/heads/main/capabilities/assemblyai-capability.yaml
tags:
- Assemblyai
- API
tools:
- description: AssemblyAI Upload a media file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadfile
- description: AssemblyAI Transcribe audio
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtranscript
- description: AssemblyAI List transcripts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtranscripts
- description: AssemblyAI Get transcript
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettranscript
- description: AssemblyAI Delete transcript
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetranscript
- description: AssemblyAI Get subtitles for transcript
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubtitles
- description: AssemblyAI Get sentences in transcript
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettranscriptsentences
- description: AssemblyAI Get paragraphs in transcript
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettranscriptparagraphs
- description: AssemblyAI Search words in transcript
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: wordsearch
- description: AssemblyAI Get redacted audio
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getredactedaudio
- description: AssemblyAI Create temporary authentication token for Streaming STT
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtemporarytoken
- description: AssemblyAI Run a task using LeMUR
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lemurtask
- description: AssemblyAI Summarize a transcript using LeMUR
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lemursummary
- description: AssemblyAI Ask questions using LeMUR
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lemurquestionanswer
- description: AssemblyAI Extract action items
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lemuractionitems
- description: AssemblyAI Purge LeMUR request data
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: purgelemurrequestdata
---
