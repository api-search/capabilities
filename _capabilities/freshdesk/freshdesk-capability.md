---
categories: []
consumed_apis: []
description: The Freshdesk REST API (v2) provides programmatic access to helpdesk data and operations within Freshdesk, a customer support platform by Freshworks. It exposes endpoints for managing tickets, contacts, companies, agents, groups, conversations, products, email configurations, SLA policies, business hours, time entries, satisfaction ratings, solution categories, solution folders, solution articles, and more. The API uses JSON for request and response payloads, supports API key-based authentication, and follows RESTful conventions for CRUD operations.
layout: capability
name: Freshdesk REST API
operations:
- description: List all tickets
  method: GET
  name: listtickets
  path: /tickets
- description: Create a ticket
  method: POST
  name: createticket
  path: /tickets
- description: View a ticket
  method: GET
  name: getticket
  path: /tickets/{ticket_id}
- description: Update a ticket
  method: PUT
  name: updateticket
  path: /tickets/{ticket_id}
- description: Delete a ticket
  method: DELETE
  name: deleteticket
  path: /tickets/{ticket_id}
- description: Restore a deleted ticket
  method: PUT
  name: restoreticket
  path: /tickets/{ticket_id}/restore
- description: Create an outbound email ticket
  method: POST
  name: createoutboundemail
  path: /tickets/outbound_email
- description: List conversations on a ticket
  method: GET
  name: listticketconversations
  path: /tickets/{ticket_id}/conversations
- description: Reply to a ticket
  method: POST
  name: replytoticket
  path: /tickets/{ticket_id}/reply
- description: Create a note on a ticket
  method: POST
  name: createnote
  path: /tickets/{ticket_id}/notes
- description: Forward a ticket
  method: POST
  name: forwardticket
  path: /tickets/{ticket_id}/forward
- description: Update a conversation
  method: PUT
  name: updateconversation
  path: /conversations/{conversation_id}
- description: Delete a conversation
  method: DELETE
  name: deleteconversation
  path: /conversations/{conversation_id}
- description: List time entries for a ticket
  method: GET
  name: listtickettimeentries
  path: /tickets/{ticket_id}/time_entries
- description: Create a time entry
  method: POST
  name: createtimeentry
  path: /tickets/{ticket_id}/time_entries
- description: List all time entries
  method: GET
  name: listalltimeentries
  path: /time_entries
- description: Update a time entry
  method: PUT
  name: updatetimeentry
  path: /time_entries/{time_entry_id}
- description: Delete a time entry
  method: DELETE
  name: deletetimeentry
  path: /time_entries/{time_entry_id}
- description: Toggle a timer
  method: PUT
  name: toggletimer
  path: /time_entries/{time_entry_id}/toggle_timer
- description: Create a satisfaction rating
  method: POST
  name: createsatisfactionrating
  path: /tickets/{ticket_id}/satisfaction_ratings
- description: List all satisfaction ratings
  method: GET
  name: listsatisfactionratings
  path: /surveys/satisfaction_ratings
- description: List watchers on a ticket
  method: GET
  name: listticketwatchers
  path: /tickets/{ticket_id}/watchers
- description: Watch a ticket
  method: POST
  name: watchticket
  path: /tickets/{ticket_id}/watch
- description: List associated tickets
  method: GET
  name: listassociatedtickets
  path: /tickets/{ticket_id}/associated_tickets
- description: Merge tickets
  method: PUT
  name: mergetickets
  path: /tickets/merge
- description: Bulk update tickets
  method: POST
  name: bulkupdatetickets
  path: /tickets/bulk_update
- description: Bulk delete tickets
  method: POST
  name: bulkdeletetickets
  path: /tickets/bulk_delete
- description: List all contacts
  method: GET
  name: listcontacts
  path: /contacts
- description: Create a contact
  method: POST
  name: createcontact
  path: /contacts
- description: View a contact
  method: GET
  name: getcontact
  path: /contacts/{contact_id}
- description: Update a contact
  method: PUT
  name: updatecontact
  path: /contacts/{contact_id}
- description: Delete a contact
  method: DELETE
  name: deletecontact
  path: /contacts/{contact_id}
