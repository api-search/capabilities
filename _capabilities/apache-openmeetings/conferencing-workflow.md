---
categories: []
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
- list all user groups
- apache openmeetings
- list users
- list all registered users
- get upcoming calendar meetings
- System Administrator
- list session recordings
- create a new conference room
- generate a secure room access hash
- unified workflow for managing conferencing sessions
- get upcoming meetings
- session recordings
- list public rooms
- create a new room
- collaboration
- whiteboard
- check health
- check system health status
- authenticate a user to openmeetings
- list groups
- list upcoming
- web conferencing
- apache
- get recordings by type
- list all public conference rooms
- login
- create room
- list recordings
- calendar and scheduling
- video conferencing
- open source
- conferencing
- Meeting Organizer
- conference room management
- user management
- manages conference rooms, invites participants, and handles recordings
- get room hash
- manages users, groups, and system health
- close a conference room
- close room
- list rooms
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
