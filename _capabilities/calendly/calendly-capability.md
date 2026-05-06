---
categories: []
consumed_apis: []
description: The Calendly Scheduling API (v2) is a RESTful API that allows developers to programmatically manage scheduling workflows. It provides endpoints for managing users, organizations, event types, scheduled events, invitees, routing forms, availability schedules, and webhook subscriptions. The API uses JSON for request and response bodies, standard HTTP methods, and supports authentication via personal access tokens and OAuth 2.1. Developers can use it to create events on behalf of invitees, retrieve scheduling data, and integrate Calendly functionality directly into their applications.
layout: capability
name: Calendly Scheduling API
operations:
- description: Get current user
  method: GET
  name: getcurrentuser
  path: /users/me
- description: Get user
  method: GET
  name: getuser
  path: /users/{uuid}
- description: List event types
  method: GET
  name: listeventtypes
  path: /event_types
- description: Get event type
  method: GET
  name: geteventtype
  path: /event_types/{uuid}
- description: Create one-off event type
  method: POST
  name: createoneoffeventtype
  path: /one_off_event_types
- description: List event type available times
  method: GET
  name: listeventtypeavailabletimes
  path: /event_type_available_times
- description: List user busy times
  method: GET
  name: listuserbusytimes
  path: /user_busy_times
- description: List user availability schedules
  method: GET
  name: listuseravailabilityschedules
  path: /user_availability_schedules
- description: Get user availability schedule
  method: GET
  name: getuseravailabilityschedule
  path: /user_availability_schedules/{uuid}
- description: List scheduled events
  method: GET
  name: listscheduledevents
  path: /scheduled_events
- description: Get scheduled event
  method: GET
  name: getscheduledevent
  path: /scheduled_events/{uuid}
- description: Cancel scheduled event
  method: POST
  name: cancelscheduledevent
  path: /scheduled_events/{uuid}/cancellation
- description: List event invitees
  method: GET
  name: listeventinvitees
  path: /scheduled_events/{event_uuid}/invitees
- description: Get event invitee
  method: GET
  name: geteventinvitee
  path: /scheduled_events/{event_uuid}/invitees/{invitee_uuid}
- description: Create event invitee
  method: POST
  name: createeventinvitee
  path: /invitees
- description: List webhook subscriptions
  method: GET
  name: listwebhooksubscriptions
  path: /webhook_subscriptions
- description: Create webhook subscription
  method: POST
  name: createwebhooksubscription
  path: /webhook_subscriptions
- description: Get webhook subscription
  method: GET
  name: getwebhooksubscription
  path: /webhook_subscriptions/{uuid}
- description: Delete webhook subscription
  method: DELETE
  name: deletewebhooksubscription
  path: /webhook_subscriptions/{uuid}
- description: List organization memberships
  method: GET
  name: listorganizationmemberships
  path: /organization_memberships
- description: Get organization membership
  method: GET
  name: getorganizationmembership
  path: /organization_memberships/{uuid}
- description: Remove organization membership
  method: DELETE
  name: deleteorganizationmembership
  path: /organization_memberships/{uuid}
- description: List organization invitations
  method: GET
  name: listorganizationinvitations
  path: /organizations/{uuid}/invitations
- description: Invite user to organization
  method: POST
  name: invitetoorganization
  path: /organizations/{uuid}/invitations
- description: Get organization invitation
  method: GET
  name: getorganizationinvitation
  path: /organizations/{org_uuid}/invitations/{invitation_uuid}
- description: Revoke organization invitation
  method: DELETE
  name: revokeorganizationinvitation
  path: /organizations/{org_uuid}/invitations/{invitation_uuid}
- description: List routing forms
  method: GET
  name: listroutingforms
  path: /routing_forms
- description: Get routing form
  method: GET
  name: getroutingform
  path: /routing_forms/{uuid}
- description: List routing form submissions
  method: GET
  name: listroutingformsubmissions
  path: /routing_form_submissions
- description: Get routing form submission
  method: GET
  name: getroutingformsubmission
  path: /routing_form_submissions/{uuid}
- description: Delete invitee data
  method: POST
  name: deleteinviteedata
  path: /data_compliance/deletion/invitees
- description: List activity log entries
  method: GET
  name: listactivitylogentries
  path: /activity_log_entries
- description: Create share
  method: POST
  name: createshare
  path: /shares
- description: List groups
  method: GET
  name: listgroups
  path: /groups
