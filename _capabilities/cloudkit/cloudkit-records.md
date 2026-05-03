---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Cloudkit Records
operations: []
personas: []
provider_name: Apple CloudKit
provider_slug: cloudkit
search_terms:
- cloud storage
- database
- sync
- web services
- apple
- cloudkit
- mobile
- icloud
slug: cloudkit-records
source_filename: cloudkit-records.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko capabilities profile for Apple CloudKit Web Services.\n# Maps verbs against the CloudKit Web Services REST surface for\n# records, zones, subscriptions, assets, and users.\nprovider: cloudkit\nname: Apple CloudKit Web Services\ndescription: >-\n  Capabilities cover record lookup/query/modify/delete in public, private,\n  and shared databases, zone management, subscription management, asset\n  upload, user info, and database change tracking. Authentication is via\n  API token (with optional ckWebAuthToken for user-authenticated access)\n  or server-to-server ECDSA key.\ncapabilities:\n  - id: cloudkit.records.lookup\n    name: Lookup records\n    description: Fetch one or more records by record name from a database.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - database\n      - record_names\n    outputs:\n      - records\n\n  - id: cloudkit.records.query\n    name: Query records\n    description: Run a typed query (recordType,\
  \ filterBy, sortBy) against a database.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - database\n      - zone_id\n      - record_type\n      - filter_by\n      - sort_by\n      - limit\n    outputs:\n      - records\n      - continuation_marker\n\n  - id: cloudkit.records.modify\n    name: Modify records\n    description: Create, update, or replace records in a database.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - database\n      - operations\n    outputs:\n      - records\n      - errors\n\n  - id: cloudkit.records.delete\n    name: Delete records\n    description: Delete one or more records by record name.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - database\n      - record_names\n    outputs:\n      - records\n\n  - id: cloudkit.zones.list\n    name: List zones\n    description: Return all zones for a database.\n    api: cloudkit:web-services\n\
  \    inputs:\n      - container\n      - environment\n      - database\n    outputs:\n      - zones\n\n  - id: cloudkit.zones.create\n    name: Create zone\n    description: Create a custom zone in the private database.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - zone_name\n    outputs:\n      - zone\n\n  - id: cloudkit.zones.delete\n    name: Delete zone\n    description: Delete a custom zone.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - zone_name\n    outputs:\n      - zone\n\n  - id: cloudkit.subscriptions.list\n    name: List subscriptions\n    description: Return subscriptions for the current user in a database.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - database\n    outputs:\n      - subscriptions\n\n  - id: cloudkit.subscriptions.create\n    name: Create subscription\n    description: Create a query, zone, or database subscription.\n\
  \    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - database\n      - subscription_id\n      - subscription_type\n      - filter_by\n    outputs:\n      - subscription\n\n  - id: cloudkit.subscriptions.delete\n    name: Delete subscription\n    description: Delete a subscription by id.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - database\n      - subscription_id\n    outputs:\n      - subscription\n\n  - id: cloudkit.assets.upload\n    name: Upload asset\n    description: Upload binary asset content for a record field.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - database\n      - record_type\n      - field_name\n      - file\n    outputs:\n      - asset\n\n  - id: cloudkit.users.current\n    name: Get current user\n    description: Return the user record name and identity for the calling token.\n    api: cloudkit:web-services\n    inputs:\n     \
  \ - container\n      - environment\n    outputs:\n      - user\n\n  - id: cloudkit.users.lookup\n    name: Lookup users\n    description: Look up user records by user record name, email, or phone.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - users\n    outputs:\n      - users\n\n  - id: cloudkit.changes.zone\n    name: Fetch zone changes\n    description: Pull incremental changes to records within a zone since a sync token.\n    api: cloudkit:web-services\n    inputs:\n      - container\n      - environment\n      - database\n      - zone_id\n      - sync_token\n    outputs:\n      - records\n      - sync_token\n      - more_coming\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudkit/refs/heads/main/capabilities/cloudkit-records.yaml
tags: []
tools: []
---
