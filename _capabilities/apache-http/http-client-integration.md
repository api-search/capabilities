---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Http Client Integration
operations: []
personas: []
provider_name: Apache HttpComponents
provider_slug: apache-http
search_terms:
- open source
- java
- sdk
- http client
- apache
slug: http-client-integration
source_yaml: "name: Apache HttpComponents HTTP Client Integration\ndescription: Workflow capability for executing HTTP requests and managing connection pools using Apache HttpComponents\npersona: Application Developer\nworkflow:\n  - step: configure-connection\n    name: Configure Connection Pool\n    description: Set timeouts and connection pool limits for the HTTP client\n    capability: http-client\n    operation: configureConnection\n    server:\n      rest: https://api.example.com\n      mcp: http://localhost:9090\n\n  - step: execute-request\n    name: Execute HTTP Request\n    description: Make an HTTP request to a target API\n    capability: http-client\n    operation: executeRequest\n    server:\n      rest: https://api.example.com\n      mcp: http://localhost:9090\n\ntools:\n  - name: executeRequest\n    description: Execute an HTTP request using Apache HttpComponents\n    server:\n      rest:\n        baseUrl: https://api.example.com\n        path: /execute\n        method: POST\n\
  \      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/executeRequest\n        method: POST\n\n  - name: configureConnection\n    description: Configure connection pool settings for the HTTP client\n    server:\n      rest:\n        baseUrl: https://api.example.com\n        path: /configure/connection\n        method: PUT\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/configureConnection\n        method: POST\n\n  - name: configureProxy\n    description: Configure HTTP proxy for outbound requests\n    server:\n      rest:\n        baseUrl: https://api.example.com\n        path: /configure/proxy\n        method: PUT\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/configureProxy\n        method: POST\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-http/refs/heads/main/capabilities/http-client-integration.yaml
tags: []
tools: []
---
