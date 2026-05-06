---
categories: []
consumed_apis: []
description: The grounded.tools Docs MCP Server is an open-source, privacy-first documentation indexing tool that keeps AI assistants informed with up-to-date, version-specific documentation. It indexes documentation from websites, GitHub repositories, npm, PyPI, and local files, then provides AI assistants with version-aware search capabilities via the Model Context Protocol (MCP). The server exposes MCP tools over Server-Sent Events (SSE) and streamable HTTP, along with a web management UI for documentation management. MCP tools include scrape_docs, search_docs, fetch_url, list_libraries, find_version, l
layout: capability
name: grounded.tools Docs MCP Server API
operations:
- description: Grounded.tools Connect to MCP server via Server-Sent Events
  method: GET
  name: connectmcpsse
  path: /sse
- description: Grounded.tools Send MCP message via streamable HTTP
  method: POST
  name: sendmcpmessage
  path: /mcp
- description: Grounded.tools Web management UI
  method: GET
  name: getwebui
  path: /
personas: []
provider_name: Grounded.tools
provider_slug: grounded-tools
search_terms:
- grounded.tools send mcp message via streamable http
- documentation
- developers
- developer tools
- connectmcpsse
- sendmcpmessage
- api
- grounded.tools web management ui
- grounded
- experience
- tools
- getwebui
- grounded.tools connect to mcp server via server-sent events
slug: grounded-tools-capability
source_filename: grounded-tools-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: grounded.tools Docs MCP Server API\n  description: The grounded.tools Docs MCP Server is an open-source, privacy-first documentation indexing tool that keeps\n    AI assistants informed with up-to-date, version-specific documentation. It indexes documentation from websites, GitHub\n    repositories, npm, PyPI, and local files, then provides AI assistants with version-aware search capabilities via the Model\n    Context Protocol (MCP). The server exposes MCP tools over Server-Sent Events (SSE) and streamable HTTP, along with a web\n    management UI for documentation management. MCP tools include scrape_docs, search_docs, fetch_url, list_libraries, find_version,\n    l\n  tags:\n  - Grounded\n  - Tools\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: grounded-tools\n    baseUri: http://localhost:6280\n    description: grounded.tools Docs MCP Server API HTTP API.\n    resources:\n\
  \    - name: sse\n      path: /sse\n      operations:\n      - name: connectmcpsse\n        method: GET\n        description: Grounded.tools Connect to MCP server via Server-Sent Events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mcp\n      path: /mcp\n      operations:\n      - name: sendmcpmessage\n        method: POST\n        description: Grounded.tools Send MCP message via streamable HTTP\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resource\n      path: /\n      operations:\n      - name: getwebui\n        method: GET\n        description: Grounded.tools Web management UI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: grounded-tools-rest\n    description:\
  \ REST adapter for grounded.tools Docs MCP Server API.\n    resources:\n    - path: /sse\n      name: connectmcpsse\n      operations:\n      - method: GET\n        name: connectmcpsse\n        description: Grounded.tools Connect to MCP server via Server-Sent Events\n        call: grounded-tools.connectmcpsse\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mcp\n      name: sendmcpmessage\n      operations:\n      - method: POST\n        name: sendmcpmessage\n        description: Grounded.tools Send MCP message via streamable HTTP\n        call: grounded-tools.sendmcpmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /\n      name: getwebui\n      operations:\n      - method: GET\n        name: getwebui\n        description: Grounded.tools Web management UI\n        call: grounded-tools.getwebui\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n   \
  \ namespace: grounded-tools-mcp\n    transport: http\n    description: MCP adapter for grounded.tools Docs MCP Server API for AI agent use.\n    tools:\n    - name: connectmcpsse\n      description: Grounded.tools Connect to MCP server via Server-Sent Events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grounded-tools.connectmcpsse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendmcpmessage\n      description: Grounded.tools Send MCP message via streamable HTTP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grounded-tools.sendmcpmessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwebui\n      description: Grounded.tools Web management UI\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grounded-tools.getwebui\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/grounded-tools/refs/heads/main/capabilities/grounded-tools-capability.yaml
tags:
- Grounded
- Tools
- API
tools:
- description: Grounded.tools Connect to MCP server via Server-Sent Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: connectmcpsse
- description: Grounded.tools Send MCP message via streamable HTTP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendmcpmessage
- description: Grounded.tools Web management UI
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebui
---
