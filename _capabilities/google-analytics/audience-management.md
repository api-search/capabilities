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
- backend engineer
- query users from an audience export
- create audience export
- analytics administrator
- builds automated reporting pipelines and dashboards from ga4 data.
- bi engineer
- run standard, realtime, pivot, and batch reports with data access auditing.
- manages data privacy compliance including gdpr deletion requests.
- list properties
- list properties for audience context
- measures campaign performance, segments audiences, and tracks conversions.
- create, export, and query ga4 audience segments.
- setting up and maintaining ga4 account and property structure.
- machine learning
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- managing data privacy, deletion, and access auditing.
- compliance team
- extracts insights from ga4 data through reports and explorations.
- reporting
- connects advertising platforms and implements server-side tracking.
- get metadata about a specific audience export
- attribution
- connecting ga4 with advertising, app, and measurement platforms.
- implements server-side event tracking and offline data collection.
- list all audience exports for a property
- marketing team
- segmentation
- platform engineer
- create and list audience exports
- marketing
- create an audience export
- retrieve users from a completed audience export
- privacy officer
- get audience export
- audiences
- export
- server-side event tracking with data stream and secret management.
- integrates ga4 with other platforms and manages infrastructure.
- retrieve users from an audience export
- get a specific audience export
- querying and analyzing ga4 event data through various report types.
- segmenting and exporting user populations for analysis and activation.
- google
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- sets up and maintains ga4 accounts, properties, and configurations.
- get audience export details
- data protection engineer
- metrics
- implements privacy-compliant data handling and deletion workflows.
- list audience exports
- list ga4 properties
- web analytics
- data analyst
- ingesting events from servers, apps, and offline sources.
- data
- list ga4 properties to identify available audiences
- analytics
- query audience export
- google analytics
- create an audience export for a ga4 property
- audits data access and monitors configuration changes.
- marketing ops
- user data deletion, access auditing, and data collection acknowledgement.
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
