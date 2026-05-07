---
categories: []
consumed_apis: []
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
- user management.
- list groups
- slack
- list user groups
- migrate ids
- productivity
- get do not disturb status.
- get team info.
- bots
- collaboration
- user group management.
- list workspace users.
- list users
- administration
- list admin resources.
- t1
- team information.
- list user groups.
- admin controls.
- get dnd status
- get team info
- enterprise
- test authentication.
- chat
- get team
- access admin controls.
- user management
- list admin
- list users.
- get workspace information.
- auth test
- admin controls
- team communication
- messaging
- migrate enterprise ids.
slug: workspace-administration
source_filename: workspace-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Slack Workspace Administration\n  description: Unified workflow for workspace administration including admin controls, team settings, user management, user\n    groups, authentication, and enterprise migration. Used by workspace administrators and IT teams.\n  tags:\n  - Slack\n  - Administration\n  - User Management\n  - Enterprise\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SLACK_BOT_TOKEN: SLACK_BOT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n     \
  \   description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description:\
  \ Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n    \
  \  token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: slack-chat\n    baseUri: https://slack.com/api\n    description: Message\
  \ posting, updating, deleting, and scheduling.\n    authentication:\n      type: bearer\n      token: '{{SLACK_BOT_TOKEN}}'\n    resources:\n    - name: api\n      path: /\n      description: Chat API resources.\n      operations:\n      - name: list\n        method: POST\n        description: Access Chat resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: workspace-admin-api\n    description: Unified REST API for workspace administration.\n    resources:\n    - path: /v1/admin\n      name: admin\n      description: Admin controls.\n      operations:\n      - method: GET\n        name: list-admin\n        description: List admin resources.\n        call: slack-admin.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User management.\n      operations:\n\
  \      - method: GET\n        name: list-users\n        description: List users.\n        call: slack-users.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-groups\n      name: user-groups\n      description: User group management.\n      operations:\n      - method: GET\n        name: list-groups\n        description: List user groups.\n        call: slack-usergroups.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/team\n      name: team\n      description: Team information.\n      operations:\n      - method: GET\n        name: get-team\n        description: Get team info.\n        call: slack-team.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: workspace-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted workspace administration.\n    tools:\n    - name: admin-controls\n      description:\
  \ Access admin controls.\n      hints:\n        readOnly: true\n      call: slack-admin.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team-info\n      description: Get workspace information.\n      hints:\n        readOnly: true\n      call: slack-team.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List workspace users.\n      hints:\n        readOnly: true\n      call: slack-users.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-user-groups\n      description: List user groups.\n      hints:\n        readOnly: true\n      call: slack-usergroups.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: migrate-ids\n      description: Migrate enterprise IDs.\n      hints:\n        readOnly: true\n      call: slack-migration.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ auth-test\n      description: Test authentication.\n      hints:\n        readOnly: true\n      call: slack-auth.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dnd-status\n      description: Get Do Not Disturb status.\n      hints:\n        readOnly: true\n      call: slack-dnd.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
