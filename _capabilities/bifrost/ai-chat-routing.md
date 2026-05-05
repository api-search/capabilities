---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Ai Chat Routing
operations: []
personas: []
provider_name: Bifrost
provider_slug: bifrost
search_terms:
- openai-compatible chat completion interface
- unified routing to multiple ai llm providers
- llm
- health monitoring and provider status tracking
- engineer managing bifrost gateway deployments and provider config
- ai gateway
- mcp
- openai compatible
- route chat completions to 20+ ai providers with failover
- load balancing
- engineer building ai applications using bifrost as a unified gateway
- open source
slug: ai-chat-routing
source_filename: ai-chat-routing.yaml
source_heading: Capability Spec
source_yaml: "name: AI Chat Routing\ndescription: >-\n  Workflow capability for routing AI chat completions through the Bifrost\n  gateway to 20+ AI providers with automatic failover and load balancing.\nversion: v1\n\nimports:\n  - shared/bifrost.yaml\n\ntools:\n  - name: create-chat-completion\n    import: bifrost.create-chat-completion\n    description: >-\n      Send a chat message to any AI provider using the provider/model-name\n      format. Supports OpenAI, Anthropic, Cohere, and 20+ other providers.\n    inputSchema:\n      type: object\n      required:\n        - model\n        - messages\n      properties:\n        model:\n          type: string\n          description: Provider and model in format provider/model-name (e.g. openai/gpt-4o)\n        messages:\n          type: array\n          description: Conversation messages array\n        temperature:\n          type: number\n          description: Sampling temperature (0-2)\n        max_tokens:\n          type: integer\n    \
  \      description: Maximum tokens to generate\n  - name: stream-chat-completion\n    import: bifrost.stream-chat-completion\n    description: >-\n      Stream a chat completion response as server-sent events from any\n      supported AI provider.\n    inputSchema:\n      type: object\n      required:\n        - model\n        - messages\n      properties:\n        model:\n          type: string\n          description: Provider and model in format provider/model-name\n        messages:\n          type: array\n          description: Conversation messages array\n  - name: get-gateway-health\n    import: bifrost.get-health\n    description: Check the health of the Bifrost gateway and all configured providers.\n\nexpose:\n  rest:\n    port: 8080\n  mcp:\n    port: 9080\n\npersonas:\n  - id: ai-engineer\n    name: AI Engineer\n    description: Engineer building AI applications that need multi-provider LLM access\n  - id: platform-engineer\n    name: Platform Engineer\n    description: Engineer\
  \ managing Bifrost gateway deployments and provider configuration\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bifrost/refs/heads/main/capabilities/ai-chat-routing.yaml
tags: []
tools: []
---
