---
categories:
- machine-learning
consumed_apis: []
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
- ask analyst
- list notebooks
- snowflake
- create notebook
- cortex
- complete
- ask a question about your data
- notebook management
- ask a question about your data using natural language
- list search services
- llm complete
- query a search service
- generate query suggestions
- run llm inference completion
- create a notebook
- available models
- list llm models
- ai
- semantic search
- sql
- data sharing
- list cortex search services
- execute a notebook
- data lakes
- database
- machine learning
- llm inference
- list models
- list available llm models
- execute notebook
- run llm completion
- list available cortex llm models
- generate verified query suggestions
- send analyst message
- natural language data analytics
- data warehousing
- query search
- send analyst feedback
- send feedback on an analyst response
- query a cortex search service
slug: cortex-ai
source_filename: cortex-ai.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Snowflake Cortex AI\n  description: Unified workflow for AI and ML capabilities including LLM inference, natural language analytics, semantic search,\n    and notebook-based development. Used by Data Scientists and ML Engineers for AI-powered data exploration and model deployment.\n  tags:\n  - Snowflake\n  - Cortex\n  - AI\n  - Machine Learning\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n    SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: snowflake-cortex-analyst\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Cortex Analyst API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: cortex-analyst\n      path: /api/v2/cortex/analyst\n      description: Cortex Analyst resources\n      operations:\n      - name: send-message\n\
  \        method: POST\n        description: Send a message to Cortex Analyst\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            messages: '{{tools.messages}}'\n      - name: send-feedback\n        method: POST\n        description: Send feedback on a Cortex Analyst response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            request_id: '{{tools.request_id}}'\n            positive: '{{tools.positive}}'\n      - name: generate-verified-query-suggestions\n        method: POST\n        description: Generate verified query suggestions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-scoped-token\n        method: POST\n\
  \        description: Get a scoped token for Cortex Analyst\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-cortex-inference\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Cortex Inference API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: cortex-inference\n      path: /api/v2/cortex/inference\n      description: Cortex inference resources\n      operations:\n      - name: get-models\n        method: GET\n        description: List available Cortex LLM models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: complete\n        method: POST\n        description: Run LLM inference completion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            prompt: '{{tools.prompt}}'\n  - type: http\n    namespace: snowflake-cortex-search\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Cortex Search API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: cortex-search\n      path: /api/v2/databases/{database}/schemas/{schema}/cortex-search-services\n      description: Cortex Search resources\n      operations:\n      - name: list-search-services\n        method: GET\n        description: List Cortex Search services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: query-search-service\n        method: POST\n        description: Query a Cortex Search service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n  - type: http\n    namespace: snowflake-notebook\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Notebook API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: notebooks\n      path: /api/v2/databases/{database}/schemas/{schema}/notebooks\n      description: Notebook resources\n      operations:\n      - name: list-notebooks\n        method: GET\n        description: List notebooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-notebook\n        method: POST\n        description: Create a notebook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-notebook\n        method: GET\n\
  \        description: Fetch a notebook by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-notebook\n        method: DELETE\n        description: Delete a notebook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: execute-notebook\n        method: POST\n        description: Execute a notebook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: snowflake-cortex-api\n    description: Unified REST API for Snowflake Cortex AI capabilities.\n    resources:\n    - path: /v1/analyst/messages\n      name: analyst-messages\n      description: Natural language data analytics\n      operations:\n      - method: POST\n        name: send-analyst-message\n        description:\
  \ Ask a question about your data\n        call: snowflake-cortex-analyst.send-message\n        inputParameters:\n        - name: messages\n          type: array\n          description: Conversation messages to send to Cortex Analyst\n          required: true\n          mapping: body.messages\n        - name: semantic_model_file\n          type: string\n          description: Reference to the semantic model file (e.g. @db.schema.stage/model.yaml)\n          required: false\n          mapping: body.semantic_model_file\n        outputParameters:\n        - name: request_id\n          type: string\n          mapping: $.request_id\n        - name: message\n          type: object\n          mapping: $.message\n        - name: warnings\n          type: array\n          mapping: $.warnings\n    - path: /v1/inference/complete\n      name: inference\n      description: LLM inference\n      operations:\n      - method: POST\n        name: complete\n        description: Run LLM completion\n      \
  \  call: snowflake-cortex-inference.complete\n        inputParameters:\n        - name: model\n          type: string\n          description: Identifier of the Cortex LLM model to run completion against\n          required: true\n          mapping: body.model\n        - name: prompt\n          type: string\n          description: Prompt text to submit for completion\n          required: true\n          mapping: body.prompt\n        outputParameters:\n        - name: id\n          type: string\n          mapping: $.id\n        - name: model\n          type: string\n          mapping: $.model\n        - name: choices\n          type: array\n          mapping: $.choices\n        - name: usage\n          type: object\n          mapping: $.usage\n    - path: /v1/inference/models\n      name: models\n      description: Available models\n      operations:\n      - method: GET\n        name: list-models\n        description: List available LLM models\n        call: snowflake-cortex-inference.get-models\n\
  \        inputParameters: []\n        outputParameters:\n        - name: models\n          type: array\n          mapping: $.data\n    - path: /v1/search\n      name: search\n      description: Semantic search\n      operations:\n      - method: POST\n        name: query-search\n        description: Query a search service\n        call: snowflake-cortex-search.query-search-service\n        inputParameters:\n        - name: database\n          type: string\n          description: Database containing the search service\n          required: true\n          mapping: path.database\n        - name: schema\n          type: string\n          description: Schema containing the search service\n          required: true\n          mapping: path.schema\n        - name: query\n          type: string\n          description: Natural language query string\n          required: true\n          mapping: body.query\n        - name: columns\n          type: array\n          description: Columns to return from\
  \ the search index\n          required: false\n          mapping: body.columns\n        - name: limit\n          type: integer\n          description: Maximum number of results to return\n          required: false\n          mapping: body.limit\n        outputParameters:\n        - name: results\n          type: array\n          mapping: $.results\n        - name: request_id\n          type: string\n          mapping: $.request_id\n    - path: /v1/notebooks\n      name: notebooks\n      description: Notebook management\n      operations:\n      - method: GET\n        name: list-notebooks\n        description: List notebooks\n        call: snowflake-notebook.list-notebooks\n        inputParameters:\n        - name: database\n          type: string\n          description: Database to list notebooks from\n          required: true\n          mapping: path.database\n        - name: schema\n          type: string\n          description: Schema to list notebooks from\n          required: true\n\
  \          mapping: path.schema\n        outputParameters:\n        - name: notebooks\n          type: array\n          mapping: $.data\n      - method: POST\n        name: create-notebook\n        description: Create a notebook\n        call: snowflake-notebook.create-notebook\n        inputParameters:\n        - name: database\n          type: string\n          description: Database to create the notebook in\n          required: true\n          mapping: path.database\n        - name: schema\n          type: string\n          description: Schema to create the notebook in\n          required: true\n          mapping: path.schema\n        - name: name\n          type: string\n          description: Notebook name\n          required: true\n          mapping: body.name\n        - name: comment\n          type: string\n          description: Optional comment describing the notebook\n          required: false\n          mapping: body.comment\n        - name: query_warehouse\n          type:\
  \ string\n          description: Warehouse used to execute notebook cells\n          required: false\n          mapping: body.query_warehouse\n        outputParameters:\n        - name: name\n          type: string\n          mapping: $.name\n        - name: database_name\n          type: string\n          mapping: $.database_name\n        - name: schema_name\n          type: string\n          mapping: $.schema_name\n        - name: created_on\n          type: string\n          mapping: $.created_on\n  - type: mcp\n    port: 9082\n    namespace: snowflake-cortex-mcp\n    transport: http\n    description: MCP server (streaming HTTP) for AI-assisted Snowflake Cortex AI capabilities.\n    tools:\n    - name: ask-analyst\n      description: Ask a question about your data using natural language\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: false\n      call: snowflake-cortex-analyst.send-message\n      inputParameters:\n      - name: messages\n     \
  \   type: array\n        description: Conversation messages to send to Cortex Analyst\n        required: true\n        mapping: body.messages\n      - name: semantic_model_file\n        type: string\n        description: Reference to the semantic model file\n        required: false\n        mapping: body.semantic_model_file\n      outputParameters:\n      - name: request_id\n        type: string\n        mapping: $.request_id\n      - name: message\n        type: object\n        mapping: $.message\n      - name: warnings\n        type: array\n        mapping: $.warnings\n    - name: send-analyst-feedback\n      description: Send feedback on an Analyst response\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-analyst.send-feedback\n      inputParameters:\n      - name: request_id\n        type: string\n        description: Analyst request identifier to attach feedback to\n        required: true\n        mapping: body.request_id\n\
  \      - name: positive\n        type: boolean\n        description: Whether the feedback is positive\n        required: true\n        mapping: body.positive\n      - name: feedback_message\n        type: string\n        description: Optional free-form feedback text\n        required: false\n        mapping: body.feedback_message\n      outputParameters:\n      - name: request_id\n        type: string\n        mapping: $.request_id\n      - name: status\n        type: string\n        mapping: $.status\n    - name: generate-query-suggestions\n      description: Generate verified query suggestions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: false\n      call: snowflake-cortex-analyst.generate-verified-query-suggestions\n      inputParameters:\n      - name: semantic_model_file\n        type: string\n        description: Semantic model file to generate suggestions for\n        required: true\n        mapping: body.semantic_model_file\n      - name:\
  \ limit\n        type: integer\n        description: Maximum number of suggestions to return\n        required: false\n        mapping: body.limit\n      outputParameters:\n      - name: suggestions\n        type: array\n        mapping: $.suggestions\n      - name: request_id\n        type: string\n        mapping: $.request_id\n    - name: list-llm-models\n      description: List available Cortex LLM models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-inference.get-models\n      inputParameters: []\n      outputParameters:\n      - name: models\n        type: array\n        mapping: $.data\n    - name: llm-complete\n      description: Run LLM inference completion\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: false\n      call: snowflake-cortex-inference.complete\n      inputParameters:\n      - name: model\n        type: string\n        description: Identifier of the\
  \ Cortex LLM model\n        required: true\n        mapping: body.model\n      - name: prompt\n        type: string\n        description: Prompt text\n        required: true\n        mapping: body.prompt\n      outputParameters:\n      - name: id\n        type: string\n        mapping: $.id\n      - name: model\n        type: string\n        mapping: $.model\n      - name: choices\n        type: array\n        mapping: $.choices\n      - name: usage\n        type: object\n        mapping: $.usage\n    - name: semantic-search\n      description: Query a Cortex Search service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-search.query-search-service\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the search service\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema containing\
  \ the search service\n        required: true\n        mapping: path.schema\n      - name: query\n        type: string\n        description: Natural language query string\n        required: true\n        mapping: body.query\n      - name: columns\n        type: array\n        description: Columns to return from the search index\n        required: false\n        mapping: body.columns\n      - name: limit\n        type: integer\n        description: Maximum number of results to return\n        required: false\n        mapping: body.limit\n      outputParameters:\n      - name: results\n        type: array\n        mapping: $.results\n      - name: request_id\n        type: string\n        mapping: $.request_id\n    - name: list-search-services\n      description: List Cortex Search services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-search.list-search-services\n      inputParameters:\n      - name: database\n \
  \       type: string\n        description: Database to list search services from\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema to list search services from\n        required: true\n        mapping: path.schema\n      outputParameters:\n      - name: services\n        type: array\n        mapping: $.data\n    - name: list-notebooks\n      description: List notebooks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-notebook.list-notebooks\n      inputParameters:\n      - name: database\n        type: string\n        description: Database to list notebooks from\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema to list notebooks from\n        required: true\n        mapping: path.schema\n      outputParameters:\n      - name: notebooks\n        type: array\n       \
  \ mapping: $.data\n    - name: create-notebook\n      description: Create a notebook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-notebook.create-notebook\n      inputParameters:\n      - name: database\n        type: string\n        description: Database to create the notebook in\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema to create the notebook in\n        required: true\n        mapping: path.schema\n      - name: name\n        type: string\n        description: Notebook name\n        required: true\n        mapping: body.name\n      - name: comment\n        type: string\n        description: Optional comment describing the notebook\n        required: false\n        mapping: body.comment\n      - name: query_warehouse\n        type: string\n        description: Warehouse used to execute notebook cells\n        required: false\n\
  \        mapping: body.query_warehouse\n      outputParameters:\n      - name: name\n        type: string\n        mapping: $.name\n      - name: database_name\n        type: string\n        mapping: $.database_name\n      - name: schema_name\n        type: string\n        mapping: $.schema_name\n      - name: created_on\n        type: string\n        mapping: $.created_on\n    - name: execute-notebook\n      description: Execute a notebook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-notebook.execute-notebook\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the notebook\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema containing the notebook\n        required: true\n        mapping: path.schema\n      - name: name\n        type: string\n        description: Notebook name to\
  \ execute\n        required: true\n        mapping: path.name\n      outputParameters:\n      - name: status\n        type: string\n        mapping: $.status\n      - name: execution_id\n        type: string\n        mapping: $.execution_id\n  - type: mcp\n    port: 9083\n    namespace: snowflake-cortex-mcp-stdio\n    transport: stdio\n    description: MCP server (stdio transport) for local IDE/agent Snowflake Cortex AI use.\n    tools:\n    - name: ask-analyst\n      description: Ask a question about your data using natural language\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: false\n      call: snowflake-cortex-analyst.send-message\n      inputParameters:\n      - name: messages\n        type: array\n        description: Conversation messages to send to Cortex Analyst\n        required: true\n        mapping: body.messages\n      - name: semantic_model_file\n        type: string\n        description: Reference to the semantic model file\n   \
  \     required: false\n        mapping: body.semantic_model_file\n      outputParameters:\n      - name: request_id\n        type: string\n        mapping: $.request_id\n      - name: message\n        type: object\n        mapping: $.message\n      - name: warnings\n        type: array\n        mapping: $.warnings\n    - name: send-analyst-feedback\n      description: Send feedback on an Analyst response\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-analyst.send-feedback\n      inputParameters:\n      - name: request_id\n        type: string\n        description: Analyst request identifier\n        required: true\n        mapping: body.request_id\n      - name: positive\n        type: boolean\n        description: Whether the feedback is positive\n        required: true\n        mapping: body.positive\n      - name: feedback_message\n        type: string\n        description: Optional free-form feedback text\n\
  \        required: false\n        mapping: body.feedback_message\n      outputParameters:\n      - name: request_id\n        type: string\n        mapping: $.request_id\n      - name: status\n        type: string\n        mapping: $.status\n    - name: generate-query-suggestions\n      description: Generate verified query suggestions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: false\n      call: snowflake-cortex-analyst.generate-verified-query-suggestions\n      inputParameters:\n      - name: semantic_model_file\n        type: string\n        description: Semantic model file to generate suggestions for\n        required: true\n        mapping: body.semantic_model_file\n      - name: limit\n        type: integer\n        description: Maximum number of suggestions to return\n        required: false\n        mapping: body.limit\n      outputParameters:\n      - name: suggestions\n        type: array\n        mapping: $.suggestions\n      - name:\
  \ request_id\n        type: string\n        mapping: $.request_id\n    - name: list-llm-models\n      description: List available Cortex LLM models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-inference.get-models\n      inputParameters: []\n      outputParameters:\n      - name: models\n        type: array\n        mapping: $.data\n    - name: llm-complete\n      description: Run LLM inference completion\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: false\n      call: snowflake-cortex-inference.complete\n      inputParameters:\n      - name: model\n        type: string\n        description: Identifier of the Cortex LLM model\n        required: true\n        mapping: body.model\n      - name: prompt\n        type: string\n        description: Prompt text\n        required: true\n        mapping: body.prompt\n      outputParameters:\n      - name: id\n        type: string\n\
  \        mapping: $.id\n      - name: model\n        type: string\n        mapping: $.model\n      - name: choices\n        type: array\n        mapping: $.choices\n      - name: usage\n        type: object\n        mapping: $.usage\n    - name: semantic-search\n      description: Query a Cortex Search service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-search.query-search-service\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the search service\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema containing the search service\n        required: true\n        mapping: path.schema\n      - name: query\n        type: string\n        description: Natural language query string\n        required: true\n        mapping: body.query\n      - name: columns\n        type: array\n\
  \        description: Columns to return from the search index\n        required: false\n        mapping: body.columns\n      - name: limit\n        type: integer\n        description: Maximum number of results to return\n        required: false\n        mapping: body.limit\n      outputParameters:\n      - name: results\n        type: array\n        mapping: $.results\n      - name: request_id\n        type: string\n        mapping: $.request_id\n    - name: list-search-services\n      description: List Cortex Search services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-search.list-search-services\n      inputParameters:\n      - name: database\n        type: string\n        description: Database to list search services from\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema to list search services from\n        required: true\n    \
  \    mapping: path.schema\n      outputParameters:\n      - name: services\n        type: array\n        mapping: $.data\n    - name: list-notebooks\n      description: List notebooks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-notebook.list-notebooks\n      inputParameters:\n      - name: database\n        type: string\n        description: Database to list notebooks from\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema to list notebooks from\n        required: true\n        mapping: path.schema\n      outputParameters:\n      - name: notebooks\n        type: array\n        mapping: $.data\n    - name: create-notebook\n      description: Create a notebook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-notebook.create-notebook\n      inputParameters:\n      - name: database\n\
  \        type: string\n        description: Database to create the notebook in\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema to create the notebook in\n        required: true\n        mapping: path.schema\n      - name: name\n        type: string\n        description: Notebook name\n        required: true\n        mapping: body.name\n      - name: comment\n        type: string\n        description: Optional comment describing the notebook\n        required: false\n        mapping: body.comment\n      - name: query_warehouse\n        type: string\n        description: Warehouse used to execute notebook cells\n        required: false\n        mapping: body.query_warehouse\n      outputParameters:\n      - name: name\n        type: string\n        mapping: $.name\n      - name: database_name\n        type: string\n        mapping: $.database_name\n      - name: schema_name\n        type: string\n        mapping:\
  \ $.schema_name\n      - name: created_on\n        type: string\n        mapping: $.created_on\n    - name: execute-notebook\n      description: Execute a notebook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-notebook.execute-notebook\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the notebook\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema containing the notebook\n        required: true\n        mapping: path.schema\n      - name: name\n        type: string\n        description: Notebook name to execute\n        required: true\n        mapping: path.name\n      outputParameters:\n      - name: status\n        type: string\n        mapping: $.status\n      - name: execution_id\n        type: string\n        mapping: $.execution_id\n  - type: skill\n    port: 10082\n    namespace:\
  \ snowflake-cortex-skill\n    description: Agent Skills surface for Snowflake Cortex AI — same tool set exposed as agent-compatible skills.\n    tools:\n    - name: ask-analyst\n      description: Ask a question about your data using natural language\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: false\n      call: snowflake-cortex-analyst.send-message\n      inputParameters:\n      - name: messages\n        type: array\n        description: Conversation messages to send to Cortex Analyst\n        required: true\n        mapping: body.messages\n      - name: semantic_model_file\n        type: string\n        description: Reference to the semantic model file\n        required: false\n        mapping: body.semantic_model_file\n      outputParameters:\n      - name: request_id\n        type: string\n        mapping: $.request_id\n      - name: message\n        type: object\n        mapping: $.message\n      - name: warnings\n        type: array\n  \
  \      mapping: $.warnings\n    - name: send-analyst-feedback\n      description: Send feedback on an Analyst response\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-analyst.send-feedback\n      inputParameters:\n      - name: request_id\n        type: string\n        description: Analyst request identifier\n        required: true\n        mapping: body.request_id\n      - name: positive\n        type: boolean\n        description: Whether the feedback is positive\n        required: true\n        mapping: body.positive\n      - name: feedback_message\n        type: string\n        description: Optional free-form feedback text\n        required: false\n        mapping: body.feedback_message\n      outputParameters:\n      - name: request_id\n        type: string\n        mapping: $.request_id\n      - name: status\n        type: string\n        mapping: $.status\n    - name: generate-query-suggestions\n      description:\
  \ Generate verified query suggestions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: false\n      call: snowflake-cortex-analyst.generate-verified-query-suggestions\n      inputParameters:\n      - name: semantic_model_file\n        type: string\n        description: Semantic model file to generate suggestions for\n        required: true\n        mapping: body.semantic_model_file\n      - name: limit\n        type: integer\n        description: Maximum number of suggestions to return\n        required: false\n        mapping: body.limit\n      outputParameters:\n      - name: suggestions\n        type: array\n        mapping: $.suggestions\n      - name: request_id\n        type: string\n        mapping: $.request_id\n    - name: list-llm-models\n      description: List available Cortex LLM models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-inference.get-models\n      inputParameters:\
  \ []\n      outputParameters:\n      - name: models\n        type: array\n        mapping: $.data\n    - name: llm-complete\n      description: Run LLM inference completion\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: false\n      call: snowflake-cortex-inference.complete\n      inputParameters:\n      - name: model\n        type: string\n        description: Identifier of the Cortex LLM model\n        required: true\n        mapping: body.model\n      - name: prompt\n        type: string\n        description: Prompt text\n        required: true\n        mapping: body.prompt\n      outputParameters:\n      - name: id\n        type: string\n        mapping: $.id\n      - name: model\n        type: string\n        mapping: $.model\n      - name: choices\n        type: array\n        mapping: $.choices\n      - name: usage\n        type: object\n        mapping: $.usage\n    - name: semantic-search\n      description: Query a Cortex Search service\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-cortex-search.query-search-service\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the search service\n        required: true\n        mapping: path.database\n      - name: schema\n        type: string\n        description: Schema containing the search service\n        required: true\n        mapping: path.schema\n      - name: query\n        type: string\n        description: Natural language query string\n        required: true\n        mapping: body.query\n      - name: columns\n        type: array\n        description: Columns to return from the search index\n        required: false\n        mapping: body.columns\n      - name: limit\n        type: intege\n\n# --- truncated at 32 KB (35 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/cortex-ai.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/cortex-ai.yaml
