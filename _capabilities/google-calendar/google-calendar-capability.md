---
categories: []
consumed_apis: []
description: The Google Calendar API provides RESTful access to Google Calendar data. It enables managing calendars, events, access control lists, settings, and free/busy information.
layout: capability
name: Google Calendar API
operations:
- description: Google Calendar Create calendar
  method: POST
  name: createcalendar
  path: /calendars
- description: Google Calendar Get calendar
  method: GET
  name: getcalendar
  path: /calendars/{calendarId}
- description: Google Calendar Update calendar
  method: PUT
  name: updatecalendar
  path: /calendars/{calendarId}
- description: Google Calendar Delete calendar
  method: DELETE
  name: deletecalendar
  path: /calendars/{calendarId}
- description: Google Calendar List events
  method: GET
  name: listevents
  path: /calendars/{calendarId}/events
- description: Google Calendar Create event
  method: POST
  name: createevent
  path: /calendars/{calendarId}/events
- description: Google Calendar Get event
  method: GET
  name: getevent
  path: /calendars/{calendarId}/events/{eventId}
- description: Google Calendar Update event
  method: PUT
  name: updateevent
  path: /calendars/{calendarId}/events/{eventId}
- description: Google Calendar Patch event
  method: PATCH
  name: patchevent
  path: /calendars/{calendarId}/events/{eventId}
- description: Google Calendar Delete event
  method: DELETE
  name: deleteevent
  path: /calendars/{calendarId}/events/{eventId}
- description: Google Calendar Quick add event
  method: POST
  name: quickaddevent
  path: /calendars/{calendarId}/events/quickAdd
- description: Google Calendar List ACL rules
  method: GET
  name: listacl
  path: /calendars/{calendarId}/acl
- description: Google Calendar Insert ACL rule
  method: POST
  name: insertacl
  path: /calendars/{calendarId}/acl
- description: Google Calendar List calendar list
  method: GET
  name: listcalendarlist
  path: /users/me/calendarList
- description: Google Calendar Insert calendar to list
  method: POST
  name: insertcalendarlist
  path: /users/me/calendarList
- description: Google Calendar List settings
  method: GET
  name: listsettings
  path: /users/me/settings
- description: Google Calendar Query free/busy
  method: POST
  name: queryfreebusy
  path: /freeBusy
- description: Google Calendar Get colors
  method: GET
  name: getcolors
  path: /colors