- description: List group relationships
  method: GET
  name: listgrouprelationships
  path: /group_relationships
personas: []
provider_name: Calendly
provider_slug: calendly
search_terms:
- invite user to organization
- create webhook subscription
- get organization membership
- listeventtypes
- listgrouprelationships
- getuseravailabilityschedule
- list routing forms
- api
- list user availability schedules
- revokeorganizationinvitation
- create one-off event type
- booking
- getuser
- list groups
- get event invitee
- invitetoorganization
- list activity log entries
- automation
- geteventtype
- cancelscheduledevent
- listeventtypeavailabletimes
- createoneoffeventtype
- list event invitees
- list event type available times
- list user busy times
- get user availability schedule
- listgroups
- get webhook subscription
- create share
- listwebhooksubscriptions
- delete invitee data
- get organization invitation
- list group relationships
- get current user
- getroutingformsubmission
- deletewebhooksubscription
- listuserbusytimes
- create event invitee
- revoke organization invitation
- getorganizationmembership
- listeventinvitees
- geteventinvitee
- createshare
- list webhook subscriptions
- get event type
- getscheduledevent
- remove organization membership
- calendars
- createwebhooksubscription
- calendly
- list routing form submissions
- listroutingforms
- getroutingform
- getwebhooksubscription
- list organization invitations
- get scheduled event
- listroutingformsubmissions
- getorganizationinvitation
- meetings
- getcurrentuser
- list organization memberships
- delete webhook subscription
- scheduling
- listorganizationinvitations
- listuseravailabilityschedules
- listactivitylogentries
- createeventinvitee
- get routing form submission
- listscheduledevents
- listorganizationmemberships
- list event types
- deleteinviteedata
- appointments
- list scheduled events
- get user
- get routing form
- deleteorganizationmembership
- cancel scheduled event
slug: calendly-capability
source_filename: calendly-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Calendly Scheduling API\n  description: The Calendly Scheduling API (v2) is a RESTful API that allows developers to programmatically manage scheduling\n    workflows. It provides endpoints for managing users, organizations, event types, scheduled events, invitees, routing forms,\n    availability schedules, and webhook subscriptions. The API uses JSON for request and response bodies, standard HTTP methods,\n    and supports authentication via personal access tokens and OAuth 2.1. Developers can use it to create events on behalf\n    of invitees, retrieve scheduling data, and integrate Calendly functionality directly into their applications.\n  tags:\n  - Calendly\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: calendly\n    baseUri: https://api.calendly.com\n    description: Calendly Scheduling API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CALENDLY_TOKEN}}'\n\
  \    resources:\n    - name: users-me\n      path: /users/me\n      operations:\n      - name: getcurrentuser\n        method: GET\n        description: Get current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-uuid\n      path: /users/{uuid}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-types\n      path: /event_types\n      operations:\n      - name: listeventtypes\n        method: GET\n        description: List event types\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          description: The URI of the user whose event types to list. Required if organization is not specified.\n        - name: organization\n          in: query\n          type:\
  \ string\n          description: The URI of the organization whose event types to list. Required if user is not specified.\n        - name: active\n          in: query\n          type: boolean\n          description: Filter by active status. When true, only active event types are returned.\n        - name: sort\n          in: query\n          type: string\n          description: Sort order for results. Use name:asc or name:desc.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-types-uuid\n      path: /event_types/{uuid}\n      operations:\n      - name: geteventtype\n        method: GET\n        description: Get event type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: one-off-event-types\n      path: /one_off_event_types\n      operations:\n      - name: createoneoffeventtype\n        method: POST\n\
  \        description: Create one-off event type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-type-available-times\n      path: /event_type_available_times\n      operations:\n      - name: listeventtypeavailabletimes\n        method: GET\n        description: List event type available times\n        inputParameters:\n        - name: event_type\n          in: query\n          type: string\n          required: true\n          description: The URI of the event type to check availability for.\n        - name: start_time\n          in: query\n          type: string\n          required: true\n          description: The start of the time range to check, in UTC format.\n        - name: end_time\n          in: query\n          type: string\n          required: true\n          description: The end of the time range to check, in UTC format.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: user-busy-times\n      path: /user_busy_times\n      operations:\n      - name: listuserbusytimes\n        method: GET\n        description: List user busy times\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          required: true\n          description: The URI of the user whose busy times to retrieve.\n        - name: start_time\n          in: query\n          type: string\n          required: true\n          description: The start of the time range to check, in UTC format.\n        - name: end_time\n          in: query\n          type: string\n          required: true\n          description: The end of the time range to check, in UTC format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-availability-schedules\n      path: /user_availability_schedules\n   \
  \   operations:\n      - name: listuseravailabilityschedules\n        method: GET\n        description: List user availability schedules\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          required: true\n          description: The URI of the user whose availability schedules to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-availability-schedules-uuid\n      path: /user_availability_schedules/{uuid}\n      operations:\n      - name: getuseravailabilityschedule\n        method: GET\n        description: Get user availability schedule\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the availability schedule.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: scheduled-events\n      path: /scheduled_events\n      operations:\n      - name: listscheduledevents\n        method: GET\n        description: List scheduled events\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          description: The URI of the user whose scheduled events to list.\n        - name: organization\n          in: query\n          type: string\n          description: The URI of the organization whose scheduled events to list.\n        - name: invitee_email\n          in: query\n          type: string\n          description: Filter by invitee email address.\n        - name: status\n          in: query\n          type: string\n          description: Filter by event status.\n        - name: min_start_time\n          in: query\n          type: string\n          description: Only return events starting on or after this time, in UTC format.\n        - name: max_start_time\n          in: query\n          type:\
  \ string\n          description: Only return events starting before this time, in UTC format.\n        - name: sort\n          in: query\n          type: string\n          description: Sort order for results. Use start_time:asc or start_time:desc.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduled-events-uuid\n      path: /scheduled_events/{uuid}\n      operations:\n      - name: getscheduledevent\n        method: GET\n        description: Get scheduled event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduled-events-uuid-cancellation\n      path: /scheduled_events/{uuid}/cancellation\n      operations:\n      - name: cancelscheduledevent\n        method: POST\n        description: Cancel scheduled event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: scheduled-events-event-uuid-invitees\n      path: /scheduled_events/{event_uuid}/invitees\n      operations:\n      - name: listeventinvitees\n        method: GET\n        description: List event invitees\n        inputParameters:\n        - name: event_uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the scheduled event.\n        - name: status\n          in: query\n          type: string\n          description: Filter by invitee status.\n        - name: sort\n          in: query\n          type: string\n          description: Sort order for results. Use created_at:asc or created_at:desc.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduled-events-event-uuid-invitees-invitee-uui\n      path: /scheduled_events/{event_uuid}/invitees/{invitee_uuid}\n      operations:\n      - name:\
  \ geteventinvitee\n        method: GET\n        description: Get event invitee\n        inputParameters:\n        - name: event_uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the scheduled event.\n        - name: invitee_uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the invitee.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invitees\n      path: /invitees\n      operations:\n      - name: createeventinvitee\n        method: POST\n        description: Create event invitee\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhook-subscriptions\n      path: /webhook_subscriptions\n      operations:\n      - name: listwebhooksubscriptions\n        method: GET\n        description: List\
  \ webhook subscriptions\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          description: The URI of the user whose webhook subscriptions to list.\n        - name: organization\n          in: query\n          type: string\n          required: true\n          description: The URI of the organization whose webhook subscriptions to list.\n        - name: scope\n          in: query\n          type: string\n          required: true\n          description: The scope of the webhook subscription. Use user for subscriptions scoped to a specific user, or organization\n            for organization-wide subscriptions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createwebhooksubscription\n        method: POST\n        description: Create webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: webhook-subscriptions-uuid\n      path: /webhook_subscriptions/{uuid}\n      operations:\n      - name: getwebhooksubscription\n        method: GET\n        description: Get webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletewebhooksubscription\n        method: DELETE\n        description: Delete webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-memberships\n      path: /organization_memberships\n      operations:\n      - name: listorganizationmemberships\n        method: GET\n        description: List organization memberships\n        inputParameters:\n        - name: organization\n          in: query\n          type: string\n          required: true\n          description: The URI of the organization whose\
  \ memberships to list.\n        - name: user\n          in: query\n          type: string\n          description: Filter by user URI.\n        - name: email\n          in: query\n          type: string\n          description: Filter by user email address.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-memberships-uuid\n      path: /organization_memberships/{uuid}\n      operations:\n      - name: getorganizationmembership\n        method: GET\n        description: Get organization membership\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the organization membership.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteorganizationmembership\n        method: DELETE\n        description:\
  \ Remove organization membership\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the organization membership to remove.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-uuid-invitations\n      path: /organizations/{uuid}/invitations\n      operations:\n      - name: listorganizationinvitations\n        method: GET\n        description: List organization invitations\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the organization.\n        - name: status\n          in: query\n          type: string\n          description: Filter invitations by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: invitetoorganization\n        method: POST\n        description: Invite user to organization\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-org-uuid-invitations-invitation-uu\n      path: /organizations/{org_uuid}/invitations/{invitation_uuid}\n      operations:\n      - name: getorganizationinvitation\n        method: GET\n        description: Get organization invitation\n        inputParameters:\n        - name: org_uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the organization.\n        - name: invitation_uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the invitation.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revokeorganizationinvitation\n        method: DELETE\n        description: Revoke organization invitation\n        inputParameters:\n        - name: org_uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the organization.\n        - name: invitation_uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the invitation to revoke.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routing-forms\n      path: /routing_forms\n      operations:\n      - name: listroutingforms\n        method: GET\n        description: List routing forms\n        inputParameters:\n        - name: organization\n          in: query\n          type: string\n          required:\
  \ true\n          description: The URI of the organization whose routing forms to list.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routing-forms-uuid\n      path: /routing_forms/{uuid}\n      operations:\n      - name: getroutingform\n        method: GET\n        description: Get routing form\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the routing form.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routing-form-submissions\n      path: /routing_form_submissions\n      operations:\n      - name: listroutingformsubmissions\n        method: GET\n        description: List routing form submissions\n        inputParameters:\n        - name: routing_form\n          in: query\n          type: string\n\
  \          required: true\n          description: The URI of the routing form whose submissions to list.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routing-form-submissions-uuid\n      path: /routing_form_submissions/{uuid}\n      operations:\n      - name: getroutingformsubmission\n        method: GET\n        description: Get routing form submission\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the routing form submission.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-compliance-deletion-invitees\n      path: /data_compliance/deletion/invitees\n      operations:\n      - name: deleteinviteedata\n        method: POST\n        description: Delete invitee data\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activity-log-entries\n      path: /activity_log_entries\n      operations:\n      - name: listactivitylogentries\n        method: GET\n        description: List activity log entries\n        inputParameters:\n        - name: organization\n          in: query\n          type: string\n          required: true\n          description: The URI of the organization whose activity log to retrieve.\n        - name: min_occurred_at\n          in: query\n          type: string\n          description: Only return entries that occurred on or after this time.\n        - name: max_occurred_at\n          in: query\n          type: string\n          description: Only return entries that occurred before this time.\n        - name: search_term\n          in: query\n          type: string\n          description: Filter entries by a search term.\n        - name: sort\n          in: query\n         \
  \ type: string\n          description: Sort order for results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shares\n      path: /shares\n      operations:\n      - name: createshare\n        method: POST\n        description: Create share\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: List groups\n        inputParameters:\n        - name: organization\n          in: query\n          type: string\n          required: true\n          description: The URI of the organization whose groups to list.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: group-relationships\n      path: /group_relationships\n \
  \     operations:\n      - name: listgrouprelationships\n        method: GET\n        description: List group relationships\n        inputParameters:\n        - name: group\n          in: query\n          type: string\n          description: The URI of the group to list relationships for.\n        - name: organization\n          in: query\n          type: string\n          required: true\n          description: The URI of the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: calendly-rest\n    description: REST adapter for Calendly Scheduling API.\n    resources:\n    - path: /users/me\n      name: getcurrentuser\n      operations:\n      - method: GET\n        name: getcurrentuser\n        description: Get current user\n        call: calendly.getcurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /users/{uuid}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get user\n        call: calendly.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_types\n      name: listeventtypes\n      operations:\n      - method: GET\n        name: listeventtypes\n        description: List event types\n        call: calendly.listeventtypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_types/{uuid}\n      name: geteventtype\n      operations:\n      - method: GET\n        name: geteventtype\n        description: Get event type\n        call: calendly.geteventtype\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /one_off_event_types\n      name: createoneoffeventtype\n      operations:\n      - method: POST\n        name: createoneoffeventtype\n        description: Create one-off event type\n        call:\
  \ calendly.createoneoffeventtype\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_type_available_times\n      name: listeventtypeavailabletimes\n      operations:\n      - method: GET\n        name: listeventtypeavailabletimes\n        description: List event type available times\n        call: calendly.listeventtypeavailabletimes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user_busy_times\n      name: listuserbusytimes\n      operations:\n      - method: GET\n        name: listuserbusytimes\n        description: List user busy times\n        call: calendly.listuserbusytimes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user_availability_schedules\n      name: listuseravailabilityschedules\n      operations:\n      - method: GET\n        name: listuseravailabilityschedules\n        description: List user availability schedules\n        call: calendly.listuseravailabilityschedules\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user_availability_schedules/{uuid}\n      name: getuseravailabilityschedule\n      operations:\n      - method: GET\n        name: getuseravailabilityschedule\n        description: Get user availability schedule\n        call: calendly.getuseravailabilityschedule\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduled_events\n      name: listscheduledevents\n      operations:\n      - method: GET\n        name: listscheduledevents\n        description: List scheduled events\n        call: calendly.listscheduledevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduled_events/{uuid}\n      name: getscheduledevent\n      operations:\n      - method: GET\n        name: getscheduledevent\n        description: Get scheduled event\n        call: calendly.getscheduledevent\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduled_events/{uuid}/cancellation\n      name: cancelscheduledevent\n      operations:\n      - method: POST\n        name: cancelscheduledevent\n        description: Cancel scheduled event\n        call: calendly.cancelscheduledevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduled_events/{event_uuid}/invitees\n      name: listeventinvitees\n      operations:\n      - method: GET\n        name: listeventinvitees\n        description: List event invitees\n        call: calendly.listeventinvitees\n        with:\n          event_uuid: rest.event_uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduled_events/{event_uuid}/invitees/{invitee_uuid}\n      name: geteventinvitee\n      operations:\n      - method: GET\n        name: geteventinvitee\n        description: Get event invitee\n        call: calendly.geteventinvitee\n\
  \        with:\n          event_uuid: rest.event_uuid\n          invitee_uuid: rest.invitee_uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /invitees\n      name: createeventinvitee\n      operations:\n      - method: POST\n        name: createeventinvitee\n        description: Create event invitee\n        call: calendly.createeventinvitee\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook_subscriptions\n      name: listwebhooksubscriptions\n      operations:\n      - method: GET\n        name: listwebhooksubscriptions\n        description: List webhook subscriptions\n        call: calendly.listwebhooksubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook_subscriptions\n      name: createwebhooksubscription\n      operations:\n      - method: POST\n        name: createwebhooksubscription\n        description: Create webhook subscription\n    \
  \    call: calendly.createwebhooksubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook_subscriptions/{uuid}\n      name: getwebhooksubscription\n      operations:\n      - method: GET\n        name: getwebhooksubscription\n        description: Get webhook subscription\n        call: calendly.getwebhooksubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook_subscriptions/{uuid}\n      name: deletewebhooksubscription\n      operations:\n      - method: DELETE\n        name: deletewebhooksubscription\n        description: Delete webhook subscription\n        call: calendly.deletewebhooksubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization_memberships\n      name: listorganizationmemberships\n      operations:\n      - method: GET\n        name: listorganizationmemberships\n        description: List organization memberships\n\
  \        call: calendly.listorganizationmemberships\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization_memberships/{uuid}\n      name: getorganizationmembership\n      operations:\n      - method: GET\n        name: getorganizationmembership\n        description: Get organization membership\n        call: calendly.getorganizationmembership\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization_memberships/{uuid}\n      name: deleteorganizationmembership\n      operations:\n      - method: DELETE\n        name: deleteorganizationmembership\n        description: Remove organization membership\n        call: calendly.deleteorganizationmembership\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{uuid}/invitations\n      name: listorganizationinvitations\n     \
  \ operations:\n      - method: GET\n        name: listorganizationinvitations\n        description: List organization invitations\n        call: calendly.listorganizationinvitations\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{uuid}/invitations\n      name: invitetoorganization\n      operations:\n      - method: POST\n        name: invitetoorganization\n        description: Invite user to organization\n        call: calendly.invitetoorganization\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{org_uuid}/invitations/{invitation_uuid}\n      name: getorganizationinvitation\n      operations:\n      - method: GET\n        name: getorganizationinvitation\n        description: Get organization invitation\n        call: calendly.getorganizationinvitation\n        with:\n          org_uuid: rest.org_uuid\n\
  \          invitation_uuid: rest.invitation_uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{org_uuid}/invitations/{invitation_uuid}\n      name: revokeorganizationinvitation\n      operations:\n      - method: DELETE\n        name: revokeorganizationinvitation\n        description: Revoke organization invitation\n        call: calendly.revokeorganizationinvitation\n        with:\n          org_uuid: rest.org_uuid\n          invitation_uuid: rest.invitation_uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routing_forms\n      name: listroutingforms\n      operations:\n      - method: GET\n        name: listroutingforms\n        description: List routing forms\n        call: calendly.listroutingforms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routing_forms/{uuid}\n      name: getroutingform\n      operations:\n      - method: GET\n        name:\
  \ getroutingform\n        description: Get routing form\n        call: calendly.getroutingform\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routing_form_submissions\n      name: listroutingformsubmissions\n      operations:\n      - method: GET\n        name: listroutingformsubmissions\n        description: List routing form submissions\n        call: calendly.listroutingformsubmissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routing_form_submissions/{uuid}\n      name: getroutingformsubmission\n      operations:\n      - method: GET\n        name: getroutingformsubmission\n        description: Get routing form submission\n        call: calendly.getroutingformsubmission\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /data_compliance/deletion/invitees\n      name: deleteinviteedata\n\
  \      operations:\n      - method: POST\n        name: deleteinviteedata\n        description: Delete invitee data\n        call: calendly.deleteinviteedata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activity_log_entries\n      name: listactivitylogentries\n      operations:\n      - method: GET\n        name: listactivitylogentries\n        description: List activity log entries\n        call: calendly.listactivitylogentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shares\n      name: createshare\n      operations:\n      - method: POST\n        name: createshare\n        description: Create share\n        call: calendly.createshare\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: List groups\n        call: calendly.listgroups\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /group_relationships\n      name: listgrouprelationships\n      operations:\n      - method: GET\n        name: listgrouprelationships\n        description: List group relationships\n        call: calendly.listgrouprelationships\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: calendly-mcp\n    transport: http\n    description: MCP adapter for Calendly Scheduling API for AI agent use.\n    tools:\n    - name: getcurrentuser\n      description: Get current user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: calendly.getcurrentuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: calendly.getuser\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: listeventtypes\n      description: List event types\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: calendly.listeventtypes\n      with:\n        user: tools.user\n        organization: tools.organization\n        active: tools.active\n        sort: tools.sort\n      inputParameters:\n      - name: user\n        type: string\n        description: The URI of the user whose event types to list. Required if organization is not specified.\n      - name: organization\n        type: string\n        description: The URI of the organization whose event types to list. Required if user is not specified.\n      - name: active\n        type: boolean\n        desc\n\n# --- truncated at 32 KB (48 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/calendly/refs/heads/main/capabilities/calendly-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/calendly/refs/heads/main/capabilities/calendly-capability.yaml
