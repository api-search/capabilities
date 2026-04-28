---
categories:
- ai-platform
consumed_apis:
- openrouter-api
description: Workflow capability for AI platform engineers consolidating LLM access through a single endpoint to route LLM calls across providers with cost telemetry per generation. Combines model discovery, auto-routed chat completion, per-generation cost lookup, model usage reporting, and spend controls into a unified surface for multi-model AI applications.
layout: capability
name: OpenRouter Multi-Model Router
operations:
- description: List all available models exposed by the OpenRouter router
  method: GET
  name: list-models
  path: /api/v1/models
- description: Create a chat completion that auto-routes to the best provider model
  method: POST
  name: create-chat-completion
  path: /api/v1/chat/completions
- description: Get the cost and token usage for a specific generation
  method: GET
  name: get-generation-cost
  path: /api/v1/generation
- description: List usage broken down by model
  method: GET
  name: list-usage-by-model
  path: /api/v1/credits
- description: Set a spend limit for the account or key
  method: POST
  name: set-spend-limit
  path: /api/v1/credits
- description: Get current credit balance and account spend
  method: GET
  name: get-credit-balance
  path: /api/v1/credits
personas:
- AI Platform Engineer
provider_name: OpenRouter
provider_slug: openrouter
search_terms:
- list available llm models
- multi-model router
- route llm calls across providers
- openrouter chat completions
- auto-route llm
- per-generation cost telemetry
- get generation cost
- list usage by model
- set spend limit
- llm cost control
- model routing
- single endpoint multi-provider llm
- ai gateway
- openrouter generation cost
- llm spend management
- model catalog
- chat completion auto-route
- credits balance
- llm telemetry
- ai platform engineer
- consolidated llm access
- one endpoint many models
- llm budget cap
slug: multi-model-router
tags:
- LLM Gateway
- Model Routing
- AI Cost Control
- Multi-Model
- OpenRouter
tools:
- description: List all LLM models available through the OpenRouter router with their pricing and capabilities
  hints:
    openWorld: false
    readOnly: true
  name: list-models
- description: Create a chat completion that auto-routes to the best available provider model
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-chat-completion
- description: Get the cost and token usage for a specific generation by id
  hints:
    openWorld: false
    readOnly: true
  name: get-generation-cost
- description: List recent usage broken down by model to understand cost distribution
  hints:
    openWorld: false
    readOnly: true
  name: list-usage-by-model
- description: Set a spend limit on the account or key to cap LLM costs
  hints:
    destructive: false
    idempotent: true
    openWorld: false
    readOnly: false
  name: set-spend-limit
- description: Get the current credit balance and account spend totals
  hints:
    openWorld: false
    readOnly: true
  name: get-credit-balance
---
