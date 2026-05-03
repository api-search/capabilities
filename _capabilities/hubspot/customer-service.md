---
categories:
- crm-sales
consumed_apis:
- crm-tickets
- conversations
- crm-contacts
- crm-associations
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
- get a support ticket by id
- hubspot
- support tickets
- create association
- search contacts to find the customer
- associate a ticket with a contact or company
- contact lookup
- get contact
- service
- conversations
- marketing automation
- sales
- look up a contact for ticket context
- commerce
- customer service
- create ticket
- update ticket
- individual ticket
- get ticket
- content
- crm
- list associations for a crm object
- search contacts
- marketing
- search tickets
- operations
- archive ticket
- analytics
- update a support ticket
- support
- email marketing
- search tickets with filters
- list associations
- list all support tickets
- tickets
- archive a support ticket
- create a new support ticket
- list tickets
slug: customer-service
source_filename: customer-service.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"HubSpot Customer Service\"\n  description: \"Unified workflow for service agents to manage support tickets, conversations, threads, messages, and CRM associations. Combines ticket management with conversation channels for complete customer service operations.\"\n  tags:\n    - HubSpot\n    - Service\n    - Support\n    - Tickets\n    - Conversations\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: crm-tickets\n      location: ./shared/crm-tickets.yaml\n    - import: conversations\n      location: ./shared/conversations-api.yaml\n    - import: crm-contacts\n      location: ./shared/crm-contacts.yaml\n    - import: crm-associations\n      location: ./shared/crm-associations.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: customer-service-api\n      description: \"Unified\
  \ REST API for customer service ticket management, conversations, and contact resolution.\"\n      resources:\n        - path: /v1/tickets\n          name: tickets\n          description: \"Support tickets\"\n          operations:\n            - { method: GET, name: list-tickets, description: \"List tickets\", call: \"crm-tickets.list-tickets\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: POST, name: create-ticket, description: \"Create ticket\", call: \"crm-tickets.create-ticket\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - path: /v1/tickets/{ticketId}\n          name: ticket-by-id\n          description: \"Individual ticket\"\n          operations:\n            - { method: GET, name: get-ticket, description: \"Get ticket\", call: \"crm-tickets.get-ticket\", with: { ticketId: \"rest.ticketId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: PATCH, name: update-ticket, description: \"Update\
  \ ticket\", call: \"crm-tickets.update-ticket\", with: { ticketId: \"rest.ticketId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - path: /v1/contacts/{contactId}\n          name: contact-by-id\n          description: \"Contact lookup\"\n          operations:\n            - { method: GET, name: get-contact, description: \"Get contact\", call: \"crm-contacts.get-contact\", with: { contactId: \"rest.contactId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n\n    - type: mcp\n      port: 9092\n      namespace: customer-service-mcp\n      transport: http\n      description: \"MCP server for AI-assisted customer service, ticket resolution, and conversation management.\"\n      tools:\n        - { name: list-tickets, description: \"List all support tickets\", hints: { readOnly: true, idempotent: true }, call: \"crm-tickets.list-tickets\", with: { limit: \"tools.limit\", after: \"tools.after\", properties: \"tools.properties\" }, outputParameters: [{ type:\
  \ object, mapping: \"$.\" }] }\n        - { name: get-ticket, description: \"Get a support ticket by ID\", hints: { readOnly: true, idempotent: true }, call: \"crm-tickets.get-ticket\", with: { ticketId: \"tools.ticketId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-ticket, description: \"Create a new support ticket\", hints: { readOnly: false }, call: \"crm-tickets.create-ticket\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: update-ticket, description: \"Update a support ticket\", hints: { readOnly: false, idempotent: true }, call: \"crm-tickets.update-ticket\", with: { ticketId: \"tools.ticketId\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: archive-ticket, description: \"Archive a support ticket\", hints: { readOnly: false, destructive: true, idempotent: true }, call: \"crm-tickets.archive-ticket\", with:\
  \ { ticketId: \"tools.ticketId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: search-tickets, description: \"Search tickets with filters\", hints: { readOnly: true, idempotent: true }, call: \"crm-tickets.search-tickets\", with: { filterGroups: \"tools.filterGroups\", query: \"tools.query\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-contact, description: \"Look up a contact for ticket context\", hints: { readOnly: true, idempotent: true }, call: \"crm-contacts.get-contact\", with: { contactId: \"tools.contactId\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: search-contacts, description: \"Search contacts to find the customer\", hints: { readOnly: true, idempotent: true }, call: \"crm-contacts.search-contacts\", with: { filterGroups: \"tools.filterGroups\", query: \"tools.query\" }, outputParameters: [{ type: object,\
  \ mapping: \"$.\" }] }\n        - { name: list-associations, description: \"List associations for a CRM object\", hints: { readOnly: true, idempotent: true }, call: \"crm-associations.list-associations\", with: { fromObjectType: \"tools.fromObjectType\", fromObjectId: \"tools.fromObjectId\", toObjectType: \"tools.toObjectType\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-association, description: \"Associate a ticket with a contact or company\", hints: { readOnly: false, idempotent: true }, call: \"crm-associations.create-association\", with: { fromObjectType: \"tools.fromObjectType\", fromObjectId: \"tools.fromObjectId\", toObjectType: \"tools.toObjectType\", to: \"tools.to\", types: \"tools.types\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n"
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