- description: Restore a deleted contact
  method: PUT
  name: restorecontact
  path: /contacts/{contact_id}/restore
- description: Merge contacts
  method: POST
  name: mergecontacts
  path: /contacts/merge
- description: Export contacts
  method: POST
  name: exportcontacts
  path: /contacts/export
- description: List all contact fields
  method: GET
  name: listcontactfields
  path: /contact_fields
- description: List all companies
  method: GET
  name: listcompanies
  path: /companies
- description: Create a company
  method: POST
  name: createcompany
  path: /companies
- description: View a company
  method: GET
  name: getcompany
  path: /companies/{company_id}
- description: Update a company
  method: PUT
  name: updatecompany
  path: /companies/{company_id}
- description: Delete a company
  method: DELETE
  name: deletecompany
  path: /companies/{company_id}
- description: List all company fields
  method: GET
  name: listcompanyfields
  path: /company_fields
- description: List all agents
  method: GET
  name: listagents
  path: /agents
- description: View an agent
  method: GET
  name: getagent
  path: /agents/{agent_id}
- description: Update an agent
  method: PUT
  name: updateagent
  path: /agents/{agent_id}
- description: Delete an agent
  method: DELETE
  name: deleteagent
  path: /agents/{agent_id}
- description: List all groups
  method: GET
  name: listgroups
  path: /groups
- description: Create a group
  method: POST
  name: creategroup
  path: /groups
- description: View a group
  method: GET
  name: getgroup
  path: /groups/{group_id}
- description: Update a group
  method: PUT
  name: updategroup
  path: /groups/{group_id}
- description: Delete a group
  method: DELETE
  name: deletegroup
  path: /groups/{group_id}
- description: List all roles
  method: GET
  name: listroles
  path: /roles
- description: View a role
  method: GET
  name: getrole
  path: /roles/{role_id}
- description: List all products
  method: GET
  name: listproducts
  path: /products
- description: View a product
  method: GET
  name: getproduct
  path: /products/{product_id}
- description: Update a product
  method: PUT
  name: updateproduct
  path: /products/{product_id}
- description: Create a product
  method: POST
  name: createproduct
  path: /products/{product_id}
- description: List all email configurations
  method: GET
  name: listemailconfigs
  path: /email_configs
- description: View an email configuration
  method: GET
  name: getemailconfig
  path: /email_configs/{email_config_id}
- description: List all SLA policies
  method: GET
  name: listslapolicies
  path: /sla_policies
