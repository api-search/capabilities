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
- machine learning
- acknowledge user data collection terms
- acknowledge user data collection
- manage user data deletion requests
- platform engineer
- implements server-side event tracking and offline data collection.
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- connects advertising platforms and implements server-side tracking.
- google analytics
- privacy
- run access report
- measures campaign performance, segments audiences, and tracks conversions.
- extracts insights from ga4 data through reports and explorations.
- data analyst
- compliance
- connecting ga4 with advertising, app, and measurement platforms.
- audits data access and monitors configuration changes.
- reporting
- data protection engineer
- acknowledge terms of user data collection for a ga4 property
- metrics
- marketing team
- data
- search change history events
- marketing ops
- manages data privacy compliance including gdpr deletion requests.
- create, export, and query ga4 audience segments.
- audit all configuration changes to an account for compliance tracking
- web analytics
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- sets up and maintains ga4 accounts, properties, and configurations.
- ingesting events from servers, apps, and offline sources.
- attribution
- user data deletion, access auditing, and data collection acknowledgement.
- managing data privacy, deletion, and access auditing.
- google
- server-side event tracking with data stream and secret management.
- submit a user data deletion request
- upsert user deletion request
- search through account configuration changes
- compliance team
- data protection
- audit configuration changes
- implements privacy-compliant data handling and deletion workflows.
- audit data access
- builds automated reporting pipelines and dashboards from ga4 data.
- analytics
- segmenting and exporting user populations for analysis and activation.
- privacy officer
- bi engineer
- gdpr
- manage user data collection acknowledgement
- querying and analyzing ga4 event data through various report types.
- setting up and maintaining ga4 account and property structure.
- analytics administrator
- submit a user data deletion request for gdpr/privacy compliance
- integrates ga4 with other platforms and manages infrastructure.
- report on who accessed ga4 reporting data
- backend engineer
- audit who accessed google analytics reporting data and when
- run standard, realtime, pivot, and batch reports with data access auditing.
slug: compliance
source_filename: compliance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Analytics Compliance and Privacy\"\n  description: \"Unified workflow for managing data privacy and compliance across Google Analytics. Combines the User Deletion API for GDPR/privacy compliance with the Admin API for data access auditing and user data collection acknowledgement. Used by privacy officers, compliance teams, and data protection engineers.\"\n  tags:\n    - Google Analytics\n    - Compliance\n    - Privacy\n    - GDPR\n    - Data Protection\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ANALYTICS_ACCESS_TOKEN: GOOGLE_ANALYTICS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: ga-user-deletion-api\n      location: ./shared/user-deletion-api.yaml\n    - import: ga-admin-api\n      location: ./shared/admin-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: ga-compliance-api\n      description: \"Unified REST API for\
  \ Google Analytics compliance and privacy management.\"\n      resources:\n        - path: /v1/user-deletion-requests\n          name: user-deletion-requests\n          description: \"Manage user data deletion requests\"\n          operations:\n            - method: POST\n              name: upsert-user-deletion-request\n              description: \"Submit a user data deletion request\"\n              call: \"ga-user-deletion-api.upsert-user-deletion-request\"\n              with:\n                id_type: \"rest.id_type\"\n                user_id: \"rest.user_id\"\n                property_id: \"rest.property_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/access-reports\n          name: access-reports\n          description: \"Audit data access\"\n          operations:\n            - method: POST\n              name: run-access-report\n              description: \"Report on who accessed GA4 reporting data\"\
  \n              call: \"ga-admin-api.run-access-report\"\n              with:\n                entity: \"rest.entity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/change-history\n          name: change-history\n          description: \"Audit configuration changes\"\n          operations:\n            - method: POST\n              name: search-change-history-events\n              description: \"Search through account configuration changes\"\n              call: \"ga-admin-api.search-change-history-events\"\n              with:\n                account: \"rest.account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-collection-acknowledgement\n          name: data-collection\n          description: \"Manage user data collection acknowledgement\"\n          operations:\n            - method: POST\n              name: acknowledge-user-data-collection\n\
  \              description: \"Acknowledge user data collection terms\"\n              call: \"ga-admin-api.acknowledge-user-data-collection\"\n              with:\n                property: \"rest.property\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9085\n      namespace: ga-compliance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Analytics compliance and privacy management.\"\n      tools:\n        - name: upsert-user-deletion-request\n          description: \"Submit a user data deletion request for GDPR/privacy compliance\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ga-user-deletion-api.upsert-user-deletion-request\"\n          with:\n            id_type: \"tools.id_type\"\n            user_id: \"tools.user_id\"\n            property_id: \"tools.property_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: run-access-report\n          description: \"Audit who accessed Google Analytics reporting data and when\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.run-access-report\"\n          with:\n            entity: \"tools.entity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-change-history-events\n          description: \"Audit all configuration changes to an account for compliance tracking\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.search-change-history-events\"\n          with:\n            account: \"tools.account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: acknowledge-user-data-collection\n          description: \"Acknowledge terms of user data collection for\
  \ a GA4 property\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"ga-admin-api.acknowledge-user-data-collection\"\n          with:\n            property: \"tools.property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-analytics/refs/heads/main/capabilities/compliance.yaml
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
