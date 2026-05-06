---
categories: []
consumed_apis: []
description: AgentQL connects LLMs and AI agents to the entire web through natural language queries, enabling structured data extraction from web pages, documents, and browser sessions. Generated from documentation.
layout: capability
name: AgentQL API
operations:
- description: AgentQL Query Web Page Data
  method: POST
  name: querywebpagedata
  path: /query-data
- description: AgentQL Create Remote Browser Session
  method: POST
  name: createremotebrowsersession
  path: /tetra/sessions
- description: AgentQL Query Document
  method: POST
  name: querydocument
  path: /query-document
personas: []
provider_name: AgentQL
provider_slug: agentql
search_terms:
- agents
- createremotebrowsersession
- rest api
- AI Developer
- extract structured data from pdf invoices, reports, and images
- developers building ai agents that need web access and data extraction capabilities
- data extraction
- extract structured data from any public web page using agentql queries
- Data Engineer
- querydocument
- agentql query document
- agentql query web page data
- artificial intelligence
- web scraping
- engineers building data pipelines that collect structured data from web sources
- programmatic browser control for authenticated and complex web interactions
- agentql
- api
- browser automation
- querywebpagedata
- agentql create remote browser session
- extracting structured data from web pages using natural language queries
- use remote browser sessions to automate authenticated web interactions
- extracting structured data from pdfs and image documents
slug: agentql-capability
source_filename: agentql-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AgentQL API\n  description: AgentQL connects LLMs and AI agents to the entire web through natural language queries, enabling structured\n    data extraction from web pages, documents, and browser sessions. Generated from documentation.\n  tags:\n  - Agentql\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: agentql\n    baseUri: https://api.agentql.com/v1\n    description: AgentQL API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{AGENTQL_TOKEN}}'\n    resources:\n    - name: query-data\n      path: /query-data\n      operations:\n      - name: querywebpagedata\n        method: POST\n        description: AgentQL Query Web Page Data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tetra-sessions\n      path: /tetra/sessions\n\
  \      operations:\n      - name: createremotebrowsersession\n        method: POST\n        description: AgentQL Create Remote Browser Session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-document\n      path: /query-document\n      operations:\n      - name: querydocument\n        method: POST\n        description: AgentQL Query Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: agentql-rest\n    description: REST adapter for AgentQL API.\n    resources:\n    - path: /query-data\n      name: querywebpagedata\n      operations:\n      - method: POST\n        name: querywebpagedata\n        description: AgentQL Query Web Page Data\n        call: agentql.querywebpagedata\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /tetra/sessions\n      name: createremotebrowsersession\n      operations:\n      - method: POST\n        name: createremotebrowsersession\n        description: AgentQL Create Remote Browser Session\n        call: agentql.createremotebrowsersession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /query-document\n      name: querydocument\n      operations:\n      - method: POST\n        name: querydocument\n        description: AgentQL Query Document\n        call: agentql.querydocument\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: agentql-mcp\n    transport: http\n    description: MCP adapter for AgentQL API for AI agent use.\n    tools:\n    - name: querywebpagedata\n      description: AgentQL Query Web Page Data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: agentql.querywebpagedata\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createremotebrowsersession\n      description: AgentQL Create Remote Browser Session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: agentql.createremotebrowsersession\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querydocument\n      description: AgentQL Query Document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: agentql.querydocument\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AGENTQL_TOKEN: AGENTQL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agentql/refs/heads/main/capabilities/agentql-capability.yaml
tags:
- Agentql
- API
tools:
- description: AgentQL Query Web Page Data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: querywebpagedata
- description: AgentQL Create Remote Browser Session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createremotebrowsersession
- description: AgentQL Query Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: querydocument
---
