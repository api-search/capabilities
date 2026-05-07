---
categories: []
consumed_apis: []
description: OpenRouter provides unified access to hundreds of AI models through a single API endpoint. It implements the OpenAI API specification for chat completions, allowing developers to use any model with the same request and response format. The API also exposes model discovery, generation statistics, credits and balance information, and provisioning endpoints for programmatic key management.
layout: capability
name: OpenRouter API
operations:
- description: Create chat completion
  method: POST
  name: createchatcompletion
  path: /chat/completions
- description: Create completion
  method: POST
  name: createcompletion
  path: /completions
- description: List available models
  method: GET
  name: listmodels
  path: /models
- description: List endpoints for a model
  method: GET
  name: listmodelendpoints
  path: /models/{author}/{slug}/endpoints
- description: Get generation stats
  method: GET
  name: getgeneration
  path: /generation
- description: Get credit balance
  method: GET
  name: getcredits
  path: /credits
- description: List providers
  method: GET
  name: listproviders
  path: /providers
- description: List API keys
  method: GET
  name: listkeys
  path: /keys
- description: Create API key
  method: POST
  name: createkey
  path: /keys
- description: Get API key
  method: GET
  name: getkey
  path: /keys/{hash}
- description: Delete API key
  method: DELETE
  name: deletekey
  path: /keys/{hash}
- description: Update API key
  method: PATCH
  name: updatekey
  path: /keys/{hash}
