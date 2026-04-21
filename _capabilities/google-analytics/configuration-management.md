---
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
- list ga4 properties for an account
- backend engineer
- create custom metric
- bi engineer
- user data deletion, access auditing, and data collection acknowledgement.
- web analytics
- google
- privacy officer
- list custom metrics
- analytics
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- create a conversion event on a property
- managing data privacy, deletion, and access auditing.
- integrates ga4 with other platforms and manages infrastructure.
- manage ga4 properties
- create property
- data
- reporting
- manage custom dimensions
- list all accessible google analytics accounts
- admin
- connects advertising platforms and implements server-side tracking.
- create a new data stream on a property
- list account summaries
- manage custom metrics
- acknowledge user data collection
- data protection engineer
- create a custom dimension
- archive custom metric
- create a ga4 property
- ga4
- search change history
- request a ticket for creating a new account
- manage ga4 accounts
- data analyst
- implements server-side event tracking and offline data collection.
- marketing ops
- create a custom metric
- create conversion event
- platform engineer
- create a custom metric on a property
- management
- create a custom dimension on a property
- run standard, realtime, pivot, and batch reports with data access auditing.
- list all accessible accounts
- view account summaries
- querying and analyzing ga4 event data through various report types.
- archive a custom metric on a property
- machine learning
- create custom dimension
- list accounts
- create a new ga4 property
- search change history events
- create a data stream
- list custom dimensions
- metrics
- builds automated reporting pipelines and dashboards from ga4 data.
- attribution
- acknowledge terms of user data collection for a property
- provision account ticket
- sets up and maintains ga4 accounts, properties, and configurations.
- extracts insights from ga4 data through reports and explorations.
- marketing team
- list properties
- list conversion events on a property
- analytics administrator
- audits data access and monitors configuration changes.
- search through all changes to an account or its children
- measures campaign performance, segments audiences, and tracks conversions.
- ingesting events from servers, apps, and offline sources.
- create a conversion event
- segmenting and exporting user populations for analysis and activation.
- list conversion events
- create data stream
- create, export, and query ga4 audience segments.
- list data streams on a property
- manage data streams
- server-side event tracking with data stream and secret management.
- list summaries of all accessible accounts with their properties
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- list summaries of all accessible accounts
- setting up and maintaining ga4 account and property structure.
- list custom metrics on a property
- google analytics
- configuration
- compliance team
- implements privacy-compliant data handling and deletion workflows.
- manages data privacy compliance including gdpr deletion requests.
- list ga4 properties
- connecting ga4 with advertising, app, and measurement platforms.
- list data streams
- manage conversion events
- search through account changes
- list custom dimensions on a property
slug: configuration-management
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
