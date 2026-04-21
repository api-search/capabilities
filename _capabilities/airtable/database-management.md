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
- no-code
- database
- creating, reading, updating, and deleting data records.
- update specific fields in an airtable record.
- airtable bases and schemas.
- delete record
- delete a record.
- create records
- data
- a specific airtable record.
- create records in a table.
- user management, audit logs, and access control.
- Developer
- list all airtable bases the user has access to.
- real-time event-driven integrations via webhooks.
- collaboration
- airtable
- records
- list all accessible bases.
- managing the structure of bases, tables, and fields.
- update a record.
- read/write airtable records, browse schemas, manage webhooks. used by developers and data teams integrating airtable with external systems.
- list records from an airtable table with optional filtering.
- Data Analyst
- reads and analyzes airtable data programmatically.
- airtable table records.
- get the schema of an airtable base with all tables and fields.
- productivity
- integrates airtable with external systems via the rest api.
- list records from a table.
- schema
- applications
- delete an airtable record permanently.
- create one or more records in an airtable table.
- databases
- manages users, audit logs, and shares across the organization.
- list bases
- list records
- update record
- low-code
- spreadsheets
- get base schema
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
