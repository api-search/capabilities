---
categories: []
consumed_apis:
- einstein-gpt
- einstein-bots
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
- create prompt template
- start a new conversation session with an einstein bot for customer service.
- bot conversation sessions.
- generate a multi-turn chat response using einstein gpt.
- list all available einstein prompt templates.
- create bot conversation
- send a raw prompt to einstein gpt for direct llm completion.
- send a raw prompt for llm completion.
- generative ai
- einstein bot definitions.
- list bots
- list available prompt templates.
- chat-style ai generation.
- salesforce
- chat
- predictive analytics
- generate salesforce content using an einstein prompt template.
- list prompt templates
- create session
- direct llm prompt completions.
- chat with einstein gpt
- generate a multi-turn chat response.
- chatbots
- generate content
- crm
- list all configured einstein bots.
- computer vision
- gpt
- create a new einstein prompt template for content generation.
- create a new prompt template.
- artificial intelligence
- send a message to an active einstein bot conversation session.
- large language models
- list einstein bots
- natural language processing
- create a new conversation session with a bot.
- list all einstein bots configured in the salesforce org.
- salesforce einstein
- send bot message
- machine learning
- content generation
- complete prompt
- ai content generation from prompt templates.
- conversational ai
- generate salesforce content
- manage einstein prompt templates.
- generate salesforce content (emails, summaries, case notes) using an einstein prompt template.
slug: generative-ai
source_filename: generative-ai.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Einstein Generative AI\"\n  description: >-\n    Workflow capability combining Einstein GPT and Einstein Bots for generative\n    AI and conversational AI workflows. Covers content generation, prompt management,\n    chatbot sessions, and AI-powered customer interactions for CRM developers\n    and customer service teams.\n  tags:\n    - Chatbots\n    - Content Generation\n    - Conversational AI\n    - CRM\n    - Generative AI\n    - GPT\n    - Large Language Models\n    - Salesforce Einstein\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_EINSTEIN_GPT_TOKEN: SALESFORCE_EINSTEIN_GPT_TOKEN\n      SALESFORCE_BOTS_TOKEN: SALESFORCE_BOTS_TOKEN\n      SALESFORCE_INSTANCE_URL: SALESFORCE_INSTANCE_URL\n\ncapability:\n  consumes:\n    - import: einstein-gpt\n      location: ./shared/einstein-gpt.yaml\n    - import: einstein-bots\n      location: ./shared/einstein-bots.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8081\n      namespace: einstein-generative-ai-api\n      description: \"Unified REST API for Salesforce Einstein generative and conversational AI.\"\n      resources:\n        - path: /v1/generations\n          name: generations\n          description: \"AI content generation from prompt templates.\"\n          operations:\n            - method: POST\n              name: generate-content\n              description: \"Generate Salesforce content using an Einstein prompt template.\"\n              call: \"einstein-gpt.generate-from-prompt\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/completions\n          name: completions\n          description: \"Direct LLM prompt completions.\"\n          operations:\n            - method: POST\n              name: complete-prompt\n              description: \"Send a raw prompt for LLM completion.\"\n              call: \"einstein-gpt.complete-prompt\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/chat\n          name: chat\n          description: \"Chat-style AI generation.\"\n          operations:\n            - method: POST\n              name: chat\n              description: \"Generate a multi-turn chat response.\"\n              call: \"einstein-gpt.chat-generation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/prompt-templates\n          name: prompt-templates\n          description: \"Manage Einstein prompt templates.\"\n          operations:\n            - method: GET\n              name: list-prompt-templates\n              description: \"List available prompt templates.\"\n              call: \"einstein-gpt.list-prompt-templates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name:\
  \ create-prompt-template\n              description: \"Create a new prompt template.\"\n              call: \"einstein-gpt.create-prompt-template\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bots\n          name: bots\n          description: \"Einstein Bot definitions.\"\n          operations:\n            - method: GET\n              name: list-bots\n              description: \"List all configured Einstein Bots.\"\n              call: \"einstein-bots.list-bots\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bot-sessions\n          name: bot-sessions\n          description: \"Bot conversation sessions.\"\n          operations:\n            - method: POST\n              name: create-session\n              description: \"Create a new conversation session with a bot.\"\n              call: \"einstein-bots.create-session\"\n             \
  \ outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: einstein-generative-ai-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce Einstein generative AI workflows.\"\n      tools:\n        - name: generate-salesforce-content\n          description: \"Generate Salesforce content (emails, summaries, case notes) using an Einstein prompt template.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"einstein-gpt.generate-from-prompt\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: complete-prompt\n          description: \"Send a raw prompt to Einstein GPT for direct LLM completion.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"einstein-gpt.complete-prompt\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: chat-with-einstein-gpt\n          description: \"Generate a multi-turn chat response using Einstein GPT.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"einstein-gpt.chat-generation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-prompt-templates\n          description: \"List all available Einstein prompt templates.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-gpt.list-prompt-templates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-prompt-template\n          description: \"Create a new Einstein prompt template for content generation.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"einstein-gpt.create-prompt-template\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-einstein-bots\n          description: \"List all Einstein Bots configured in the Salesforce org.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-bots.list-bots\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bot-conversation\n          description: \"Start a new conversation session with an Einstein Bot for customer service.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"einstein-bots.create-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-bot-message\n          description: \"Send a message to an active Einstein Bot conversation session.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"einstein-bots.send-message\"\
  \n          with:\n            sessionId: \"tools.sessionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
