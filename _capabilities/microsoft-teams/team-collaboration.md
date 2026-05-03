---
categories:
- collaboration
consumed_apis:
- teams-graph
description: Workflow capability for team collaboration including managing teams, channels, messaging, members, meetings, and calls. Used by IT administrators, team leads, and developers building Teams integrations.
layout: capability
name: Microsoft Teams Collaboration
operations:
- description: List joined teams.
  method: GET
  name: list-joined-teams
  path: /v1/teams
- description: Create a team.
  method: POST
  name: create-team
  path: /v1/teams
- description: List channels.
  method: GET
  name: list-channels
  path: /v1/channels
- description: Create a channel.
  method: POST
  name: create-channel
  path: /v1/channels
- description: List messages.
  method: GET
  name: list-channel-messages
  path: /v1/messages
- description: Send a message.
  method: POST
  name: send-channel-message
  path: /v1/messages
- description: List members.
  method: GET
  name: list-team-members
  path: /v1/members
- description: Create a meeting.
  method: POST
  name: create-online-meeting
  path: /v1/meetings
personas: []
provider_name: Microsoft Teams
provider_slug: microsoft-teams
search_terms:
- list channels
- send a message.
- manage teams collaboration workflows.
- create call
- IT Administrator
- create a meeting.
- create a channel.
- send channel message
- Team Lead
- initiate a call.
- microsoft 365
- list messages.
- team leads managing channels, members, and communication.
- create online meeting
- create channel
- it admins managing teams infrastructure and policies.
- microsoft teams
- create an online meeting.
- chat
- meeting management.
- create a new channel.
- send a message to a channel.
- list joined teams
- video conferencing
- create a new team.
- list channels.
- developers building teams integrations and bots.
- productivity
- Developer
- list all teams the user has joined.
- list joined teams.
- create team
- add a member to a team.
- list all members of a team.
- messaging.
- team management.
- member management.
- list channels in a team.
- list messages from a channel.
- communication
- channel management.
- add team member
- list channel messages
- collaboration
- create a team.
- list members.
- list team members
slug: team-collaboration
source_filename: team-collaboration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Teams Collaboration\"\n  description: \"Workflow capability for team collaboration including managing teams, channels, messaging, members, meetings, and calls. Used by IT administrators, team leads, and developers building Teams integrations.\"\n  tags:\n    - Microsoft Teams\n    - Collaboration\n    - Communication\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MICROSOFT_GRAPH_TOKEN: MICROSOFT_GRAPH_TOKEN\n\ncapability:\n  consumes:\n    - import: teams-graph\n      location: ./shared/teams-graph-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: team-collaboration-api\n      description: \"Unified REST API for Teams collaboration workflows.\"\n      resources:\n        - path: /v1/teams\n          name: teams\n          description: \"Team management.\"\n          operations:\n            - method: GET\n              name: list-joined-teams\n\
  \              description: \"List joined teams.\"\n              call: \"teams-graph.list-joined-teams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-team\n              description: \"Create a team.\"\n              call: \"teams-graph.create-team\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/channels\n          name: channels\n          description: \"Channel management.\"\n          operations:\n            - method: GET\n              name: list-channels\n              description: \"List channels.\"\n              call: \"teams-graph.list-channels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-channel\n              description: \"Create a channel.\"\n              call: \"teams-graph.create-channel\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages\n          name: messages\n          description: \"Messaging.\"\n          operations:\n            - method: GET\n              name: list-channel-messages\n              description: \"List messages.\"\n              call: \"teams-graph.list-channel-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: send-channel-message\n              description: \"Send a message.\"\n              call: \"teams-graph.send-channel-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/members\n          name: members\n          description: \"Member management.\"\n          operations:\n            - method: GET\n              name: list-team-members\n              description: \"List members.\"\
  \n              call: \"teams-graph.list-team-members\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meetings\n          name: meetings\n          description: \"Meeting management.\"\n          operations:\n            - method: POST\n              name: create-online-meeting\n              description: \"Create a meeting.\"\n              call: \"teams-graph.create-online-meeting\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: team-collaboration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Teams collaboration.\"\n      tools:\n        - name: list-joined-teams\n          description: \"List all teams the user has joined.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"teams-graph.list-joined-teams\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-team\n          description: \"Create a new team.\"\n          hints:\n            readOnly: false\n          call: \"teams-graph.create-team\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-channels\n          description: \"List channels in a team.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"teams-graph.list-channels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-channel\n          description: \"Create a new channel.\"\n          hints:\n            readOnly: false\n          call: \"teams-graph.create-channel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-channel-messages\n          description: \"List messages from a channel.\"\n          hints:\n         \
  \   readOnly: true\n            openWorld: true\n          call: \"teams-graph.list-channel-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-channel-message\n          description: \"Send a message to a channel.\"\n          hints:\n            readOnly: false\n          call: \"teams-graph.send-channel-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-team-members\n          description: \"List all members of a team.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"teams-graph.list-team-members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-team-member\n          description: \"Add a member to a team.\"\n          hints:\n            readOnly: false\n          call: \"teams-graph.add-team-member\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n        - name: create-online-meeting\n          description: \"Create an online meeting.\"\n          hints:\n            readOnly: false\n          call: \"teams-graph.create-online-meeting\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-call\n          description: \"Initiate a call.\"\n          hints:\n            readOnly: false\n          call: \"teams-graph.create-call\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-teams/refs/heads/main/capabilities/team-collaboration.yaml
tags:
- Microsoft Teams
- Collaboration
- Communication
tools:
- description: List all teams the user has joined.
  hints:
    openWorld: true
    readOnly: true
  name: list-joined-teams
- description: Create a new team.
  hints:
    readOnly: false
  name: create-team
- description: List channels in a team.
  hints:
    openWorld: true
    readOnly: true
  name: list-channels
- description: Create a new channel.
  hints:
    readOnly: false
  name: create-channel
- description: List messages from a channel.
  hints:
    openWorld: true
    readOnly: true
  name: list-channel-messages
- description: Send a message to a channel.
  hints:
    readOnly: false
  name: send-channel-message
- description: List all members of a team.
  hints:
    openWorld: true
    readOnly: true
  name: list-team-members
- description: Add a member to a team.
  hints:
    readOnly: false
  name: add-team-member
- description: Create an online meeting.
  hints:
    readOnly: false
  name: create-online-meeting
- description: Initiate a call.
  hints:
    readOnly: false
  name: create-call
---