personas: []
provider_name: Google Calendar
provider_slug: google-calendar
search_terms:
- google workspace
- listevents
- quickaddevent
- insertcalendarlist
- google calendar query free/busy
- updateevent
- scheduling
- google calendar create calendar
- google calendar patch event
- google calendar create event
- google calendar update calendar
- calendar
- deletecalendar
- listacl
- google calendar insert calendar to list
- getcalendar
- listsettings
- google calendar insert acl rule
- google
- google calendar get calendar
- google calendar quick add event
- patchevent
- google calendar list acl rules
- queryfreebusy
- getcolors
- createevent
- api
- listcalendarlist
- createcalendar
- google calendar update event
- deleteevent
- google calendar list calendar list
- google calendar get colors
- google calendar list settings
- insertacl
- getevent
- google calendar delete event
- availability
- google calendar get event
- updatecalendar
- google calendar list events
- events
- google calendar delete calendar
slug: google-calendar-capability
source_filename: google-calendar-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Calendar API\n  description: The Google Calendar API provides RESTful access to Google Calendar data. It enables managing calendars, events,\n    access control lists, settings, and free/busy information.\n  tags:\n  - Google\n  - Calendar\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-calendar\n    baseUri: https://www.googleapis.com/calendar/v3\n    description: Google Calendar API HTTP API.\n    resources:\n    - name: calendars\n      path: /calendars\n      operations:\n      - name: createcalendar\n        method: POST\n        description: Google Calendar Create calendar\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calendars-calendarid\n      path: /calendars/{calendarId}\n      operations:\n      - name: getcalendar\n        method: GET\n        description:\
  \ Google Calendar Get calendar\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecalendar\n        method: PUT\n        description: Google Calendar Update calendar\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecalendar\n        method: DELETE\n        description: Google Calendar Delete calendar\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: calendars-calendarid-events\n      path: /calendars/{calendarId}/events\n      operations:\n      - name: listevents\n        method: GET\n        description: Google Calendar List events\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: timeMin\n          in: query\n          type: string\n        - name: timeMax\n          in: query\n          type: string\n        - name: q\n          in: query\n          type: string\n        - name: singleEvents\n          in: query\n          type: boolean\n        - name: orderBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createevent\n        method: POST\n  \
  \      description: Google Calendar Create event\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calendars-calendarid-events-eventid\n      path: /calendars/{calendarId}/events/{eventId}\n      operations:\n      - name: getevent\n        method: GET\n        description: Google Calendar Get event\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        - name: eventId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateevent\n        method: PUT\n        description: Google Calendar Update event\n        inputParameters:\n        - name:\
  \ calendarId\n          in: path\n          type: string\n          required: true\n        - name: eventId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchevent\n        method: PATCH\n        description: Google Calendar Patch event\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        - name: eventId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteevent\n        method: DELETE\n        description: Google Calendar Delete event\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        - name: eventId\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calendars-calendarid-events-quickadd\n      path: /calendars/{calendarId}/events/quickAdd\n      operations:\n      - name: quickaddevent\n        method: POST\n        description: Google Calendar Quick add event\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        - name: text\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calendars-calendarid-acl\n      path: /calendars/{calendarId}/acl\n      operations:\n      - name: listacl\n        method: GET\n        description: Google Calendar List ACL rules\n        inputParameters:\n        -\
  \ name: calendarId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertacl\n        method: POST\n        description: Google Calendar Insert ACL rule\n        inputParameters:\n        - name: calendarId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-me-calendarlist\n      path: /users/me/calendarList\n      operations:\n      - name: listcalendarlist\n        method: GET\n        description: Google Calendar List calendar list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertcalendarlist\n        method: POST\n        description: Google Calendar Insert calendar\
  \ to list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-me-settings\n      path: /users/me/settings\n      operations:\n      - name: listsettings\n        method: GET\n        description: Google Calendar List settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: freebusy\n      path: /freeBusy\n      operations:\n      - name: queryfreebusy\n        method: POST\n        description: Google Calendar Query free/busy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: colors\n      path: /colors\n      operations:\n      - name: getcolors\n        method: GET\n        description: Google Calendar Get colors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-calendar-rest\n    description: REST adapter for Google Calendar API.\n    resources:\n    - path: /calendars\n      name: createcalendar\n      operations:\n      - method: POST\n        name: createcalendar\n        description: Google Calendar Create calendar\n        call: google-calendar.createcalendar\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}\n      name: getcalendar\n      operations:\n      - method: GET\n        name: getcalendar\n        description: Google Calendar Get calendar\n        call: google-calendar.getcalendar\n        with:\n          calendarId: rest.calendarId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}\n      name: updatecalendar\n      operations:\n      - method: PUT\n        name: updatecalendar\n        description: Google Calendar Update\
  \ calendar\n        call: google-calendar.updatecalendar\n        with:\n          calendarId: rest.calendarId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}\n      name: deletecalendar\n      operations:\n      - method: DELETE\n        name: deletecalendar\n        description: Google Calendar Delete calendar\n        call: google-calendar.deletecalendar\n        with:\n          calendarId: rest.calendarId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}/events\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: Google Calendar List events\n        call: google-calendar.listevents\n        with:\n          calendarId: rest.calendarId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}/events\n      name: createevent\n      operations:\n     \
  \ - method: POST\n        name: createevent\n        description: Google Calendar Create event\n        call: google-calendar.createevent\n        with:\n          calendarId: rest.calendarId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}/events/{eventId}\n      name: getevent\n      operations:\n      - method: GET\n        name: getevent\n        description: Google Calendar Get event\n        call: google-calendar.getevent\n        with:\n          calendarId: rest.calendarId\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}/events/{eventId}\n      name: updateevent\n      operations:\n      - method: PUT\n        name: updateevent\n        description: Google Calendar Update event\n        call: google-calendar.updateevent\n        with:\n          calendarId: rest.calendarId\n          eventId: rest.eventId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}/events/{eventId}\n      name: patchevent\n      operations:\n      - method: PATCH\n        name: patchevent\n        description: Google Calendar Patch event\n        call: google-calendar.patchevent\n        with:\n          calendarId: rest.calendarId\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}/events/{eventId}\n      name: deleteevent\n      operations:\n      - method: DELETE\n        name: deleteevent\n        description: Google Calendar Delete event\n        call: google-calendar.deleteevent\n        with:\n          calendarId: rest.calendarId\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}/events/quickAdd\n      name: quickaddevent\n      operations:\n      - method: POST\n        name: quickaddevent\n\
  \        description: Google Calendar Quick add event\n        call: google-calendar.quickaddevent\n        with:\n          calendarId: rest.calendarId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}/acl\n      name: listacl\n      operations:\n      - method: GET\n        name: listacl\n        description: Google Calendar List ACL rules\n        call: google-calendar.listacl\n        with:\n          calendarId: rest.calendarId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendars/{calendarId}/acl\n      name: insertacl\n      operations:\n      - method: POST\n        name: insertacl\n        description: Google Calendar Insert ACL rule\n        call: google-calendar.insertacl\n        with:\n          calendarId: rest.calendarId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/me/calendarList\n      name: listcalendarlist\n      operations:\n\
  \      - method: GET\n        name: listcalendarlist\n        description: Google Calendar List calendar list\n        call: google-calendar.listcalendarlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/me/calendarList\n      name: insertcalendarlist\n      operations:\n      - method: POST\n        name: insertcalendarlist\n        description: Google Calendar Insert calendar to list\n        call: google-calendar.insertcalendarlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/me/settings\n      name: listsettings\n      operations:\n      - method: GET\n        name: listsettings\n        description: Google Calendar List settings\n        call: google-calendar.listsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /freeBusy\n      name: queryfreebusy\n      operations:\n      - method: POST\n        name: queryfreebusy\n        description: Google\
  \ Calendar Query free/busy\n        call: google-calendar.queryfreebusy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /colors\n      name: getcolors\n      operations:\n      - method: GET\n        name: getcolors\n        description: Google Calendar Get colors\n        call: google-calendar.getcolors\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-calendar-mcp\n    transport: http\n    description: MCP adapter for Google Calendar API for AI agent use.\n    tools:\n    - name: createcalendar\n      description: Google Calendar Create calendar\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-calendar.createcalendar\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcalendar\n      description: Google Calendar Get calendar\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-calendar.getcalendar\n      with:\n        calendarId: tools.calendarId\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecalendar\n      description: Google Calendar Update calendar\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-calendar.updatecalendar\n      with:\n        calendarId: tools.calendarId\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecalendar\n      description: Google Calendar Delete calendar\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-calendar.deletecalendar\n\
  \      with:\n        calendarId: tools.calendarId\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listevents\n      description: Google Calendar List events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-calendar.listevents\n      with:\n        calendarId: tools.calendarId\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n        timeMin: tools.timeMin\n        timeMax: tools.timeMax\n        q: tools.q\n        singleEvents: tools.singleEvents\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n     \
  \   description: pageToken\n      - name: timeMin\n        type: string\n        description: timeMin\n      - name: timeMax\n        type: string\n        description: timeMax\n      - name: q\n        type: string\n        description: q\n      - name: singleEvents\n        type: boolean\n        description: singleEvents\n      - name: orderBy\n        type: string\n        description: orderBy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createevent\n      description: Google Calendar Create event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-calendar.createevent\n      with:\n        calendarId: tools.calendarId\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getevent\n      description: Google Calendar Get event\n    \
  \  hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-calendar.getevent\n      with:\n        calendarId: tools.calendarId\n        eventId: tools.eventId\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      - name: eventId\n        type: string\n        description: eventId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateevent\n      description: Google Calendar Update event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-calendar.updateevent\n      with:\n        calendarId: tools.calendarId\n        eventId: tools.eventId\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      - name: eventId\n        type: string\n        description: eventId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchevent\n      description: Google Calendar Patch event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-calendar.patchevent\n      with:\n        calendarId: tools.calendarId\n        eventId: tools.eventId\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      - name: eventId\n        type: string\n        description: eventId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteevent\n      description: Google Calendar Delete event\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-calendar.deleteevent\n      with:\n        calendarId: tools.calendarId\n        eventId: tools.eventId\n      inputParameters:\n      -\
  \ name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      - name: eventId\n        type: string\n        description: eventId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: quickaddevent\n      description: Google Calendar Quick add event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-calendar.quickaddevent\n      with:\n        calendarId: tools.calendarId\n        text: tools.text\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      - name: text\n        type: string\n        description: text\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listacl\n      description: Google Calendar List ACL rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: google-calendar.listacl\n      with:\n        calendarId: tools.calendarId\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertacl\n      description: Google Calendar Insert ACL rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-calendar.insertacl\n      with:\n        calendarId: tools.calendarId\n      inputParameters:\n      - name: calendarId\n        type: string\n        description: calendarId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcalendarlist\n      description: Google Calendar List calendar list\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-calendar.listcalendarlist\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: insertcalendarlist\n      description: Google Calendar Insert calendar to list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-calendar.insertcalendarlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsettings\n      description: Google Calendar List settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-calendar.listsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queryfreebusy\n      description: Google Calendar Query free/busy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-calendar.queryfreebusy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcolors\n      description: Google Calendar Get colors\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: google-calendar.getcolors\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-calendar/refs/heads/main/capabilities/google-calendar-capability.yaml
tags:
- Google
- Calendar
- API
tools:
- description: Google Calendar Create calendar
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcalendar
- description: Google Calendar Get calendar
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcalendar
- description: Google Calendar Update calendar
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecalendar
- description: Google Calendar Delete calendar
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecalendar
- description: Google Calendar List events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: Google Calendar Create event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createevent
- description: Google Calendar Get event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevent
- description: Google Calendar Update event
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateevent
- description: Google Calendar Patch event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchevent
- description: Google Calendar Delete event
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteevent
- description: Google Calendar Quick add event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: quickaddevent
- description: Google Calendar List ACL rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listacl
- description: Google Calendar Insert ACL rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertacl
- description: Google Calendar List calendar list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcalendarlist
- description: Google Calendar Insert calendar to list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertcalendarlist
- description: Google Calendar List settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsettings
- description: Google Calendar Query free/busy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: queryfreebusy
- description: Google Calendar Get colors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcolors
---
