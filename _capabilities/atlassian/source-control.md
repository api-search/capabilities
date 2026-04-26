---
consumed_apis:
- atlassian-admin
description: Source control workflow combining Bitbucket Repositories, Pull Requests, Workspaces, Snippets, and Teams APIs for developers to manage code, reviews, and collaboration.
layout: capability
name: Atlassian Source Control
operations:
- description: List repositories in a workspace
  method: GET
  name: list-repositories
  path: /v1/repositories
- description: List pull requests
  method: GET
  name: list-pull-requests
  path: /v1/pull-requests
- description: List workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
personas: []
provider_name: Atlassian
provider_slug: atlassian
search_terms:
- list teams
- list bitbucket repositories in a workspace
- repository management
- source control
- atlassian
- collaboration
- list repositories
- bitbucket
- list code snippets
- list snippets
- platform
- list workspaces
- productivity
- workspace management
- code
- pull request management
- list bitbucket workspaces
- list pull requests
- list pull requests for a repository
- list repositories in a workspace
- software development
- list teams in a workspace
slug: source-control
tags:
- Atlassian
- Bitbucket
- Source Control
tools:
- description: List Bitbucket repositories in a workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-repositories
- description: List pull requests for a repository
  hints:
    readOnly: true
  name: list-pull-requests
- description: List Bitbucket workspaces
  hints:
    readOnly: true
  name: list-workspaces
- description: List code snippets
  hints:
    readOnly: true
  name: list-snippets
- description: List teams in a workspace
  hints:
    readOnly: true
  name: list-teams
---
