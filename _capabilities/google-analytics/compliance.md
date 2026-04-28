---
categories:
- compliance
consumed_apis:
- ga-user-deletion-api
- ga-admin-api
description: Unified workflow for managing data privacy and compliance across Google Analytics. Combines the User Deletion API for GDPR/privacy compliance with the Admin API for data access auditing and user data collection acknowledgement. Used by privacy officers, compliance teams, and data protection engineers.
layout: capability
name: Google Analytics Compliance and Privacy
operations:
- description: Submit a user data deletion request
  method: POST
  name: upsert-user-deletion-request
  path: /v1/user-deletion-requests
- description: Report on who accessed GA4 reporting data
  method: POST
  name: run-access-report
  path: /v1/access-reports
- description: Search through account configuration changes
  method: POST
  name: search-change-history-events
  path: /v1/change-history
- description: Acknowledge user data collection terms
  method: POST
  name: acknowledge-user-data-collection
  path: /v1/data-collection-acknowledgement
personas:
- description: Manages data privacy compliance including GDPR deletion requests.
  id: privacy-officer
  name: Privacy Officer
- description: Audits data access and monitors configuration changes.
  id: compliance-team
  name: Compliance Team
- description: Implements privacy-compliant data handling and deletion workflows.
  id: data-protection-engineer
  name: Data Protection Engineer
provider_name: Google Analytics
provider_slug: google-analytics
search_terms:
- querying and analyzing ga4 event data through various report types.
- user data deletion, access auditing, and data collection acknowledgement.
- reporting
- google
- acknowledge user data collection
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- segmenting and exporting user populations for analysis and activation.
- attribution
- sets up and maintains ga4 accounts, properties, and configurations.
- server-side event tracking with data stream and secret management.
- setting up and maintaining ga4 account and property structure.
- manage user data deletion requests
- data protection engineer
- submit a user data deletion request
- extracts insights from ga4 data through reports and explorations.
- data protection
- submit a user data deletion request for gdpr/privacy compliance
- acknowledge user data collection terms
- data analyst
- compliance
- audit all configuration changes to an account for compliance tracking
- implements server-side event tracking and offline data collection.
- implements privacy-compliant data handling and deletion workflows.
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- integrates ga4 with other platforms and manages infrastructure.
- measures campaign performance, segments audiences, and tracks conversions.
- privacy
- google analytics
- backend engineer
- machine learning
- audit who accessed google analytics reporting data and when
- search change history events
- bi engineer
- privacy officer
- manages data privacy compliance including gdpr deletion requests.
- upsert user deletion request
- report on who accessed ga4 reporting data
- connecting ga4 with advertising, app, and measurement platforms.
- gdpr
- audits data access and monitors configuration changes.
- metrics
- run access report
- audit data access
- compliance team
- builds automated reporting pipelines and dashboards from ga4 data.
- analytics
- managing data privacy, deletion, and access auditing.
- run standard, realtime, pivot, and batch reports with data access auditing.
- data
- marketing team
- connects advertising platforms and implements server-side tracking.
- platform engineer
- web analytics
- manage user data collection acknowledgement
- analytics administrator
- acknowledge terms of user data collection for a ga4 property
- search through account configuration changes
- audit configuration changes
- marketing ops
- ingesting events from servers, apps, and offline sources.
- create, export, and query ga4 audience segments.
slug: compliance
tags:
- Google Analytics
- Compliance
- Privacy
- GDPR
- Data Protection
tools:
- description: Submit a user data deletion request for GDPR/privacy compliance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: upsert-user-deletion-request
- description: Audit who accessed Google Analytics reporting data and when
  hints:
    idempotent: true
    readOnly: true
  name: run-access-report
- description: Audit all configuration changes to an account for compliance tracking
  hints:
    idempotent: true
    readOnly: true
  name: search-change-history-events
- description: Acknowledge terms of user data collection for a GA4 property
  hints:
    idempotent: true
    readOnly: false
  name: acknowledge-user-data-collection
---
