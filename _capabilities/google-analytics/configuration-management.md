---
categories: []
consumed_apis:
- ga-admin-api
description: Unified workflow for managing GA4 property configuration including accounts, properties, data streams, custom dimensions and metrics, conversion events, and integration links. Used by analytics administrators and platform engineers to set up and maintain GA4 properties.
layout: capability
name: Google Analytics Configuration Management
operations:
- description: List all accessible accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: List summaries of all accessible accounts
  method: GET
  name: list-account-summaries
  path: /v1/account-summaries
- description: List GA4 properties
  method: GET
  name: list-properties
  path: /v1/properties
- description: Create a GA4 property
  method: POST
  name: create-property
  path: /v1/properties
- description: List data streams on a property
  method: GET
  name: list-data-streams
  path: /v1/data-streams
- description: Create a data stream
  method: POST
  name: create-data-stream
  path: /v1/data-streams
- description: List custom dimensions
  method: GET
  name: list-custom-dimensions
  path: /v1/custom-dimensions
- description: Create a custom dimension
  method: POST
  name: create-custom-dimension
  path: /v1/custom-dimensions
- description: List custom metrics
  method: GET
  name: list-custom-metrics
  path: /v1/custom-metrics
- description: Create a custom metric
  method: POST
  name: create-custom-metric
  path: /v1/custom-metrics
- description: List conversion events
  method: GET
  name: list-conversion-events
  path: /v1/conversion-events
- description: Create a conversion event
  method: POST
  name: create-conversion-event
  path: /v1/conversion-events
- description: Search through account changes
  method: POST
  name: search-change-history-events
  path: /v1/change-history
personas:
- description: Sets up and maintains GA4 accounts, properties, and configurations.
  id: analytics-administrator
  name: Analytics Administrator
- description: Integrates GA4 with other platforms and manages infrastructure.
  id: platform-engineer
  name: Platform Engineer
provider_name: Google Analytics
provider_slug: google-analytics
search_terms:
- privacy officer
- list data streams
- user data deletion, access auditing, and data collection acknowledgement.
- reporting
- querying and analyzing ga4 event data through various report types.
- data protection engineer
- connects advertising platforms and implements server-side tracking.
- ingesting events from servers, apps, and offline sources.
- list all accessible google analytics accounts
- builds automated reporting pipelines and dashboards from ga4 data.
- create, export, and query ga4 audience segments.
- list ga4 properties for an account
- connecting ga4 with advertising, app, and measurement platforms.
- search change history events
- server-side event tracking with data stream and secret management.
- integrates ga4 with other platforms and manages infrastructure.
- create a custom dimension on a property
- platform engineer
- acknowledge terms of user data collection for a property
- create a new ga4 property
- bi engineer
- attribution
- list custom metrics on a property
- google analytics
- sets up and maintains ga4 accounts, properties, and configurations.
- create data stream
- admin
- implements privacy-compliant data handling and deletion workflows.
- managing data privacy, deletion, and access auditing.
- search through all changes to an account or its children
- acknowledge user data collection
- extracts insights from ga4 data through reports and explorations.
- create custom dimension
- list properties
- compliance team
- create custom metric
- measures campaign performance, segments audiences, and tracks conversions.
- manage data streams
- archive a custom metric on a property
- manage conversion events
- create property
- list custom metrics
- manage custom dimensions
- audits data access and monitors configuration changes.
- backend engineer
- manages data privacy compliance including gdpr deletion requests.
- configuration
- create a conversion event on a property
- manage ga4 accounts
- marketing ops
- machine learning
- manage ga4 properties
- create a custom metric on a property
- data analyst
- view account summaries
- list conversion events on a property
- setting up and maintaining ga4 account and property structure.
- create a conversion event
- list conversion events
- list account summaries
- search change history
- metrics
- web analytics
- archive custom metric
- manage custom metrics
- management
- segmenting and exporting user populations for analysis and activation.
- google
- create a custom dimension
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- provision account ticket
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- request a ticket for creating a new account
- create a new data stream on a property
- list custom dimensions
- list custom dimensions on a property
- run standard, realtime, pivot, and batch reports with data access auditing.
- search through account changes
- create conversion event
- list all accessible accounts
- create a custom metric
- implements server-side event tracking and offline data collection.
- data
- analytics
- list summaries of all accessible accounts
- analytics administrator
- create a ga4 property
- marketing team
- list summaries of all accessible accounts with their properties
- create a data stream
- list accounts
- list ga4 properties
- list data streams on a property
- ga4
slug: configuration-management
source_filename: configuration-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Analytics Configuration Management\"\n  description: \"Unified workflow for managing GA4 property configuration including accounts, properties, data streams, custom dimensions and metrics, conversion events, and integration links. Used by analytics administrators and platform engineers to set up and maintain GA4 properties.\"\n  tags:\n    - Google Analytics\n    - Configuration\n    - Admin\n    - Management\n    - GA4\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ANALYTICS_ACCESS_TOKEN: GOOGLE_ANALYTICS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: ga-admin-api\n      location: ./shared/admin-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: ga-config-api\n      description: \"Unified REST API for Google Analytics configuration management.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n   \
  \       description: \"Manage GA4 accounts\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List all accessible accounts\"\n              call: \"ga-admin-api.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/account-summaries\n          name: account-summaries\n          description: \"View account summaries\"\n          operations:\n            - method: GET\n              name: list-account-summaries\n              description: \"List summaries of all accessible accounts\"\n              call: \"ga-admin-api.list-account-summaries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/properties\n          name: properties\n          description: \"Manage GA4 properties\"\n          operations:\n            - method: GET\n              name: list-properties\n    \
  \          description: \"List GA4 properties\"\n              call: \"ga-admin-api.list-properties\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-property\n              description: \"Create a GA4 property\"\n              call: \"ga-admin-api.create-property\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-streams\n          name: data-streams\n          description: \"Manage data streams\"\n          operations:\n            - method: GET\n              name: list-data-streams\n              description: \"List data streams on a property\"\n              call: \"ga-admin-api.list-data-streams\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n            \
  \  name: create-data-stream\n              description: \"Create a data stream\"\n              call: \"ga-admin-api.create-data-stream\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/custom-dimensions\n          name: custom-dimensions\n          description: \"Manage custom dimensions\"\n          operations:\n            - method: GET\n              name: list-custom-dimensions\n              description: \"List custom dimensions\"\n              call: \"ga-admin-api.list-custom-dimensions\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-custom-dimension\n              description: \"Create a custom dimension\"\n              call: \"ga-admin-api.create-custom-dimension\"\n      \
  \        with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/custom-metrics\n          name: custom-metrics\n          description: \"Manage custom metrics\"\n          operations:\n            - method: GET\n              name: list-custom-metrics\n              description: \"List custom metrics\"\n              call: \"ga-admin-api.list-custom-metrics\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-custom-metric\n              description: \"Create a custom metric\"\n              call: \"ga-admin-api.create-custom-metric\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/conversion-events\n          name: conversion-events\n          description: \"Manage conversion events\"\n          operations:\n            - method: GET\n              name: list-conversion-events\n              description: \"List conversion events\"\n              call: \"ga-admin-api.list-conversion-events\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-conversion-event\n              description: \"Create a conversion event\"\n              call: \"ga-admin-api.create-conversion-event\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/change-history\n          name: change-history\n          description: \"Search change history\"\n          operations:\n            - method:\
  \ POST\n              name: search-change-history-events\n              description: \"Search through account changes\"\n              call: \"ga-admin-api.search-change-history-events\"\n              with:\n                account: \"rest.account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: ga-config-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Analytics configuration management.\"\n      tools:\n        - name: list-accounts\n          description: \"List all accessible Google Analytics accounts\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-account-summaries\n          description: \"List summaries of all accessible accounts with their properties\"\n\
  \          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-account-summaries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: provision-account-ticket\n          description: \"Request a ticket for creating a new account\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.provision-account-ticket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-properties\n          description: \"List GA4 properties for an account\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-properties\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-property\n          description: \"Create a new GA4 property\"\n          hints:\n            readOnly: false\n\
  \            idempotent: false\n          call: \"ga-admin-api.create-property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-streams\n          description: \"List data streams on a property\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-data-streams\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-data-stream\n          description: \"Create a new data stream on a property\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.create-data-stream\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-custom-dimensions\n          description: \"List custom dimensions\
  \ on a property\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-custom-dimensions\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-custom-dimension\n          description: \"Create a custom dimension on a property\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.create-custom-dimension\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-custom-metrics\n          description: \"List custom metrics on a property\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-custom-metrics\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n        - name: create-custom-metric\n          description: \"Create a custom metric on a property\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.create-custom-metric\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: archive-custom-metric\n          description: \"Archive a custom metric on a property\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ga-admin-api.archive-custom-metric\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-conversion-events\n          description: \"List conversion events on a property\"\n          hints:\n            readOnly: true\n    \
  \        idempotent: true\n          call: \"ga-admin-api.list-conversion-events\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-conversion-event\n          description: \"Create a conversion event on a property\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.create-conversion-event\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-change-history-events\n          description: \"Search through all changes to an account or its children\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.search-change-history-events\"\n          with:\n            account: \"tools.account\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: acknowledge-user-data-collection\n          description: \"Acknowledge terms of user data collection for a property\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"ga-admin-api.acknowledge-user-data-collection\"\n          with:\n            property: \"tools.property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-analytics/refs/heads/main/capabilities/configuration-management.yaml