tags:
- Calendly
- API
tools:
- description: Get current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentuser
- description: Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: List event types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventtypes
- description: Get event type
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventtype
- description: Create one-off event type
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createoneoffeventtype
- description: List event type available times
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventtypeavailabletimes
- description: List user busy times
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuserbusytimes
- description: List user availability schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuseravailabilityschedules
- description: Get user availability schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuseravailabilityschedule
- description: List scheduled events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscheduledevents
- description: Get scheduled event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getscheduledevent
- description: Cancel scheduled event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelscheduledevent
- description: List event invitees
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventinvitees
- description: Get event invitee
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventinvitee
- description: Create event invitee
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createeventinvitee
- description: List webhook subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebhooksubscriptions
- description: Create webhook subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhooksubscription
- description: Get webhook subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhooksubscription
- description: Delete webhook subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewebhooksubscription
- description: List organization memberships
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationmemberships
- description: Get organization membership
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationmembership
- description: Remove organization membership
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteorganizationmembership
- description: List organization invitations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationinvitations
- description: Invite user to organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invitetoorganization
- description: Get organization invitation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationinvitation
- description: Revoke organization invitation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revokeorganizationinvitation
- description: List routing forms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutingforms
- description: Get routing form
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroutingform
- description: List routing form submissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutingformsubmissions
- description: Get routing form submission
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroutingformsubmission
- description: Delete invitee data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteinviteedata
- description: List activity log entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listactivitylogentries
- description: Create share
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createshare
- description: List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: List group relationships
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgrouprelationships
---
