---
categories: []
consumed_apis: []
description: Unified workflow for managing GA4 property configuration including accounts, properties, data streams, custom dimensions and metrics, conversion events, and integration links. Used by analytics administrators and platform engineers to set up and maintain GA4 properties.
layout: capability
name: Google Analytics Configuration Management
operations:
- description: List all accessible accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: List summaries of all accessible accounts
  method: GET
  name: list-account-summaries
  path: /v1/account-summaries
- description: List GA4 properties
  method: GET
  name: list-properties
  path: /v1/properties
- description: Create a GA4 property
  method: POST
  name: create-property
  path: /v1/properties
- description: List data streams on a property
  method: GET
  name: list-data-streams
  path: /v1/data-streams
- description: Create a data stream
  method: POST
  name: create-data-stream
  path: /v1/data-streams
- description: List custom dimensions
  method: GET
  name: list-custom-dimensions
  path: /v1/custom-dimensions
- description: Create a custom dimension
  method: POST
  name: create-custom-dimension
  path: /v1/custom-dimensions
- description: List custom metrics
  method: GET
  name: list-custom-metrics
  path: /v1/custom-metrics
- description: Create a custom metric
  method: POST
  name: create-custom-metric
  path: /v1/custom-metrics
- description: List conversion events
  method: GET
  name: list-conversion-events
  path: /v1/conversion-events
- description: Create a conversion event
  method: POST
  name: create-conversion-event
  path: /v1/conversion-events
- description: Search through account changes
  method: POST
  name: search-change-history-events
  path: /v1/change-history
personas:
- description: Sets up and maintains GA4 accounts, properties, and configurations.
  id: analytics-administrator
  name: Analytics Administrator
- description: Integrates GA4 with other platforms and manages infrastructure.
  id: platform-engineer
  name: Platform Engineer
