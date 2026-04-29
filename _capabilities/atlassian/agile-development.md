---
categories: []
consumed_apis:
- atlassian-admin
description: Agile software development workflow combining Jira Issue, Project, Filter, Search, Field, Workflow, and Dashboard APIs for software developers and scrum masters to plan, track, and deliver software.
layout: capability
name: Atlassian Agile Development
operations:
- description: Search issues using JQL
  method: GET
  name: search-issues
  path: /v1/issues
- description: List all projects
  method: GET
  name: list-projects
  path: /v1/projects
personas: []
provider_name: Atlassian
provider_slug: atlassian
search_terms:
- list all jira projects
- search issues using jql
- agile
- list workflows
- atlassian
- search jira issues using jql queries
- search issues
- collaboration
- list jira dashboards
- jira project management
- list jira workflows
- productivity
- list filters
- list all projects
- list saved jira filters
- platform
- list workflow statuses
- jira issue management
- code
- jira
- software development
- list statuses
- list dashboards
- list projects
slug: agile-development
source_filename: agile-development.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Atlassian Agile Development\"\n  description: \"Agile software development workflow combining Jira Issue, Project, Filter, Search, Field, Workflow, and Dashboard APIs for software developers and scrum masters to plan, track, and deliver software.\"\n  tags:\n    - Agile\n    - Atlassian\n    - Jira\n    - Software Development\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ATLASSIAN_API_TOKEN: ATLASSIAN_API_TOKEN\n      ATLASSIAN_EMAIL: ATLASSIAN_EMAIL\n      ATLASSIAN_SITE: ATLASSIAN_SITE\n\ncapability:\n  consumes:\n    - import: atlassian-admin\n      location: ./shared/admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: atlassian-agile-api\n      description: \"Unified REST API for Atlassian agile development operations.\"\n      resources:\n        - path: /v1/issues\n          name: issues\n          description: \"Jira issue management\"\n\
  \          operations:\n            - method: GET\n              name: search-issues\n              description: \"Search issues using JQL\"\n              call: \"atlassian-admin.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects\n          name: projects\n          description: \"Jira project management\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all projects\"\n              call: \"atlassian-admin.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: atlassian-agile-mcp\n      transport: http\n      description: \"MCP server for AI-assisted agile development with Jira.\"\n      tools:\n        - name: search-issues\n          description: \"Search Jira issues using JQL queries\"\n      \
  \    hints:\n            readOnly: true\n            openWorld: true\n          call: \"atlassian-admin.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: \"List all Jira projects\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dashboards\n          description: \"List Jira dashboards\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-filters\n          description: \"List saved Jira filters\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-organizations\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-workflows\n          description: \"List Jira workflows\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-statuses\n          description: \"List workflow statuses\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/atlassian/refs/heads/main/capabilities/agile-development.yaml
tags:
- Agile
- Atlassian
- Jira
- Software Development
tools:
- description: Search Jira issues using JQL queries
  hints:
    openWorld: true
    readOnly: true
  name: search-issues
- description: List all Jira projects
  hints:
    readOnly: true
  name: list-projects
- description: List Jira dashboards
  hints:
    readOnly: true
  name: list-dashboards
- description: List saved Jira filters
  hints:
    readOnly: true
  name: list-filters
- description: List Jira workflows
  hints:
    readOnly: true
  name: list-workflows
- description: List workflow statuses
  hints:
    readOnly: true
  name: list-statuses
---
