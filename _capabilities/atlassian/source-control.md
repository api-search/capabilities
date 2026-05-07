---
categories: []
consumed_apis: []
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
- list workspaces
- workspace management
- atlassian
- list pull requests for a repository
- list bitbucket workspaces
- platform
- bitbucket
- list pull requests
- productivity
- list teams
- collaboration
- list repositories in a workspace
- software development
- list code snippets
- repository management
- list bitbucket repositories in a workspace
- pull request management
- source control
- list teams in a workspace
- list snippets
- code
- list repositories
slug: source-control
source_filename: source-control.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Atlassian Source Control\n  description: Source control workflow combining Bitbucket Repositories, Pull Requests, Workspaces, Snippets, and Teams APIs\n    for developers to manage code, reviews, and collaboration.\n  tags:\n  - Atlassian\n  - Bitbucket\n  - Source Control\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ATLASSIAN_API_TOKEN: ATLASSIAN_API_TOKEN\n    ATLASSIAN_EMAIL: ATLASSIAN_EMAIL\ncapability:\n  consumes:\n  - type: http\n    namespace: atlassian-admin\n    baseUri: https://api.atlassian.com\n    description: Atlassian Admin API for organization management.\n    authentication:\n      type: bearer\n      token: '{{ATLASSIAN_API_TOKEN}}'\n    resources:\n    - name: organizations\n      path: /v1/orgs\n      description: Organization management\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List accessible organizations\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-organization\n        method: GET\n        description: Get organization details\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /v1/orgs/{orgId}/users\n      description: User management within organization\n      operations:\n      - name: list-users\n        method: GET\n        description: List users in organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: domains\n      path: /v1/orgs/{orgId}/domains\n      description: Domain management\n      operations:\n      - name: list-domains\n        method: GET\n        description: List domains in organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /v1/orgs/{orgId}/groups\n      description: Group management\n      operations:\n      - name: list-groups\n        method: GET\n        description: List groups in organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: policies\n      path: /v1/orgs/{orgId}/policies\n      description: Policy management\n      operations:\n      - name: list-policies\n        method: GET\n        description: List organization policies\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /v1/orgs/{orgId}/events\n      description: Audit events\n      operations:\n      - name: list-events\n        method: GET\n        description: List organization audit events\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: atlassian-source-control-api\n    description: Unified REST API for Bitbucket source control operations.\n    resources:\n    - path: /v1/repositories\n      name: repositories\n      description: Repository management\n      operations:\n      - method: GET\n        name: list-repositories\n        description: List repositories in a workspace\n        call: atlassian-admin.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pull-requests\n      name: pull-requests\n      description: Pull request management\n      operations:\n      - method: GET\n        name: list-pull-requests\n        description: List pull requests\n        call: atlassian-admin.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: Workspace management\n      operations:\n\
  \      - method: GET\n        name: list-workspaces\n        description: List workspaces\n        call: atlassian-admin.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: atlassian-source-control-mcp\n    transport: http\n    description: MCP server for AI-assisted Bitbucket source control.\n    tools:\n    - name: list-repositories\n      description: List Bitbucket repositories in a workspace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pull-requests\n      description: List pull requests for a repository\n      hints:\n        readOnly: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List Bitbucket workspaces\n      hints:\n\
  \        readOnly: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-snippets\n      description: List code snippets\n      hints:\n        readOnly: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List teams in a workspace\n      hints:\n        readOnly: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/atlassian/refs/heads/main/capabilities/source-control.yaml
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
