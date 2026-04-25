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
- documentation
- list projects.
- create project
- api code generation
- deploy documentation site
- PHP Developer
- create project.
- php
- writer managing and publishing api documentation sites.
- deploy
- developer generating api documentation for php projects using apigen.
- Technical Writer
- deploy an api documentation site for a project.
- deploy documentation.
- generation
- code
- create documentation project
- list projects
- list all apigen documentation projects.
- open source
- apigen
- create a new php api documentation project in apigen.
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
