---
consumed_apis:
- openmeetings
description: Unified workflow capability for managing web conferencing sessions, users, rooms, recordings, and calendars in Apache OpenMeetings.
layout: capability
name: Apache OpenMeetings Conferencing Workflow
operations:
- description: List public rooms
  method: GET
  name: list-rooms
  path: /v1/rooms
- description: Create a new room
  method: POST
  name: create-room
  path: /v1/rooms
- description: List users
  method: GET
  name: list-users
  path: /v1/users
- description: Get recordings by type
  method: GET
  name: list-recordings
  path: /v1/recordings
- description: Get upcoming meetings
  method: GET
  name: list-upcoming
  path: /v1/calendar
personas: []
provider_name: Apache OpenMeetings
provider_slug: apache-openmeetings
search_terms:
- login
- create a new conference room
- get upcoming calendar meetings
- session recordings
- collaboration
- list session recordings
- check health
- video conferencing
- get upcoming meetings
- close a conference room
- close room
- open source
- list recordings
- authenticate a user to openmeetings
- apache
- list all registered users
- create room
- conference room management
- whiteboard
- list public rooms
- generate a secure room access hash
- list all public conference rooms
- check system health status
- list users
- create a new room
- get recordings by type
- manages conference rooms, invites participants, and handles recordings
- list rooms
- get room hash
- Meeting Organizer
- manages users, groups, and system health
- System Administrator
- apache openmeetings
- unified workflow for managing conferencing sessions
- calendar and scheduling
- conferencing
- list groups
- web conferencing
- list upcoming
- user management
- list all user groups
slug: conferencing-workflow
tags:
- Apache OpenMeetings
- Conferencing
- Collaboration
- Web Conferencing
tools:
- description: List all public conference rooms
  hints:
    readOnly: true
  name: list-rooms
- description: Create a new conference room
  hints:
    readOnly: false
  name: create-room
- description: Close a conference room
  hints:
    destructive: true
    readOnly: false
  name: close-room
- description: List all registered users
  hints:
    readOnly: true
  name: list-users
- description: Authenticate a user to OpenMeetings
  hints:
    readOnly: false
  name: login
- description: Generate a secure room access hash
  hints:
    readOnly: false
  name: get-room-hash
- description: List session recordings
  hints:
    readOnly: true
  name: list-recordings
- description: Get upcoming calendar meetings
  hints:
    readOnly: true
  name: get-upcoming-meetings
- description: List all user groups
  hints:
    readOnly: true
  name: list-groups
- description: Check system health status
  hints:
    readOnly: true
  name: check-health
---
