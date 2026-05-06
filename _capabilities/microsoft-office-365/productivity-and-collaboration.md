---
categories:
- collaboration
consumed_apis: []
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
- create event
- list events
- create a new group.
- list events.
- get signed in user
- list mail folders
- remove a member from a group.
- list group members
- list messages
- calendar management.
- get a specific group.
- get calendar view for a date range.
- create a calendar event.
- get a specific event.
- get a specific user.
- delete a calendar event.
- list calendars.
- delete group
- get event
- create a user.
- create a draft message.
- decline event
- add group member
- delete message
- delete a user.
- create user
- get group
- delete a message.
- send mail.
- update user properties.
- cloud
- list messages.
- enterprise
- list calendar events.
- send mail
- productivity
- microsoft
- delete user
- delete a group.
- create an event.
- get a specific message.
- send an email message.
- user management.
- remove group member
- list mail folders.
- list calendars
- update user
- list users.
- get user
- accept a meeting invitation.
- create a group.
- decline a meeting invitation.
- office 365
- list users
- list groups.
- update event
- get calendar view
- list members of a group.
- update a calendar event.
- list groups
- get the signed-in user profile.
- list users in the organization.
- list mail messages.
- group management.
- mail management.
- add a member to a group.
- delete event
- create group
- collaboration
- accept event
- get message
- create a new user.
- create message
slug: productivity-and-collaboration
source_filename: productivity-and-collaboration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Office 365 Productivity and Collaboration\n  description: Unified productivity workflow combining mail, calendar, user management, and group collaboration for enterprise\n    users and IT administrators.\n  tags:\n  - Microsoft\n  - Office 365\n  - Productivity\n  - Collaboration\n  - Enterprise\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_GRAPH_TOKEN: MICROSOFT_GRAPH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: graph-api\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Graph API for accessing Microsoft 365 data.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_GRAPH_TOKEN}}'\n    resources:\n    - name: users\n      path: /users\n      description: Manage Microsoft 365 users.\n      operations:\n      - name: list-users\n        method: GET\n        description: List users in the organization.\n        inputParameters:\n\
  \        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return.\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression.\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of properties to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            mailNickname: '{{tools.mailNickname}}'\n            userPrincipalName: '{{tools.userPrincipalName}}'\n\
  \            accountEnabled: '{{tools.accountEnabled}}'\n            passwordProfile: '{{tools.passwordProfile}}'\n      - name: get-user\n        method: GET\n        description: Get a specific user by ID.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID or userPrincipalName.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PATCH\n        description: Update user properties.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n      - name:\
  \ delete-user\n        method: DELETE\n        description: Delete a user.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-signed-in-user\n        method: GET\n        description: Get the signed-in user profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Manage Microsoft 365 groups.\n      operations:\n      - name: list-groups\n        method: GET\n        description: List groups in the organization.\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        - name: $filter\n      \
  \    in: query\n          type: string\n          required: false\n          description: OData filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            mailEnabled: '{{tools.mailEnabled}}'\n            mailNickname: '{{tools.mailNickname}}'\n            securityEnabled: '{{tools.securityEnabled}}'\n            groupTypes: '{{tools.groupTypes}}'\n      - name: get-group\n        method: GET\n        description: Get a specific group.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group\
  \ ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-group\n        method: PATCH\n        description: Update group properties.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-group\n        method: DELETE\n        description: Delete a group.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-group-members\n        method: GET\n        description: List members of a group.\n        inputParameters:\n\
  \        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-group-member\n        method: POST\n        description: Add a member to a group.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-group-member\n        method: DELETE\n        description: Remove a member from a group.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        - name: memberId\n          in: path\n          type: string\n          required: true\n\
  \          description: Member ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mail\n      path: /me/messages\n      description: Manage Outlook mail.\n      operations:\n      - name: list-messages\n        method: GET\n        description: List messages in the signed-in user mailbox.\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter.\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Properties to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-message\n        method:\
  \ POST\n        description: Create a draft message.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            subject: '{{tools.subject}}'\n            body: '{{tools.body}}'\n            toRecipients: '{{tools.toRecipients}}'\n      - name: get-message\n        method: GET\n        description: Get a specific message.\n        inputParameters:\n        - name: messageId\n          in: path\n          type: string\n          required: true\n          description: Message ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-message\n        method: PATCH\n        description: Update a message.\n        inputParameters:\n        - name: messageId\n          in: path\n          type: string\n          required: true\n          description: Message ID.\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-message\n        method: DELETE\n        description: Delete a message.\n        inputParameters:\n        - name: messageId\n          in: path\n          type: string\n          required: true\n          description: Message ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-mail\n        method: POST\n        description: Send an email message.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n            saveToSentItems: '{{tools.saveToSentItems}}'\n      - name: list-mail-folders\n        method: GET\n        description: List mail folders.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calendar\n      path: /me\n      description: Manage Outlook calendar.\n      operations:\n      - name: list-events\n        method: GET\n        description: List calendar events.\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-event\n        method: POST\n        description: Create a new calendar event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            subject: '{{tools.subject}}'\n            start: '{{tools.start}}'\n            end: '{{tools.end}}'\n            body: '{{tools.body}}'\n            attendees: '{{tools.attendees}}'\n      - name: get-event\n        method: GET\n        description: Get a specific event.\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Event ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-event\n        method: PATCH\n        description: Update an event.\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Event ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-event\n        method: DELETE\n      \
  \  description: Delete an event.\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Event ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-calendars\n        method: GET\n        description: List calendars.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-calendar-view\n        method: GET\n        description: Get calendar view for a date range.\n        inputParameters:\n        - name: startDateTime\n          in: query\n          type: string\n          required: true\n          description: Start date/time.\n        - name: endDateTime\n          in: query\n          type: string\n          required: true\n          description: End date/time.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: accept-event\n        method: POST\n        description: Accept a meeting invitation.\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Event ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: decline-event\n        method: POST\n        description: Decline a meeting invitation.\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Event ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: productivity-api\n    description: Unified REST API for Microsoft 365 productivity and collaboration.\n\
  \    resources:\n    - path: /v1/users\n      name: users\n      description: User management.\n      operations:\n      - method: GET\n        name: list-users\n        description: List users.\n        call: graph-api.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a user.\n        call: graph-api.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Group management.\n      operations:\n      - method: GET\n        name: list-groups\n        description: List groups.\n        call: graph-api.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create a group.\n        call: graph-api.create-group\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /v1/messages\n      name: mail\n      description: Mail management.\n      operations:\n      - method: GET\n        name: list-messages\n        description: List messages.\n        call: graph-api.list-messages\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: send-mail\n        description: Send mail.\n        call: graph-api.send-mail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: calendar\n      description: Calendar management.\n      operations:\n      - method: GET\n        name: list-events\n        description: List events.\n        call: graph-api.list-events\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-event\n        description: Create an event.\n        call: graph-api.create-event\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type:\
  \ mcp\n    port: 9090\n    namespace: productivity-mcp\n    transport: http\n    description: MCP server for AI-assisted Microsoft 365 productivity and collaboration.\n    tools:\n    - name: list-users\n      description: List users in the organization.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: graph-api.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new user.\n      hints:\n        readOnly: false\n      call: graph-api.create-user\n      with:\n        displayName: tools.displayName\n        mailNickname: tools.mailNickname\n        userPrincipalName: tools.userPrincipalName\n        accountEnabled: tools.accountEnabled\n        passwordProfile: tools.passwordProfile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get a specific user.\n      hints:\n        readOnly: true\n      call: graph-api.get-user\n\
  \      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n      description: Update user properties.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: graph-api.update-user\n      with:\n        userId: tools.userId\n        displayName: tools.displayName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Delete a user.\n      hints:\n        readOnly: false\n        destructive: true\n      call: graph-api.delete-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-signed-in-user\n      description: Get the signed-in user profile.\n      hints:\n        readOnly: true\n      call: graph-api.get-signed-in-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List groups.\n     \
  \ hints:\n        readOnly: true\n        openWorld: true\n      call: graph-api.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-group\n      description: Create a new group.\n      hints:\n        readOnly: false\n      call: graph-api.create-group\n      with:\n        displayName: tools.displayName\n        mailEnabled: tools.mailEnabled\n        mailNickname: tools.mailNickname\n        securityEnabled: tools.securityEnabled\n        groupTypes: tools.groupTypes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-group\n      description: Get a specific group.\n      hints:\n        readOnly: true\n      call: graph-api.get-group\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-group\n      description: Delete a group.\n      hints:\n        readOnly: false\n        destructive: true\n      call: graph-api.delete-group\n\
  \      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-group-members\n      description: List members of a group.\n      hints:\n        readOnly: true\n      call: graph-api.list-group-members\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-group-member\n      description: Add a member to a group.\n      hints:\n        readOnly: false\n      call: graph-api.add-group-member\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-group-member\n      description: Remove a member from a group.\n      hints:\n        readOnly: false\n        destructive: true\n      call: graph-api.remove-group-member\n      with:\n        groupId: tools.groupId\n        memberId: tools.memberId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ list-messages\n      description: List mail messages.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: graph-api.list-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-message\n      description: Create a draft message.\n      hints:\n        readOnly: false\n      call: graph-api.create-message\n      with:\n        subject: tools.subject\n        body: tools.body\n        toRecipients: tools.toRecipients\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-message\n      description: Get a specific message.\n      hints:\n        readOnly: true\n      call: graph-api.get-message\n      with:\n        messageId: tools.messageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-message\n      description: Delete a message.\n      hints:\n        readOnly: false\n        destructive: true\n      call: graph-api.delete-message\n      with:\n  \
  \      messageId: tools.messageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-mail\n      description: Send an email message.\n      hints:\n        readOnly: false\n      call: graph-api.send-mail\n      with:\n        message: tools.message\n        saveToSentItems: tools.saveToSentItems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-mail-folders\n      description: List mail folders.\n      hints:\n        readOnly: true\n      call: graph-api.list-mail-folders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-events\n      description: List calendar events.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: graph-api.list-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-event\n      description: Create a calendar event.\n      hints:\n        readOnly: false\n      call: graph-api.create-event\n \
  \     with:\n        subject: tools.subject\n        start: tools.start\n        end: tools.end\n        body: tools.body\n        attendees: tools.attendees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event\n      description: Get a specific event.\n      hints:\n        readOnly: true\n      call: graph-api.get-event\n      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-event\n      description: Update a calendar event.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: graph-api.update-event\n      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-event\n      description: Delete a calendar event.\n      hints:\n        readOnly: false\n        destructive: true\n      call: graph-api.delete-event\n      with:\n        eventId: tools.eventId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-calendars\n      description: List calendars.\n      hints:\n        readOnly: true\n      call: graph-api.list-calendars\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-calendar-view\n      description: Get calendar view for a date range.\n      hints:\n        readOnly: true\n      call: graph-api.get-calendar-view\n      with:\n        startDateTime: tools.startDateTime\n        endDateTime: tools.endDateTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: accept-event\n      description: Accept a meeting invitation.\n      hints:\n        readOnly: false\n      call: graph-api.accept-event\n      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: decline-event\n      description: Decline a meeting invitation.\n      hints:\n        readOnly: false\n      call: graph-api.decline-event\n\
  \      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-office-365/refs/heads/main/capabilities/productivity-and-collaboration.yaml
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
