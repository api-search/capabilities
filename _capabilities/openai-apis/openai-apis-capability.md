---
categories: []
consumed_apis: []
description: API for building AI assistants with custom instructions, knowledge retrieval, code execution, and function calling capabilities. Supports managing assistants, threads, messages, and runs.
layout: capability
name: OpenAI APIs OpenAI Assistants API
operations:
- description: OpenAI APIs List assistants
  method: GET
  name: listassistants
  path: /assistants
- description: OpenAI APIs Create assistant
  method: POST
  name: createassistant
  path: /assistants
- description: OpenAI APIs Retrieve assistant
  method: GET
  name: getassistant
  path: /assistants/{assistant_id}
- description: OpenAI APIs Modify assistant
  method: POST
  name: modifyassistant
  path: /assistants/{assistant_id}
- description: OpenAI APIs Delete assistant
  method: DELETE
  name: deleteassistant
  path: /assistants/{assistant_id}
- description: OpenAI APIs Create thread
  method: POST
  name: createthread
  path: /threads
- description: OpenAI APIs Retrieve thread
  method: GET
  name: getthread
  path: /threads/{thread_id}
- description: OpenAI APIs Modify thread
  method: POST
  name: modifythread
  path: /threads/{thread_id}
- description: OpenAI APIs Delete thread
  method: DELETE
  name: deletethread
  path: /threads/{thread_id}
- description: OpenAI APIs List messages
  method: GET
  name: listmessages
  path: /threads/{thread_id}/messages
- description: OpenAI APIs Create message
  method: POST
  name: createmessage
  path: /threads/{thread_id}/messages
- description: OpenAI APIs Retrieve message
  method: GET
  name: getmessage
  path: /threads/{thread_id}/messages/{message_id}
- description: OpenAI APIs List runs
  method: GET
  name: listruns
  path: /threads/{thread_id}/runs
- description: OpenAI APIs Create run
  method: POST
  name: createrun
  path: /threads/{thread_id}/runs
- description: OpenAI APIs Retrieve run
  method: GET
  name: getrun
  path: /threads/{thread_id}/runs/{run_id}
- description: OpenAI APIs Cancel run
  method: POST
  name: cancelrun
  path: /threads/{thread_id}/runs/{run_id}/cancel
- description: OpenAI APIs Submit tool outputs
  method: POST
  name: submittooloutputs
  path: /threads/{thread_id}/runs/{run_id}/submit_tool_outputs
- description: OpenAI APIs Create thread and run
  method: POST
  name: createthreadandrun
  path: /threads/runs
