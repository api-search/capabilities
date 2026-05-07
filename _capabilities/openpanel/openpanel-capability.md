---
categories: []
consumed_apis: []
description: OpenPanel API API capability.
layout: capability
name: OpenPanel API
operations:
- description: Deprecated direct event ingestion endpoint. Use /track instead.
  method: POST
  name: post-event
  path: /event/
- description: Identify or update a user profile.
  method: POST
  name: post-profile
  path: /profile/
- description: Increment a numeric property on a user profile.
  method: POST
  name: post-profile-increment
  path: /profile/increment
- description: Decrement a numeric property on a user profile.
  method: POST
  name: post-profile-decrement
  path: /profile/decrement
- description: Export a paginated list of raw events with optional filtering by date, profile, and event type.
  method: GET
  name: get-export-events
  path: /export/events
- description: Export aggregated chart/analytics data for a series of events over a time range.
  method: GET
  name: get-export-charts
  path: /export/charts
- description: Bulk import historical events.
  method: POST
  name: post-import-events
  path: /import/events
- description: Get an overview of key metrics for the project (sessions, pageviews, bounce rate, duration).
  method: GET
  name: get-insights-projectid-overview
  path: /insights/{projectId}/overview
- description: Get rolling active user counts over the last N days.
  method: GET
  name: get-insights-projectid-active-users
  path: /insights/{projectId}/active_users
- description: Get weekly retention series data.
  method: GET
  name: get-insights-projectid-retention
  path: /insights/{projectId}/retention
- description: Get retention cohort data.
  method: GET
  name: get-insights-projectid-retention-cohort
  path: /insights/{projectId}/retention/cohort
- description: Get the top pages by pageviews for the given date range.
  method: GET
  name: get-insights-projectid-pages-top
  path: /insights/{projectId}/pages/top
- description: Get entry or exit pages ranked by session count.
  method: GET
  name: get-insights-projectid-pages-entry-exit
  path: /insights/{projectId}/pages/entry_exit
- description: Get page-level performance metrics (bounce rate, avg duration, sessions).
  method: GET
  name: get-insights-projectid-pages-performance
  path: /insights/{projectId}/pages/performance
- description: Get aggregated website metrics including sessions, pageviews, and bounce rate.
  method: GET
  name: get-insights-projectid-metrics
  path: /insights/{projectId}/metrics
- description: Get the current number of live (active) visitors.
  method: GET
  name: get-insights-projectid-live
  path: /insights/{projectId}/live
- description: Get top pages with pageview counts for the selected date range.
  method: GET
  name: get-insights-projectid-pages
  path: /insights/{projectId}/pages
- description: Get top values for the "referrer" dimension.
  method: GET
  name: get-insights-projectid-referrer
  path: /insights/{projectId}/referrer
- description: Get top values for the "referrer_name" dimension.
  method: GET
  name: get-insights-projectid-referrer-name
  path: /insights/{projectId}/referrer_name
- description: Get top values for the "referrer_type" dimension.
  method: GET
  name: get-insights-projectid-referrer-type
  path: /insights/{projectId}/referrer_type
- description: Get top values for the "utm_source" dimension.
  method: GET
  name: get-insights-projectid-utm-source
  path: /insights/{projectId}/utm_source
- description: Get top values for the "utm_medium" dimension.
  method: GET
  name: get-insights-projectid-utm-medium
  path: /insights/{projectId}/utm_medium
- description: Get top values for the "utm_campaign" dimension.
  method: GET
  name: get-insights-projectid-utm-campaign
  path: /insights/{projectId}/utm_campaign
- description: Get top values for the "utm_term" dimension.
  method: GET
  name: get-insights-projectid-utm-term
  path: /insights/{projectId}/utm_term
- description: Get top values for the "utm_content" dimension.
  method: GET
  name: get-insights-projectid-utm-content
  path: /insights/{projectId}/utm_content
- description: Get top values for the "region" dimension.
  method: GET
  name: get-insights-projectid-region
  path: /insights/{projectId}/region
- description: Get top values for the "country" dimension.
  method: GET
  name: get-insights-projectid-country
  path: /insights/{projectId}/country
