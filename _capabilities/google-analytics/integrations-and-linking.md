---
categories: []
consumed_apis: []
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
- integrations
- update a google ads link
- ingesting events from servers, apps, and offline sources.
- analytics
- measures campaign performance, segments audiences, and tracks conversions.
- list firebase links on a property
- list google ads links
- platform engineer
- sets up and maintains ga4 accounts, properties, and configurations.
- list google ads links on a property
- implements privacy-compliant data handling and deletion workflows.
- compliance team
- attribution
- delete google ads link
- get measurement protocol secret
- implements server-side event tracking and offline data collection.
- web analytics
- create measurement protocol secret
- list firebase links on a ga4 property
- create a measurement protocol secret for server-side tracking
- manage a specific google ads link
- marketing ops
- manage google ads integration links
- integrates ga4 with other platforms and manages infrastructure.
- create a google ads link
- managing data privacy, deletion, and access auditing.
- segmenting and exporting user populations for analysis and activation.
- get details of a specific measurement protocol secret
- audits data access and monitors configuration changes.
- google
- privacy officer
- machine learning
- update google ads link
- connecting ga4 with advertising, app, and measurement platforms.
- builds automated reporting pipelines and dashboards from ga4 data.
- extracts insights from ga4 data through reports and explorations.
- manage measurement protocol secrets
- create a firebase integration link on a ga4 property
- user data deletion, access auditing, and data collection acknowledgement.
- querying and analyzing ga4 event data through various report types.
- run standard, realtime, pivot, and batch reports with data access auditing.
- manages data privacy compliance including gdpr deletion requests.
- list measurement protocol secrets for a data stream
- update a google ads link configuration
- create a google ads integration link on a ga4 property
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- create firebase link
- delete a google ads link
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- create, export, and query ga4 audience segments.
- firebase
- server-side event tracking with data stream and secret management.
- list google ads links on a ga4 property
- get a specific measurement protocol secret
- setting up and maintaining ga4 account and property structure.
- create google ads link
- delete a google ads integration link
- backend engineer
- google analytics
- google ads
- create a firebase link
- list measurement protocol secrets
- marketing team
- data protection engineer
- connects advertising platforms and implements server-side tracking.
- get a measurement protocol secret
- metrics
- data analyst
- reporting
- data
- list firebase links
- linking
- create a measurement protocol secret
- manage firebase integration links
- bi engineer
- analytics administrator
slug: integrations-and-linking
source_filename: integrations-and-linking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Analytics Integrations and Linking\n  description: Unified workflow for managing GA4 integration links with Firebase, Google Ads, and measurement protocol secrets.\n    Used by platform engineers and marketing ops teams to connect GA4 with advertising and app platforms.\n  tags:\n  - Google Analytics\n  - Integrations\n  - Firebase\n  - Google Ads\n  - Linking\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ANALYTICS_ACCESS_TOKEN: GOOGLE_ANALYTICS_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ga-admin-api\n    baseUri: https://analyticsadmin.googleapis.com\n    auth:\n      type: bearer\n      token: '{{GOOGLE_ANALYTICS_ACCESS_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /v1beta\n      operations:\n      - id: list-account-summaries\n        method: GET\n        path: /accountSummaries\n        description: Returns summaries of all accounts\
  \ accessible by the caller.\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of AccountSummary resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-accounts\n        method: GET\n        path: /accounts\n        description: Returns all accounts accessible by the caller.\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        - name: showDeleted\n          in: query\n          type: boolean\n          description: Whether\
  \ to include soft-deleted accounts in the results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: provision-account-ticket\n        method: POST\n        path: /accounts:provisionAccountTicket\n        description: Requests a ticket for creating an account.\n        inputParameters:\n        - name: account\n          in: body\n          type: object\n          description: The account to create.\n          properties:\n            displayName:\n              type: string\n            regionCode:\n              type: string\n          value:\n            displayName: '{{tools.displayName}}'\n            regionCode: '{{tools.regionCode}}'\n        - name: redirectUri\n          in: body\n          type: string\n          description: Redirect URI where the user will be sent after accepting Terms of Service.\n          value: '{{tools.redirectUri}}'\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - id: search-change-history-events\n        method: POST\n        path: /{account}:searchChangeHistoryEvents\n        description: Searches through the change history of an account.\n        inputParameters:\n        - name: account\n          in: path\n          type: string\n          description: 'Required. The account resource for which to return change history resources. Format: accounts/{account_id}'\n        - name: action\n          in: body\n          type: string\n          description: Optional. If set, only return changes that match this action type.\n          value: '{{tools.action}}'\n        - name: actorEmail\n          in: body\n          type: string\n          description: Optional. If set, only return changes made by this actor.\n          value: '{{tools.actorEmail}}'\n        - name: earliestChangeTime\n          in: body\n          type: string\n          description: Optional. Earliest change time to filter by.\n          value: '{{tools.earliestChangeTime}}'\n\
  \        - name: latestChangeTime\n          in: body\n          type: string\n          description: Optional. Latest change time to filter by.\n          value: '{{tools.latestChangeTime}}'\n        - name: pageSize\n          in: body\n          type: integer\n          description: Optional. Maximum number of results to return.\n          value: '{{tools.pageSize}}'\n        - name: pageToken\n          in: body\n          type: string\n          description: Optional. Page token for retrieving subsequent pages.\n          value: '{{tools.pageToken}}'\n        - name: property\n          in: body\n          type: string\n          description: Optional. Resource name for a child property to filter by.\n          value: '{{tools.property}}'\n        - name: resourceType\n          in: body\n          type: string\n          description: Optional. If set, only return changes for resources that match this type.\n          value: '{{tools.resourceType}}'\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: properties\n      path: /v1beta\n      operations:\n      - id: list-properties\n        method: GET\n        path: /properties\n        description: Returns child properties under the specified parent account.\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Required. Filter expression for the list request.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        - name: showDeleted\n          in: query\n          type: boolean\n          description: Whether to include soft-deleted properties in the results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - id: create-property\n        method: POST\n        path: /properties\n        description: Creates a GA4 property with the specified attributes.\n        inputParameters:\n        - name: displayName\n          in: body\n          type: string\n          description: Required. Human-readable display name for this property.\n          value: '{{tools.displayName}}'\n        - name: timeZone\n          in: body\n          type: string\n          description: Required. Reporting time zone for the property.\n          value: '{{tools.timeZone}}'\n        - name: currencyCode\n          in: body\n          type: string\n          description: The currency type used in reports.\n          value: '{{tools.currencyCode}}'\n        - name: industryCategory\n          in: body\n          type: string\n          description: Industry associated with this property.\n          value: '{{tools.industryCategory}}'\n        - name: account\n          in: body\n          type: string\n        \
  \  description: 'Required. Parent account resource name. Format: accounts/{account_id}'\n          value: '{{tools.account}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: run-access-report\n        method: POST\n        path: /{entity}:runAccessReport\n        description: Returns a customized report of data access records.\n        inputParameters:\n        - name: entity\n          in: path\n          type: string\n          description: The Data Access Report supports requesting at the property or account level.\n        - name: dateRanges\n          in: body\n          type: array\n          description: Date ranges of access records to read.\n          value: '{{tools.dateRanges}}'\n        - name: dimensions\n          in: body\n          type: array\n          description: The dimensions requested and displayed in the response.\n          value: '{{tools.dimensions}}'\n        - name: metrics\n          in: body\n \
  \         type: array\n          description: The metrics requested and displayed in the response.\n          value: '{{tools.metrics}}'\n        - name: dimensionFilter\n          in: body\n          type: object\n          description: Dimension filters to restrict the report data.\n          value: '{{tools.dimensionFilter}}'\n        - name: metricFilter\n          in: body\n          type: object\n          description: Metric filters to restrict the report data.\n          value: '{{tools.metricFilter}}'\n        - name: offset\n          in: body\n          type: integer\n          description: Row offset for the report.\n          value: '{{tools.offset}}'\n        - name: limit\n          in: body\n          type: integer\n          description: The number of rows to return.\n          value: '{{tools.limit}}'\n        - name: orderBys\n          in: body\n          type: array\n          description: Specifies how rows are ordered in the response.\n          value: '{{tools.orderBys}}'\n\
  \        - name: returnEntityQuota\n          in: body\n          type: boolean\n          description: Whether to return the current quota state for this Analytics property.\n          value: '{{tools.returnEntityQuota}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: acknowledge-user-data-collection\n        method: POST\n        path: /{property}:acknowledgeUserDataCollection\n        description: Acknowledges the terms of user data collection for the specified property.\n        inputParameters:\n        - name: property\n          in: path\n          type: string\n          description: 'Required. The property for which to acknowledge user data collection. Format: properties/{property_id}'\n        - name: acknowledgement\n          in: body\n          type: string\n          description: Required. An acknowledgement that the caller of this method understands the terms of user data collection.\n          value: '{{tools.acknowledgement}}'\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversion-events\n      path: /v1beta\n      operations:\n      - id: list-conversion-events\n        method: GET\n        path: /{parent}/conversionEvents\n        description: Returns a list of conversion events in the specified parent property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The resource name of the parent property. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-conversion-event\n        method: POST\n\
  \        path: /{parent}/conversionEvents\n        description: Creates a conversion event with the specified attributes.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The resource name of the parent property. Format: properties/{property_id}'\n        - name: eventName\n          in: body\n          type: string\n          description: Required. The event name for this conversion event.\n          value: '{{tools.eventName}}'\n        - name: countingMethod\n          in: body\n          type: string\n          description: The method by which conversions will be counted.\n          value: '{{tools.countingMethod}}'\n        - name: defaultConversionValue\n          in: body\n          type: object\n          description: Optional default value for a conversion event.\n          value: '{{tools.defaultConversionValue}}'\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: custom-dimensions\n      path: /v1beta\n      operations:\n      - id: list-custom-dimensions\n        method: GET\n        path: /{parent}/customDimensions\n        description: Lists custom dimensions on a property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-custom-dimension\n        method: POST\n        path: /{parent}/customDimensions\n        description: Creates a custom dimension.\n        inputParameters:\n\
  \        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: displayName\n          in: body\n          type: string\n          description: Required. Display name for this custom dimension.\n          value: '{{tools.displayName}}'\n        - name: parameterName\n          in: body\n          type: string\n          description: Required. Immutable. Tagging parameter name for this custom dimension.\n          value: '{{tools.parameterName}}'\n        - name: scope\n          in: body\n          type: string\n          description: Required. Immutable. The scope of this dimension.\n          value: '{{tools.scope}}'\n        - name: description\n          in: body\n          type: string\n          description: Optional. Description for this custom dimension.\n          value: '{{tools.description}}'\n        - name: disallowAdsPersonalization\n          in: body\n\
  \          type: boolean\n          description: Optional. If true, sets this dimension as NPA and excludes it from ads personalization.\n          value: '{{tools.disallowAdsPersonalization}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-metrics\n      path: /v1beta\n      operations:\n      - id: list-custom-metrics\n        method: GET\n        path: /{parent}/customMetrics\n        description: Lists custom metrics on a property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - id: create-custom-metric\n        method: POST\n        path: /{parent}/customMetrics\n        description: Creates a custom metric.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: displayName\n          in: body\n          type: string\n          description: Required. Display name for this custom metric.\n          value: '{{tools.displayName}}'\n        - name: parameterName\n          in: body\n          type: string\n          description: Required. Immutable. Tagging name for this custom metric.\n          value: '{{tools.parameterName}}'\n        - name: measurementUnit\n          in: body\n          type: string\n          description: Required. The type for the custom metric's value.\n          value: '{{tools.measurementUnit}}'\n     \
  \   - name: scope\n          in: body\n          type: string\n          description: Required. Immutable. The scope of this custom metric.\n          value: '{{tools.scope}}'\n        - name: description\n          in: body\n          type: string\n          description: Optional. Description for this custom metric.\n          value: '{{tools.description}}'\n        - name: restrictedMetricType\n          in: body\n          type: array\n          description: Optional. Types of restricted data that this metric may contain.\n          value: '{{tools.restrictedMetricType}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: archive-custom-metric\n        method: POST\n        path: /{name}:archive\n        description: Archives a custom metric on a property.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          description: 'Required. The name of the custom metric to archive. Format:\
  \ properties/{property_id}/customMetrics/{custom_metric_id}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-streams\n      path: /v1beta\n      operations:\n      - id: list-data-streams\n        method: GET\n        path: /{parent}/dataStreams\n        description: Lists data streams on a property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-data-stream\n        method: POST\n\
  \        path: /{parent}/dataStreams\n        description: Creates a data stream.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: type\n          in: body\n          type: string\n          description: Required. Immutable. The type of this DataStream resource.\n          value: '{{tools.type}}'\n        - name: displayName\n          in: body\n          type: string\n          description: Human-readable display name for the data stream.\n          value: '{{tools.displayName}}'\n        - name: webStreamData\n          in: body\n          type: object\n          description: Data specific to web streams.\n          value: '{{tools.webStreamData}}'\n        - name: androidAppStreamData\n          in: body\n          type: object\n          description: Data specific to Android app streams.\n          value: '{{tools.androidAppStreamData}}'\n\
  \        - name: iosAppStreamData\n          in: body\n          type: object\n          description: Data specific to iOS app streams.\n          value: '{{tools.iosAppStreamData}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firebase-links\n      path: /v1beta\n      operations:\n      - id: list-firebase-links\n        method: GET\n        path: /{parent}/firebaseLinks\n        description: Lists FirebaseLinks on a property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - id: create-firebase-link\n        method: POST\n        path: /{parent}/firebaseLinks\n        description: Creates a FirebaseLink.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: project\n          in: body\n          type: string\n          description: 'Required. Immutable. The Firebase project resource name. Format: projects/{project_id}'\n          value: '{{tools.project}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: google-ads-links\n      path: /v1beta\n      operations:\n      - id: list-google-ads-links\n        method: GET\n        path: /{parent}/googleAdsLinks\n        description: Lists GoogleAdsLinks on a property.\n        inputParameters:\n        - name: parent\n\
  \          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-google-ads-link\n        method: POST\n        path: /{parent}/googleAdsLinks\n        description: Creates a GoogleAdsLink.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: customerId\n          in: body\n          type: string\n          description: Required. Immutable. Google Ads customer\
  \ ID.\n          value: '{{tools.customerId}}'\n        - name: adsPersonalizationEnabled\n          in: body\n          type: boolean\n          description: Enable personalized advertising features with this integration.\n          value: '{{tools.adsPersonalizationEnabled}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: update-google-ads-link\n        method: PATCH\n        path: /{name}\n        description: Updates a GoogleAdsLink on a property.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          description: 'Required. Resource name of the GoogleAdsLink. Format: properties/{property_id}/googleAdsLinks/{google_ads_link_id}'\n        - name: updateMask\n          in: query\n          type: string\n          description: Required. The list of fields to update. Field names must be in snake_case.\n        - name: adsPersonalizationEnabled\n          in: body\n          type:\
  \ boolean\n          description: Enable personalized advertising features with this integration.\n          value: '{{tools.adsPersonalizationEnabled}}'\n        - name: customerId\n          in: body\n          type: string\n          description: Immutable. Google Ads customer ID.\n          value: '{{tools.customerId}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: delete-google-ads-link\n        method: DELETE\n        path: /{name}\n        description: Deletes a GoogleAdsLink on a property.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          description: 'Required. Resource name of the GoogleAdsLink to delete. Format: properties/{property_id}/googleAdsLinks/{google_ads_link_id}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: measurement-protocol-secrets\n      path: /v1beta\n      operations:\n      - id:\
  \ list-measurement-protocol-secrets\n        method: GET\n        path: /{parent}/measurementProtocolSecrets\n        description: Returns child MeasurementProtocolSecrets under the specified parent property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The resource name of the parent stream. Format: properties/{property_id}/dataStreams/{data_stream_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-measurement-protocol-secret\n        method: POST\n        path: /{parent}/measurementProtocolSecrets\n        description: Creates a measurement protocol secret.\n\
  \        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent resource name. Format: properties/{property_id}/dataStreams/{data_stream_id}'\n        - name: displayName\n          in: body\n          type: string\n          description: Required. Human-readable display name for this secret.\n          value: '{{tools.displayName}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-measurement-protocol-secret\n        method: GET\n        path: /{name}\n        description: Lookup for a single MeasurementProtocolSecret.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          description: 'Required. The name of the measurement protocol secret to look up. Format: properties/{property_id}/dataStreams/{data_stream_id}/measurementProtocolSecrets/{measurement_protocol_secret_id}'\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: ga-integrations-api\n    description: Unified REST API for Google Analytics integration management.\n    resources:\n    - path: /v1/firebase-links\n      name: firebase-links\n      description: Manage Firebase integration links\n      operations:\n      - method: GET\n        name: list-firebase-links\n        description: List Firebase links on a property\n        call: ga-admin-api.list-firebase-links\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-firebase-link\n        description: Create a Firebase link\n        call: ga-admin-api.create-firebase-link\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/google-ads-links\n      name: google-ads-links\n    \
  \  description: Manage Google Ads integration links\n      operations:\n      - method: GET\n        name: list-google-ads-links\n        description: List Google Ads links on a property\n        call: ga-admin-api.list-google-ads-links\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-google-ads-link\n        description: Create a Google Ads link\n        call: ga-admin-api.create-google-ads-link\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/google-ads-links/{id}\n      name: google-ads-link\n      description: Manage a specific Google Ads link\n      operations:\n      - method: PATCH\n        name: update-google-ads-link\n        description: Update a Google Ads link\n        call: ga-admin-api.update-google-ads-link\n        with:\n          name: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-google-ads-link\n        description: Delete a Google Ads link\n        call: ga-admin-api.delete-google-ads-link\n        with:\n          name: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/measurement-protocol-secrets\n      name: measurement-protocol-secrets\n      description: Manage measurement protocol secrets\n      operations:\n      - method: GET\n        name: list-measurement-protocol-secrets\n        description: List measurement protocol secrets\n        call: ga-admin-api.list-measurement-protocol-secrets\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-measurement-protocol-secret\n        description: Create a measurement protocol secret\n        call: ga-admin-api.create-measurement-protocol-secret\n        with:\n\
  \          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/measurement-protocol-secrets/{id}\n      name: measurement-protocol-secret\n      description: Get a specific measurement protocol secret\n      operations:\n      - method: GET\n        name: get-measurement-protocol-secret\n        description: Get a measurement protocol secret\n        call: ga-admin-api.get-measurement-protocol-secret\n        with:\n          name: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: ga-integrations-mcp\n    transport: http\n    description: MCP server for AI-assisted Google Analytics integration management.\n    tools:\n    - name: list-firebase-links\n      description: List Firebase links on a GA4 property\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.list-firebase-links\n      with:\n        parent: tools.parent\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-firebase-link\n      description: Create a Firebase integration link on a GA4 property\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ga-admin-api.create-firebase-link\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-google-ads-links\n      description: List Google Ads links on a GA4 property\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.list-google-ads-links\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-google-ads-link\n      description: Create a Google Ads integration link on a GA4 property\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ga-admin-api.create-google-ads-link\n      with:\n        parent: tools.parent\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: update-google-ads-link\n      description: Update a Google Ads link configuration\n      hints:\n        readOnly: false\n        idempotent: true\n      call: ga-admin-api.update-google-ads-link\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-google-ads-link\n      description: Delete a Google Ads integration link\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ga-admin-api.delete-google-ads-link\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-measurement-protocol-secrets\n      description: List measurement protocol secrets for a data stream\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.list-measurement-protocol-secrets\n      with:\n        parent: tools.parent\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-measurement-protocol-secret\n      description: Create a measurement protocol secret for server-side tracking\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ga-admin-api.create-measurement-protocol-secret\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-measurement-protocol-secret\n      description: Get details of a specific measurement protocol secret\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.get-measurement-protocol-secret\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-analytics/refs/heads/main/capabilities/integrations-and-linking.yaml
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
