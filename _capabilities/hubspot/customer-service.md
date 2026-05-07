---
categories:
- crm-sales
consumed_apis: []
description: Unified workflow for service agents to manage support tickets, conversations, threads, messages, and CRM associations. Combines ticket management with conversation channels for complete customer service operations.
layout: capability
name: HubSpot Customer Service
operations:
- description: List tickets
  method: GET
  name: list-tickets
  path: /v1/tickets
- description: Create ticket
  method: POST
  name: create-ticket
  path: /v1/tickets
- description: Get ticket
  method: GET
  name: get-ticket
  path: /v1/tickets/{ticketId}
- description: Update ticket
  method: PATCH
  name: update-ticket
  path: /v1/tickets/{ticketId}
- description: Get contact
  method: GET
  name: get-contact
  path: /v1/contacts/{contactId}
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- analytics
- hubspot
- list tickets
- archive a support ticket
- list associations for a crm object
- conversations
- operations
- tickets
- get contact
- update ticket
- support
- search tickets with filters
- search tickets
- service
- create a new support ticket
- search contacts to find the customer
- crm
- content
- list all support tickets
- update a support ticket
- look up a contact for ticket context
- list associations
- contact lookup
- create association
- marketing
- create ticket
- archive ticket
- sales
- search contacts
- get ticket
- associate a ticket with a contact or company
- individual ticket
- customer service
- get a support ticket by id
- marketing automation
- commerce
- support tickets
- email marketing
slug: customer-service
source_filename: customer-service.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot Customer Service\n  description: Unified workflow for service agents to manage support tickets, conversations, threads, messages, and CRM associations.\n    Combines ticket management with conversation channels for complete customer service operations.\n  tags:\n  - HubSpot\n  - Service\n  - Support\n  - Tickets\n  - Conversations\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: crm-tickets\n    baseUri: https://api.hubapi.com\n    description: HubSpot CRM Tickets API for managing support ticket records.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: tickets\n      path: /crm/v3/objects/tickets\n      description: Ticket records\n      operations:\n      - name: list-tickets\n        method: GET\n        description: List all\
  \ tickets\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ticket\n        method: POST\n        description: Create a ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: ticket-by-id\n      path: /crm/v3/objects/tickets/{ticketId}\n      description:\
  \ Individual ticket\n      operations:\n      - name: get-ticket\n        method: GET\n        description: Get a ticket by ID\n        inputParameters:\n        - name: ticketId\n          in: path\n          type: string\n          required: true\n          description: Ticket ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ticket\n        method: PATCH\n        description: Update a ticket\n        inputParameters:\n        - name: ticketId\n          in: path\n          type: string\n          required: true\n          description: Ticket ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-ticket\n        method: DELETE\n        description: Archive a ticket\n        inputParameters:\n\
  \        - name: ticketId\n          in: path\n          type: string\n          required: true\n          description: Ticket ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /crm/v3/objects/tickets/search\n      description: Search tickets\n      operations:\n      - name: search-tickets\n        method: POST\n        description: Search tickets with filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filterGroups: '{{tools.filterGroups}}'\n            query: '{{tools.query}}'\n            limit: '{{tools.limit}}'\n            properties: '{{tools.properties}}'\n  - type: http\n    namespace: conversations-api\n    baseUri: https://api.hubapi.com\n    description: \"The HubSpot Conversations API enables you to manage conversation\
  \ threads, \\nmessages, and inboxes programmatically.\\\n      \\ Use this API to query existing \\nconversations, send messages, manage thread assignmen\"\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: inboxes\n      path: /inboxes\n      description: inboxes operations\n      operations:\n      - name: listinboxes\n        method: GET\n        description: HubSpot List All Inboxes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getinboxbyid\n        method: GET\n        description: HubSpot Retrieve an Inbox\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads\n      path: /threads\n      description: threads operations\n      operations:\n      - name: listthreads\n        method: GET\n        description: HubSpot List Conversation Threads\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getthreadbyid\n        method: GET\n        description: HubSpot Retrieve a Thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatethread\n        method: PATCH\n        description: HubSpot Update a Thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: archivethread\n        method: DELETE\n        description: HubSpot Archive a Thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /messages\n      description: messages operations\n      operations:\n      - name: listthreadmessages\n        method: GET\n        description: HubSpot List Thread\
  \ Messages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sendmessage\n        method: POST\n        description: HubSpot Send a Message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getmessagebyid\n        method: GET\n        description: HubSpot Retrieve a Message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channels\n      path: /channels\n      description: channels operations\n      operations:\n      - name: listchannels\n        method: GET\n        description: HubSpot List Channels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: actors\n      path: /actors\n      description: actors operations\n      operations:\n\
  \      - name: listactors\n        method: GET\n        description: HubSpot List Actors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getactorbyid\n        method: GET\n        description: HubSpot Retrieve an Actor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: crm-contacts\n    baseUri: https://api.hubapi.com\n    description: HubSpot CRM Contacts API for managing contact records.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: contacts\n      path: /crm/v3/objects/contacts\n      description: Contact records\n      operations:\n      - name: list-contacts\n        method: GET\n        description: List all contacts\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n     \
  \     required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Comma-separated properties to return\n        - name: archived\n          in: query\n          type: boolean\n          required: false\n          description: Return archived contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: contact-by-id\n      path:\
  \ /crm/v3/objects/contacts/{contactId}\n      description: Individual contact\n      operations:\n      - name: get-contact\n        method: GET\n        description: Get a contact by ID\n        inputParameters:\n        - name: contactId\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contact\n        method: PATCH\n        description: Update a contact\n        inputParameters:\n        - name: contactId\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \    body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-contact\n        method: DELETE\n        description: Archive a contact\n        inputParameters:\n        - name: contactId\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /crm/v3/objects/contacts/search\n      description: Search contacts\n      operations:\n      - name: search-contacts\n        method: POST\n        description: Search contacts with filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filterGroups: '{{tools.filterGroups}}'\n            query: '{{tools.query}}'\n            limit: '{{tools.limit}}'\n\
  \            properties: '{{tools.properties}}'\n    - name: batch-read\n      path: /crm/v3/objects/contacts/batch/read\n      description: Batch read contacts\n      operations:\n      - name: batch-read-contacts\n        method: POST\n        description: Read multiple contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            properties: '{{tools.properties}}'\n    - name: batch-create\n      path: /crm/v3/objects/contacts/batch/create\n      description: Batch create contacts\n      operations:\n      - name: batch-create-contacts\n        method: POST\n        description: Create multiple contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n\
  \    - name: batch-archive\n      path: /crm/v3/objects/contacts/batch/archive\n      description: Batch archive contacts\n      operations:\n      - name: batch-archive-contacts\n        method: POST\n        description: Archive multiple contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n  - type: http\n    namespace: crm-associations\n    baseUri: https://api.hubapi.com\n    description: HubSpot CRM Associations API for managing relationships between CRM objects.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: object-associations\n      path: /crm/v4/objects/{fromObjectType}/{fromObjectId}/associations/{toObjectType}\n      description: Object associations\n      operations:\n      - name: list-associations\n        method: GET\n        description:\
  \ List associations for an object\n        inputParameters:\n        - name: fromObjectType\n          in: path\n          type: string\n          required: true\n          description: Source object type\n        - name: fromObjectId\n          in: path\n          type: string\n          required: true\n          description: Source object ID\n        - name: toObjectType\n          in: path\n          type: string\n          required: true\n          description: Target object type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-association\n        method: PUT\n        description: Create an association between objects\n        inputParameters:\n        - name: fromObjectType\n          in: path\n          type: string\n          required: true\n          description: Source object type\n        - name: fromObjectId\n          in: path\n          type: string\n          required: true\n\
  \          description: Source object ID\n        - name: toObjectType\n          in: path\n          type: string\n          required: true\n          description: Target object type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            to: '{{tools.to}}'\n            types: '{{tools.types}}'\n    - name: batch-read\n      path: /crm/v4/associations/{fromObjectType}/{toObjectType}/batch/read\n      description: Batch read associations\n      operations:\n      - name: batch-read-associations\n        method: POST\n        description: Read associations for multiple objects\n        inputParameters:\n        - name: fromObjectType\n          in: path\n          type: string\n          required: true\n          description: Source object type\n        - name: toObjectType\n          in: path\n          type: string\n          required: true\n      \
  \    description: Target object type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: batch-create\n      path: /crm/v4/associations/{fromObjectType}/{toObjectType}/batch/create\n      description: Batch create associations\n      operations:\n      - name: batch-create-associations\n        method: POST\n        description: Create multiple associations\n        inputParameters:\n        - name: fromObjectType\n          in: path\n          type: string\n          required: true\n          description: Source object type\n        - name: toObjectType\n          in: path\n          type: string\n          required: true\n          description: Target object type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: definitions\n      path: /crm/v4/associations/definitions\n      description: Association definitions\n      operations:\n      - name: list-definitions\n        method: GET\n        description: List all association definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: labels\n      path: /crm/v4/associations/{fromObjectType}/{toObjectType}/labels\n      description: Association labels\n      operations:\n      - name: list-labels\n        method: GET\n        description: List association labels\n        inputParameters:\n        - name: fromObjectType\n          in: path\n          type: string\n          required: true\n          description: Source object type\n        - name: toObjectType\n          in: path\n          type: string\n          required: true\n          description: Target object\
  \ type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-label\n        method: POST\n        description: Create an association label\n        inputParameters:\n        - name: fromObjectType\n          in: path\n          type: string\n          required: true\n          description: Source object type\n        - name: toObjectType\n          in: path\n          type: string\n          required: true\n          description: Target object type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            label: '{{tools.label}}'\n            name: '{{tools.name}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: customer-service-api\n    description: Unified REST API for customer service ticket management, conversations, and contact resolution.\n\
  \    resources:\n    - path: /v1/tickets\n      name: tickets\n      description: Support tickets\n      operations:\n      - method: GET\n        name: list-tickets\n        description: List tickets\n        call: crm-tickets.list-tickets\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ticket\n        description: Create ticket\n        call: crm-tickets.create-ticket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tickets/{ticketId}\n      name: ticket-by-id\n      description: Individual ticket\n      operations:\n      - method: GET\n        name: get-ticket\n        description: Get ticket\n        call: crm-tickets.get-ticket\n        with:\n          ticketId: rest.ticketId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-ticket\n        description: Update ticket\n        call: crm-tickets.update-ticket\n\
  \        with:\n          ticketId: rest.ticketId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/{contactId}\n      name: contact-by-id\n      description: Contact lookup\n      operations:\n      - method: GET\n        name: get-contact\n        description: Get contact\n        call: crm-contacts.get-contact\n        with:\n          contactId: rest.contactId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: customer-service-mcp\n    transport: http\n    description: MCP server for AI-assisted customer service, ticket resolution, and conversation management.\n    tools:\n    - name: list-tickets\n      description: List all support tickets\n      hints:\n        readOnly: true\n        idempotent: true\n      call: crm-tickets.list-tickets\n      with:\n        limit: tools.limit\n        after: tools.after\n        properties: tools.properties\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-ticket\n      description: Get a support ticket by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: crm-tickets.get-ticket\n      with:\n        ticketId: tools.ticketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ticket\n      description: Create a new support ticket\n      hints:\n        readOnly: false\n      call: crm-tickets.create-ticket\n      with:\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-ticket\n      description: Update a support ticket\n      hints:\n        readOnly: false\n        idempotent: true\n      call: crm-tickets.update-ticket\n      with:\n        ticketId: tools.ticketId\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: archive-ticket\n      description: Archive a support ticket\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: crm-tickets.archive-ticket\n      with:\n        ticketId: tools.ticketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-tickets\n      description: Search tickets with filters\n      hints:\n        readOnly: true\n        idempotent: true\n      call: crm-tickets.search-tickets\n      with:\n        filterGroups: tools.filterGroups\n        query: tools.query\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contact\n      description: Look up a contact for ticket context\n      hints:\n        readOnly: true\n        idempotent: true\n      call: crm-contacts.get-contact\n      with:\n        contactId: tools.contactId\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-contacts\n      description:\
  \ Search contacts to find the customer\n      hints:\n        readOnly: true\n        idempotent: true\n      call: crm-contacts.search-contacts\n      with:\n        filterGroups: tools.filterGroups\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-associations\n      description: List associations for a CRM object\n      hints:\n        readOnly: true\n        idempotent: true\n      call: crm-associations.list-associations\n      with:\n        fromObjectType: tools.fromObjectType\n        fromObjectId: tools.fromObjectId\n        toObjectType: tools.toObjectType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-association\n      description: Associate a ticket with a contact or company\n      hints:\n        readOnly: false\n        idempotent: true\n      call: crm-associations.create-association\n      with:\n        fromObjectType: tools.fromObjectType\n        fromObjectId: tools.fromObjectId\n\
  \        toObjectType: tools.toObjectType\n        to: tools.to\n        types: tools.types\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/customer-service.yaml
tags:
- HubSpot
- Service
- Support
- Tickets
- Conversations
tools:
- description: List all support tickets
  hints:
    idempotent: true
    readOnly: true
  name: list-tickets
- description: Get a support ticket by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-ticket
- description: Create a new support ticket
  hints:
    readOnly: false
  name: create-ticket
- description: Update a support ticket
  hints:
    idempotent: true
    readOnly: false
  name: update-ticket
- description: Archive a support ticket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: archive-ticket
- description: Search tickets with filters
  hints:
    idempotent: true
    readOnly: true
  name: search-tickets
- description: Look up a contact for ticket context
  hints:
    idempotent: true
    readOnly: true
  name: get-contact
- description: Search contacts to find the customer
  hints:
    idempotent: true
    readOnly: true
  name: search-contacts
- description: List associations for a CRM object
  hints:
    idempotent: true
    readOnly: true
  name: list-associations
- description: Associate a ticket with a contact or company
  hints:
    idempotent: true
    readOnly: false
  name: create-association
---
