---
categories: []
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
- analytics administrator
- reporting
- connects advertising platforms and implements server-side tracking.
- server-side event tracking with data stream and secret management.
- audiences
- web analytics
- get audience export
- list all audience exports for a property
- create, export, and query ga4 audience segments.
- run standard, realtime, pivot, and batch reports with data access auditing.
- create an audience export for a ga4 property
- privacy officer
- querying and analyzing ga4 event data through various report types.
- segmentation
- marketing team
- list audience exports
- query audience export
- manages data privacy compliance including gdpr deletion requests.
- data protection engineer
- ingesting events from servers, apps, and offline sources.
- implements server-side event tracking and offline data collection.
- builds automated reporting pipelines and dashboards from ga4 data.
- query users from an audience export
- segmenting and exporting user populations for analysis and activation.
- compliance team
- metrics
- integrates ga4 with other platforms and manages infrastructure.
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- retrieve users from a completed audience export
- managing data privacy, deletion, and access auditing.
- list ga4 properties
- create and list audience exports
- extracts insights from ga4 data through reports and explorations.
- list properties
- export
- sets up and maintains ga4 accounts, properties, and configurations.
- data analyst
- attribution
- marketing
- get audience export details
- list ga4 properties to identify available audiences
- create audience export
- list properties for audience context
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- implements privacy-compliant data handling and deletion workflows.
- machine learning
- platform engineer
- get a specific audience export
- create an audience export
- google
- get metadata about a specific audience export
- backend engineer
- user data deletion, access auditing, and data collection acknowledgement.
- measures campaign performance, segments audiences, and tracks conversions.
- analytics
- connecting ga4 with advertising, app, and measurement platforms.
- google analytics
- audits data access and monitors configuration changes.
- data
- retrieve users from an audience export
- marketing ops
- bi engineer
- setting up and maintaining ga4 account and property structure.
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
