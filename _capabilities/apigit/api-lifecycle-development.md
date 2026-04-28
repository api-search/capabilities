---
categories: []
consumed_apis:
- apigit
description: Workflow for Git-native API lifecycle development using APIGit - managing API repositories, designing APIs with visual tools, running mock servers for development, and executing automated tests.
layout: capability
name: APIGit API Lifecycle Development
operations:
- description: List repositories.
  method: GET
  name: list-repositories
  path: /v1/repos
- description: Create repository.
  method: POST
  name: create-repository
  path: /v1/repos
personas: []
provider_name: APIGit
provider_slug: apigit
search_terms:
- create repository
- start a dynamic mock server from an api definition for development testing.
- documentation
- mocking
- list repositories
- api design
- create repository.
- platform
- create api repository
- API Developer
- list api repositories
- apigit
- Backend Engineer
- list all api git repositories in apigit.
- start mock server
- git
- api lifecycle
- create a new git-native api repository in apigit.
- governance
- developer designing and building apis using git-native workflows.
- list repositories.
- engineer using mock servers for frontend/backend parallel development.
- testing
slug: api-lifecycle-development
tags:
- APIGit
- API Lifecycle
- Git
- Mocking
tools:
- description: List all API Git repositories in APIGit.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-repositories
- description: Create a new Git-native API repository in APIGit.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-repository
- description: Start a dynamic mock server from an API definition for development testing.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: start-mock-server
---
