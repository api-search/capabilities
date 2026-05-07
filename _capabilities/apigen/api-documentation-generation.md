---
categories: []
consumed_apis: []
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
- writer managing and publishing api documentation sites.
- apigen
- developer generating api documentation for php projects using apigen.
- deploy an api documentation site for a project.
- api code generation
- deploy
- open source
- create project.
- documentation
- create documentation project
- generation
- Technical Writer
- create project
- list projects
- create a new php api documentation project in apigen.
- php
- deploy documentation.
- deploy documentation site
- PHP Developer
- code
- list all apigen documentation projects.
- list projects.
slug: api-documentation-generation
source_filename: api-documentation-generation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: APIGen Documentation Generation\n  description: Workflow for generating, publishing, and managing API documentation using APIGen - creating projects from PHP\n    source code, configuring endpoints, and deploying documentation sites.\n  tags:\n  - APIGen\n  - Documentation\n  - PHP\n  - API Code Generation\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APIGEN_API_TOKEN: APIGEN_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: apigen\n    baseUri: https://api.apigen.com/v1\n    description: APIGen REST API for documentation generation.\n    authentication:\n      type: bearer\n      token: '{{APIGEN_API_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      description: Manage APIGen projects.\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-project\n        method: GET\n        description: Get project details.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis\n      path: /projects/{projectId}/apis\n      description: Manage APIs within a project.\n      operations:\n      - name: list-apis\n        method: GET\n        description: List APIs in a project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Project ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /projects/{projectId}/deployments\n      description: Deploy API documentation.\n      operations:\n      - name: deploy\n        method: POST\n        description: Deploy documentation for a project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apigen-docs-api\n    description: Unified REST API for APIGen documentation management.\n    resources:\n    - path: /v1/projects\n      name: projects\n      operations:\n      - method: GET\n        name: list-projects\n        description: List\
  \ projects.\n        call: apigen.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create project.\n        call: apigen.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/deploy\n      name: deploy\n      operations:\n      - method: POST\n        name: deploy\n        description: Deploy documentation.\n        call: apigen.deploy\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apigen-docs-mcp\n    transport: http\n    description: MCP server for AI-assisted API documentation generation.\n    tools:\n    - name: list-projects\n      description: List all APIGen documentation projects.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apigen.list-projects\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-documentation-project\n      description: Create a new PHP API documentation project in APIGen.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apigen.create-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-documentation-site\n      description: Deploy an API documentation site for a project.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apigen.deploy\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
