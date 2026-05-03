---
api_specs:
- filename: traceable-platform-openapi.yml
  format: yaml
  label: traceable-platform
  slug: traceable-platform
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/traceable/refs/heads/main/openapi/traceable-platform-openapi.yml
categories: []
consumed_apis:
- traceable-platform
description: Unified API security operations workflow combining API discovery analytics, vulnerability management, threat activity monitoring, and security testing. Used by security engineers and SOC analysts to monitor API risks, investigate threats, and manage vulnerability remediation.
layout: capability
name: Traceable API Security Operations
operations:
- description: Execute GraphQL query for security analytics
  method: POST
  name: execute-graphql-query
  path: /v1/graphql
- description: Download discovered API specification
  method: GET
  name: download-api-spec
  path: /v1/specifications
- description: Execute an MCP security analysis tool
  method: POST
  name: execute-mcp-tool
  path: /v1/mcp
personas: []
provider_name: Traceable
provider_slug: traceable
search_terms:
- api testing
- download openapi specification discovered by traceable for a service or domain
- security
- execute mcp tool
- query traceable for discovered api endpoints with risk scores and authentication status
- api protection
- execute graphql query for security analytics
- api discovery
- download api spec
- graphql
- execute an mcp security analysis tool
- query vulnerabilities
- execute traceable mcp tools for ai-assisted security analysis
- execute graphql queries for api discovery, vulnerabilities, and threat data
- observability
- query discovered apis
- execute graphql query
- vulnerability management
- query threat activity
- threat detection
- security operations
- execute a traceable mcp tool for ai-assisted security analysis
- api security
- download api specifications discovered by traceable
- download discovered api specification
- query traceable for api threat actor activity, attack patterns, and incidents
- query traceable for api vulnerability findings with owasp classification and severity
slug: api-security-operations
source_filename: api-security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Traceable API Security Operations\"\n  description: \"Unified API security operations workflow combining API discovery analytics, vulnerability management, threat activity monitoring, and security testing. Used by security engineers and SOC analysts to monitor API risks, investigate threats, and manage vulnerability remediation.\"\n  tags:\n    - API Discovery\n    - API Security\n    - GraphQL\n    - Observability\n    - Security Operations\n    - Threat Detection\n    - Vulnerability Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRACEABLE_API_TOKEN: TRACEABLE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: traceable-platform\n      location: ./shared/traceable-platform.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: api-security-operations-api\n      description: \"Unified REST API for Traceable API security operations.\"\n     \
  \ resources:\n        - path: /v1/graphql\n          name: graphql\n          description: \"Execute GraphQL queries for API discovery, vulnerabilities, and threat data\"\n          operations:\n            - method: POST\n              name: execute-graphql-query\n              description: \"Execute GraphQL query for security analytics\"\n              call: \"traceable-platform.execute-graphql-query\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/specifications\n          name: specifications\n          description: \"Download API specifications discovered by Traceable\"\n          operations:\n            - method: GET\n              name: download-api-spec\n              description: \"Download discovered API specification\"\n              call: \"traceable-platform.download-api-spec\"\n              with:\n\
  \                format: \"rest.format\"\n                service: \"rest.service\"\n                domain: \"rest.domain\"\n                environment: \"rest.environment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/mcp\n          name: mcp-tools\n          description: \"Execute Traceable MCP tools for AI-assisted security analysis\"\n          operations:\n            - method: POST\n              name: execute-mcp-tool\n              description: \"Execute an MCP security analysis tool\"\n              call: \"traceable-platform.execute-mcp-tool\"\n              with:\n                tool_name: \"rest.tool\"\n                parameters: \"rest.parameters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: api-security-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ Traceable API security operations.\"\n      tools:\n        - name: query-discovered-apis\n          description: \"Query Traceable for discovered API endpoints with risk scores and authentication status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"traceable-platform.execute-graphql-query\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-vulnerabilities\n          description: \"Query Traceable for API vulnerability findings with OWASP classification and severity\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"traceable-platform.execute-graphql-query\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: query-threat-activity\n          description: \"Query Traceable for API threat actor activity, attack patterns, and incidents\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"traceable-platform.execute-graphql-query\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: download-api-spec\n          description: \"Download OpenAPI specification discovered by Traceable for a service or domain\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"traceable-platform.download-api-spec\"\n          with:\n            format: \"tools.format\"\n            service: \"tools.service\"\n            domain: \"tools.domain\"\n            environment: \"tools.environment\"\n          outputParameters:\n            - type: object\n       \
  \       mapping: \"$.\"\n        - name: execute-mcp-tool\n          description: \"Execute a Traceable MCP tool for AI-assisted security analysis\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"traceable-platform.execute-mcp-tool\"\n          with:\n            tool_name: \"tools.tool_name\"\n            parameters: \"tools.parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/traceable/refs/heads/main/capabilities/api-security-operations.yaml
tags:
- API Discovery
- API Security
- GraphQL
- Observability
- Security Operations
- Threat Detection
- Vulnerability Management
tools:
- description: Query Traceable for discovered API endpoints with risk scores and authentication status
  hints:
    openWorld: false
    readOnly: true
  name: query-discovered-apis
- description: Query Traceable for API vulnerability findings with OWASP classification and severity
  hints:
    openWorld: false
    readOnly: true
  name: query-vulnerabilities
- description: Query Traceable for API threat actor activity, attack patterns, and incidents
  hints:
    openWorld: false
    readOnly: true
  name: query-threat-activity
- description: Download OpenAPI specification discovered by Traceable for a service or domain
  hints:
    openWorld: false
    readOnly: true
  name: download-api-spec
- description: Execute a Traceable MCP tool for AI-assisted security analysis
  hints:
    openWorld: false
    readOnly: true
  name: execute-mcp-tool
---