personas: []
provider_name: OpenAI APIs
provider_slug: openai-apis
search_terms:
- createassistant
- getmessage
- listruns
- createthreadandrun
- getrun
- openai apis retrieve message
- openai
- language models
- listassistants
- submittooloutputs
- cancelrun
- openai apis retrieve thread
- modifyassistant
- apis
- openai apis create message
- getthread
- openai apis retrieve assistant
- deleteassistant
- openai apis retrieve run
- getassistant
- openai apis list messages
- openai apis modify thread
- embeddings
- openai apis delete thread
- openai apis list assistants
- speech
- artificial intelligence
- openai apis delete assistant
- api
- openai apis create assistant
- openai apis list runs
- openai apis create run
- createthread
- listmessages
- openai apis cancel run
- deletethread
- openai apis create thread and run
- createmessage
- image generation
- createrun
- openai apis create thread
- openai apis modify assistant
- openai apis submit tool outputs
- modifythread
slug: openai-apis-capability
source_filename: openai-apis-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenAI APIs OpenAI Assistants API\n  description: API for building AI assistants with custom instructions, knowledge retrieval, code execution, and function\n    calling capabilities. Supports managing assistants, threads, messages, and runs.\n  tags:\n  - Openai\n  - Apis\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openai-apis\n    baseUri: https://api.openai.com/v1\n    description: OpenAI APIs OpenAI Assistants API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OPENAI_APIS_TOKEN}}'\n    resources:\n    - name: assistants\n      path: /assistants\n      operations:\n      - name: listassistants\n        method: GET\n        description: OpenAI APIs List assistants\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createassistant\n        method: POST\n\
  \        description: OpenAI APIs Create assistant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assistants-assistant-id\n      path: /assistants/{assistant_id}\n      operations:\n      - name: getassistant\n        method: GET\n        description: OpenAI APIs Retrieve assistant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modifyassistant\n        method: POST\n        description: OpenAI APIs Modify assistant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteassistant\n        method: DELETE\n        description: OpenAI APIs Delete assistant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads\n      path:\
  \ /threads\n      operations:\n      - name: createthread\n        method: POST\n        description: OpenAI APIs Create thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads-thread-id\n      path: /threads/{thread_id}\n      operations:\n      - name: getthread\n        method: GET\n        description: OpenAI APIs Retrieve thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modifythread\n        method: POST\n        description: OpenAI APIs Modify thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletethread\n        method: DELETE\n        description: OpenAI APIs Delete thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: threads-thread-id-messages\n      path: /threads/{thread_id}/messages\n      operations:\n      - name: listmessages\n        method: GET\n        description: OpenAI APIs List messages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmessage\n        method: POST\n        description: OpenAI APIs Create message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads-thread-id-messages-message-id\n      path: /threads/{thread_id}/messages/{message_id}\n      operations:\n      - name: getmessage\n        method: GET\n        description: OpenAI APIs Retrieve message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads-thread-id-runs\n      path: /threads/{thread_id}/runs\n   \
  \   operations:\n      - name: listruns\n        method: GET\n        description: OpenAI APIs List runs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrun\n        method: POST\n        description: OpenAI APIs Create run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads-thread-id-runs-run-id\n      path: /threads/{thread_id}/runs/{run_id}\n      operations:\n      - name: getrun\n        method: GET\n        description: OpenAI APIs Retrieve run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads-thread-id-runs-run-id-cancel\n      path: /threads/{thread_id}/runs/{run_id}/cancel\n      operations:\n      - name: cancelrun\n        method: POST\n        description: OpenAI APIs Cancel run\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads-thread-id-runs-run-id-submit-tool-output\n      path: /threads/{thread_id}/runs/{run_id}/submit_tool_outputs\n      operations:\n      - name: submittooloutputs\n        method: POST\n        description: OpenAI APIs Submit tool outputs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads-runs\n      path: /threads/runs\n      operations:\n      - name: createthreadandrun\n        method: POST\n        description: OpenAI APIs Create thread and run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openai-apis-rest\n    description: REST adapter for OpenAI APIs OpenAI Assistants API.\n    resources:\n    - path: /assistants\n\
  \      name: listassistants\n      operations:\n      - method: GET\n        name: listassistants\n        description: OpenAI APIs List assistants\n        call: openai-apis.listassistants\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assistants\n      name: createassistant\n      operations:\n      - method: POST\n        name: createassistant\n        description: OpenAI APIs Create assistant\n        call: openai-apis.createassistant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assistants/{assistant_id}\n      name: getassistant\n      operations:\n      - method: GET\n        name: getassistant\n        description: OpenAI APIs Retrieve assistant\n        call: openai-apis.getassistant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assistants/{assistant_id}\n      name: modifyassistant\n      operations:\n      - method: POST\n        name: modifyassistant\n\
  \        description: OpenAI APIs Modify assistant\n        call: openai-apis.modifyassistant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assistants/{assistant_id}\n      name: deleteassistant\n      operations:\n      - method: DELETE\n        name: deleteassistant\n        description: OpenAI APIs Delete assistant\n        call: openai-apis.deleteassistant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads\n      name: createthread\n      operations:\n      - method: POST\n        name: createthread\n        description: OpenAI APIs Create thread\n        call: openai-apis.createthread\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}\n      name: getthread\n      operations:\n      - method: GET\n        name: getthread\n        description: OpenAI APIs Retrieve thread\n        call: openai-apis.getthread\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /threads/{thread_id}\n      name: modifythread\n      operations:\n      - method: POST\n        name: modifythread\n        description: OpenAI APIs Modify thread\n        call: openai-apis.modifythread\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}\n      name: deletethread\n      operations:\n      - method: DELETE\n        name: deletethread\n        description: OpenAI APIs Delete thread\n        call: openai-apis.deletethread\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}/messages\n      name: listmessages\n      operations:\n      - method: GET\n        name: listmessages\n        description: OpenAI APIs List messages\n        call: openai-apis.listmessages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}/messages\n      name: createmessage\n  \
  \    operations:\n      - method: POST\n        name: createmessage\n        description: OpenAI APIs Create message\n        call: openai-apis.createmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}/messages/{message_id}\n      name: getmessage\n      operations:\n      - method: GET\n        name: getmessage\n        description: OpenAI APIs Retrieve message\n        call: openai-apis.getmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}/runs\n      name: listruns\n      operations:\n      - method: GET\n        name: listruns\n        description: OpenAI APIs List runs\n        call: openai-apis.listruns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}/runs\n      name: createrun\n      operations:\n      - method: POST\n        name: createrun\n        description: OpenAI APIs Create run\n     \
  \   call: openai-apis.createrun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}/runs/{run_id}\n      name: getrun\n      operations:\n      - method: GET\n        name: getrun\n        description: OpenAI APIs Retrieve run\n        call: openai-apis.getrun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}/runs/{run_id}/cancel\n      name: cancelrun\n      operations:\n      - method: POST\n        name: cancelrun\n        description: OpenAI APIs Cancel run\n        call: openai-apis.cancelrun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threads/{thread_id}/runs/{run_id}/submit_tool_outputs\n      name: submittooloutputs\n      operations:\n      - method: POST\n        name: submittooloutputs\n        description: OpenAI APIs Submit tool outputs\n        call: openai-apis.submittooloutputs\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /threads/runs\n      name: createthreadandrun\n      operations:\n      - method: POST\n        name: createthreadandrun\n        description: OpenAI APIs Create thread and run\n        call: openai-apis.createthreadandrun\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: openai-apis-mcp\n    transport: http\n    description: MCP adapter for OpenAI APIs OpenAI Assistants API for AI agent use.\n    tools:\n    - name: listassistants\n      description: OpenAI APIs List assistants\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openai-apis.listassistants\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createassistant\n      description: OpenAI APIs Create assistant\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openai-apis.createassistant\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getassistant\n      description: OpenAI APIs Retrieve assistant\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openai-apis.getassistant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modifyassistant\n      description: OpenAI APIs Modify assistant\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openai-apis.modifyassistant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteassistant\n      description: OpenAI APIs Delete assistant\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: openai-apis.deleteassistant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createthread\n      description: OpenAI APIs Create thread\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: openai-apis.createthread\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getthread\n      description: OpenAI APIs Retrieve thread\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openai-apis.getthread\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modifythread\n      description: OpenAI APIs Modify thread\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openai-apis.modifythread\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletethread\n      description: OpenAI APIs Delete thread\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: openai-apis.deletethread\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmessages\n\
  \      description: OpenAI APIs List messages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openai-apis.listmessages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmessage\n      description: OpenAI APIs Create message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openai-apis.createmessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmessage\n      description: OpenAI APIs Retrieve message\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openai-apis.getmessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listruns\n      description: OpenAI APIs List runs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openai-apis.listruns\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createrun\n      description: OpenAI APIs Create run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openai-apis.createrun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrun\n      description: OpenAI APIs Retrieve run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openai-apis.getrun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelrun\n      description: OpenAI APIs Cancel run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openai-apis.cancelrun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submittooloutputs\n      description: OpenAI APIs Submit tool outputs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: openai-apis.submittooloutputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createthreadandrun\n      description: OpenAI APIs Create thread and run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openai-apis.createthreadandrun\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPENAI_APIS_TOKEN: OPENAI_APIS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openai-apis/refs/heads/main/capabilities/openai-apis-capability.yaml
tags:
- Openai
- Apis
- API
tools:
- description: OpenAI APIs List assistants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassistants
- description: OpenAI APIs Create assistant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createassistant
- description: OpenAI APIs Retrieve assistant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getassistant
- description: OpenAI APIs Modify assistant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: modifyassistant
- description: OpenAI APIs Delete assistant
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteassistant
- description: OpenAI APIs Create thread
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createthread
- description: OpenAI APIs Retrieve thread
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthread
- description: OpenAI APIs Modify thread
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: modifythread
- description: OpenAI APIs Delete thread
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletethread
- description: OpenAI APIs List messages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmessages
- description: OpenAI APIs Create message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmessage
- description: OpenAI APIs Retrieve message
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmessage
- description: OpenAI APIs List runs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listruns
- description: OpenAI APIs Create run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrun
- description: OpenAI APIs Retrieve run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrun
- description: OpenAI APIs Cancel run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelrun
- description: OpenAI APIs Submit tool outputs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submittooloutputs
- description: OpenAI APIs Create thread and run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createthreadandrun
---
