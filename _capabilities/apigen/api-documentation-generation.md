---
categories: []
consumed_apis:
- apigen
description: Workflow for generating, publishing, and managing API documentation using APIGen - creating projects from PHP source code, configuring endpoints, and deploying documentation sites.
layout: capability
name: APIGen Documentation Generation
operations:
- description: List projects.
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create project.
  method: POST
  name: create-project
  path: /v1/projects
- description: Deploy documentation.
  method: POST
  name: deploy
  path: /v1/projects/{projectId}/deploy
personas: []
provider_name: APIGen
provider_slug: apigen
search_terms:
- php
- deploy documentation site
- deploy an api documentation site for a project.
- list projects
- deploy
- code
- create a new php api documentation project in apigen.
- create project.
- developer generating api documentation for php projects using apigen.
- api code generation
- documentation
- deploy documentation.
- apigen
- generation
- create documentation project
- list projects.
- list all apigen documentation projects.
- create project
- writer managing and publishing api documentation sites.
- PHP Developer
- Technical Writer
- open source
slug: api-documentation-generation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"APIGen Documentation Generation\"\n  description: \"Workflow for generating, publishing, and managing API documentation using APIGen - creating projects from PHP source code, configuring endpoints, and deploying documentation sites.\"\n  tags:\n    - APIGen\n    - Documentation\n    - PHP\n    - API Code Generation\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APIGEN_API_TOKEN: APIGEN_API_TOKEN\n\ncapability:\n  consumes:\n    - import: apigen\n      location: ./shared/apigen.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: apigen-docs-api\n      description: \"Unified REST API for APIGen documentation management.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List projects.\"\n              call: \"apigen.list-projects\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create project.\"\n              call: \"apigen.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{projectId}/deploy\n          name: deploy\n          operations:\n            - method: POST\n              name: deploy\n              description: \"Deploy documentation.\"\n              call: \"apigen.deploy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: apigen-docs-mcp\n      transport: http\n      description: \"MCP server for AI-assisted API documentation generation.\"\n      tools:\n        - name: list-projects\n          description: \"List all APIGen documentation projects.\"\n     \
  \     hints: {readOnly: true, destructive: false, idempotent: true}\n          call: \"apigen.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-documentation-project\n          description: \"Create a new PHP API documentation project in APIGen.\"\n          hints: {readOnly: false, destructive: false, idempotent: false}\n          call: \"apigen.create-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deploy-documentation-site\n          description: \"Deploy an API documentation site for a project.\"\n          hints: {readOnly: false, destructive: false, idempotent: false}\n          call: \"apigen.deploy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apigen/refs/heads/main/capabilities/api-documentation-generation.yaml
tags:
- APIGen
- Documentation
- PHP
- API Code Generation
tools:
- description: List all APIGen documentation projects.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-projects
- description: Create a new PHP API documentation project in APIGen.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-documentation-project
- description: Deploy an API documentation site for a project.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-documentation-site
---
