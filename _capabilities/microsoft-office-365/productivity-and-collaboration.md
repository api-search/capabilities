---
categories:
- collaboration
consumed_apis:
- graph-api
description: Unified productivity workflow combining mail, calendar, user management, and group collaboration for enterprise users and IT administrators.
layout: capability
name: Microsoft Office 365 Productivity and Collaboration
operations:
- description: List users.
  method: GET
  name: list-users
  path: /v1/users
- description: Create a user.
  method: POST
  name: create-user
  path: /v1/users
- description: List groups.
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create a group.
  method: POST
  name: create-group
  path: /v1/groups
- description: List messages.
  method: GET
  name: list-messages
  path: /v1/messages
- description: Send mail.
  method: POST
  name: send-mail
  path: /v1/messages
- description: List events.
  method: GET
  name: list-events
  path: /v1/events
- description: Create an event.
  method: POST
  name: create-event
  path: /v1/events
personas: []
provider_name: Microsoft Office 365
provider_slug: microsoft-office-365
search_terms:
- list users.
- get a specific group.
- list users
- create event
- create a draft message.
- update event
- send mail
- delete group
- update a calendar event.
- accept event
- list groups.
- create a group.
- calendar management.
- create a user.
- delete a group.
- add a member to a group.
- list group members
- microsoft
- list calendars
- decline event
- user management.
- collaboration
- enterprise
- create user
- create a new user.
- create message
- delete message
- list groups
- create a new group.
- get a specific message.
- list events.
- delete a user.
- get user
- get calendar view for a date range.
- create group
- list messages.
- list mail folders.
- update user properties.
- list calendars.
- get group
- decline a meeting invitation.
- send an email message.
- update user
- list calendar events.
- delete event
- get the signed-in user profile.
- remove a member from a group.
- list users in the organization.
- create a calendar event.
- get a specific event.
- delete a calendar event.
- get calendar view
- list mail folders
- productivity
- list events
- get a specific user.
- send mail.
- group management.
- get signed in user
- office 365
- get message
- list mail messages.
- accept a meeting invitation.
- list messages
- delete user
- add group member
- delete a message.
- get event
- cloud
- remove group member
- create an event.
- mail management.
- list members of a group.
slug: productivity-and-collaboration
tags:
- Microsoft
- Office 365
- Productivity
- Collaboration
- Enterprise
tools:
- description: List users in the organization.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new user.
  hints:
    readOnly: false
  name: create-user
- description: Get a specific user.
  hints:
    readOnly: true
  name: get-user
- description: Update user properties.
  hints:
    idempotent: true
    readOnly: false
  name: update-user
- description: Delete a user.
  hints:
    destructive: true
    readOnly: false
  name: delete-user
- description: Get the signed-in user profile.
  hints:
    readOnly: true
  name: get-signed-in-user
- description: List groups.
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Create a new group.
  hints:
    readOnly: false
  name: create-group
- description: Get a specific group.
  hints:
    readOnly: true
  name: get-group
- description: Delete a group.
  hints:
    destructive: true
    readOnly: false
  name: delete-group
- description: List members of a group.
  hints:
    readOnly: true
  name: list-group-members
- description: Add a member to a group.
  hints:
    readOnly: false
  name: add-group-member
- description: Remove a member from a group.
  hints:
    destructive: true
    readOnly: false
  name: remove-group-member
- description: List mail messages.
  hints:
    openWorld: true
    readOnly: true
  name: list-messages
- description: Create a draft message.
  hints:
    readOnly: false
  name: create-message
- description: Get a specific message.
  hints:
    readOnly: true
  name: get-message
- description: Delete a message.
  hints:
    destructive: true
    readOnly: false
  name: delete-message
- description: Send an email message.
  hints:
    readOnly: false
  name: send-mail
- description: List mail folders.
  hints:
    readOnly: true
  name: list-mail-folders
- description: List calendar events.
  hints:
    openWorld: true
    readOnly: true
  name: list-events
- description: Create a calendar event.
  hints:
    readOnly: false
  name: create-event
- description: Get a specific event.
  hints:
    readOnly: true
  name: get-event
- description: Update a calendar event.
  hints:
    idempotent: true
    readOnly: false
  name: update-event
- description: Delete a calendar event.
  hints:
    destructive: true
    readOnly: false
  name: delete-event
- description: List calendars.
  hints:
    readOnly: true
  name: list-calendars
- description: Get calendar view for a date range.
  hints:
    readOnly: true
  name: get-calendar-view
- description: Accept a meeting invitation.
  hints:
    readOnly: false
  name: accept-event
- description: Decline a meeting invitation.
  hints:
    readOnly: false
  name: decline-event
---
