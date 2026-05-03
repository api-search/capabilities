---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Clio
operations: []
personas: []
provider_name: Clio
provider_slug: clio
search_terms:
- document management
- law firms
- oauth 2.0
- calendaring
- time tracking
- legal
- trust accounting
- practice management
- billing
- matter management
slug: clio
source_filename: clio.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko capabilities profile for Clio.\n# Capabilities map verbs against the high-value operations in the\n# Clio Manage API v4 (https://docs.developers.clio.com/).\nprovider: clio\nname: Clio\ndescription: >-\n  Clio is a cloud-based legal practice management platform. These\n  capabilities cover matter management, contacts, time tracking,\n  billing, trust accounting, calendaring, tasks, documents, and\n  webhooks across the Clio Manage API v4.\ncapabilities:\n  - id: clio.matters.list\n    name: List matters\n    description: Return matters with paging, filtering, and sparse fieldsets.\n    api: clio:manage-api-v4\n    operationRef: openapi/clio-manage-api-v4-openapi.yml#/paths/~1matters/get\n    inputs:\n      - page\n      - limit\n      - fields\n      - status\n      - client_id\n      - updated_since\n    outputs:\n      - data\n      - meta\n\n  - id: clio.matters.create\n    name: Create matter\n    description: Create a new matter for an existing client contact.\n\
  \    api: clio:manage-api-v4\n    operationRef: openapi/clio-manage-api-v4-openapi.yml#/paths/~1matters/post\n    inputs:\n      - description\n      - client\n      - status\n      - open_date\n      - practice_area\n    outputs:\n      - id\n      - display_number\n\n  - id: clio.contacts.list\n    name: List contacts\n    description: Return contacts (people and companies) with filtering and paging.\n    api: clio:manage-api-v4\n    operationRef: openapi/clio-manage-api-v4-openapi.yml#/paths/~1contacts/get\n    inputs:\n      - page\n      - limit\n      - fields\n      - type\n      - query\n    outputs:\n      - data\n      - meta\n\n  - id: clio.activities.create\n    name: Log a time or expense activity\n    description: Create a billable or non-billable activity entry on a matter.\n    api: clio:manage-api-v4\n    operationRef: openapi/clio-manage-api-v4-openapi.yml#/paths/~1activities/post\n    inputs:\n      - type\n      - date\n      - quantity_in_seconds\n      - rate\n  \
  \    - matter_id\n      - user_id\n      - note\n      - billable\n    outputs:\n      - id\n\n  - id: clio.bills.list\n    name: List bills\n    description: Return bills with paging and state filters.\n    api: clio:manage-api-v4\n    operationRef: openapi/clio-manage-api-v4-openapi.yml#/paths/~1bills/get\n    inputs:\n      - page\n      - limit\n      - state\n      - client_id\n      - matter_id\n    outputs:\n      - data\n      - meta\n\n  - id: clio.calendar-entries.create\n    name: Create calendar entry\n    description: Create an event on a Clio calendar.\n    api: clio:manage-api-v4\n    operationRef: openapi/clio-manage-api-v4-openapi.yml#/paths/~1calendar_entries/post\n    inputs:\n      - calendar_owner\n      - summary\n      - description\n      - start_at\n      - end_at\n      - matter_id\n    outputs:\n      - id\n\n  - id: clio.tasks.create\n    name: Create task\n    description: Create a task on a matter or for a user.\n    api: clio:manage-api-v4\n    operationRef:\
  \ openapi/clio-manage-api-v4-openapi.yml#/paths/~1tasks/post\n    inputs:\n      - name\n      - description\n      - due_at\n      - assignee\n      - matter_id\n      - priority\n    outputs:\n      - id\n\n  - id: clio.documents.upload\n    name: Upload a document\n    description: Upload a document and attach it to a matter.\n    api: clio:manage-api-v4\n    operationRef: openapi/clio-manage-api-v4-openapi.yml#/paths/~1documents/post\n    inputs:\n      - filename\n      - content\n      - matter_id\n      - description\n    outputs:\n      - id\n\n  - id: clio.trust-accounts.list\n    name: List trust accounts\n    description: Return trust accounts and balances.\n    api: clio:manage-api-v4\n    operationRef: openapi/clio-manage-api-v4-openapi.yml#/paths/~1trust_accounts/get\n    inputs:\n      - page\n      - limit\n    outputs:\n      - data\n      - meta\n\n  - id: clio.webhooks.subscribe\n    name: Create webhook subscription\n    description: Subscribe an external URL to Clio\
  \ resource events.\n    api: clio:manage-api-v4\n    operationRef: openapi/clio-manage-api-v4-openapi.yml#/paths/~1webhooks/post\n    inputs:\n      - url\n      - model\n      - events\n      - shared_secret\n    outputs:\n      - id\n\n  - id: clio.events.matter-updated\n    name: Matter updated event\n    description: Webhook event fired when a matter changes.\n    api: clio:webhooks\n    operationRef: asyncapi/clio-webhooks-asyncapi.yml#/channels/matter-updated\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/clio/refs/heads/main/capabilities/clio.yaml
tags: []
tools: []
---