personas: []
provider_name: OpenRouter
provider_slug: openrouter
search_terms:
- create completion
- delete api key
- list providers
- updatekey
- api
- listproviders
- get credit balance
- openrouter
- artificial intelligence
- get api key
- createcompletion
- router
- listmodels
- createchatcompletion
- listmodelendpoints
- deletekey
- listkeys
- gateway
- getcredits
- list api keys
- getkey
- large language models
- create api key
- getgeneration
- list endpoints for a model
- createkey
- get generation stats
- create chat completion
- update api key
- list available models
slug: openrouter-capability
source_filename: openrouter-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenRouter API\n  description: OpenRouter provides unified access to hundreds of AI models through a single API endpoint. It implements the\n    OpenAI API specification for chat completions, allowing developers to use any model with the same request and response\n    format. The API also exposes model discovery, generation statistics, credits and balance information, and provisioning\n    endpoints for programmatic key management.\n  tags:\n  - Openrouter\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openrouter\n    baseUri: https://openrouter.ai/api/v1\n    description: OpenRouter API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OPENROUTER_TOKEN}}'\n    resources:\n    - name: chat-completions\n      path: /chat/completions\n      operations:\n      - name: createchatcompletion\n        method: POST\n        description: Create chat completion\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: completions\n      path: /completions\n      operations:\n      - name: createcompletion\n        method: POST\n        description: Create completion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /models\n      operations:\n      - name: listmodels\n        method: GET\n        description: List available models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models-author-slug-endpoints\n      path: /models/{author}/{slug}/endpoints\n      operations:\n      - name: listmodelendpoints\n        method: GET\n        description: List endpoints for a model\n        inputParameters:\n        - name: author\n          in: path\n          type: string\n\
  \          required: true\n        - name: slug\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generation\n      path: /generation\n      operations:\n      - name: getgeneration\n        method: GET\n        description: Get generation stats\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Generation identifier returned in chat completion responses.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credits\n      path: /credits\n      operations:\n      - name: getcredits\n        method: GET\n        description: Get credit balance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: providers\n      path: /providers\n      operations:\n      - name: listproviders\n        method: GET\n        description: List providers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keys\n      path: /keys\n      operations:\n      - name: listkeys\n        method: GET\n        description: List API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createkey\n        method: POST\n        description: Create API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keys-hash\n      path: /keys/{hash}\n      operations:\n      - name: getkey\n        method: GET\n        description: Get API key\n        inputParameters:\n        - name: hash\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletekey\n        method: DELETE\n        description: Delete API key\n        inputParameters:\n        - name: hash\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatekey\n        method: PATCH\n        description: Update API key\n        inputParameters:\n        - name: hash\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openrouter-rest\n    description: REST adapter for OpenRouter API.\n    resources:\n    - path: /chat/completions\n      name:\
  \ createchatcompletion\n      operations:\n      - method: POST\n        name: createchatcompletion\n        description: Create chat completion\n        call: openrouter.createchatcompletion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /completions\n      name: createcompletion\n      operations:\n      - method: POST\n        name: createcompletion\n        description: Create completion\n        call: openrouter.createcompletion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models\n      name: listmodels\n      operations:\n      - method: GET\n        name: listmodels\n        description: List available models\n        call: openrouter.listmodels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models/{author}/{slug}/endpoints\n      name: listmodelendpoints\n      operations:\n      - method: GET\n        name: listmodelendpoints\n        description: List endpoints\
  \ for a model\n        call: openrouter.listmodelendpoints\n        with:\n          author: rest.author\n          slug: rest.slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /generation\n      name: getgeneration\n      operations:\n      - method: GET\n        name: getgeneration\n        description: Get generation stats\n        call: openrouter.getgeneration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credits\n      name: getcredits\n      operations:\n      - method: GET\n        name: getcredits\n        description: Get credit balance\n        call: openrouter.getcredits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /providers\n      name: listproviders\n      operations:\n      - method: GET\n        name: listproviders\n        description: List providers\n        call: openrouter.listproviders\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /keys\n      name: listkeys\n      operations:\n      - method: GET\n        name: listkeys\n        description: List API keys\n        call: openrouter.listkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /keys\n      name: createkey\n      operations:\n      - method: POST\n        name: createkey\n        description: Create API key\n        call: openrouter.createkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /keys/{hash}\n      name: getkey\n      operations:\n      - method: GET\n        name: getkey\n        description: Get API key\n        call: openrouter.getkey\n        with:\n          hash: rest.hash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /keys/{hash}\n      name: deletekey\n      operations:\n      - method: DELETE\n        name: deletekey\n        description: Delete API key\n        call: openrouter.deletekey\n\
  \        with:\n          hash: rest.hash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /keys/{hash}\n      name: updatekey\n      operations:\n      - method: PATCH\n        name: updatekey\n        description: Update API key\n        call: openrouter.updatekey\n        with:\n          hash: rest.hash\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: openrouter-mcp\n    transport: http\n    description: MCP adapter for OpenRouter API for AI agent use.\n    tools:\n    - name: createchatcompletion\n      description: Create chat completion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openrouter.createchatcompletion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcompletion\n      description: Create completion\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: openrouter.createcompletion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmodels\n      description: List available models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openrouter.listmodels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmodelendpoints\n      description: List endpoints for a model\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openrouter.listmodelendpoints\n      with:\n        author: tools.author\n        slug: tools.slug\n      inputParameters:\n      - name: author\n        type: string\n        description: author\n        required: true\n      - name: slug\n        type: string\n        description: slug\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgeneration\n      description:\
  \ Get generation stats\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openrouter.getgeneration\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: Generation identifier returned in chat completion responses.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcredits\n      description: Get credit balance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openrouter.getcredits\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproviders\n      description: List providers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openrouter.listproviders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listkeys\n      description: List API keys\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openrouter.listkeys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createkey\n      description: Create API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openrouter.createkey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getkey\n      description: Get API key\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openrouter.getkey\n      with:\n        hash: tools.hash\n      inputParameters:\n      - name: hash\n        type: string\n        description: hash\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletekey\n      description: Delete API key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n  \
  \    call: openrouter.deletekey\n      with:\n        hash: tools.hash\n      inputParameters:\n      - name: hash\n        type: string\n        description: hash\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatekey\n      description: Update API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openrouter.updatekey\n      with:\n        hash: tools.hash\n      inputParameters:\n      - name: hash\n        type: string\n        description: hash\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPENROUTER_TOKEN: OPENROUTER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openrouter/refs/heads/main/capabilities/openrouter-capability.yaml
tags:
- Openrouter
- API
tools:
- description: Create chat completion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchatcompletion
- description: Create completion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcompletion
- description: List available models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodels
- description: List endpoints for a model
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodelendpoints
- description: Get generation stats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgeneration
- description: Get credit balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcredits
- description: List providers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproviders
- description: List API keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkeys
- description: Create API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createkey
- description: Get API key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkey
- description: Delete API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletekey
- description: Update API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatekey
---
