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
- querying and analyzing ga4 event data through various report types.
- data
- acknowledge user data collection terms
- metrics
- sets up and maintains ga4 accounts, properties, and configurations.
- extracts insights from ga4 data through reports and explorations.
- marketing ops
- manage user data collection acknowledgement
- data protection engineer
- audit data access
- integrates ga4 with other platforms and manages infrastructure.
- manage user data deletion requests
- segmenting and exporting user populations for analysis and activation.
- privacy officer
- analytics
- web analytics
- audit who accessed google analytics reporting data and when
- measures campaign performance, segments audiences, and tracks conversions.
- submit a user data deletion request for gdpr/privacy compliance
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- audit configuration changes
- machine learning
- report on who accessed ga4 reporting data
- bi engineer
- server-side event tracking with data stream and secret management.
- upsert user deletion request
- implements server-side event tracking and offline data collection.
- managing data privacy, deletion, and access auditing.
- google analytics
- create, export, and query ga4 audience segments.
- backend engineer
- compliance
- setting up and maintaining ga4 account and property structure.
- marketing team
- audits data access and monitors configuration changes.
- run access report
- run standard, realtime, pivot, and batch reports with data access auditing.
- manages data privacy compliance including gdpr deletion requests.
- connecting ga4 with advertising, app, and measurement platforms.
- search through account configuration changes
- audit all configuration changes to an account for compliance tracking
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- implements privacy-compliant data handling and deletion workflows.
- analytics administrator
- google
- gdpr
- compliance team
- acknowledge user data collection
- privacy
- attribution
- connects advertising platforms and implements server-side tracking.
- platform engineer
- user data deletion, access auditing, and data collection acknowledgement.
- builds automated reporting pipelines and dashboards from ga4 data.
- data analyst
- ingesting events from servers, apps, and offline sources.
- search change history events
- data protection
- acknowledge terms of user data collection for a ga4 property
- reporting
- submit a user data deletion request
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
