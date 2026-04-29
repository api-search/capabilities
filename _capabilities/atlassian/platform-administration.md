---
categories:
- identity-access
consumed_apis:
- atlassian-admin
description: Platform administration workflow combining Admin Organizations, User Management, User Provisioning, and Jira Configuration APIs for IT administrators to manage users, groups, organizations, and platform settings.
layout: capability
name: Atlassian Platform Administration
operations:
- description: List Atlassian organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List organization users
  method: GET
  name: list-users
  path: /v1/users
- description: List organization groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: List organization domains
  method: GET
  name: list-domains
  path: /v1/domains
- description: List organization policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: List audit events
  method: GET
  name: list-events
  path: /v1/events
personas: []
provider_name: Atlassian
provider_slug: atlassian
search_terms:
- collaboration
- identity
- list events
- list groups in an organization
- list organizations
- list organization policies
- list audit events
- list users in an organization
- list groups
- software development
- list organization domains
- group management
- platform
- code
- list organization groups
- domain management
- list policies
- list users
- atlassian
- get organization details
- user management
- list organization audit events
- list organization users
- get organization
- organization management
- list domains in an organization
- list atlassian organizations
- productivity
- audit events
- list domains
- policy management
- administration
- list all atlassian organizations
slug: platform-administration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Atlassian Platform Administration\"\n  description: \"Platform administration workflow combining Admin Organizations, User Management, User Provisioning, and Jira Configuration APIs for IT administrators to manage users, groups, organizations, and platform settings.\"\n  tags:\n    - Administration\n    - Atlassian\n    - Identity\n    - Platform\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ATLASSIAN_API_TOKEN: ATLASSIAN_API_TOKEN\n      ATLASSIAN_EMAIL: ATLASSIAN_EMAIL\n      ATLASSIAN_SITE: ATLASSIAN_SITE\n\ncapability:\n  consumes:\n    - import: atlassian-admin\n      location: ./shared/admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: atlassian-platform-admin-api\n      description: \"Unified REST API for Atlassian platform administration.\"\n      resources:\n        - path: /v1/organizations\n          name: organizations\n          description:\
  \ \"Organization management\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List Atlassian organizations\"\n              call: \"atlassian-admin.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List organization users\"\n              call: \"atlassian-admin.list-users\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Group management\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List\
  \ organization groups\"\n              call: \"atlassian-admin.list-groups\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/domains\n          name: domains\n          description: \"Domain management\"\n          operations:\n            - method: GET\n              name: list-domains\n              description: \"List organization domains\"\n              call: \"atlassian-admin.list-domains\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/policies\n          name: policies\n          description: \"Policy management\"\n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List organization policies\"\n              call: \"atlassian-admin.list-policies\"\n    \
  \          with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Audit events\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List audit events\"\n              call: \"atlassian-admin.list-events\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: atlassian-platform-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Atlassian platform administration.\"\n      tools:\n        - name: list-organizations\n          description: \"List all Atlassian organizations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"atlassian-admin.list-organizations\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-organization\n          description: \"Get organization details\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.get-organization\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List users in an organization\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-users\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List groups in an organization\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-groups\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-domains\n          description: \"List domains in an organization\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-domains\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-policies\n          description: \"List organization policies\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-policies\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-events\n          description: \"List organization audit events\"\n          hints:\n            readOnly: true\n          call: \"atlassian-admin.list-events\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/atlassian/refs/heads/main/capabilities/platform-administration.yaml
tags:
- Administration
- Atlassian
- Identity
- Platform
tools:
- description: List all Atlassian organizations
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: Get organization details
  hints:
    readOnly: true
  name: get-organization
- description: List users in an organization
  hints:
    readOnly: true
  name: list-users
- description: List groups in an organization
  hints:
    readOnly: true
  name: list-groups
- description: List domains in an organization
  hints:
    readOnly: true
  name: list-domains
- description: List organization policies
  hints:
    readOnly: true
  name: list-policies
- description: List organization audit events
  hints:
    readOnly: true
  name: list-events
---
