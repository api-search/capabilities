---
categories: []
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
- workspace management
- list teams
- list repositories
- atlassian
- platform
- bitbucket
- list teams in a workspace
- list workspaces
- collaboration
- list repositories in a workspace
- list pull requests for a repository
- code
- list bitbucket repositories in a workspace
- list pull requests
- repository management
- productivity
- list bitbucket workspaces
- list code snippets
- source control
- pull request management
- software development
- list snippets
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
