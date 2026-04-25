---
consumed_apis:
- airtable
- airtable-meta
description: Unified workflow for managing Airtable databases — reading and writing records, browsing base schemas, managing webhooks, and administering tables. Used by developers and data teams integrating Airtable with external systems.
layout: capability
name: Airtable Database Management
operations:
- description: List all accessible bases.
  method: GET
  name: list-bases
  path: /v1/bases
- description: List records from a table.
  method: GET
  name: list-records
  path: /v1/records
- description: Create records in a table.
  method: POST
  name: create-records
  path: /v1/records
- description: Update a record.
  method: PATCH
  name: update-record
  path: /v1/records/{recordId}
- description: Delete a record.
  method: DELETE
  name: delete-record
  path: /v1/records/{recordId}
personas: []
provider_name: Airtable
provider_slug: airtable
search_terms:
- list all airtable bases the user has access to.
- create one or more records in an airtable table.
- creating, reading, updating, and deleting data records.
- low-code
- delete an airtable record permanently.
- spreadsheets
- list records from a table.
- create records
- database
- update record
- update specific fields in an airtable record.
- managing the structure of bases, tables, and fields.
- list all accessible bases.
- get base schema
- list records from an airtable table with optional filtering.
- user management, audit logs, and access control.
- productivity
- create records in a table.
- list bases
- no-code
- collaboration
- read/write airtable records, browse schemas, manage webhooks. used by developers and data teams integrating airtable with external systems.
- airtable
- update a record.
- delete a record.
- list records
- databases
- applications
- manages users, audit logs, and shares across the organization.
- Data Analyst
- airtable bases and schemas.
- get the schema of an airtable base with all tables and fields.
- schema
- delete record
- integrates airtable with external systems via the rest api.
- records
- a specific airtable record.
- Developer
- data
- real-time event-driven integrations via webhooks.
- airtable table records.
- reads and analyzes airtable data programmatically.
slug: database-management
tags:
- Airtable
- Database
- Low-Code
- No-Code
- Records
- Schema
- Collaboration
tools:
- description: List all Airtable bases the user has access to.
  hints:
    openWorld: true
    readOnly: true
  name: list-bases
- description: Get the schema of an Airtable base with all tables and fields.
  hints:
    readOnly: true
  name: get-base-schema
- description: List records from an Airtable table with optional filtering.
  hints:
    openWorld: true
    readOnly: true
  name: list-records
- description: Create one or more records in an Airtable table.
  hints:
    readOnly: false
  name: create-records
- description: Update specific fields in an Airtable record.
  hints:
    idempotent: false
    readOnly: false
  name: update-record
- description: Delete an Airtable record permanently.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-record
---
