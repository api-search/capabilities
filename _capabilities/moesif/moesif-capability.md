---
categories: []
consumed_apis: []
description: Management API to query data in Moesif. You can use the management API to export data for custom reports or to build custom dashboards.
layout: capability
name: Management API
operations:
- description: Update a Company
  method: POST
  name: updatecompanies
  path: /search/~/companies
- description: Update Companies in Batch
  method: POST
  name: batchupdatecompanies
  path: /search/~/companies/batch
- description: Get a Company
  method: GET
  name: getcompany
  path: /search/~/companies/{id}
- description: Delete a Company
  method: DELETE
  name: deletecompany
  path: /search/~/companies/{id}
- description: Get the Subscriptions of a Company
  method: GET
  name: getcompanysubscriptions
  path: /search/~/companies/{id}/subscriptions
- description: Count Companies
  method: POST
  name: countcompanies
  path: /search/~/count/companies
- description: Count Events
  method: POST
  name: countevents
  path: /search/~/count/events
- description: Count Users
  method: POST
  name: countusers
  path: /search/~/count/users
- description: Get an Event
  method: GET
  name: getevent
  path: /search/~/events/{id}
- description: Get Property Mapping for Companies
  method: GET
  name: getproperties
  path: /search/~/mappings/companies/properties
- description: Get Property Mapping for CompanyMetrics
  method: GET
  name: getproperties
  path: /search/~/mappings/companymetrics/properties
- description: Get Property Mapping for Events
  method: GET
  name: getproperties
  path: /search/~/mappings/events/properties
- description: Get Property Mapping for Events Request Body
  method: GET
  name: getrequestbodyproperties
  path: /search/~/mappings/events/request/body/properties
- description: Get Property Mapping for Events Response Body
  method: GET
  name: getresponsebodyproperties
  path: /search/~/mappings/events/response/body/properties
- description: Get Property Mapping for UserMetrics
  method: GET
  name: getproperties
  path: /search/~/mappings/usermetrics/properties
- description: Get Property Mapping for Users
  method: GET
  name: getproperties
  path: /search/~/mappings/users/properties
- description: Search CompanyMetrics/Companies
  method: POST
  name: searchcompanymetrics
  path: /search/~/search/companymetrics/companies
- description: Search Events
  method: POST
  name: searchevents
  path: /search/~/search/events
- description: Search UserMetrics/Users
  method: POST
  name: searchusermetrics
  path: /search/~/search/usermetrics/users
- description: Create or Update a Subscription
  method: POST
  name: createsubscription
  path: /search/~/subscriptions
- description: Create or Update Subscriptions in Batch
  method: POST
  name: batchcreatesubscriptions
  path: /search/~/subscriptions/batch
- description: Get a Subscription
  method: GET
  name: getsubscription
  path: /search/~/subscriptions/{id}
- description: Update a User
  method: POST
  name: updateusers
  path: /search/~/users
- description: Update Users in Batch
  method: POST
  name: batchupdateusers
  path: /search/~/users/batch
- description: Get a User
  method: GET
  name: getuser
  path: /search/~/users/{id}
- description: Delete a User
  method: DELETE
  name: deleteuser
  path: /search/~/users/{id}
- description: Search Events in saved public Workspace
  method: POST
  name: searchpublicworkspaces
  path: /search/~/workspaces/{workspaceId}/search
- description: Get new Workspace Token
  method: GET
  name: getworkspacetoken
  path: /workspaces/access_token
- description: Get a Public Workspace
  method: GET
  name: getpublicworkspace
  path: /workspaces/public/{id}
- description: Create a new App
  method: POST
  name: addapp
  path: /~/apps
- description: Gets Apps
  method: GET
  name: getapps
  path: /~/apps
- description: Update Apps
  method: POST
  name: updateapp
  path: /~/apps/{id}
- description: Delete Apps
  method: DELETE
  name: deleteapp
  path: /~/apps/{id}
- description: Create a new Moesif Plan
  method: POST
  name: createmoesifplan
  path: /~/billing/catalog/plans
- description: List all Moesif Plans
  method: GET
  name: listmoesifplans
  path: /~/billing/catalog/plans