provider_name: Google Analytics
provider_slug: google-analytics
search_terms:
- create a ga4 property
- implements privacy-compliant data handling and deletion workflows.
- manage ga4 accounts
- implements server-side event tracking and offline data collection.
- manage custom metrics
- list accounts
- list conversion events
- integrates ga4 with other platforms and manages infrastructure.
- list all accessible accounts
- managing data privacy, deletion, and access auditing.
- google
- audits data access and monitors configuration changes.
- view account summaries
- list ga4 properties
- machine learning
- connecting ga4 with advertising, app, and measurement platforms.
- list account summaries
- create data stream
- extracts insights from ga4 data through reports and explorations.
- search through all changes to an account or its children
- run standard, realtime, pivot, and batch reports with data access auditing.
- create property
- request a ticket for creating a new account
- create, export, and query ga4 audience segments.
- list custom dimensions on a property
- setting up and maintaining ga4 account and property structure.
- create a data stream
- list custom dimensions
- acknowledge terms of user data collection for a property
- bi engineer
- ingesting events from servers, apps, and offline sources.
- list ga4 properties for an account
- compliance team
- configuration
- create a conversion event
- list conversion events on a property
- list data streams
- create custom dimension
- user data deletion, access auditing, and data collection acknowledgement.
- ga4
- server-side event tracking with data stream and secret management.
- archive custom metric
- metrics
- create a custom dimension
- analytics administrator
- measures campaign performance, segments audiences, and tracks conversions.
- create a conversion event on a property
- attribution
- create a custom metric on a property
- web analytics
- manage conversion events
- create custom metric
- provision account ticket
- list summaries of all accessible accounts
- list properties
- management
- create a custom dimension on a property
- manage ga4 properties
- list data streams on a property
- google analytics
- list custom metrics on a property
- create a new data stream on a property
- data protection engineer
- list summaries of all accessible accounts with their properties
- search change history events
- reporting
- manage data streams
- analytics
- sets up and maintains ga4 accounts, properties, and configurations.
- search through account changes
- manage custom dimensions
- platform engineer
- admin
- create a custom metric
- list custom metrics
- marketing ops
- archive a custom metric on a property
- segmenting and exporting user populations for analysis and activation.
- privacy officer
- create a new ga4 property
- builds automated reporting pipelines and dashboards from ga4 data.
- acknowledge user data collection
- querying and analyzing ga4 event data through various report types.
- manages data privacy compliance including gdpr deletion requests.
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- search change history
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- connects advertising platforms and implements server-side tracking.
- marketing team
- data
- create conversion event
- list all accessible google analytics accounts
- data analyst
- backend engineer
slug: configuration-management
source_filename: configuration-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Analytics Configuration Management\n  description: Unified workflow for managing GA4 property configuration including accounts, properties, data streams, custom\n    dimensions and metrics, conversion events, and integration links. Used by analytics administrators and platform engineers\n    to set up and maintain GA4 properties.\n  tags:\n  - Google Analytics\n  - Configuration\n  - Admin\n  - Management\n  - GA4\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ANALYTICS_ACCESS_TOKEN: GOOGLE_ANALYTICS_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ga-admin-api\n    baseUri: https://analyticsadmin.googleapis.com\n    auth:\n      type: bearer\n      token: '{{GOOGLE_ANALYTICS_ACCESS_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /v1beta\n      operations:\n      - id: list-account-summaries\n        method: GET\n        path: /accountSummaries\n\
  \        description: Returns summaries of all accounts accessible by the caller.\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of AccountSummary resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-accounts\n        method: GET\n        path: /accounts\n        description: Returns all accounts accessible by the caller.\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        - name: showDeleted\n          in: query\n\
  \          type: boolean\n          description: Whether to include soft-deleted accounts in the results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: provision-account-ticket\n        method: POST\n        path: /accounts:provisionAccountTicket\n        description: Requests a ticket for creating an account.\n        inputParameters:\n        - name: account\n          in: body\n          type: object\n          description: The account to create.\n          properties:\n            displayName:\n              type: string\n            regionCode:\n              type: string\n          value:\n            displayName: '{{tools.displayName}}'\n            regionCode: '{{tools.regionCode}}'\n        - name: redirectUri\n          in: body\n          type: string\n          description: Redirect URI where the user will be sent after accepting Terms of Service.\n          value: '{{tools.redirectUri}}'\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - id: search-change-history-events\n        method: POST\n        path: /{account}:searchChangeHistoryEvents\n        description: Searches through the change history of an account.\n        inputParameters:\n        - name: account\n          in: path\n          type: string\n          description: 'Required. The account resource for which to return change history resources. Format: accounts/{account_id}'\n        - name: action\n          in: body\n          type: string\n          description: Optional. If set, only return changes that match this action type.\n          value: '{{tools.action}}'\n        - name: actorEmail\n          in: body\n          type: string\n          description: Optional. If set, only return changes made by this actor.\n          value: '{{tools.actorEmail}}'\n        - name: earliestChangeTime\n          in: body\n          type: string\n          description: Optional. Earliest\
  \ change time to filter by.\n          value: '{{tools.earliestChangeTime}}'\n        - name: latestChangeTime\n          in: body\n          type: string\n          description: Optional. Latest change time to filter by.\n          value: '{{tools.latestChangeTime}}'\n        - name: pageSize\n          in: body\n          type: integer\n          description: Optional. Maximum number of results to return.\n          value: '{{tools.pageSize}}'\n        - name: pageToken\n          in: body\n          type: string\n          description: Optional. Page token for retrieving subsequent pages.\n          value: '{{tools.pageToken}}'\n        - name: property\n          in: body\n          type: string\n          description: Optional. Resource name for a child property to filter by.\n          value: '{{tools.property}}'\n        - name: resourceType\n          in: body\n          type: string\n          description: Optional. If set, only return changes for resources that match this type.\n\
  \          value: '{{tools.resourceType}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: properties\n      path: /v1beta\n      operations:\n      - id: list-properties\n        method: GET\n        path: /properties\n        description: Returns child properties under the specified parent account.\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Required. Filter expression for the list request.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        - name: showDeleted\n          in: query\n          type: boolean\n          description: Whether to include soft-deleted properties in the results.\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - id: create-property\n        method: POST\n        path: /properties\n        description: Creates a GA4 property with the specified attributes.\n        inputParameters:\n        - name: displayName\n          in: body\n          type: string\n          description: Required. Human-readable display name for this property.\n          value: '{{tools.displayName}}'\n        - name: timeZone\n          in: body\n          type: string\n          description: Required. Reporting time zone for the property.\n          value: '{{tools.timeZone}}'\n        - name: currencyCode\n          in: body\n          type: string\n          description: The currency type used in reports.\n          value: '{{tools.currencyCode}}'\n        - name: industryCategory\n          in: body\n          type: string\n          description: Industry associated with this property.\n          value: '{{tools.industryCategory}}'\n       \
  \ - name: account\n          in: body\n          type: string\n          description: 'Required. Parent account resource name. Format: accounts/{account_id}'\n          value: '{{tools.account}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: run-access-report\n        method: POST\n        path: /{entity}:runAccessReport\n        description: Returns a customized report of data access records.\n        inputParameters:\n        - name: entity\n          in: path\n          type: string\n          description: The Data Access Report supports requesting at the property or account level.\n        - name: dateRanges\n          in: body\n          type: array\n          description: Date ranges of access records to read.\n          value: '{{tools.dateRanges}}'\n        - name: dimensions\n          in: body\n          type: array\n          description: The dimensions requested and displayed in the response.\n          value: '{{tools.dimensions}}'\n\
  \        - name: metrics\n          in: body\n          type: array\n          description: The metrics requested and displayed in the response.\n          value: '{{tools.metrics}}'\n        - name: dimensionFilter\n          in: body\n          type: object\n          description: Dimension filters to restrict the report data.\n          value: '{{tools.dimensionFilter}}'\n        - name: metricFilter\n          in: body\n          type: object\n          description: Metric filters to restrict the report data.\n          value: '{{tools.metricFilter}}'\n        - name: offset\n          in: body\n          type: integer\n          description: Row offset for the report.\n          value: '{{tools.offset}}'\n        - name: limit\n          in: body\n          type: integer\n          description: The number of rows to return.\n          value: '{{tools.limit}}'\n        - name: orderBys\n          in: body\n          type: array\n          description: Specifies how rows are ordered\
  \ in the response.\n          value: '{{tools.orderBys}}'\n        - name: returnEntityQuota\n          in: body\n          type: boolean\n          description: Whether to return the current quota state for this Analytics property.\n          value: '{{tools.returnEntityQuota}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: acknowledge-user-data-collection\n        method: POST\n        path: /{property}:acknowledgeUserDataCollection\n        description: Acknowledges the terms of user data collection for the specified property.\n        inputParameters:\n        - name: property\n          in: path\n          type: string\n          description: 'Required. The property for which to acknowledge user data collection. Format: properties/{property_id}'\n        - name: acknowledgement\n          in: body\n          type: string\n          description: Required. An acknowledgement that the caller of this method understands the\
  \ terms of user data collection.\n          value: '{{tools.acknowledgement}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversion-events\n      path: /v1beta\n      operations:\n      - id: list-conversion-events\n        method: GET\n        path: /{parent}/conversionEvents\n        description: Returns a list of conversion events in the specified parent property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The resource name of the parent property. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - id: create-conversion-event\n        method: POST\n        path: /{parent}/conversionEvents\n        description: Creates a conversion event with the specified attributes.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The resource name of the parent property. Format: properties/{property_id}'\n        - name: eventName\n          in: body\n          type: string\n          description: Required. The event name for this conversion event.\n          value: '{{tools.eventName}}'\n        - name: countingMethod\n          in: body\n          type: string\n          description: The method by which conversions will be counted.\n          value: '{{tools.countingMethod}}'\n        - name: defaultConversionValue\n          in: body\n          type: object\n          description: Optional default value for a conversion event.\n          value: '{{tools.defaultConversionValue}}'\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-dimensions\n      path: /v1beta\n      operations:\n      - id: list-custom-dimensions\n        method: GET\n        path: /{parent}/customDimensions\n        description: Lists custom dimensions on a property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-custom-dimension\n        method: POST\n        path: /{parent}/customDimensions\n\
  \        description: Creates a custom dimension.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: displayName\n          in: body\n          type: string\n          description: Required. Display name for this custom dimension.\n          value: '{{tools.displayName}}'\n        - name: parameterName\n          in: body\n          type: string\n          description: Required. Immutable. Tagging parameter name for this custom dimension.\n          value: '{{tools.parameterName}}'\n        - name: scope\n          in: body\n          type: string\n          description: Required. Immutable. The scope of this dimension.\n          value: '{{tools.scope}}'\n        - name: description\n          in: body\n          type: string\n          description: Optional. Description for this custom dimension.\n          value: '{{tools.description}}'\n\
  \        - name: disallowAdsPersonalization\n          in: body\n          type: boolean\n          description: Optional. If true, sets this dimension as NPA and excludes it from ads personalization.\n          value: '{{tools.disallowAdsPersonalization}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-metrics\n      path: /v1beta\n      operations:\n      - id: list-custom-metrics\n        method: GET\n        path: /{parent}/customMetrics\n        description: Lists custom metrics on a property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description:\
  \ Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-custom-metric\n        method: POST\n        path: /{parent}/customMetrics\n        description: Creates a custom metric.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: displayName\n          in: body\n          type: string\n          description: Required. Display name for this custom metric.\n          value: '{{tools.displayName}}'\n        - name: parameterName\n          in: body\n          type: string\n          description: Required. Immutable. Tagging name for this custom metric.\n          value: '{{tools.parameterName}}'\n        - name: measurementUnit\n          in: body\n          type: string\n          description: Required. The type for\
  \ the custom metric's value.\n          value: '{{tools.measurementUnit}}'\n        - name: scope\n          in: body\n          type: string\n          description: Required. Immutable. The scope of this custom metric.\n          value: '{{tools.scope}}'\n        - name: description\n          in: body\n          type: string\n          description: Optional. Description for this custom metric.\n          value: '{{tools.description}}'\n        - name: restrictedMetricType\n          in: body\n          type: array\n          description: Optional. Types of restricted data that this metric may contain.\n          value: '{{tools.restrictedMetricType}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: archive-custom-metric\n        method: POST\n        path: /{name}:archive\n        description: Archives a custom metric on a property.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n\
  \          description: 'Required. The name of the custom metric to archive. Format: properties/{property_id}/customMetrics/{custom_metric_id}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-streams\n      path: /v1beta\n      operations:\n      - id: list-data-streams\n        method: GET\n        path: /{parent}/dataStreams\n        description: Lists data streams on a property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - id: create-data-stream\n        method: POST\n        path: /{parent}/dataStreams\n        description: Creates a data stream.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: type\n          in: body\n          type: string\n          description: Required. Immutable. The type of this DataStream resource.\n          value: '{{tools.type}}'\n        - name: displayName\n          in: body\n          type: string\n          description: Human-readable display name for the data stream.\n          value: '{{tools.displayName}}'\n        - name: webStreamData\n          in: body\n          type: object\n          description: Data specific to web streams.\n          value: '{{tools.webStreamData}}'\n        - name: androidAppStreamData\n          in: body\n          type: object\n       \
  \   description: Data specific to Android app streams.\n          value: '{{tools.androidAppStreamData}}'\n        - name: iosAppStreamData\n          in: body\n          type: object\n          description: Data specific to iOS app streams.\n          value: '{{tools.iosAppStreamData}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firebase-links\n      path: /v1beta\n      operations:\n      - id: list-firebase-links\n        method: GET\n        path: /{parent}/firebaseLinks\n        description: Lists FirebaseLinks on a property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type:\
  \ string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-firebase-link\n        method: POST\n        path: /{parent}/firebaseLinks\n        description: Creates a FirebaseLink.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: project\n          in: body\n          type: string\n          description: 'Required. Immutable. The Firebase project resource name. Format: projects/{project_id}'\n          value: '{{tools.project}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: google-ads-links\n      path: /v1beta\n      operations:\n      - id: list-google-ads-links\n        method: GET\n        path: /{parent}/googleAdsLinks\n\
  \        description: Lists GoogleAdsLinks on a property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-google-ads-link\n        method: POST\n        path: /{parent}/googleAdsLinks\n        description: Creates a GoogleAdsLink.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent property resource name. Format: properties/{property_id}'\n        - name: customerId\n\
  \          in: body\n          type: string\n          description: Required. Immutable. Google Ads customer ID.\n          value: '{{tools.customerId}}'\n        - name: adsPersonalizationEnabled\n          in: body\n          type: boolean\n          description: Enable personalized advertising features with this integration.\n          value: '{{tools.adsPersonalizationEnabled}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: update-google-ads-link\n        method: PATCH\n        path: /{name}\n        description: Updates a GoogleAdsLink on a property.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          description: 'Required. Resource name of the GoogleAdsLink. Format: properties/{property_id}/googleAdsLinks/{google_ads_link_id}'\n        - name: updateMask\n          in: query\n          type: string\n          description: Required. The list of fields to update. Field\
  \ names must be in snake_case.\n        - name: adsPersonalizationEnabled\n          in: body\n          type: boolean\n          description: Enable personalized advertising features with this integration.\n          value: '{{tools.adsPersonalizationEnabled}}'\n        - name: customerId\n          in: body\n          type: string\n          description: Immutable. Google Ads customer ID.\n          value: '{{tools.customerId}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: delete-google-ads-link\n        method: DELETE\n        path: /{name}\n        description: Deletes a GoogleAdsLink on a property.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          description: 'Required. Resource name of the GoogleAdsLink to delete. Format: properties/{property_id}/googleAdsLinks/{google_ads_link_id}'\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: measurement-protocol-secrets\n      path: /v1beta\n      operations:\n      - id: list-measurement-protocol-secrets\n        method: GET\n        path: /{parent}/measurementProtocolSecrets\n        description: Returns child MeasurementProtocolSecrets under the specified parent property.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The resource name of the parent stream. Format: properties/{property_id}/dataStreams/{data_stream_id}'\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of resources to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for retrieving the next page of results.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-measurement-protocol-secret\n        method: POST\n\
  \        path: /{parent}/measurementProtocolSecrets\n        description: Creates a measurement protocol secret.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          description: 'Required. The parent resource name. Format: properties/{property_id}/dataStreams/{data_stream_id}'\n        - name: displayName\n          in: body\n          type: string\n          description: Required. Human-readable display name for this secret.\n          value: '{{tools.displayName}}'\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-measurement-protocol-secret\n        method: GET\n        path: /{name}\n        description: Lookup for a single MeasurementProtocolSecret.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          description: 'Required. The name of the measurement protocol secret to look up. Format: properties/{property_id}/dataStreams/{data_stream_id}/measurementProtocolSecrets/{measurement_protocol_secret_id}'\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: ga-config-api\n    description: Unified REST API for Google Analytics configuration management.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Manage GA4 accounts\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all accessible accounts\n        call: ga-admin-api.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/account-summaries\n      name: account-summaries\n      description: View account summaries\n      operations:\n      - method: GET\n        name: list-account-summaries\n        description: List summaries of all accessible accounts\n        call: ga-admin-api.list-account-summaries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties\n  \
  \    name: properties\n      description: Manage GA4 properties\n      operations:\n      - method: GET\n        name: list-properties\n        description: List GA4 properties\n        call: ga-admin-api.list-properties\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-property\n        description: Create a GA4 property\n        call: ga-admin-api.create-property\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-streams\n      name: data-streams\n      description: Manage data streams\n      operations:\n      - method: GET\n        name: list-data-streams\n        description: List data streams on a property\n        call: ga-admin-api.list-data-streams\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-data-stream\n        description: Create a data stream\n\
  \        call: ga-admin-api.create-data-stream\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/custom-dimensions\n      name: custom-dimensions\n      description: Manage custom dimensions\n      operations:\n      - method: GET\n        name: list-custom-dimensions\n        description: List custom dimensions\n        call: ga-admin-api.list-custom-dimensions\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-custom-dimension\n        description: Create a custom dimension\n        call: ga-admin-api.create-custom-dimension\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/custom-metrics\n      name: custom-metrics\n      description: Manage custom metrics\n      operations:\n      - method: GET\n   \
  \     name: list-custom-metrics\n        description: List custom metrics\n        call: ga-admin-api.list-custom-metrics\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-custom-metric\n        description: Create a custom metric\n        call: ga-admin-api.create-custom-metric\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conversion-events\n      name: conversion-events\n      description: Manage conversion events\n      operations:\n      - method: GET\n        name: list-conversion-events\n        description: List conversion events\n        call: ga-admin-api.list-conversion-events\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-conversion-event\n        description:\
  \ Create a conversion event\n        call: ga-admin-api.create-conversion-event\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/change-history\n      name: change-history\n      description: Search change history\n      operations:\n      - method: POST\n        name: search-change-history-events\n        description: Search through account changes\n        call: ga-admin-api.search-change-history-events\n        with:\n          account: rest.account\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: ga-config-mcp\n    transport: http\n    description: MCP server for AI-assisted Google Analytics configuration management.\n    tools:\n    - name: list-accounts\n      description: List all accessible Google Analytics accounts\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.list-accounts\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-account-summaries\n      description: List summaries of all accessible accounts with their properties\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.list-account-summaries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provision-account-ticket\n      description: Request a ticket for creating a new account\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ga-admin-api.provision-account-ticket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-properties\n      description: List GA4 properties for an account\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.list-properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-property\n      description: Create a new GA4 property\n      hints:\n\
  \        readOnly: false\n        idempotent: false\n      call: ga-admin-api.create-property\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-streams\n      description: List data streams on a property\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.list-data-streams\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-data-stream\n      description: Create a new data stream on a property\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ga-admin-api.create-data-stream\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-custom-dimensions\n      description: List custom dimensions on a property\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.list-custom-dimensions\n      with:\n  \
  \      parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-custom-dimension\n      description: Create a custom dimension on a property\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ga-admin-api.create-custom-dimension\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-custom-metrics\n      description: List custom metrics on a property\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ga-admin-api.list-custom-metrics\n      with:\n    \n\n# --- truncated at 32 KB (33 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/google-analytics/refs/heads/main/capabilities/configuration-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-analytics/refs/heads/main/capabilities/configuration-management.yaml
tags:
- Google Analytics
- Configuration
- Admin
- Management
- GA4
tools:
- description: List all accessible Google Analytics accounts
  hints:
    idempotent: true
    readOnly: true
  name: list-accounts
- description: List summaries of all accessible accounts with their properties
  hints:
    idempotent: true
    readOnly: true
  name: list-account-summaries
- description: Request a ticket for creating a new account
  hints:
    idempotent: false
    readOnly: false
  name: provision-account-ticket
- description: List GA4 properties for an account
  hints:
    idempotent: true
    readOnly: true
  name: list-properties
- description: Create a new GA4 property
  hints:
    idempotent: false
    readOnly: false
  name: create-property
- description: List data streams on a property
  hints:
    idempotent: true
    readOnly: true
  name: list-data-streams
- description: Create a new data stream on a property
  hints:
    idempotent: false
    readOnly: false
  name: create-data-stream
- description: List custom dimensions on a property
  hints:
    idempotent: true
    readOnly: true
  name: list-custom-dimensions
- description: Create a custom dimension on a property
  hints:
    idempotent: false
    readOnly: false
  name: create-custom-dimension
- description: List custom metrics on a property
  hints:
    idempotent: true
    readOnly: true
  name: list-custom-metrics
- description: Create a custom metric on a property
  hints:
    idempotent: false
    readOnly: false
  name: create-custom-metric
- description: Archive a custom metric on a property
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: archive-custom-metric
- description: List conversion events on a property
  hints:
    idempotent: true
    readOnly: true
  name: list-conversion-events
- description: Create a conversion event on a property
  hints:
    idempotent: false
    readOnly: false
  name: create-conversion-event
- description: Search through all changes to an account or its children
  hints:
    idempotent: true
    readOnly: true
  name: search-change-history-events
- description: Acknowledge terms of user data collection for a property
  hints:
    idempotent: true
    readOnly: false
  name: acknowledge-user-data-collection
---
