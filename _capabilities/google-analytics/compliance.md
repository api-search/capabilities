---
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
- audit all configuration changes to an account for compliance tracking
- web analytics
- metrics
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- google analytics
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- querying and analyzing ga4 event data through various report types.
- setting up and maintaining ga4 account and property structure.
- data analyst
- gdpr
- run access report
- managing data privacy, deletion, and access auditing.
- extracts insights from ga4 data through reports and explorations.
- builds automated reporting pipelines and dashboards from ga4 data.
- manage user data deletion requests
- segmenting and exporting user populations for analysis and activation.
- analytics
- acknowledge user data collection terms
- analytics administrator
- platform engineer
- implements privacy-compliant data handling and deletion workflows.
- search change history events
- submit a user data deletion request for gdpr/privacy compliance
- server-side event tracking with data stream and secret management.
- manages data privacy compliance including gdpr deletion requests.
- audit configuration changes
- bi engineer
- privacy officer
- integrates ga4 with other platforms and manages infrastructure.
- compliance
- connecting ga4 with advertising, app, and measurement platforms.
- measures campaign performance, segments audiences, and tracks conversions.
- audit data access
- marketing ops
- search through account configuration changes
- machine learning
- implements server-side event tracking and offline data collection.
- data protection
- submit a user data deletion request
- manage user data collection acknowledgement
- user data deletion, access auditing, and data collection acknowledgement.
- acknowledge user data collection
- marketing team
- sets up and maintains ga4 accounts, properties, and configurations.
- connects advertising platforms and implements server-side tracking.
- audits data access and monitors configuration changes.
- privacy
- run standard, realtime, pivot, and batch reports with data access auditing.
- compliance team
- audit who accessed google analytics reporting data and when
- ingesting events from servers, apps, and offline sources.
- google
- acknowledge terms of user data collection for a ga4 property
- data protection engineer
- report on who accessed ga4 reporting data
- upsert user deletion request
- backend engineer
- create, export, and query ga4 audience segments.
- data
- reporting
- attribution
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
