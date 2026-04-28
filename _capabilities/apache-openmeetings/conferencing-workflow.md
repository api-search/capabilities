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
- check health
- web conferencing
- unified workflow for managing conferencing sessions
- session recordings
- list upcoming
- whiteboard
- get room hash
- check system health status
- calendar and scheduling
- list public rooms
- list all public conference rooms
- get upcoming calendar meetings
- video conferencing
- list recordings
- login
- get upcoming meetings
- create a new conference room
- list all registered users
- list all user groups
- create a new room
- list users
- close a conference room
- manages conference rooms, invites participants, and handles recordings
- apache openmeetings
- list groups
- Meeting Organizer
- apache
- collaboration
- conference room management
- conferencing
- open source
- list rooms
- list session recordings
- get recordings by type
- close room
- generate a secure room access hash
- authenticate a user to openmeetings
- System Administrator
- manages users, groups, and system health
- user management
- create room
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