personas: []
provider_name: freshdesk
provider_slug: freshdesk
search_terms:
- list all roles
- bulk delete tickets
- create a product
- getticket
- create an outbound email ticket
- deletetimeentry
- list conversations on a ticket
- listticketconversations
- getemailconfig
- getrole
- view a group
- createproduct
- listsatisfactionratings
- delete a conversation
- list all groups
- updatecontact
- update a group
- delete a group
- listagents
- bulkdeletetickets
- update a ticket
- toggletimer
- api
- update a contact
- create a group
- mergetickets
- updateconversation
- list time entries for a ticket
- creategroup
- delete an agent
- createtimeentry
- createcompany
- bulk update tickets
- deleteagent
- merge tickets
- createnote
- listcompanyfields
- listalltimeentries
- list all tickets
- restoreticket
- restorecontact
- watch a ticket
- createticket
- list all company fields
- create a contact
- delete a ticket
- listgroups
- list associated tickets
- listroles
- list all time entries
- updateagent
- listproducts
- listslapolicies
- forwardticket
- createsatisfactionrating
- exportcontacts
- listcompanies
- updateproduct
- getproduct
- view an email configuration
- getgroup
- listcontactfields
- list all agents
- reply to a ticket
- updategroup
- listemailconfigs
- create a satisfaction rating
- list all companies
- merge contacts
- update a company
- update a product
- toggle a timer
- list all email configurations
- deleteconversation
- listtickettimeentries
- list all products
- getcontact
- createcontact
- freshdesk
- view a role
- updateticket
- updatetimeentry
- list all satisfaction ratings
- update a time entry
- delete a company
- delete a contact
- create a time entry
- restore a deleted ticket
- replytoticket
- updatecompany
- listassociatedtickets
- forward a ticket
- listticketwatchers
- list all sla policies
- create a company
- view a contact
- deleteticket
- listcontacts
- update an agent
- create a ticket
- deletegroup
- create a note on a ticket
- getcompany
- export contacts
- createoutboundemail
- view a company
- getagent
- mergecontacts
- update a conversation
- bulkupdatetickets
- deletecompany
- view an agent
- view a product
- view a ticket
- delete a time entry
- list all contact fields
- deletecontact
- list all contacts
- listtickets
- list watchers on a ticket
- restore a deleted contact
- watchticket
slug: freshdesk-capability
source_filename: freshdesk-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Freshdesk REST API\n  description: The Freshdesk REST API (v2) provides programmatic access to helpdesk data and operations within Freshdesk,\n    a customer support platform by Freshworks. It exposes endpoints for managing tickets, contacts, companies, agents, groups,\n    conversations, products, email configurations, SLA policies, business hours, time entries, satisfaction ratings, solution\n    categories, solution folders, solution articles, and more. The API uses JSON for request and response payloads, supports\n    API key-based authentication, and follows RESTful conventions for CRUD operations.\n  tags:\n  - Freshdesk\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: freshdesk\n    baseUri: https://yourdomain.freshdesk.com/api/v2\n    description: Freshdesk REST API HTTP API.\n    authentication:\n      type: basic\n      username: '{{FRESHDESK_USERNAME}}'\n \
  \     password: '{{FRESHDESK_PASSWORD}}'\n    resources:\n    - name: tickets\n      path: /tickets\n      operations:\n      - name: listtickets\n        method: GET\n        description: List all tickets\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Pre-defined filter to apply. Options include new_and_my_open, watching, spam, deleted.\n        - name: requester_id\n          in: query\n          type: integer\n          description: Filter tickets by requester ID.\n        - name: email\n          in: query\n          type: string\n          description: Filter tickets by requester email address.\n        - name: updated_since\n          in: query\n          type: string\n          description: Return tickets updated since the given date-time in UTC format.\n        - name: order_by\n          in: query\n          type: string\n          description: Field to order results by.\n        - name: order_type\n     \
  \     in: query\n          type: string\n          description: Sort direction for results.\n        - name: include\n          in: query\n          type: string\n          description: Include additional information such as requester, stats, or description.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createticket\n        method: POST\n        description: Create a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-ticket-id\n      path: /tickets/{ticket_id}\n      operations:\n      - name: getticket\n        method: GET\n        description: View a ticket\n        inputParameters:\n        - name: include\n          in: query\n          type: string\n          description: Include additional information in the response.\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: updateticket\n        method: PUT\n        description: Update a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteticket\n        method: DELETE\n        description: Delete a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-ticket-id-restore\n      path: /tickets/{ticket_id}/restore\n      operations:\n      - name: restoreticket\n        method: PUT\n        description: Restore a deleted ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-outbound-email\n      path: /tickets/outbound_email\n      operations:\n      - name: createoutboundemail\n        method: POST\n        description: Create an\
  \ outbound email ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-ticket-id-conversations\n      path: /tickets/{ticket_id}/conversations\n      operations:\n      - name: listticketconversations\n        method: GET\n        description: List conversations on a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-ticket-id-reply\n      path: /tickets/{ticket_id}/reply\n      operations:\n      - name: replytoticket\n        method: POST\n        description: Reply to a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-ticket-id-notes\n      path: /tickets/{ticket_id}/notes\n      operations:\n      - name: createnote\n        method: POST\n        description: Create a note on\
  \ a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-ticket-id-forward\n      path: /tickets/{ticket_id}/forward\n      operations:\n      - name: forwardticket\n        method: POST\n        description: Forward a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-conversation-id\n      path: /conversations/{conversation_id}\n      operations:\n      - name: updateconversation\n        method: PUT\n        description: Update a conversation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteconversation\n        method: DELETE\n        description: Delete a conversation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: tickets-ticket-id-time-entries\n      path: /tickets/{ticket_id}/time_entries\n      operations:\n      - name: listtickettimeentries\n        method: GET\n        description: List time entries for a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtimeentry\n        method: POST\n        description: Create a time entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: time-entries\n      path: /time_entries\n      operations:\n      - name: listalltimeentries\n        method: GET\n        description: List all time entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: time-entries-time-entry-id\n      path: /time_entries/{time_entry_id}\n      operations:\n      - name:\
  \ updatetimeentry\n        method: PUT\n        description: Update a time entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetimeentry\n        method: DELETE\n        description: Delete a time entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: time-entries-time-entry-id-toggle-timer\n      path: /time_entries/{time_entry_id}/toggle_timer\n      operations:\n      - name: toggletimer\n        method: PUT\n        description: Toggle a timer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-ticket-id-satisfaction-ratings\n      path: /tickets/{ticket_id}/satisfaction_ratings\n      operations:\n      - name: createsatisfactionrating\n        method: POST\n        description: Create a satisfaction\
  \ rating\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: surveys-satisfaction-ratings\n      path: /surveys/satisfaction_ratings\n      operations:\n      - name: listsatisfactionratings\n        method: GET\n        description: List all satisfaction ratings\n        inputParameters:\n        - name: created_since\n          in: query\n          type: string\n          description: Return ratings created since the given date-time.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-ticket-id-watchers\n      path: /tickets/{ticket_id}/watchers\n      operations:\n      - name: listticketwatchers\n        method: GET\n        description: List watchers on a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ tickets-ticket-id-watch\n      path: /tickets/{ticket_id}/watch\n      operations:\n      - name: watchticket\n        method: POST\n        description: Watch a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-ticket-id-associated-tickets\n      path: /tickets/{ticket_id}/associated_tickets\n      operations:\n      - name: listassociatedtickets\n        method: GET\n        description: List associated tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-merge\n      path: /tickets/merge\n      operations:\n      - name: mergetickets\n        method: PUT\n        description: Merge tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-bulk-update\n      path: /tickets/bulk_update\n\
  \      operations:\n      - name: bulkupdatetickets\n        method: POST\n        description: Bulk update tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets-bulk-delete\n      path: /tickets/bulk_delete\n      operations:\n      - name: bulkdeletetickets\n        method: POST\n        description: Bulk delete tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /contacts\n      operations:\n      - name: listcontacts\n        method: GET\n        description: List all contacts\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          description: Filter contacts by email address.\n        - name: phone\n          in: query\n          type: string\n          description: Filter contacts by phone number.\n        - name:\
  \ mobile\n          in: query\n          type: string\n          description: Filter contacts by mobile number.\n        - name: company_id\n          in: query\n          type: integer\n          description: Filter contacts by company ID.\n        - name: state\n          in: query\n          type: string\n          description: Filter contacts by state.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontact\n        method: POST\n        description: Create a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-contact-id\n      path: /contacts/{contact_id}\n      operations:\n      - name: getcontact\n        method: GET\n        description: View a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: updatecontact\n        method: PUT\n        description: Update a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontact\n        method: DELETE\n        description: Delete a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-contact-id-restore\n      path: /contacts/{contact_id}/restore\n      operations:\n      - name: restorecontact\n        method: PUT\n        description: Restore a deleted contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-merge\n      path: /contacts/merge\n      operations:\n      - name: mergecontacts\n        method: POST\n        description: Merge contacts\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: contacts-export\n      path: /contacts/export\n      operations:\n      - name: exportcontacts\n        method: POST\n        description: Export contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contact-fields\n      path: /contact_fields\n      operations:\n      - name: listcontactfields\n        method: GET\n        description: List all contact fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies\n      path: /companies\n      operations:\n      - name: listcompanies\n        method: GET\n        description: List all companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcompany\n        method: POST\n        description:\
  \ Create a company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-company-id\n      path: /companies/{company_id}\n      operations:\n      - name: getcompany\n        method: GET\n        description: View a company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecompany\n        method: PUT\n        description: Update a company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecompany\n        method: DELETE\n        description: Delete a company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-fields\n      path: /company_fields\n      operations:\n      - name: listcompanyfields\n       \
  \ method: GET\n        description: List all company fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents\n      path: /agents\n      operations:\n      - name: listagents\n        method: GET\n        description: List all agents\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          description: Filter agents by email address.\n        - name: phone\n          in: query\n          type: string\n          description: Filter agents by phone number.\n        - name: mobile\n          in: query\n          type: string\n          description: Filter agents by mobile number.\n        - name: state\n          in: query\n          type: string\n          description: Filter agents by state.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-agent-id\n\
  \      path: /agents/{agent_id}\n      operations:\n      - name: getagent\n        method: GET\n        description: View an agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateagent\n        method: PUT\n        description: Update an agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteagent\n        method: DELETE\n        description: Delete an agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: List all groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method:\
  \ POST\n        description: Create a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-group-id\n      path: /groups/{group_id}\n      operations:\n      - name: getgroup\n        method: GET\n        description: View a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n        method: PUT\n        description: Update a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: Delete a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /roles\n      operations:\n      - name: listroles\n        method: GET\n        description:\
  \ List all roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles-role-id\n      path: /roles/{role_id}\n      operations:\n      - name: getrole\n        method: GET\n        description: View a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      operations:\n      - name: listproducts\n        method: GET\n        description: List all products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-product-id\n      path: /products/{product_id}\n      operations:\n      - name: getproduct\n        method: GET\n        description: View a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: updateproduct\n        method: PUT\n        description: Update a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproduct\n        method: POST\n        description: Create a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: email-configs\n      path: /email_configs\n      operations:\n      - name: listemailconfigs\n        method: GET\n        description: List all email configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: email-configs-email-config-id\n      path: /email_configs/{email_config_id}\n      operations:\n      - name: getemailconfig\n        method: GET\n        description: View an email configuration\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: sla-policies\n      path: /sla_policies\n      operations:\n      - name: listslapolicies\n        method: GET\n        description: List all SLA policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: freshdesk-rest\n    description: REST adapter for Freshdesk REST API.\n    resources:\n    - path: /tickets\n      name: listtickets\n      operations:\n      - method: GET\n        name: listtickets\n        description: List all tickets\n        call: freshdesk.listtickets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets\n      name: createticket\n      operations:\n      - method: POST\n        name: createticket\n        description: Create a ticket\n        call: freshdesk.createticket\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}\n      name: getticket\n      operations:\n      - method: GET\n        name: getticket\n        description: View a ticket\n        call: freshdesk.getticket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}\n      name: updateticket\n      operations:\n      - method: PUT\n        name: updateticket\n        description: Update a ticket\n        call: freshdesk.updateticket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}\n      name: deleteticket\n      operations:\n      - method: DELETE\n        name: deleteticket\n        description: Delete a ticket\n        call: freshdesk.deleteticket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/restore\n      name: restoreticket\n      operations:\n      - method: PUT\n        name: restoreticket\n\
  \        description: Restore a deleted ticket\n        call: freshdesk.restoreticket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/outbound_email\n      name: createoutboundemail\n      operations:\n      - method: POST\n        name: createoutboundemail\n        description: Create an outbound email ticket\n        call: freshdesk.createoutboundemail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/conversations\n      name: listticketconversations\n      operations:\n      - method: GET\n        name: listticketconversations\n        description: List conversations on a ticket\n        call: freshdesk.listticketconversations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/reply\n      name: replytoticket\n      operations:\n      - method: POST\n        name: replytoticket\n        description: Reply to a ticket\n  \
  \      call: freshdesk.replytoticket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/notes\n      name: createnote\n      operations:\n      - method: POST\n        name: createnote\n        description: Create a note on a ticket\n        call: freshdesk.createnote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/forward\n      name: forwardticket\n      operations:\n      - method: POST\n        name: forwardticket\n        description: Forward a ticket\n        call: freshdesk.forwardticket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversation_id}\n      name: updateconversation\n      operations:\n      - method: PUT\n        name: updateconversation\n        description: Update a conversation\n        call: freshdesk.updateconversation\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /conversations/{conversation_id}\n      name: deleteconversation\n      operations:\n      - method: DELETE\n        name: deleteconversation\n        description: Delete a conversation\n        call: freshdesk.deleteconversation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/time_entries\n      name: listtickettimeentries\n      operations:\n      - method: GET\n        name: listtickettimeentries\n        description: List time entries for a ticket\n        call: freshdesk.listtickettimeentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/time_entries\n      name: createtimeentry\n      operations:\n      - method: POST\n        name: createtimeentry\n        description: Create a time entry\n        call: freshdesk.createtimeentry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /time_entries\n      name:\
  \ listalltimeentries\n      operations:\n      - method: GET\n        name: listalltimeentries\n        description: List all time entries\n        call: freshdesk.listalltimeentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /time_entries/{time_entry_id}\n      name: updatetimeentry\n      operations:\n      - method: PUT\n        name: updatetimeentry\n        description: Update a time entry\n        call: freshdesk.updatetimeentry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /time_entries/{time_entry_id}\n      name: deletetimeentry\n      operations:\n      - method: DELETE\n        name: deletetimeentry\n        description: Delete a time entry\n        call: freshdesk.deletetimeentry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /time_entries/{time_entry_id}/toggle_timer\n      name: toggletimer\n      operations:\n      - method: PUT\n        name: toggletimer\n\
  \        description: Toggle a timer\n        call: freshdesk.toggletimer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/satisfaction_ratings\n      name: createsatisfactionrating\n      operations:\n      - method: POST\n        name: createsatisfactionrating\n        description: Create a satisfaction rating\n        call: freshdesk.createsatisfactionrating\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /surveys/satisfaction_ratings\n      name: listsatisfactionratings\n      operations:\n      - method: GET\n        name: listsatisfactionratings\n        description: List all satisfaction ratings\n        call: freshdesk.listsatisfactionratings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/watchers\n      name: listticketwatchers\n      operations:\n      - method: GET\n        name: listticketwatchers\n        description:\
  \ List watchers on a ticket\n        call: freshdesk.listticketwatchers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/watch\n      name: watchticket\n      operations:\n      - method: POST\n        name: watchticket\n        description: Watch a ticket\n        call: freshdesk.watchticket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/{ticket_id}/associated_tickets\n      name: listassociatedtickets\n      operations:\n      - method: GET\n        name: listassociatedtickets\n        description: List associated tickets\n        call: freshdesk.listassociatedtickets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/merge\n      name: mergetickets\n      operations:\n      - method: PUT\n        name: mergetickets\n        description: Merge tickets\n        call: freshdesk.mergetickets\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /tickets/bulk_update\n      name: bulkupdatetickets\n      operations:\n      - method: POST\n        name: bulkupdatetickets\n        description: Bulk update tickets\n        call: freshdesk.bulkupdatetickets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tickets/bulk_delete\n      name: bulkdeletetickets\n      operations:\n      - method: POST\n        name: bulkdeletetickets\n        description: Bulk delete tickets\n        call: freshdesk.bulkdeletetickets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: listcontacts\n      operations:\n      - method: GET\n        name: listcontacts\n        description: List all contacts\n        call: freshdesk.listcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: createcontact\n      operations:\n      - method: POST\n        name: createcontact\n\
  \        description: Create a contact\n        call: freshdesk.createcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{contact_id}\n      name: getcontact\n      operations:\n      - method: GET\n        name: getcontact\n        description: View a contact\n        call: freshdesk.getcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{contact_id}\n      name: updatecontact\n      operations:\n      - method: PUT\n        name: updatecontact\n        description: Update a contact\n        call: freshdesk.updatecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{contact_id}\n      name: deletecontact\n      operations:\n      - method: DELETE\n        name: deletecontact\n        description: Delete a contact\n        call: freshdesk.deletecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /contacts/{contact_id}/restore\n      name: restorecontact\n      operations:\n      - method: PUT\n        name: restorecontact\n        description: Restore a deleted contact\n        call: freshdesk.restorecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/merge\n      name: mergecontacts\n      operations:\n      - method: POST\n        name: mergecontacts\n        description: Merge contacts\n        call: freshdesk.mergecontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/export\n      name: exportcontacts\n      operations:\n      - method: POST\n        name: exportcontacts\n        description: Export contacts\n        call: freshdesk.exportcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contact_fields\n      name: listcontactfields\n      operations:\n      - method: GET\n        name: listcontactfields\n      \
  \  description: List all contact fields\n        call: freshdesk.listcontactfields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies\n      name: listcompanies\n      operations:\n      - method: GET\n        name: listcompanies\n        description: List all companies\n        call: freshdesk.listcompanies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies\n      name: createcompany\n      operations:\n      - method: POST\n        name: createcompany\n        description: Create a company\n        call: freshdesk.createcompany\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies/{company_id}\n      name: getcompany\n      operations:\n      - method: GET\n        name: getcompany\n        description: View a company\n        call: freshdesk.getcompany\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies/{company_id}\n\
  \      name: updatecompany\n      operations:\n      - method: PUT\n        name: updatecompany\n        description: Update a company\n        call: freshdesk.updatecompany\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies/{company_id}\n      name: deletecompany\n      operations:\n      - method: DELETE\n        name: deletecompany\n        description: Delete a company\n        call: freshdesk.deletecompany\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /company_fields\n      name: listcompanyfields\n      operations:\n      - method: GET\n        name: listcompanyfields\n        description: List all company fields\n        call: freshdesk.listcompanyfields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agents\n      name: listagents\n      operations:\n      - method: GET\n        name: listagents\n        description: List all agents\n        call: freshdesk.listagents\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agents/{agent_id}\n      name: getagent\n      operations:\n      - method: GET\n        name: getagent\n        description: View an agent\n        call: freshdesk.getagent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agents/{agent_id}\n      name: updateagent\n      operations:\n      - method: PUT\n        name: updateagent\n        description: Update an agent\n        call: freshdesk.updateagent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agents/{agent_id}\n      name: deleteagent\n      operations:\n      - method: DELETE\n        name: deleteagent\n        description: Delete an agent\n        call: freshdesk.deleteagent\n        outputParameters:\n        - type: object\n          \n\n# --- truncated at 32 KB (53 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/freshdesk/refs/heads/main/capabilities/freshdesk-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/freshdesk/refs/heads/main/capabilities/freshdesk-capability.yaml