- description: Get a Moesif Plan
  method: GET
  name: getmoesifplan
  path: /~/billing/catalog/plans/{id}
- description: Delete a Moesif Plan
  method: DELETE
  name: deletemoesifplan
  path: /~/billing/catalog/plans/{id}
- description: Update a Moesif Plan
  method: PUT
  name: updatemoesifplan
  path: /~/billing/catalog/plans/{id}
- description: Create a new Moesif Price
  method: POST
  name: createmoesifprice
  path: /~/billing/catalog/prices
- description: List all Moesif Prices for a specific Plan
  method: GET
  name: listmoesifprices
  path: /~/billing/catalog/prices
- description: Get a Moesif Price
  method: GET
  name: getmoesifprice
  path: /~/billing/catalog/prices/{id}
- description: Delete a Moesif Price
  method: DELETE
  name: deletemoesifprice
  path: /~/billing/catalog/prices/{id}
- description: Update a Moesif Price
  method: PUT
  name: updatemoesifprice
  path: /~/billing/catalog/prices/{id}
- description: List Billing Meters
  method: GET
  name: listmeters
  path: /~/billing/meters
- description: Get Billing Meter by id
  method: GET
  name: getmeter
  path: /~/billing/meters/{meterId}
- description: Delete Billing Meter by id
  method: DELETE
  name: deletemeter
  path: /~/billing/meters/{meterId}
- description: Get BillingReports
  method: GET
  name: getbillingreports
  path: /~/billing/reports
- description: Post BillingReports Balance Transactions
  method: POST
  name: createbalancetransaction
  path: /~/billing/reports/balance_transactions
- description: Get BillingReports' values for a given meter and time range for a single company or all companies
  method: GET
  name: getbillingreportsmetrics
  path: /~/billing/reports/metrics
- description: Create New Cohort
  method: POST
  name: createcohort
  path: /~/cohorts
- description: Get Cohorts
  method: GET
  name: getcohorts
  path: /~/cohorts
- description: Update a Cohort
  method: POST
  name: updatecohort
  path: /~/cohorts/{cohortId}
- description: Get Cohort
  method: GET
  name: getcohort
  path: /~/cohorts/{cohortId}
- description: Delete Cohort
  method: DELETE
  name: deletecohort
  path: /~/cohorts/{cohortId}
- description: Delete Sample Rate for a Cohort
  method: DELETE
  name: deletecohortsamplerate
  path: /~/cohorts/{cohortId}/sample_rate
- description: Delete a Dashboard
  method: DELETE
  name: deletedashboards
  path: /~/dashboard/{dashId}
- description: Copy Dashboard
  method: POST
  name: copydashboard
  path: /~/dashboard/{id}/copy
- description: Create New Dashboard
  method: POST
  name: createdashboard
  path: /~/dashboards
- description: Get a Dashboard
  method: GET
  name: getdashboards
  path: /~/dashboards
- description: Copy All Dashboards
  method: POST
  name: copyalldashboards
  path: /~/dashboards/copy
