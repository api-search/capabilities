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
- create an online meeting.
- communication
- manage teams collaboration workflows.
- initiate a call.
- list messages from a channel.
- list messages.
- list channels.
- it admins managing teams infrastructure and policies.
- list team members
- microsoft 365
- list joined teams.
- add team member
- create a team.
- create a meeting.
- send a message.
- create a new team.
- list channel messages
- messaging.
- video conferencing
- productivity
- list channels
- list members.
- create a channel.
- team leads managing channels, members, and communication.
- list all teams the user has joined.
- send a message to a channel.
- collaboration
- Developer
- microsoft teams
- create call
- team management.
- list channels in a team.
- Team Lead
- developers building teams integrations and bots.
- add a member to a team.
- list all members of a team.
- create team
- member management.
- create channel
- create a new channel.
- channel management.
- chat
- list joined teams
- IT Administrator
- create online meeting
- meeting management.
- send channel message
slug: team-collaboration
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