- description: Get top values for the "city" dimension.
  method: GET
  name: get-insights-projectid-city
  path: /insights/{projectId}/city
- description: Get top values for the "device" dimension.
  method: GET
  name: get-insights-projectid-device
  path: /insights/{projectId}/device
- description: Get top values for the "brand" dimension.
  method: GET
  name: get-insights-projectid-brand
  path: /insights/{projectId}/brand
- description: Get top values for the "model" dimension.
  method: GET
  name: get-insights-projectid-model
  path: /insights/{projectId}/model
- description: Get top values for the "browser" dimension.
  method: GET
  name: get-insights-projectid-browser
  path: /insights/{projectId}/browser
- description: Get top values for the "browser_version" dimension.
  method: GET
  name: get-insights-projectid-browser-version
  path: /insights/{projectId}/browser_version
- description: Get top values for the "os" dimension.
  method: GET
  name: get-insights-projectid-os
  path: /insights/{projectId}/os
- description: Get top values for the "os_version" dimension.
  method: GET
  name: get-insights-projectid-os-version
  path: /insights/{projectId}/os_version
- description: Get funnel conversion rates for a sequence of events.
  method: GET
  name: get-insights-projectid-funnel
  path: /insights/{projectId}/funnel
- description: Get traffic breakdown by referrer source.
  method: GET
  name: get-insights-projectid-traffic-referrers
  path: /insights/{projectId}/traffic/referrers
- description: Get traffic breakdown by geographic dimension (country, region, city).
  method: GET
  name: get-insights-projectid-traffic-geo
  path: /insights/{projectId}/traffic/geo
- description: Get traffic breakdown by device type, browser, or OS.
  method: GET
  name: get-insights-projectid-traffic-devices
  path: /insights/{projectId}/traffic/devices
- description: Get user flow paths before, after, or between specified events.
  method: GET
  name: get-insights-projectid-user-flow
  path: /insights/{projectId}/user_flow
- description: Get engagement metrics for the project.
  method: GET
  name: get-insights-projectid-engagement
  path: /insights/{projectId}/engagement
- description: Query events with optional filters for date range, profile, and properties.
  method: GET
  name: get-insights-projectid-events
  path: /insights/{projectId}/events
- description: List all distinct event names tracked in the project.
  method: GET
  name: get-insights-projectid-events-names
  path: /insights/{projectId}/events/names
- description: List all property keys for a given event name.
  method: GET
  name: get-insights-projectid-events-properties
  path: /insights/{projectId}/events/properties
- description: Get the top values for a specific event property key.
  method: GET
  name: get-insights-projectid-events-property-values
  path: /insights/{projectId}/events/property_values
- description: Search and filter user profiles.
  method: GET
  name: get-insights-projectid-profiles
  path: /insights/{projectId}/profiles
- description: Get a single user profile with their recent events.
  method: GET
  name: get-insights-projectid-profiles-profileid
  path: /insights/{projectId}/profiles/{profileId}
- description: Get sessions for a specific user profile.
  method: GET
  name: get-insights-projectid-profiles-profileid-sessio
  path: /insights/{projectId}/profiles/{profileId}/sessions
- description: Get aggregated metrics for a specific user profile.
  method: GET
  name: get-insights-projectid-profiles-profileid-metric
  path: /insights/{projectId}/profiles/{profileId}/metrics
- description: Query sessions with optional filters.
  method: GET
  name: get-insights-projectid-sessions
  path: /insights/{projectId}/sessions
- description: List all group types defined in the project.
  method: GET
  name: get-insights-projectid-groups-types
  path: /insights/{projectId}/groups/types
- description: Search and filter groups.
  method: GET
  name: get-insights-projectid-groups
  path: /insights/{projectId}/groups
- description: Get a single group with its members.
  method: GET
  name: get-insights-projectid-groups-groupid
  path: /insights/{projectId}/groups/{groupId}
- description: Get the data for a saved report.
  method: GET
  name: get-insights-projectid-reports-reportid-data
  path: /insights/{projectId}/reports/{reportId}/data
