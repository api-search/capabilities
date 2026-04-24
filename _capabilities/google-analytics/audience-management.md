---
consumed_apis:
- ga-data-api
- ga-admin-api
description: Unified workflow for creating, exporting, and analyzing GA4 audiences. Combines the Data API audience export capabilities with Admin API property configuration. Used by marketing teams and data analysts for audience segmentation, export, and activation.
layout: capability
name: Google Analytics Audience Management
operations:
- description: Create an audience export
  method: POST
  name: create-audience-export
  path: /v1/audience-exports
- description: List audience exports
  method: GET
  name: list-audience-exports
  path: /v1/audience-exports
- description: Get audience export details
  method: GET
  name: get-audience-export
  path: /v1/audience-exports/{id}
- description: Query users from an audience export
  method: POST
  name: query-audience-export
  path: /v1/audience-exports/{id}/users
- description: List GA4 properties
  method: GET
  name: list-properties
  path: /v1/properties
personas:
- description: Measures campaign performance, segments audiences, and tracks conversions.
  id: marketing-team
  name: Marketing Team
- description: Extracts insights from GA4 data through reports and explorations.
  id: data-analyst
  name: Data Analyst
provider_name: Google Analytics
provider_slug: google-analytics
search_terms:
- web analytics
- marketing
- metrics
- get metadata about a specific audience export
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- google analytics
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- querying and analyzing ga4 event data through various report types.
- setting up and maintaining ga4 account and property structure.
- get audience export details
- get a specific audience export
- data analyst
- managing data privacy, deletion, and access auditing.
- list ga4 properties
- list properties
- list audience exports
- extracts insights from ga4 data through reports and explorations.
- builds automated reporting pipelines and dashboards from ga4 data.
- segmenting and exporting user populations for analysis and activation.
- analytics
- segmentation
- query users from an audience export
- analytics administrator
- platform engineer
- implements privacy-compliant data handling and deletion workflows.
- manages data privacy compliance including gdpr deletion requests.
- server-side event tracking with data stream and secret management.
- list properties for audience context
- audiences
- retrieve users from a completed audience export
- bi engineer
- privacy officer
- integrates ga4 with other platforms and manages infrastructure.
- list ga4 properties to identify available audiences
- create and list audience exports
- connecting ga4 with advertising, app, and measurement platforms.
- measures campaign performance, segments audiences, and tracks conversions.
- marketing ops
- machine learning
- retrieve users from an audience export
- export
- implements server-side event tracking and offline data collection.
- attribution
- user data deletion, access auditing, and data collection acknowledgement.
- audits data access and monitors configuration changes.
- marketing team
- sets up and maintains ga4 accounts, properties, and configurations.
- connects advertising platforms and implements server-side tracking.
- query audience export
- create an audience export for a ga4 property
- list all audience exports for a property
- run standard, realtime, pivot, and batch reports with data access auditing.
- compliance team
- ingesting events from servers, apps, and offline sources.
- google
- data protection engineer
- backend engineer
- create, export, and query ga4 audience segments.
- create an audience export
- data
- reporting
- create audience export
- get audience export
slug: audience-management
tags:
- Google Analytics
- Audiences
- Segmentation
- Export
- Marketing
tools:
- description: Create an audience export for a GA4 property
  hints:
    idempotent: false
    readOnly: false
  name: create-audience-export
- description: Get metadata about a specific audience export
  hints:
    idempotent: true
    readOnly: true
  name: get-audience-export
- description: List all audience exports for a property
  hints:
    idempotent: true
    readOnly: true
  name: list-audience-exports
- description: Retrieve users from a completed audience export
  hints:
    idempotent: true
    readOnly: true
  name: query-audience-export
- description: List GA4 properties to identify available audiences
  hints:
    idempotent: true
    readOnly: true
  name: list-properties
---
