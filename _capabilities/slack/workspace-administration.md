---
categories: []
consumed_apis:
- slack-admin
- slack-team
- slack-users
- slack-usergroups
- slack-migration
- slack-auth
- slack-oauth
- slack-openid
- slack-dnd
description: Unified workflow for workspace administration including admin controls, team settings, user management, user groups, authentication, and enterprise migration. Used by workspace administrators and IT teams.
layout: capability
name: Slack Workspace Administration
operations:
- description: List admin resources.
  method: GET
  name: list-admin
  path: /v1/admin
- description: List users.
  method: GET
  name: list-users
  path: /v1/users
- description: List user groups.
  method: GET
  name: list-groups
  path: /v1/user-groups
- description: Get team info.
  method: GET
  name: get-team
  path: /v1/team
personas: []
provider_name: Slack
provider_slug: slack
search_terms:
- collaboration
- get team
- list user groups.
- migrate ids
- messaging
- list groups
- slack
- list user groups
- chat
- get team info
- user group management.
- migrate enterprise ids.
- team communication
- admin controls.
- get do not disturb status.
- list users
- list admin resources.
- get team info.
- get workspace information.
- user management
- auth test
- bots
- list users.
- access admin controls.
- user management.
- enterprise
- list admin
- productivity
- admin controls
- test authentication.
- list workspace users.
- t1
- administration
- team information.
- get dnd status
slug: workspace-administration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Slack Workspace Administration\"\n  description: \"Unified workflow for workspace administration including admin controls, team settings, user management, user groups, authentication, and enterprise migration. Used by workspace administrators and IT teams.\"\n  tags:\n    - Slack\n    - Administration\n    - User Management\n    - Enterprise\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SLACK_BOT_TOKEN: SLACK_BOT_TOKEN\n\ncapability:\n  consumes:\n    - import: slack-admin\n      location: ./shared/admin.yaml\n    - import: slack-team\n      location: ./shared/team.yaml\n    - import: slack-users\n      location: ./shared/users.yaml\n    - import: slack-usergroups\n      location: ./shared/usergroups.yaml\n    - import: slack-migration\n      location: ./shared/migration.yaml\n    - import: slack-auth\n      location: ./shared/auth.yaml\n    - import: slack-oauth\n      location:\
  \ ./shared/oauth.yaml\n    - import: slack-openid\n      location: ./shared/openid-connect.yaml\n    - import: slack-dnd\n      location: ./shared/dnd.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: workspace-admin-api\n      description: \"Unified REST API for workspace administration.\"\n      resources:\n        - path: /v1/admin\n          name: admin\n          description: \"Admin controls.\"\n          operations:\n            - method: GET\n              name: list-admin\n              description: \"List admin resources.\"\n              call: \"slack-admin.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User management.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users.\"\n              call: \"slack-users.list\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/user-groups\n          name: user-groups\n          description: \"User group management.\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List user groups.\"\n              call: \"slack-usergroups.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/team\n          name: team\n          description: \"Team information.\"\n          operations:\n            - method: GET\n              name: get-team\n              description: \"Get team info.\"\n              call: \"slack-team.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: workspace-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted workspace administration.\"\n \
  \     tools:\n        - name: admin-controls\n          description: \"Access admin controls.\"\n          hints:\n            readOnly: true\n          call: \"slack-admin.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-team-info\n          description: \"Get workspace information.\"\n          hints:\n            readOnly: true\n          call: \"slack-team.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List workspace users.\"\n          hints:\n            readOnly: true\n          call: \"slack-users.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-user-groups\n          description: \"List user groups.\"\n          hints:\n            readOnly: true\n          call: \"slack-usergroups.list\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: migrate-ids\n          description: \"Migrate enterprise IDs.\"\n          hints:\n            readOnly: true\n          call: \"slack-migration.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: auth-test\n          description: \"Test authentication.\"\n          hints:\n            readOnly: true\n          call: \"slack-auth.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dnd-status\n          description: \"Get Do Not Disturb status.\"\n          hints:\n            readOnly: true\n          call: \"slack-dnd.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/slack/refs/heads/main/capabilities/workspace-administration.yaml
tags:
- Slack
- Administration
- User Management
- Enterprise
tools:
- description: Access admin controls.
  hints:
    readOnly: true
  name: admin-controls
- description: Get workspace information.
  hints:
    readOnly: true
  name: get-team-info
- description: List workspace users.
  hints:
    readOnly: true
  name: list-users
- description: List user groups.
  hints:
    readOnly: true
  name: list-user-groups
- description: Migrate enterprise IDs.
  hints:
    readOnly: true
  name: migrate-ids
- description: Test authentication.
  hints:
    readOnly: true
  name: auth-test
- description: Get Do Not Disturb status.
  hints:
    readOnly: true
  name: get-dnd-status
---