- description: Get a Google Search Console performance overview (clicks, impressions, CTR, position).
  method: GET
  name: get-insights-projectid-gsc-overview
  path: /insights/{projectId}/gsc/overview
- description: Get top pages from Google Search Console.
  method: GET
  name: get-insights-projectid-gsc-pages
  path: /insights/{projectId}/gsc/pages
- description: Get detailed GSC metrics for a specific page URL.
  method: GET
  name: get-insights-projectid-gsc-pages-details
  path: /insights/{projectId}/gsc/pages/details
- description: Get top search queries from Google Search Console.
  method: GET
  name: get-insights-projectid-gsc-queries
  path: /insights/{projectId}/gsc/queries
- description: Get detailed GSC metrics for a specific search query.
  method: GET
  name: get-insights-projectid-gsc-queries-details
  path: /insights/{projectId}/gsc/queries/details
- description: Get GSC query opportunities (high impressions, low CTR).
  method: GET
  name: get-insights-projectid-gsc-queries-opportunities
  path: /insights/{projectId}/gsc/queries/opportunities
personas: []
provider_name: OpenPanel
provider_slug: openpanel
search_terms:
- get insights projectid gsc pages details
- get page-level performance metrics (bounce rate, avg duration, sessions).
- funnels
- get rolling active user counts over the last n days.
- get export events
- api
- get top values for the "device" dimension.
- get export charts
- get insights projectid os
- get top pages from google search console.
- get sessions for a specific user profile.
- get top values for the "model" dimension.
- user analytics
- get a google search console performance overview (clicks, impressions, ctr, position).
- event tracking
- get insights projectid pages performance
- get insights projectid active users
- get insights projectid device
- get insights projectid groups groupid
- get insights projectid utm source
- get insights projectid model
- get traffic breakdown by device type, browser, or os.
- query sessions with optional filters.
- get insights projectid retention cohort
- list all group types defined in the project.
- get insights projectid utm content
- identify or update a user profile.
- get insights projectid funnel
- openpanel
- get top values for the "utm_campaign" dimension.
- get insights projectid profiles profileid metric
- search and filter groups.
- get insights projectid browser version
- get insights projectid reports reportid data
- post import events
- get insights projectid gsc queries details
- get insights projectid brand
- get insights projectid browser
- get insights projectid events properties
- get insights projectid live
- deprecated direct event ingestion endpoint. use /track instead.
- get insights projectid engagement
- get insights projectid gsc overview
- get aggregated metrics for a specific user profile.
- get aggregated website metrics including sessions, pageviews, and bounce rate.
- get insights projectid utm medium
- get insights projectid region
- get insights projectid groups types
- get entry or exit pages ranked by session count.
- get top values for the "brand" dimension.
- get top pages with pageview counts for the selected date range.
- decrement a numeric property on a user profile.
- get top values for the "referrer_type" dimension.
- get the top values for a specific event property key.
- list all property keys for a given event name.
- get insights projectid profiles profileid sessio
- post profile decrement
- get insights projectid metrics
- get insights projectid traffic geo
- get insights projectid referrer name
- get top values for the "utm_source" dimension.
- export aggregated chart/analytics data for a series of events over a time range.
- get insights projectid os version
- get insights projectid groups
- get traffic breakdown by referrer source.
- get insights projectid events property values
- get insights projectid referrer
- get insights projectid pages entry exit
- list all distinct event names tracked in the project.
- get top values for the "utm_content" dimension.
- get funnel conversion rates for a sequence of events.
- get insights projectid gsc queries
- get top values for the "browser" dimension.
- get retention cohort data.
- product analytics
- get insights projectid pages
- get top values for the "region" dimension.
- get insights projectid events names
- get a single group with its members.
- get weekly retention series data.
- get insights projectid traffic referrers
- increment a numeric property on a user profile.
- get detailed gsc metrics for a specific search query.
- search and filter user profiles.
- get insights projectid referrer type
- get top values for the "city" dimension.
- get top search queries from google search console.
- get insights projectid gsc pages
- get insights projectid sessions
- get gsc query opportunities (high impressions, low ctr).
- get insights projectid utm term
- get engagement metrics for the project.
- get the top pages by pageviews for the given date range.
- get top values for the "utm_medium" dimension.
- get top values for the "referrer" dimension.
- get insights projectid profiles profileid
- get insights projectid utm campaign
- get insights projectid gsc queries opportunities
- get top values for the "country" dimension.
- get an overview of key metrics for the project (sessions, pageviews, bounce rate, duration).
- get insights projectid retention
- get insights projectid country
- get top values for the "utm_term" dimension.
- get top values for the "os" dimension.
- open source
- get top values for the "referrer_name" dimension.
- get insights projectid pages top
- get insights projectid events
- post profile increment
- get insights projectid user flow
- get detailed gsc metrics for a specific page url.
- get insights projectid overview
- get top values for the "os_version" dimension.
- get a single user profile with their recent events.
- real-time analytics
- get insights projectid profiles
- get the current number of live (active) visitors.
- get top values for the "browser_version" dimension.
- query events with optional filters for date range, profile, and properties.
- get insights projectid traffic devices
- post profile
- export a paginated list of raw events with optional filtering by date, profile, and event type.
- get the data for a saved report.
- post event
- bulk import historical events.
- get traffic breakdown by geographic dimension (country, region, city).
- get user flow paths before, after, or between specified events.
- get insights projectid city
slug: openpanel-capability
source_filename: openpanel-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenPanel API\n  description: OpenPanel API API capability.\n  tags:\n  - Openpanel\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openpanel\n    baseUri: https://api.example.com\n    description: OpenPanel API HTTP API.\n    resources:\n    - name: event\n      path: /event/\n      operations:\n      - name: post-event\n        method: POST\n        description: Deprecated direct event ingestion endpoint. Use /track instead.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profile\n      path: /profile/\n      operations:\n      - name: post-profile\n        method: POST\n        description: Identify or update a user profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profile-increment\n\
  \      path: /profile/increment\n      operations:\n      - name: post-profile-increment\n        method: POST\n        description: Increment a numeric property on a user profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profile-decrement\n      path: /profile/decrement\n      operations:\n      - name: post-profile-decrement\n        method: POST\n        description: Decrement a numeric property on a user profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export-events\n      path: /export/events\n      operations:\n      - name: get-export-events\n        method: GET\n        description: Export a paginated list of raw events with optional filtering by date, profile, and event type.\n        inputParameters:\n        - name: project_id\n          in: query\n          type: string\n      \
  \  - name: projectId\n          in: query\n          type: string\n        - name: profileId\n          in: query\n          type: string\n        - name: event\n          in: query\n          type: string\n        - name: start\n          in: query\n          type: string\n        - name: end\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: includes\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export-charts\n      path: /export/charts\n      operations:\n      - name: get-export-charts\n        method: GET\n        description: Export aggregated chart/analytics data for a series of events over a time range.\n        inputParameters:\n        - name: breakdowns\n          in: query\n          type: array\n\
  \          description: Array of dimensions to break down the data by\n        - name: interval\n          in: query\n          type: string\n          description: The time interval for data aggregation (e.g., day, week, month)\n        - name: range\n          in: query\n          type: string\n          description: The time range for which data should be displayed\n        - name: previous\n          in: query\n          type: boolean\n          description: Whether to show data from the previous period for comparison\n        - name: startDate\n          in: query\n          type: string\n          description: Custom start date for the data range (overrides range if provided)\n        - name: endDate\n          in: query\n          type: string\n          description: Custom end date for the data range (overrides range if provided)\n        - name: project_id\n          in: query\n          type: string\n        - name: projectId\n          in: query\n          type: string\n   \
  \     - name: series\n          in: query\n          type: array\n        - name: events\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: import-events\n      path: /import/events\n      operations:\n      - name: post-import-events\n        method: POST\n        description: Bulk import historical events.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-overview\n      path: /insights/{projectId}/overview\n      operations:\n      - name: get-insights-projectid-overview\n        method: GET\n        description: Get an overview of key metrics for the project (sessions, pageviews, bounce rate, duration).\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n\
  \          type: string\n        - name: range\n          in: query\n          type: string\n        - name: interval\n          in: query\n          type: string\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-active-users\n      path: /insights/{projectId}/active_users\n      operations:\n      - name: get-insights-projectid-active-users\n        method: GET\n        description: Get rolling active user counts over the last N days.\n        inputParameters:\n        - name: days\n          in: query\n          type: integer\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-retention\n\
  \      path: /insights/{projectId}/retention\n      operations:\n      - name: get-insights-projectid-retention\n        method: GET\n        description: Get weekly retention series data.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-retention-cohort\n      path: /insights/{projectId}/retention/cohort\n      operations:\n      - name: get-insights-projectid-retention-cohort\n        method: GET\n        description: Get retention cohort data.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-pages-top\n      path: /insights/{projectId}/pages/top\n\
  \      operations:\n      - name: get-insights-projectid-pages-top\n        method: GET\n        description: Get the top pages by pageviews for the given date range.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-pages-entry-exit\n      path: /insights/{projectId}/pages/entry_exit\n      operations:\n      - name: get-insights-projectid-pages-entry-exit\n        method: GET\n        description: Get entry or exit pages ranked by session count.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n      \
  \  - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: mode\n          in: query\n          type: string\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-pages-performance\n      path: /insights/{projectId}/pages/performance\n      operations:\n      - name: get-insights-projectid-pages-performance\n        method: GET\n        description: Get page-level performance metrics (bounce rate, avg duration, sessions).\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: search\n          in: query\n\
  \          type: string\n        - name: sortBy\n          in: query\n          type: string\n        - name: sortOrder\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-metrics\n      path: /insights/{projectId}/metrics\n      operations:\n      - name: get-insights-projectid-metrics\n        method: GET\n        description: Get aggregated website metrics including sessions, pageviews, and bounce rate.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: filters\n         \
  \ in: query\n          type: array\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-live\n      path: /insights/{projectId}/live\n      operations:\n      - name: get-insights-projectid-live\n        method: GET\n        description: Get the current number of live (active) visitors.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-pages\n      path: /insights/{projectId}/pages\n      operations:\n      - name: get-insights-projectid-pages\n        method: GET\n        description: Get top pages with pageview counts for the selected date range.\n        inputParameters:\n\
  \        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-referrer\n      path: /insights/{projectId}/referrer\n      operations:\n      - name: get-insights-projectid-referrer\n        method: GET\n        description: Get top values for the \"referrer\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n\
  \          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-referrer-name\n      path: /insights/{projectId}/referrer_name\n      operations:\n      - name: get-insights-projectid-referrer-name\n        method: GET\n        description: Get top values for the \"referrer_name\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n \
  \         in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-referrer-type\n      path: /insights/{projectId}/referrer_type\n      operations:\n      - name: get-insights-projectid-referrer-type\n        method: GET\n        description: Get top values for the \"referrer_type\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n    \
  \      in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-utm-source\n      path: /insights/{projectId}/utm_source\n      operations:\n      - name: get-insights-projectid-utm-source\n        method: GET\n        description: Get top values for the \"utm_source\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n\
  \          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-utm-medium\n      path: /insights/{projectId}/utm_medium\n      operations:\n      - name: get-insights-projectid-utm-medium\n        method: GET\n        description: Get top values for the \"utm_medium\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type:\
  \ number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-utm-campaign\n      path: /insights/{projectId}/utm_campaign\n      operations:\n      - name: get-insights-projectid-utm-campaign\n        method: GET\n        description: Get top values for the \"utm_campaign\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-utm-term\n      path: /insights/{projectId}/utm_term\n      operations:\n      - name: get-insights-projectid-utm-term\n        method: GET\n        description: Get top values for the \"utm_term\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-utm-content\n      path: /insights/{projectId}/utm_content\n      operations:\n      - name: get-insights-projectid-utm-content\n        method: GET\n        description: Get top values for the \"utm_content\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-region\n\
  \      path: /insights/{projectId}/region\n      operations:\n      - name: get-insights-projectid-region\n        method: GET\n        description: Get top values for the \"region\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-country\n      path: /insights/{projectId}/country\n      operations:\n      - name: get-insights-projectid-country\n\
  \        method: GET\n        description: Get top values for the \"country\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-city\n      path: /insights/{projectId}/city\n      operations:\n      - name: get-insights-projectid-city\n        method: GET\n        description: Get top values for the \"city\" dimension.\n        inputParameters:\n\
  \        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-device\n      path: /insights/{projectId}/device\n      operations:\n      - name: get-insights-projectid-device\n        method: GET\n        description: Get top values for the \"device\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n   \
  \       in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-brand\n      path: /insights/{projectId}/brand\n      operations:\n      - name: get-insights-projectid-brand\n        method: GET\n        description: Get top values for the \"brand\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type:\
  \ string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-model\n      path: /insights/{projectId}/model\n      operations:\n      - name: get-insights-projectid-model\n        method: GET\n        description: Get top values for the \"model\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n  \
  \        in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-browser\n      path: /insights/{projectId}/browser\n      operations:\n      - name: get-insights-projectid-browser\n        method: GET\n        description: Get top values for the \"browser\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n        \
  \  type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-browser-version\n      path: /insights/{projectId}/browser_version\n      operations:\n      - name: get-insights-projectid-browser-version\n        method: GET\n        description: Get top values for the \"browser_version\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-os\n      path: /insights/{projectId}/os\n      operations:\n      - name: get-insights-projectid-os\n        method: GET\n        description: Get top values for the \"os\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-os-version\n      path: /insights/{projectId}/os_version\n      operations:\n      - name: get-insights-projectid-os-version\n        method: GET\n        description: Get top values for the \"os_version\" dimension.\n        inputParameters:\n        - name: filters\n          in: query\n          type: array\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: cursor\n          in: query\n          type: number\n        - name: limit\n          in: query\n          type: number\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-funnel\n\
  \      path: /insights/{projectId}/funnel\n      operations:\n      - name: get-insights-projectid-funnel\n        method: GET\n        description: Get funnel conversion rates for a sequence of events.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: steps\n          in: query\n          type: string\n          required: true\n        - name: windowHours\n          in: query\n          type: integer\n        - name: groupBy\n          in: query\n          type: string\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-traffic-referrers\n      path: /insights/{projectId}/traffic/referrers\n\
  \      operations:\n      - name: get-insights-projectid-traffic-referrers\n        method: GET\n        description: Get traffic breakdown by referrer source.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: breakdown\n          in: query\n          type: string\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-traffic-geo\n      path: /insights/{projectId}/traffic/geo\n      operations:\n      - name: get-insights-projectid-traffic-geo\n        method: GET\n        description: Get traffic breakdown by geographic dimension (country, region, city).\n        inputParameters:\n      \
  \  - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: breakdown\n          in: query\n          type: string\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-traffic-devices\n      path: /insights/{projectId}/traffic/devices\n      operations:\n      - name: get-insights-projectid-traffic-devices\n        method: GET\n        description: Get traffic breakdown by device type, browser, or OS.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n\
  \        - name: breakdown\n          in: query\n          type: string\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-user-flow\n      path: /insights/{projectId}/user_flow\n      operations:\n      - name: get-insights-projectid-user-flow\n        method: GET\n        description: Get user flow paths before, after, or between specified events.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: startEvent\n          in: query\n          type: string\n          required: true\n        - name: endEvent\n          in: query\n          type: string\n        - name: mode\n          in:\
  \ query\n          type: string\n        - name: steps\n          in: query\n          type: integer\n        - name: exclude\n          in: query\n          type: string\n        - name: include\n          in: query\n          type: string\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-engagement\n      path: /insights/{projectId}/engagement\n      operations:\n      - name: get-insights-projectid-engagement\n        method: GET\n        description: Get engagement metrics for the project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights-projectid-events\n    \
  \  path: /insights/{projectId}/events\n      operations:\n      - name: get-insights-projectid-events\n        method: GET\n        description: Query events with optional filters for date range, profile, and properties.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: range\n          in: query\n          type: string\n        - name: eventNames\n          in: query\n          type: string\n        - name: path\n          in: query\n          type: string\n        - name: country\n          in: query\n          type: string\n        - name: city\n          in: query\n          type: string\n        - name: device\n          in: query\n          type: string\n        - name: browser\n          in: query\n          type: string\n        - name: os\n          in: query\n          type: string\n        - name: referrer\n \n\n# --- truncated at 32 KB (125\
  \ KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/openpanel/refs/heads/main/capabilities/openpanel-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openpanel/refs/heads/main/capabilities/openpanel-capability.yaml
