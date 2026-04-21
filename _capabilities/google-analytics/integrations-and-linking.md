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
- delete a google ads link
- list firebase links
- marketing team
- data protection engineer
- extracts insights from ga4 data through reports and explorations.
- privacy officer
- firebase
- implements server-side event tracking and offline data collection.
- machine learning
- connecting ga4 with advertising, app, and measurement platforms.
- create a google ads integration link on a ga4 property
- integrates ga4 with other platforms and manages infrastructure.
- list google ads links
- get details of a specific measurement protocol secret
- get a measurement protocol secret
- create a firebase link
- manage firebase integration links
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- web analytics
- builds automated reporting pipelines and dashboards from ga4 data.
- create google ads link
- create a google ads link
- bi engineer
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- list google ads links on a property
- create a firebase integration link on a ga4 property
- create, export, and query ga4 audience segments.
- linking
- create measurement protocol secret
- audits data access and monitors configuration changes.
- google
- run standard, realtime, pivot, and batch reports with data access auditing.
- manage google ads integration links
- compliance team
- implements privacy-compliant data handling and deletion workflows.
- list measurement protocol secrets for a data stream
- marketing ops
- get measurement protocol secret
- data analyst
- querying and analyzing ga4 event data through various report types.
- analytics administrator
- list google ads links on a ga4 property
- platform engineer
- user data deletion, access auditing, and data collection acknowledgement.
- measures campaign performance, segments audiences, and tracks conversions.
- delete a google ads integration link
- google ads
- update google ads link
- data
- analytics
- get a specific measurement protocol secret
- integrations
- manages data privacy compliance including gdpr deletion requests.
- attribution
- list firebase links on a ga4 property
- list firebase links on a property
- manage measurement protocol secrets
- server-side event tracking with data stream and secret management.
- backend engineer
- sets up and maintains ga4 accounts, properties, and configurations.
- update a google ads link configuration
- connects advertising platforms and implements server-side tracking.
- ingesting events from servers, apps, and offline sources.
- managing data privacy, deletion, and access auditing.
- google analytics
- update a google ads link
- create a measurement protocol secret
- segmenting and exporting user populations for analysis and activation.
- metrics
- reporting
- create firebase link
- setting up and maintaining ga4 account and property structure.
- manage a specific google ads link
- list measurement protocol secrets
- create a measurement protocol secret for server-side tracking
- delete google ads link
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
