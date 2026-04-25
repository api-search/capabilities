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
- segmentation
- connects advertising platforms and implements server-side tracking.
- connecting ga4 with advertising, app, and measurement platforms.
- google
- analytics
- bi engineer
- data
- attribution
- marketing
- ingesting events from servers, apps, and offline sources.
- list ga4 properties
- audiences
- measures campaign performance, segments audiences, and tracks conversions.
- integrates ga4 with other platforms and manages infrastructure.
- sets up and maintains ga4 accounts, properties, and configurations.
- querying and analyzing ga4 event data through various report types.
- managing data privacy, deletion, and access auditing.
- list properties
- implements privacy-compliant data handling and deletion workflows.
- create and list audience exports
- reporting
- web analytics
- create an audience export for a ga4 property
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- server-side event tracking with data stream and secret management.
- audits data access and monitors configuration changes.
- run standard, realtime, pivot, and batch reports with data access auditing.
- machine learning
- create, export, and query ga4 audience segments.
- list audience exports
- get audience export
- list properties for audience context
- privacy officer
- get metadata about a specific audience export
- list all audience exports for a property
- extracts insights from ga4 data through reports and explorations.
- get audience export details
- segmenting and exporting user populations for analysis and activation.
- query audience export
- marketing ops
- user data deletion, access auditing, and data collection acknowledgement.
- export
- setting up and maintaining ga4 account and property structure.
- metrics
- implements server-side event tracking and offline data collection.
- manages data privacy compliance including gdpr deletion requests.
- google analytics
- get a specific audience export
- data protection engineer
- compliance team
- builds automated reporting pipelines and dashboards from ga4 data.
- analytics administrator
- backend engineer
- create audience export
- data analyst
- retrieve users from a completed audience export
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- marketing team
- create an audience export
- retrieve users from an audience export
- platform engineer
- query users from an audience export
- list ga4 properties to identify available audiences
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
