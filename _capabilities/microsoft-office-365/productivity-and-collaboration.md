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
- get a specific user.
- microsoft
- get the signed-in user profile.
- create a new group.
- list mail folders.
- list mail folders
- list calendar events.
- create user
- calendar management.
- create a calendar event.
- delete event
- list messages.
- decline a meeting invitation.
- get a specific message.
- accept event
- create a group.
- get calendar view for a date range.
- get calendar view
- list group members
- get event
- list users.
- decline event
- create a new user.
- get message
- delete message
- add a member to a group.
- delete a calendar event.
- user management.
- list mail messages.
- remove group member
- create a draft message.
- create a user.
- send mail.
- get a specific event.
- get a specific group.
- productivity
- create an event.
- get signed in user
- delete a message.
- mail management.
- delete group
- list messages
- list users in the organization.
- update user properties.
- get user
- delete user
- send an email message.
- list users
- group management.
- list members of a group.
- update user
- remove a member from a group.
- list calendars.
- cloud
- list groups
- send mail
- create message
- list calendars
- collaboration
- accept a meeting invitation.
- delete a user.
- update event
- list events
- add group member
- list events.
- enterprise
- list groups.
- delete a group.
- get group
- office 365
- create event
- create group
- update a calendar event.
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
