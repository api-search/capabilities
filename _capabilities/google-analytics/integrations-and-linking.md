---
consumed_apis:
- ga-admin-api
description: Unified workflow for managing GA4 integration links with Firebase, Google Ads, and measurement protocol secrets. Used by platform engineers and marketing ops teams to connect GA4 with advertising and app platforms.
layout: capability
name: Google Analytics Integrations and Linking
operations:
- description: List Firebase links on a property
  method: GET
  name: list-firebase-links
  path: /v1/firebase-links
- description: Create a Firebase link
  method: POST
  name: create-firebase-link
  path: /v1/firebase-links
- description: List Google Ads links on a property
  method: GET
  name: list-google-ads-links
  path: /v1/google-ads-links
- description: Create a Google Ads link
  method: POST
  name: create-google-ads-link
  path: /v1/google-ads-links
- description: Update a Google Ads link
  method: PATCH
  name: update-google-ads-link
  path: /v1/google-ads-links/{id}
- description: Delete a Google Ads link
  method: DELETE
  name: delete-google-ads-link
  path: /v1/google-ads-links/{id}
- description: List measurement protocol secrets
  method: GET
  name: list-measurement-protocol-secrets
  path: /v1/measurement-protocol-secrets
- description: Create a measurement protocol secret
  method: POST
  name: create-measurement-protocol-secret
  path: /v1/measurement-protocol-secrets
- description: Get a measurement protocol secret
  method: GET
  name: get-measurement-protocol-secret
  path: /v1/measurement-protocol-secrets/{id}
personas:
- description: Integrates GA4 with other platforms and manages infrastructure.
  id: platform-engineer
  name: Platform Engineer
- description: Connects advertising platforms and implements server-side tracking.
  id: marketing-ops
  name: Marketing Operations
provider_name: Google Analytics
provider_slug: google-analytics
search_terms:
- manage a specific google ads link
- list google ads links on a ga4 property
- querying and analyzing ga4 event data through various report types.
- data
- metrics
- get details of a specific measurement protocol secret
- sets up and maintains ga4 accounts, properties, and configurations.
- extracts insights from ga4 data through reports and explorations.
- marketing ops
- segmenting and exporting user populations for analysis and activation.
- data protection engineer
- integrates ga4 with other platforms and manages infrastructure.
- web analytics
- analytics
- create google ads link
- privacy officer
- update google ads link
- get measurement protocol secret
- list firebase links on a property
- measures campaign performance, segments audiences, and tracks conversions.
- update a google ads link configuration
- create a firebase integration link on a ga4 property
- manage firebase integration links
- create firebase link
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- machine learning
- delete a google ads link
- delete google ads link
- create measurement protocol secret
- bi engineer
- list google ads links on a property
- server-side event tracking with data stream and secret management.
- managing data privacy, deletion, and access auditing.
- get a measurement protocol secret
- implements server-side event tracking and offline data collection.
- create a google ads integration link on a ga4 property
- google analytics
- create, export, and query ga4 audience segments.
- list firebase links
- create a firebase link
- create a measurement protocol secret
- linking
- list firebase links on a ga4 property
- backend engineer
- setting up and maintaining ga4 account and property structure.
- marketing team
- firebase
- google ads
- manage google ads integration links
- audits data access and monitors configuration changes.
- list measurement protocol secrets
- run standard, realtime, pivot, and batch reports with data access auditing.
- manages data privacy compliance including gdpr deletion requests.
- connecting ga4 with advertising, app, and measurement platforms.
- google
- implements privacy-compliant data handling and deletion workflows.
- delete a google ads integration link
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- analytics administrator
- update a google ads link
- get a specific measurement protocol secret
- create a measurement protocol secret for server-side tracking
- compliance team
- manage measurement protocol secrets
- attribution
- list google ads links
- connects advertising platforms and implements server-side tracking.
- platform engineer
- user data deletion, access auditing, and data collection acknowledgement.
- builds automated reporting pipelines and dashboards from ga4 data.
- create a google ads link
- list measurement protocol secrets for a data stream
- data analyst
- integrations
- ingesting events from servers, apps, and offline sources.
- reporting
slug: integrations-and-linking
tags:
- Google Analytics
- Integrations
- Firebase
- Google Ads
- Linking
tools:
- description: List Firebase links on a GA4 property
  hints:
    idempotent: true
    readOnly: true
  name: list-firebase-links
- description: Create a Firebase integration link on a GA4 property
  hints:
    idempotent: false
    readOnly: false
  name: create-firebase-link
- description: List Google Ads links on a GA4 property
  hints:
    idempotent: true
    readOnly: true
  name: list-google-ads-links
- description: Create a Google Ads integration link on a GA4 property
  hints:
    idempotent: false
    readOnly: false
  name: create-google-ads-link
- description: Update a Google Ads link configuration
  hints:
    idempotent: true
    readOnly: false
  name: update-google-ads-link
- description: Delete a Google Ads integration link
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-google-ads-link
- description: List measurement protocol secrets for a data stream
  hints:
    idempotent: true
    readOnly: true
  name: list-measurement-protocol-secrets
- description: Create a measurement protocol secret for server-side tracking
  hints:
    idempotent: false
    readOnly: false
  name: create-measurement-protocol-secret
- description: Get details of a specific measurement protocol secret
  hints:
    idempotent: true
    readOnly: true
  name: get-measurement-protocol-secret
---
