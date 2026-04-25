---
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
- list projects.
- generation
- list all apigen documentation projects.
- deploy
- create a new php api documentation project in apigen.
- create documentation project
- deploy documentation.
- code
- developer generating api documentation for php projects using apigen.
- list projects
- create project.
- PHP Developer
- documentation
- deploy an api documentation site for a project.
- Technical Writer
- deploy documentation site
- writer managing and publishing api documentation sites.
- apigen
- api code generation
- php
- open source
- create project
slug: api-documentation-generation
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