tags:
- Google Analytics
- Configuration
- Admin
- Management
- GA4
tools:
- description: List all accessible Google Analytics accounts
  hints:
    idempotent: true
    readOnly: true
  name: list-accounts
- description: List summaries of all accessible accounts with their properties
  hints:
    idempotent: true
    readOnly: true
  name: list-account-summaries
- description: Request a ticket for creating a new account
  hints:
    idempotent: false
    readOnly: false
  name: provision-account-ticket
- description: List GA4 properties for an account
  hints:
    idempotent: true
    readOnly: true
  name: list-properties
- description: Create a new GA4 property
  hints:
    idempotent: false
    readOnly: false
  name: create-property
- description: List data streams on a property
  hints:
    idempotent: true
    readOnly: true
  name: list-data-streams
- description: Create a new data stream on a property
  hints:
    idempotent: false
    readOnly: false
  name: create-data-stream
- description: List custom dimensions on a property
  hints:
    idempotent: true
    readOnly: true
  name: list-custom-dimensions
- description: Create a custom dimension on a property
  hints:
    idempotent: false
    readOnly: false
  name: create-custom-dimension
- description: List custom metrics on a property
  hints:
    idempotent: true
    readOnly: true
  name: list-custom-metrics
- description: Create a custom metric on a property
  hints:
    idempotent: false
    readOnly: false
  name: create-custom-metric
- description: Archive a custom metric on a property
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: archive-custom-metric
- description: List conversion events on a property
  hints:
    idempotent: true
    readOnly: true
  name: list-conversion-events
- description: Create a conversion event on a property
  hints:
    idempotent: false
    readOnly: false
  name: create-conversion-event
- description: Search through all changes to an account or its children
  hints:
    idempotent: true
    readOnly: true
  name: search-change-history-events
- description: Acknowledge terms of user data collection for a property
  hints:
    idempotent: true
    readOnly: false
  name: acknowledge-user-data-collection
---
