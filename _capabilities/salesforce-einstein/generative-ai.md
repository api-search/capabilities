---
categories: []
consumed_apis: []
description: Workflow capability combining Einstein GPT and Einstein Bots for generative AI and conversational AI workflows. Covers content generation, prompt management, chatbot sessions, and AI-powered customer interactions for CRM developers and customer service teams.
layout: capability
name: Salesforce Einstein Generative AI
operations:
- description: Generate Salesforce content using an Einstein prompt template.
  method: POST
  name: generate-content
  path: /v1/generations
- description: Send a raw prompt for LLM completion.
  method: POST
  name: complete-prompt
  path: /v1/completions
- description: Generate a multi-turn chat response.
  method: POST
  name: chat
  path: /v1/chat
- description: List available prompt templates.
  method: GET
  name: list-prompt-templates
  path: /v1/prompt-templates
- description: Create a new prompt template.
  method: POST
  name: create-prompt-template
  path: /v1/prompt-templates
- description: List all configured Einstein Bots.
  method: GET
  name: list-bots
  path: /v1/bots
- description: Create a new conversation session with a bot.
  method: POST
  name: create-session
  path: /v1/bot-sessions
personas: []
provider_name: Salesforce Einstein
provider_slug: salesforce-einstein
search_terms:
- salesforce einstein
- start a new conversation session with an einstein bot for customer service.
- create session
- gpt
- send a raw prompt to einstein gpt for direct llm completion.
- generate salesforce content using an einstein prompt template.
- generate a multi-turn chat response using einstein gpt.
- create a new einstein prompt template for content generation.
- chatbots
- conversational ai
- generate salesforce content
- content generation
- create bot conversation
- artificial intelligence
- create a new prompt template.
- list available prompt templates.
- crm
- create a new conversation session with a bot.
- machine learning
- bot conversation sessions.
- list bots
- salesforce
- send bot message
- generate a multi-turn chat response.
- ai content generation from prompt templates.
- computer vision
- generative ai
- direct llm prompt completions.
- chat
- large language models
- natural language processing
- chat with einstein gpt
- send a raw prompt for llm completion.
- list all available einstein prompt templates.
- list einstein bots
- manage einstein prompt templates.
- einstein bot definitions.
- create prompt template
- generate content
- chat-style ai generation.
- generate salesforce content (emails, summaries, case notes) using an einstein prompt template.
- predictive analytics
- list all configured einstein bots.
- send a message to an active einstein bot conversation session.
- list prompt templates
- complete prompt
- list all einstein bots configured in the salesforce org.
slug: generative-ai
source_filename: generative-ai.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Einstein Generative AI\n  description: Workflow capability combining Einstein GPT and Einstein Bots for generative AI and conversational AI workflows.\n    Covers content generation, prompt management, chatbot sessions, and AI-powered customer interactions for CRM developers\n    and customer service teams.\n  tags:\n  - Chatbots\n  - Content Generation\n  - Conversational AI\n  - CRM\n  - Generative AI\n  - GPT\n  - Large Language Models\n  - Salesforce Einstein\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_EINSTEIN_GPT_TOKEN: SALESFORCE_EINSTEIN_GPT_TOKEN\n    SALESFORCE_BOTS_TOKEN: SALESFORCE_BOTS_TOKEN\n    SALESFORCE_INSTANCE_URL: SALESFORCE_INSTANCE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: einstein-gpt\n    baseUri: '{{env.SALESFORCE_INSTANCE_URL}}/services/data/v58.0'\n    description: Salesforce Einstein GPT / Generative AI API.\n    authentication:\n\
  \      type: bearer\n      token: '{{env.SALESFORCE_EINSTEIN_GPT_TOKEN}}'\n    resources:\n    - name: generations\n      path: /einstein/llm/prompt/generations\n      description: Generate content from prompt templates.\n      operations:\n      - name: generate-from-prompt\n        method: POST\n        description: Generate content using a prompt template.\n        outputRawFormat: json\n        outputParameters:\n        - name: generation\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            promptTemplateName: '{{tools.promptTemplateName}}'\n            inputParams: '{{tools.inputParams}}'\n    - name: completions\n      path: /einstein/llm/prompt/completions\n      description: Direct LLM prompt completions.\n      operations:\n      - name: complete-prompt\n        method: POST\n        description: Send a raw prompt to the LLM for completion.\n        outputRawFormat: json\n        outputParameters:\n        - name: completion\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            modelName: '{{tools.modelName}}'\n    - name: chat\n      path: /einstein/llm/prompt/chat\n      description: Chat-style generation.\n      operations:\n      - name: chat-generation\n        method: POST\n        description: Generate a chat response using conversation history.\n        outputRawFormat: json\n        outputParameters:\n        - name: chat\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            messages: '{{tools.messages}}'\n            modelName: '{{tools.modelName}}'\n    - name: prompt-templates\n      path: /einstein/llm/prompt-templates\n      description: Manage prompt templates.\n      operations:\n      - name: list-prompt-templates\n        method: GET\n        description: List all available prompt templates.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: templates\n          type: object\n          value: $.\n      - name: create-prompt-template\n        method: POST\n        description: Create a new prompt template.\n        outputRawFormat: json\n        outputParameters:\n        - name: template\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            templateContent: '{{tools.templateContent}}'\n  - type: http\n    namespace: einstein-bots\n    baseUri: '{{env.SALESFORCE_INSTANCE_URL}}/services/data/v58.0/einstein/bots'\n    description: Salesforce Einstein Bots conversational AI API.\n    authentication:\n      type: bearer\n      token: '{{env.SALESFORCE_BOTS_TOKEN}}'\n    resources:\n    - name: bots\n      path: /bots\n      description: Einstein Bot definitions.\n      operations:\n      - name: list-bots\n        method: GET\n        description: List all Einstein Bots in the org.\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: bots\n          type: object\n          value: $.\n      - name: get-bot\n        method: GET\n        description: Get a bot by ID.\n        inputParameters:\n        - name: botId\n          in: path\n          type: string\n          required: true\n          description: Bot ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: bot\n          type: object\n          value: $.\n    - name: sessions\n      path: /sessions\n      description: Bot conversation sessions.\n      operations:\n      - name: create-session\n        method: POST\n        description: Create a new conversation session with a bot.\n        outputRawFormat: json\n        outputParameters:\n        - name: session\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            botId: '{{tools.botId}}'\n            externalSessionKey: '{{tools.externalSessionKey}}'\n      - name: send-message\n       \
  \ method: POST\n        description: Send a message to an active bot session.\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Session ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: response\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message:\n              text: '{{tools.text}}'\n              type: '{{tools.type}}'\n      - name: end-session\n        method: DELETE\n        description: End an active bot session.\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Session ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: einstein-generative-ai-api\n    description:\
  \ Unified REST API for Salesforce Einstein generative and conversational AI.\n    resources:\n    - path: /v1/generations\n      name: generations\n      description: AI content generation from prompt templates.\n      operations:\n      - method: POST\n        name: generate-content\n        description: Generate Salesforce content using an Einstein prompt template.\n        call: einstein-gpt.generate-from-prompt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/completions\n      name: completions\n      description: Direct LLM prompt completions.\n      operations:\n      - method: POST\n        name: complete-prompt\n        description: Send a raw prompt for LLM completion.\n        call: einstein-gpt.complete-prompt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/chat\n      name: chat\n      description: Chat-style AI generation.\n      operations:\n      - method: POST\n        name: chat\n   \
  \     description: Generate a multi-turn chat response.\n        call: einstein-gpt.chat-generation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/prompt-templates\n      name: prompt-templates\n      description: Manage Einstein prompt templates.\n      operations:\n      - method: GET\n        name: list-prompt-templates\n        description: List available prompt templates.\n        call: einstein-gpt.list-prompt-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-prompt-template\n        description: Create a new prompt template.\n        call: einstein-gpt.create-prompt-template\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bots\n      name: bots\n      description: Einstein Bot definitions.\n      operations:\n      - method: GET\n        name: list-bots\n        description: List all configured Einstein Bots.\n     \
  \   call: einstein-bots.list-bots\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bot-sessions\n      name: bot-sessions\n      description: Bot conversation sessions.\n      operations:\n      - method: POST\n        name: create-session\n        description: Create a new conversation session with a bot.\n        call: einstein-bots.create-session\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: einstein-generative-ai-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce Einstein generative AI workflows.\n    tools:\n    - name: generate-salesforce-content\n      description: Generate Salesforce content (emails, summaries, case notes) using an Einstein prompt template.\n      hints:\n        readOnly: false\n        destructive: false\n      call: einstein-gpt.generate-from-prompt\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: complete-prompt\n      description: Send a raw prompt to Einstein GPT for direct LLM completion.\n      hints:\n        readOnly: false\n        destructive: false\n      call: einstein-gpt.complete-prompt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chat-with-einstein-gpt\n      description: Generate a multi-turn chat response using Einstein GPT.\n      hints:\n        readOnly: false\n        destructive: false\n      call: einstein-gpt.chat-generation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-prompt-templates\n      description: List all available Einstein prompt templates.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-gpt.list-prompt-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-prompt-template\n      description: Create a new Einstein prompt template for content generation.\n      hints:\n    \
  \    readOnly: false\n        destructive: false\n      call: einstein-gpt.create-prompt-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-einstein-bots\n      description: List all Einstein Bots configured in the Salesforce org.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-bots.list-bots\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bot-conversation\n      description: Start a new conversation session with an Einstein Bot for customer service.\n      hints:\n        readOnly: false\n        destructive: false\n      call: einstein-bots.create-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-bot-message\n      description: Send a message to an active Einstein Bot conversation session.\n      hints:\n        readOnly: false\n        destructive: false\n      call: einstein-bots.send-message\n      with:\n        sessionId:\
  \ tools.sessionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-einstein/refs/heads/main/capabilities/generative-ai.yaml