tags:
- Snowflake
- Cortex
- AI
- Machine Learning
tools:
- description: Ask a question about your data using natural language
  hints:
    destructive: false
    idempotent: false
    readOnly: true
  name: ask-analyst
- description: Send feedback on an Analyst response
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: send-analyst-feedback
- description: Generate verified query suggestions
  hints:
    destructive: false
    idempotent: false
    readOnly: true
  name: generate-query-suggestions
- description: List available Cortex LLM models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-llm-models
- description: Run LLM inference completion
  hints:
    destructive: false
    idempotent: false
    readOnly: true
  name: llm-complete
- description: Query a Cortex Search service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: semantic-search
- description: List Cortex Search services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-search-services
- description: List notebooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-notebooks
- description: Create a notebook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-notebook
- description: Execute a notebook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-notebook
- description: Ask a question about your data using natural language
  hints:
    destructive: false
    idempotent: false
    readOnly: true
  name: ask-analyst
- description: Send feedback on an Analyst response
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: send-analyst-feedback
- description: Generate verified query suggestions
  hints:
    destructive: false
    idempotent: false
    readOnly: true
  name: generate-query-suggestions
- description: List available Cortex LLM models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-llm-models
- description: Run LLM inference completion
  hints:
    destructive: false
    idempotent: false
    readOnly: true
  name: llm-complete
- description: Query a Cortex Search service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: semantic-search
- description: List Cortex Search services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-search-services
- description: List notebooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-notebooks
- description: Create a notebook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-notebook
- description: Execute a notebook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-notebook
---