tags:
- Openpanel
- API
tools:
- description: Deprecated direct event ingestion endpoint. Use /track instead.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-event
- description: Identify or update a user profile.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-profile
- description: Increment a numeric property on a user profile.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-profile-increment
- description: Decrement a numeric property on a user profile.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-profile-decrement
- description: Export a paginated list of raw events with optional filtering by date, profile, and event type.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-export-events
- description: Export aggregated chart/analytics data for a series of events over a time range.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-export-charts
- description: Bulk import historical events.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-import-events
- description: Get an overview of key metrics for the project (sessions, pageviews, bounce rate, duration).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-overview
- description: Get rolling active user counts over the last N days.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-active-users
- description: Get weekly retention series data.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-retention
- description: Get retention cohort data.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-retention-cohort
- description: Get the top pages by pageviews for the given date range.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-pages-top
- description: Get entry or exit pages ranked by session count.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-pages-entry-exit
- description: Get page-level performance metrics (bounce rate, avg duration, sessions).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-pages-performance
- description: Get aggregated website metrics including sessions, pageviews, and bounce rate.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-metrics
- description: Get the current number of live (active) visitors.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-live
- description: Get top pages with pageview counts for the selected date range.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-pages
- description: Get top values for the "referrer" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-referrer
- description: Get top values for the "referrer_name" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-referrer-name
- description: Get top values for the "referrer_type" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-referrer-type
- description: Get top values for the "utm_source" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-utm-source
- description: Get top values for the "utm_medium" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-utm-medium
- description: Get top values for the "utm_campaign" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-utm-campaign
- description: Get top values for the "utm_term" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-utm-term
- description: Get top values for the "utm_content" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-utm-content
- description: Get top values for the "region" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-region
- description: Get top values for the "country" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-country
- description: Get top values for the "city" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-city
- description: Get top values for the "device" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-device
- description: Get top values for the "brand" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-brand
- description: Get top values for the "model" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-model
- description: Get top values for the "browser" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-browser
- description: Get top values for the "browser_version" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-browser-version
- description: Get top values for the "os" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-os
- description: Get top values for the "os_version" dimension.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-os-version
- description: Get funnel conversion rates for a sequence of events.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-funnel
- description: Get traffic breakdown by referrer source.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-traffic-referrers
- description: Get traffic breakdown by geographic dimension (country, region, city).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-traffic-geo
- description: Get traffic breakdown by device type, browser, or OS.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-traffic-devices
- description: Get user flow paths before, after, or between specified events.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-user-flow
- description: Get engagement metrics for the project.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-engagement
- description: Query events with optional filters for date range, profile, and properties.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-events
- description: List all distinct event names tracked in the project.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-events-names
- description: List all property keys for a given event name.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-events-properties
- description: Get the top values for a specific event property key.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-events-property-values
- description: Search and filter user profiles.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-profiles
- description: Get a single user profile with their recent events.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-profiles-profileid
- description: Get sessions for a specific user profile.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-profiles-profileid-sessio
- description: Get aggregated metrics for a specific user profile.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-profiles-profileid-metric
- description: Query sessions with optional filters.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-sessions
- description: List all group types defined in the project.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-groups-types
- description: Search and filter groups.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-groups
- description: Get a single group with its members.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-groups-groupid
- description: Get the data for a saved report.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-reports-reportid-data
- description: Get a Google Search Console performance overview (clicks, impressions, CTR, position).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-gsc-overview
- description: Get top pages from Google Search Console.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-gsc-pages
- description: Get detailed GSC metrics for a specific page URL.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-gsc-pages-details
- description: Get top search queries from Google Search Console.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-gsc-queries
- description: Get detailed GSC metrics for a specific search query.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-gsc-queries-details
- description: Get GSC query opportunities (high impressions, low CTR).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-insights-projectid-gsc-queries-opportunities
---