personas: []
provider_name: Moesif
provider_slug: moesif
search_terms:
- update users in batch
- getcompanysubscriptions
- create a new moesif price
- get property mapping for companies
- get property mapping for events request body
- getworkspacetoken
- get billingreports' values for a given meter and time range for a single company or all companies
- delete sample rate for a cohort
- analytics
- get a moesif price
- get billing meter by id
- delete billing meter by id
- insights
- getcohorts
- countevents
- listmoesifplans
- getsubscription
- createsubscription
- list all moesif plans
- get a public workspace
- monetization
- copy dashboard
- updateapp
- api
- get new workspace token
- deletemoesifplan
- search usermetrics/users
- createbalancetransaction
- batchcreatesubscriptions
- get the subscriptions of a company
- batchupdateusers
- getmoesifplan
- count companies
- getuser
- getevent
- copy all dashboards
- getmoesifprice
- create new cohort
- deleteuser
- update companies in batch
- get a dashboard
- searchcompanymetrics
- getmeter
- updatecompanies
- create new dashboard
- count events
- search events
- update a cohort
- search companymetrics/companies
- addapp
- get an event
- deletemeter
- createcohort
- delete cohort
- getbillingreportsmetrics
- countcompanies
- getpublicworkspace
- listmeters
- gets apps
- get property mapping for events
- create or update subscriptions in batch
- get property mapping for users
- create or update a subscription
- get a moesif plan
- createmoesifprice
- updatemoesifprice
- getcohort
- get property mapping for usermetrics
- search events in saved public workspace
- searchevents
- getproperties
- delete apps
- delete a moesif price
- get cohorts
- get property mapping for events response body
- post billingreports balance transactions
- deleteapp
- update a moesif plan
- update a company
- copydashboard
- searchpublicworkspaces
- getrequestbodyproperties
- deletemoesifprice
- get property mapping for companymetrics
- delete a dashboard
- update apps
- list billing meters
- getdashboards
- create a new moesif plan
- listmoesifprices
- getresponsebodyproperties
- getapps
- copyalldashboards
- delete a company
- createdashboard
- delete a moesif plan
- get billingreports
- create a new app
- searchusermetrics
- getcompany
- delete a user
- get cohort
- batchupdatecompanies
- count users
- createmoesifplan
- deletecompany
- updateusers
- deletecohort
- deletedashboards
- getbillingreports
- moesif
- get a subscription
- updatemoesifplan
- updatecohort
- get a company
- countusers
- platform
- get a user
- list all moesif prices for a specific plan
- deletecohortsamplerate
- update a user
- update a moesif price
slug: moesif-capability
source_filename: moesif-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Management API\n  description: Management API to query data in Moesif. You can use the management API to export data for custom reports or\n    to build custom dashboards.\n  tags:\n  - Moesif\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: moesif\n    baseUri: https://api.moesif.com/v1\n    description: Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MOESIF_TOKEN}}'\n    resources:\n    - name: search-companies\n      path: /search/~/companies\n      operations:\n      - name: updatecompanies\n        method: POST\n        description: Update a Company\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: search-companies-batch\n      path: /search/~/companies/batch\n      operations:\n      - name: batchupdatecompanies\n        method: POST\n        description: Update Companies in Batch\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-companies-id\n      path: /search/~/companies/{id}\n      operations:\n      - name: getcompany\n        method: GET\n        description: Get a Company\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecompany\n        method: DELETE\n        description: Delete a Company\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: delete_events\n          in: query\n          type: boolean\n          description: Delete events associated with the company which can be set to true or false(default)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-companies-id-subscriptions\n      path: /search/~/companies/{id}/subscriptions\n      operations:\n      - name: getcompanysubscriptions\n        method: GET\n        description:\
  \ Get the Subscriptions of a Company\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-count-companies\n      path: /search/~/count/companies\n      operations:\n      - name: countcompanies\n        method: POST\n        description: Count Companies\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-count-events\n\
  \      path: /search/~/count/events\n      operations:\n      - name: countevents\n        method: POST\n        description: Count Events\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: from\n          in: query\n          type: string\n          required: true\n          description: The start date, which can be absolute such as 2019-07-01T00:00:00Z or relative such as -24h\n        - name: to\n          in: query\n          type: string\n          required: true\n          description: The end date, which can be absolute such as 2019-07-02T00:00:00Z or relative such as now\n        - name: track_total_hits\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-count-users\n      path: /search/~/count/users\n\
  \      operations:\n      - name: countusers\n        method: POST\n        description: Count Users\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-events-id\n      path: /search/~/events/{id}\n      operations:\n      - name: getevent\n        method: GET\n        description: Get an Event\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: event_time\n          in: query\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-mappings-companies-properties\n      path: /search/~/mappings/companies/properties\n      operations:\n      - name: getproperties\n        method: GET\n        description: Get Property Mapping for Companies\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-mappings-companymetrics-properties\n      path: /search/~/mappings/companymetrics/properties\n      operations:\n      - name: getproperties\n        method: GET\n        description: Get Property Mapping for CompanyMetrics\n        inputParameters:\n        - name: orgId\n          in: path\n          type:\
  \ string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-mappings-events-properties\n      path: /search/~/mappings/events/properties\n      operations:\n      - name: getproperties\n        method: GET\n        description: Get Property Mapping for Events\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n        - name: to\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: search-mappings-events-request-body-properties\n      path: /search/~/mappings/events/request/body/properties\n      operations:\n      - name: getrequestbodyproperties\n        method: GET\n        description: Get Property Mapping for Events Request Body\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n          required: true\n        - name: to\n          in: query\n          type: string\n          required: true\n        - name: include_values\n          in: query\n          type: boolean\n        - name: key_path\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-mappings-events-response-body-properties\n\
  \      path: /search/~/mappings/events/response/body/properties\n      operations:\n      - name: getresponsebodyproperties\n        method: GET\n        description: Get Property Mapping for Events Response Body\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n          required: true\n        - name: to\n          in: query\n          type: string\n          required: true\n        - name: include_values\n          in: query\n          type: boolean\n        - name: key_path\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-mappings-usermetrics-properties\n      path: /search/~/mappings/usermetrics/properties\n    \
  \  operations:\n      - name: getproperties\n        method: GET\n        description: Get Property Mapping for UserMetrics\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-mappings-users-properties\n      path: /search/~/mappings/users/properties\n      operations:\n      - name: getproperties\n        method: GET\n        description: Get Property Mapping for Users\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-search-companymetrics-companies\n      path: /search/~/search/companymetrics/companies\n      operations:\n      - name: searchcompanymetrics\n        method: POST\n        description: Search CompanyMetrics/Companies\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: from\n          in: query\n          type: string\n          description: The start date, which can be absolute such as 2023-07-01T00:00:00Z or relative such as -24h\n        - name: to\n          in: query\n          type: string\n          description: The end date, which can be absolute such as 2023-07-02T00:00:00Z or relative such as now\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: search-search-events\n      path: /search/~/search/events\n      operations:\n      - name: searchevents\n        method: POST\n        description: Search Events\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: from\n          in: query\n          type: string\n          required: true\n          description: The start date, which can be absolute such as 2023-07-01T00:00:00Z or relative such as -24h\n        - name: to\n          in: query\n          type: string\n          required: true\n          description: The end date, which can be absolute such as 2023-07-02T00:00:00Z or relative such as now\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-search-usermetrics-users\n      path: /search/~/search/usermetrics/users\n\
  \      operations:\n      - name: searchusermetrics\n        method: POST\n        description: Search UserMetrics/Users\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: from\n          in: query\n          type: string\n          description: The start date, which can be absolute such as 2023-07-01T00:00:00Z or relative such as -24h\n        - name: to\n          in: query\n          type: string\n          description: The end date, which can be absolute such as 2023-07-02T00:00:00Z or relative such as now\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-subscriptions\n      path: /search/~/subscriptions\n      operations:\n      - name: createsubscription\n        method: POST\n        description: Create or Update a Subscription\n \
  \       inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-subscriptions-batch\n      path: /search/~/subscriptions/batch\n      operations:\n      - name: batchcreatesubscriptions\n        method: POST\n        description: Create or Update Subscriptions in Batch\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-subscriptions-id\n      path: /search/~/subscriptions/{id}\n      operations:\n      - name: getsubscription\n        method:\
  \ GET\n        description: Get a Subscription\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-users\n      path: /search/~/users\n      operations:\n      - name: updateusers\n        method: POST\n        description: Update a User\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-users-batch\n      path: /search/~/users/batch\n     \
  \ operations:\n      - name: batchupdateusers\n        method: POST\n        description: Update Users in Batch\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-users-id\n      path: /search/~/users/{id}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get a User\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: deleteuser\n        method: DELETE\n        description: Delete a User\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: delete_events\n          in: query\n          type: boolean\n          description: Delete events associated with the user which can be set to true or false(default)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-workspaces-workspaceid-search\n      path: /search/~/workspaces/{workspaceId}/search\n      operations:\n      - name: searchpublicworkspaces\n        method: POST\n        description: Search Events in saved public Workspace\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n\
  \          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: from\n          in: query\n          type: string\n          required: true\n          description: The start date, which can be absolute such as 2023-07-01T00:00:00Z or relative such as -24h\n        - name: to\n          in: query\n          type: string\n          required: true\n          description: The end date, which can be absolute such as 2023-07-02T00:00:00Z or relative such as now\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n        - name: include_details\n          in: query\n          type: boolean\n        - name: take\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-access-token\n      path: /workspaces/access_token\n      operations:\n      - name: getworkspacetoken\n\
  \        method: GET\n        description: Get new Workspace Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-public-id\n      path: /workspaces/public/{id}\n      operations:\n      - name: getpublicworkspace\n        method: GET\n        description: Get a Public Workspace\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps\n      path: /~/apps\n      operations:\n      - name: addapp\n        method: POST\n        description: Create a new App\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n      - name: getapps\n        method: GET\n        description: Gets Apps\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: take\n          in: query\n          type: integer\n          required: true\n        - name: before_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-id\n      path: /~/apps/{id}\n      operations:\n      - name: updateapp\n        method: POST\n        description: Update Apps\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ deleteapp\n        method: DELETE\n        description: Delete Apps\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-catalog-plans\n      path: /~/billing/catalog/plans\n      operations:\n      - name: createmoesifplan\n        method: POST\n        description: Create a new Moesif Plan\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: provider\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n      - name: listmoesifplans\n        method: GET\n        description: List all Moesif Plans\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: provider\n          in: query\n          type: string\n        - name: includes\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-catalog-plans-id\n      path: /~/billing/catalog/plans/{id}\n      operations:\n      - name: getmoesifplan\n        method: GET\n        description: Get a Moesif Plan\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type:\
  \ string\n          required: true\n        - name: provider\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemoesifplan\n        method: DELETE\n        description: Delete a Moesif Plan\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: provider\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemoesifplan\n        method: PUT\n        description: Update a Moesif Plan\n        inputParameters:\n        - name: orgId\n\
  \          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: provider\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-catalog-prices\n      path: /~/billing/catalog/prices\n      operations:\n      - name: createmoesifprice\n        method: POST\n        description: Create a new Moesif Price\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: provider\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: listmoesifprices\n        method: GET\n        description: List all Moesif Prices for a specific Plan\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: provider\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-catalog-prices-id\n      path: /~/billing/catalog/prices/{id}\n      operations:\n      - name: getmoesifprice\n        method: GET\n        description: Get a Moesif Price\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n        \
  \  type: string\n          required: true\n        - name: provider\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemoesifprice\n        method: DELETE\n        description: Delete a Moesif Price\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: provider\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemoesifprice\n        method: PUT\n        description: Update a Moesif Price\n        inputParameters:\n     \
  \   - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: provider\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-meters\n      path: /~/billing/meters\n      operations:\n      - name: listmeters\n        method: GET\n        description: List Billing Meters\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-meters-meterid\n      path:\
  \ /~/billing/meters/{meterId}\n      operations:\n      - name: getmeter\n        method: GET\n        description: Get Billing Meter by id\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: meterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemeter\n        method: DELETE\n        description: Delete Billing Meter by id\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: meterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: billing-reports\n      path: /~/billing/reports\n      operations:\n      - name: getbillingreports\n        method: GET\n        description: Get BillingReports\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: from\n          in: query\n          type: string\n        - name: to\n          in: query\n          type: string\n        - name: billing_meter_id\n          in: query\n          type: string\n        - name: company_id\n          in: query\n          type: string\n        - name: provider\n          in: query\n          type: string\n        - name: subscription_id\n          in: query\n          type: string\n        - name: success\n          in: query\n          type: boolean\n        - name: status_code\n          in: query\n          type: integer\n\
  \        - name: error_code\n          in: query\n          type: string\n        - name: '`type`'\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-reports-balance-transactions\n      path: /~/billing/reports/balance_transactions\n      operations:\n      - name: createbalancetransaction\n        method: POST\n        description: Post BillingReports Balance Transactions\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-reports-metrics\n      path: /~/billing/reports/metrics\n      operations:\n      - name: getbillingreportsmetrics\n        method: GET\n        description:\
  \ Get BillingReports' values for a given meter and time range for a single company or all companies\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: from\n          in: query\n          type: string\n          required: true\n        - name: to\n          in: query\n          type: string\n          required: true\n        - name: billing_meter_id\n          in: query\n          type: string\n        - name: success\n          in: query\n          type: boolean\n        - name: aggregator\n          in: query\n          type: string\n        - name: interval\n          in: query\n          type: string\n        - name: company_id\n          in: query\n          type: string\n        - name: subscription_id\n          in: query\n          type: string\n        - name: '`type`'\n          in: query\n          type: array\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cohorts\n      path: /~/cohorts\n      operations:\n      - name: createcohort\n        method: POST\n        description: Create New Cohort\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getcohorts\n        method: GET\n        description: Get Cohorts\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: cohort_type\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: cohorts-cohortid\n      path: /~/cohorts/{cohortId}\n      operations:\n      - name: updatecohort\n        method: POST\n        description: Update a Cohort\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: cohortId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getcohort\n        method: GET\n        description: Get Cohort\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: app_id\n          in: query\n          type: string\n        - name: cohort_type\n          in: query\n    \n\n# --- truncated at 32\
  \ KB (96 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/moesif/refs/heads/main/capabilities/moesif-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/moesif/refs/heads/main/capabilities/moesif-capability.yaml