tags:
- Chatbots
- Content Generation
- Conversational AI
- CRM
- Generative AI
- GPT
- Large Language Models
- Salesforce Einstein
tools:
- description: Generate Salesforce content (emails, summaries, case notes) using an Einstein prompt template.
  hints:
    destructive: false
    readOnly: false
  name: generate-salesforce-content
- description: Send a raw prompt to Einstein GPT for direct LLM completion.
  hints:
    destructive: false
    readOnly: false
  name: complete-prompt
- description: Generate a multi-turn chat response using Einstein GPT.
  hints:
    destructive: false
    readOnly: false
  name: chat-with-einstein-gpt
- description: List all available Einstein prompt templates.
  hints:
    idempotent: true
    readOnly: true
  name: list-prompt-templates
- description: Create a new Einstein prompt template for content generation.
  hints:
    destructive: false
    readOnly: false
  name: create-prompt-template
- description: List all Einstein Bots configured in the Salesforce org.
  hints:
    idempotent: true
    readOnly: true
  name: list-einstein-bots
- description: Start a new conversation session with an Einstein Bot for customer service.
  hints:
    destructive: false
    readOnly: false
  name: create-bot-conversation
- description: Send a message to an active Einstein Bot conversation session.
  hints:
    destructive: false
    readOnly: false
  name: send-bot-message
---
