---
categories:
- machine-learning
consumed_apis:
- snowflake-cortex-analyst
- snowflake-cortex-inference
- snowflake-cortex-search
- snowflake-notebook
description: Unified workflow for AI and ML capabilities including LLM inference, natural language analytics, semantic search, and notebook-based development. Used by Data Scientists and ML Engineers for AI-powered data exploration and model deployment.
layout: capability
name: Snowflake Cortex AI
operations:
- description: Ask a question about your data
  method: POST
  name: send-analyst-message
  path: /v1/analyst/messages
- description: Run LLM completion
  method: POST
  name: complete
  path: /v1/inference/complete
- description: List available LLM models
  method: GET
  name: list-models
  path: /v1/inference/models
- description: Query a search service
  method: POST
  name: query-search
  path: /v1/search
- description: List notebooks
  method: GET
  name: list-notebooks
  path: /v1/notebooks
- description: Create a notebook
  method: POST
  name: create-notebook
  path: /v1/notebooks
personas: []
provider_name: Snowflake
provider_slug: snowflake
search_terms:
- notebook management
- generate verified query suggestions
- available models
- query a cortex search service
- snowflake
- create notebook
- machine learning
- run llm completion
- query a search service
- execute a notebook
- execute notebook
- list cortex search services
- list search services
- list models
- sql
- data lakes
- natural language data analytics
- query search
- data warehousing
- database
- generate query suggestions
- list llm models
- list available cortex llm models
- data sharing
- ask analyst
- create a notebook
- ai
- send feedback on an analyst response
- list available llm models
- semantic search
- cortex
- list notebooks
- llm complete
- send analyst feedback
- send analyst message
- ask a question about your data
- ask a question about your data using natural language
- complete
- llm inference
- run llm inference completion
slug: cortex-ai
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Cortex AI\"\n  description: \"Unified workflow for AI and ML capabilities including LLM inference, natural language analytics, semantic search, and notebook-based development. Used by Data Scientists and ML Engineers for AI-powered data exploration and model deployment.\"\n  tags:\n    - Snowflake\n    - Cortex\n    - AI\n    - Machine Learning\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-cortex-analyst\n      location: ./shared/cortex-analyst.yaml\n    - import: snowflake-cortex-inference\n      location: ./shared/cortex-inference.yaml\n    - import: snowflake-cortex-search\n      location: ./shared/cortex-search-service.yaml\n    - import: snowflake-notebook\n      location: ./shared/notebook.yaml\n\n  exposes:\n  \
  \  - type: rest\n      port: 8082\n      namespace: snowflake-cortex-api\n      description: \"Unified REST API for Snowflake Cortex AI capabilities.\"\n      resources:\n        - path: /v1/analyst/messages\n          name: analyst-messages\n          description: \"Natural language data analytics\"\n          operations:\n            - method: POST\n              name: send-analyst-message\n              description: \"Ask a question about your data\"\n              call: \"snowflake-cortex-analyst.send-message\"\n        - path: /v1/inference/complete\n          name: inference\n          description: \"LLM inference\"\n          operations:\n            - method: POST\n              name: complete\n              description: \"Run LLM completion\"\n              call: \"snowflake-cortex-inference.complete\"\n        - path: /v1/inference/models\n          name: models\n          description: \"Available models\"\n          operations:\n            - method: GET\n              name:\
  \ list-models\n              description: \"List available LLM models\"\n              call: \"snowflake-cortex-inference.get-models\"\n        - path: /v1/search\n          name: search\n          description: \"Semantic search\"\n          operations:\n            - method: POST\n              name: query-search\n              description: \"Query a search service\"\n              call: \"snowflake-cortex-search.query-search-service\"\n        - path: /v1/notebooks\n          name: notebooks\n          description: \"Notebook management\"\n          operations:\n            - method: GET\n              name: list-notebooks\n              description: \"List notebooks\"\n              call: \"snowflake-notebook.list-notebooks\"\n            - method: POST\n              name: create-notebook\n              description: \"Create a notebook\"\n              call: \"snowflake-notebook.create-notebook\"\n\n    - type: mcp\n      port: 9082\n      namespace: snowflake-cortex-mcp\n      transport:\
  \ http\n      description: \"MCP server for AI-assisted Snowflake Cortex AI capabilities.\"\n      tools:\n        - name: ask-analyst\n          description: \"Ask a question about your data using natural language\"\n          hints:\n            readOnly: true\n          call: \"snowflake-cortex-analyst.send-message\"\n        - name: send-analyst-feedback\n          description: \"Send feedback on an Analyst response\"\n          hints:\n            readOnly: false\n          call: \"snowflake-cortex-analyst.send-feedback\"\n        - name: generate-query-suggestions\n          description: \"Generate verified query suggestions\"\n          hints:\n            readOnly: true\n          call: \"snowflake-cortex-analyst.generate-verified-query-suggestions\"\n        - name: list-llm-models\n          description: \"List available Cortex LLM models\"\n          hints:\n            readOnly: true\n          call: \"snowflake-cortex-inference.get-models\"\n        - name: llm-complete\n\
  \          description: \"Run LLM inference completion\"\n          hints:\n            readOnly: true\n          call: \"snowflake-cortex-inference.complete\"\n        - name: semantic-search\n          description: \"Query a Cortex Search service\"\n          hints:\n            readOnly: true\n          call: \"snowflake-cortex-search.query-search-service\"\n        - name: list-search-services\n          description: \"List Cortex Search services\"\n          hints:\n            readOnly: true\n          call: \"snowflake-cortex-search.list-search-services\"\n        - name: list-notebooks\n          description: \"List notebooks\"\n          hints:\n            readOnly: true\n          call: \"snowflake-notebook.list-notebooks\"\n        - name: create-notebook\n          description: \"Create a notebook\"\n          hints:\n            readOnly: false\n          call: \"snowflake-notebook.create-notebook\"\n        - name: execute-notebook\n          description: \"Execute a notebook\"\
  \n          hints:\n            readOnly: false\n          call: \"snowflake-notebook.execute-notebook\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/cortex-ai.yaml
tags:
- Snowflake
- Cortex
- AI
- Machine Learning
tools:
- description: Ask a question about your data using natural language
  hints:
    readOnly: true
  name: ask-analyst
- description: Send feedback on an Analyst response
  hints:
    readOnly: false
  name: send-analyst-feedback
- description: Generate verified query suggestions
  hints:
    readOnly: true
  name: generate-query-suggestions
- description: List available Cortex LLM models
  hints:
    readOnly: true
  name: list-llm-models
- description: Run LLM inference completion
  hints:
    readOnly: true
  name: llm-complete
- description: Query a Cortex Search service
  hints:
    readOnly: true
  name: semantic-search
- description: List Cortex Search services
  hints:
    readOnly: true
  name: list-search-services
- description: List notebooks
  hints:
    readOnly: true
  name: list-notebooks
- description: Create a notebook
  hints:
    readOnly: false
  name: create-notebook
- description: Execute a notebook
  hints:
    readOnly: false
  name: execute-notebook
---