tags:
- Moesif
- API
tools:
- description: Update a Company
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecompanies
- description: Update Companies in Batch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchupdatecompanies
- description: Get a Company
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompany
- description: Delete a Company
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecompany
- description: Get the Subscriptions of a Company
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanysubscriptions
- description: Count Companies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: countcompanies
- description: Count Events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: countevents
- description: Count Users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: countusers
- description: Get an Event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevent
- description: Get Property Mapping for Companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproperties
- description: Get Property Mapping for CompanyMetrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproperties
- description: Get Property Mapping for Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproperties
- description: Get Property Mapping for Events Request Body
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrequestbodyproperties
- description: Get Property Mapping for Events Response Body
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresponsebodyproperties
- description: Get Property Mapping for UserMetrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproperties
- description: Get Property Mapping for Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproperties
- description: Search CompanyMetrics/Companies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchcompanymetrics
- description: Search Events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchevents
- description: Search UserMetrics/Users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchusermetrics
- description: Create or Update a Subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubscription
- description: Create or Update Subscriptions in Batch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchcreatesubscriptions
- description: Get a Subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscription
- description: Update a User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateusers
- description: Update Users in Batch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchupdateusers
- description: Get a User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Delete a User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Search Events in saved public Workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchpublicworkspaces
- description: Get new Workspace Token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkspacetoken
- description: Get a Public Workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpublicworkspace
- description: Create a new App
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addapp
- description: Gets Apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapps
- description: Update Apps
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapp
- description: Delete Apps
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapp
- description: Create a new Moesif Plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmoesifplan
- description: List all Moesif Plans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmoesifplans
- description: Get a Moesif Plan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmoesifplan
- description: Delete a Moesif Plan
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemoesifplan
- description: Update a Moesif Plan
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemoesifplan
- description: Create a new Moesif Price
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmoesifprice
- description: List all Moesif Prices for a specific Plan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmoesifprices
- description: Get a Moesif Price
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmoesifprice
- description: Delete a Moesif Price
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemoesifprice
- description: Update a Moesif Price
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemoesifprice
- description: List Billing Meters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmeters
- description: Get Billing Meter by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeter
- description: Delete Billing Meter by id
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeter
- description: Get BillingReports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbillingreports
- description: Post BillingReports Balance Transactions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbalancetransaction
- description: Get BillingReports' values for a given meter and time range for a single company or all companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbillingreportsmetrics
- description: Create New Cohort
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcohort
- description: Get Cohorts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcohorts
- description: Update a Cohort
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecohort
- description: Get Cohort
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcohort
- description: Delete Cohort
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecohort
- description: Delete Sample Rate for a Cohort
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecohortsamplerate
- description: Delete a Dashboard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedashboards
- description: Copy Dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copydashboard
- description: Create New Dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdashboard
- description: Get a Dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboards
- description: Copy All Dashboards
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copyalldashboards
---