tags:
- Freshdesk
- API
tools:
- description: List all tickets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtickets
- description: Create a ticket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createticket
- description: View a ticket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getticket
- description: Update a ticket
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateticket
- description: Delete a ticket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteticket
- description: Restore a deleted ticket
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: restoreticket
- description: Create an outbound email ticket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createoutboundemail
- description: List conversations on a ticket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listticketconversations
- description: Reply to a ticket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: replytoticket
- description: Create a note on a ticket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnote
- description: Forward a ticket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: forwardticket
- description: Update a conversation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateconversation
- description: Delete a conversation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconversation
- description: List time entries for a ticket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtickettimeentries
- description: Create a time entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtimeentry
- description: List all time entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalltimeentries
- description: Update a time entry
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetimeentry
- description: Delete a time entry
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetimeentry
- description: Toggle a timer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: toggletimer
- description: Create a satisfaction rating
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsatisfactionrating
- description: List all satisfaction ratings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsatisfactionratings
- description: List watchers on a ticket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listticketwatchers
- description: Watch a ticket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: watchticket
- description: List associated tickets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassociatedtickets
- description: Merge tickets
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: mergetickets
- description: Bulk update tickets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulkupdatetickets
- description: Bulk delete tickets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulkdeletetickets
- description: List all contacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontacts
- description: Create a contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontact
- description: View a contact
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontact
- description: Update a contact
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontact
- description: Delete a contact
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontact
- description: Restore a deleted contact
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: restorecontact
- description: Merge contacts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mergecontacts
- description: Export contacts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exportcontacts
- description: List all contact fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactfields
- description: List all companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcompanies
- description: Create a company
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcompany
- description: View a company
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompany
- description: Update a company
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecompany
- description: Delete a company
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecompany
- description: List all company fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcompanyfields
- description: List all agents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagents
- description: View an agent
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getagent
- description: Update an agent
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateagent
- description: Delete an agent
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteagent
- description: List all groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Create a group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: View a group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: Update a group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroup
- description: Delete a group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: List all roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: View a role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: List all products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: View a product
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproduct
- description: Update a product
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproduct
- description: Create a product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproduct
- description: List all email configurations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listemailconfigs
- description: View an email configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailconfig
- description: List all SLA policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listslapolicies
---
