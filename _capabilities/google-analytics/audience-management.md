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
- create, export, and query ga4 audience segments.
- list properties for audience context
- list ga4 properties to identify available audiences
- metrics
- builds automated reporting pipelines and dashboards from ga4 data.
- backend engineer
- attribution
- retrieve users from an audience export
- bi engineer
- create an audience export
- server-side event tracking with data stream and secret management.
- user data deletion, access auditing, and data collection acknowledgement.
- data analyst
- query users from an audience export
- web analytics
- implements server-side event tracking and offline data collection.
- google
- marketing ops
- privacy officer
- create and list audience exports
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- analytics
- sets up and maintains ga4 accounts, properties, and configurations.
- segmentation
- platform engineer
- setting up and maintaining ga4 account and property structure.
- extracts insights from ga4 data through reports and explorations.
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- marketing team
- list audience exports
- managing data privacy, deletion, and access auditing.
- google analytics
- get a specific audience export
- get metadata about a specific audience export
- run standard, realtime, pivot, and batch reports with data access auditing.
- integrates ga4 with other platforms and manages infrastructure.
- list properties
- analytics administrator
- data
- get audience export
- audits data access and monitors configuration changes.
- reporting
- create an audience export for a ga4 property
- measures campaign performance, segments audiences, and tracks conversions.
- querying and analyzing ga4 event data through various report types.
- get audience export details
- list all audience exports for a property
- compliance team
- connects advertising platforms and implements server-side tracking.
- implements privacy-compliant data handling and deletion workflows.
- marketing
- query audience export
- manages data privacy compliance including gdpr deletion requests.
- ingesting events from servers, apps, and offline sources.
- machine learning
- list ga4 properties
- segmenting and exporting user populations for analysis and activation.
- connecting ga4 with advertising, app, and measurement platforms.
- create audience export
- retrieve users from a completed audience export
- export
- data protection engineer
- audiences
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
