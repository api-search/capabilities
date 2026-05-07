---
categories: []
consumed_apis: []
description: This document describes the PagerDuty REST APIs. For guides and examples please visit our [Documentation.](https://developer.pagerduty.com/docs/get-started/getting-started/) Our REST APIs are defined in OpenAPI v3.x. You can view the schema at [github.com/PagerDuty/api-schema](https://github.com/PagerDuty/api-schema). Note that properties in some schemas have fields not shown by default such as `readOnly`, `format`, and `default`. Hover your cursor over the right column that looks like `optional+1` to see the full list of fields.
layout: capability
name: PagerDuty API
operations:
- description: PagerDuty Assign tags
  method: POST
  name: createentitytypebyidchangetags
  path: /{entity_type}/{id}/change_tags
- description: PagerDuty Get tags for entities
  method: GET
  name: getentitytypebyidtags
  path: /{entity_type}/{id}/tags
- description: PagerDuty List abilities
  method: GET
  name: listabilities
  path: /abilities
- description: PagerDuty Test an ability
  method: GET
  name: getability
  path: /abilities/{id}
- description: PagerDuty List installed Add-ons
  method: GET
  name: listaddon
  path: /addons
- description: PagerDuty Install an Add-on
  method: POST
  name: createaddon
  path: /addons
- description: PagerDuty Get an Add-on
  method: GET
  name: getaddon
  path: /addons/{id}
- description: PagerDuty Delete an Add-on
  method: DELETE
  name: deleteaddon
  path: /addons/{id}
- description: PagerDuty Update an Add-on
  method: PUT
  name: updateaddon
  path: /addons/{id}
- description: PagerDuty List alert grouping settings
  method: GET
  name: listalertgroupingsettings
  path: /alert_grouping_settings
- description: PagerDuty Create an Alert Grouping Setting
  method: POST
  name: postalertgroupingsettings
  path: /alert_grouping_settings
- description: PagerDuty Get an Alert Grouping Setting
  method: GET
  name: getalertgroupingsetting
  path: /alert_grouping_settings/{id}
- description: PagerDuty Delete an Alert Grouping Setting
  method: DELETE
  name: deletealertgroupingsetting
  path: /alert_grouping_settings/{id}
- description: PagerDuty Update an Alert Grouping Setting
  method: PUT
  name: putalertgroupingsetting
  path: /alert_grouping_settings/{id}
- description: PagerDuty Get aggregated incident data
  method: POST
  name: getanalyticsmetricsincidentsall
  path: /analytics/metrics/incidents/all
- description: PagerDuty Get aggregated escalation policy data
  method: POST
  name: getanalyticsmetricsincidentsescalationpolicy
  path: /analytics/metrics/incidents/escalation_policies
- description: PagerDuty Get aggregated metrics for all escalation policies
  method: POST
  name: getanalyticsmetricsincidentsescalationpolicyall
  path: /analytics/metrics/incidents/escalation_policies/all
- description: PagerDuty Get aggregated service data
  method: POST
  name: getanalyticsmetricsincidentsservice
  path: /analytics/metrics/incidents/services
- description: PagerDuty Get aggregated metrics for all services
  method: POST
  name: getanalyticsmetricsincidentsserviceall
  path: /analytics/metrics/incidents/services/all
- description: PagerDuty Get aggregated team data
  method: POST
  name: getanalyticsmetricsincidentsteam
  path: /analytics/metrics/incidents/teams
- description: PagerDuty Get aggregated metrics for all teams
  method: POST
  name: getanalyticsmetricsincidentsteamall
  path: /analytics/metrics/incidents/teams/all
- description: PagerDuty Get aggregated metrics for all responders
  method: POST
  name: getanalyticsmetricsrespondersall
  path: /analytics/metrics/responders/all
- description: PagerDuty Get responder data aggregated by team
  method: POST
  name: getanalyticsmetricsrespondersteam
  path: /analytics/metrics/responders/teams
- description: PagerDuty Get raw data - multiple incidents
  method: POST
  name: getanalyticsincidents
  path: /analytics/raw/incidents
- description: PagerDuty Get raw data - single incident
  method: GET
  name: getanalyticsincidentsbyid
  path: /analytics/raw/incidents/{id}
- description: PagerDuty Get raw responses from a single incident
  method: GET
  name: getanalyticsincidentresponsesbyid
  path: /analytics/raw/incidents/{id}/responses
- description: PagerDuty Get raw incidents for a single responder_id
  method: POST
  name: getanalyticsresponderincidents
  path: /analytics/raw/responders/{responder_id}/incidents
- description: PagerDuty List audit records
  method: GET
  name: listauditrecords
  path: /audit/records
- description: PagerDuty Create an Automation Action
  method: POST
  name: createautomationaction
  path: /automation_actions/actions
- description: PagerDuty List Automation Actions
  method: GET
  name: getallautomationactions
  path: /automation_actions/actions
- description: PagerDuty Get an Automation Action
  method: GET
  name: getautomationaction
  path: /automation_actions/actions/{id}
- description: PagerDuty Delete an Automation Action
  method: DELETE
  name: deleteautomationaction
  path: /automation_actions/actions/{id}
- description: PagerDuty Update an Automation Action
  method: PUT
  name: updateautomationaction
  path: /automation_actions/actions/{id}
- description: PagerDuty Create an Invocation
  method: POST
  name: createautomationactioninvocation
  path: /automation_actions/actions/{id}/invocations
- description: PagerDuty Get all service references associated with an Automation Action
  method: GET
  name: getautomationactionsactionserviceassociations
  path: /automation_actions/actions/{id}/services
- description: PagerDuty Associate an Automation Action with a service
  method: POST
  name: createautomationactionserviceassocation
  path: /automation_actions/actions/{id}/services
- description: PagerDuty Get the details of an Automation Action / service relation
  method: GET
  name: getautomationactionsactionserviceassociation
  path: /automation_actions/actions/{id}/services/{service_id}
- description: PagerDuty Disassociate an Automation Action from a service
  method: DELETE
  name: deleteautomationactionserviceassociation
  path: /automation_actions/actions/{id}/services/{service_id}
- description: PagerDuty Associate an Automation Action with a team
  method: POST
  name: createautomationactionteamassociation
  path: /automation_actions/actions/{id}/teams
- description: PagerDuty Get all team references associated with an Automation Action
  method: GET
  name: getautomationactionsactionteamassociations
  path: /automation_actions/actions/{id}/teams
- description: PagerDuty Disassociate an Automation Action from a team
  method: DELETE
  name: deleteautomationactionteamassociation
  path: /automation_actions/actions/{id}/teams/{team_id}
- description: PagerDuty Get the details of an Automation Action / team relation
  method: GET
  name: getautomationactionsactionteamassociation
  path: /automation_actions/actions/{id}/teams/{team_id}
- description: PagerDuty List Invocations
  method: GET
  name: listautomationactioninvocations
  path: /automation_actions/invocations
- description: PagerDuty Get an Invocation
  method: GET
  name: getautomationactionsinvocation
  path: /automation_actions/invocations/{id}
- description: PagerDuty Create an Automation Action runner.
  method: POST
  name: createautomationactionsrunner
  path: /automation_actions/runners
- description: PagerDuty List Automation Action runners
  method: GET
  name: getautomationactionsrunners
  path: /automation_actions/runners
- description: PagerDuty Get an Automation Action runner
  method: GET
  name: getautomationactionsrunner
  path: /automation_actions/runners/{id}
- description: PagerDuty Update an Automation Action runner
  method: PUT
  name: updateautomationactionsrunner
  path: /automation_actions/runners/{id}
- description: PagerDuty Delete an Automation Action runner
  method: DELETE
  name: deleteautomationactionsrunner
  path: /automation_actions/runners/{id}
- description: PagerDuty Associate a runner with a team
  method: POST
  name: createautomationactionsrunnerteamassociation
  path: /automation_actions/runners/{id}/teams
- description: PagerDuty Get all team references associated with a runner
  method: GET
  name: getautomationactionsrunnerteamassociations
  path: /automation_actions/runners/{id}/teams
- description: PagerDuty Disassociate a runner from a team
  method: DELETE
  name: deleteautomationactionsrunnerteamassociation
  path: /automation_actions/runners/{id}/teams/{team_id}
- description: PagerDuty Get the details of a runner / team relation
  method: GET
  name: getautomationactionsrunnerteamassociation
  path: /automation_actions/runners/{id}/teams/{team_id}
- description: PagerDuty List Business Services
  method: GET
  name: listbusinessservices
  path: /business_services
- description: PagerDuty Create a Business Service
  method: POST
  name: createbusinessservice
  path: /business_services
- description: PagerDuty Get a Business Service
  method: GET
  name: getbusinessservice
  path: /business_services/{id}
- description: PagerDuty Delete a Business Service
  method: DELETE
  name: deletebusinessservice
  path: /business_services/{id}
- description: PagerDuty Update a Business Service
  method: PUT
  name: updatebusinessservice
  path: /business_services/{id}
- description: PagerDuty Create Business Service Account Subscription
  method: POST
  name: createbusinessserviceaccountsubscription
  path: /business_services/{id}/account_subscription
- description: PagerDuty Delete Business Service Account Subscription
  method: DELETE
  name: removebusinessserviceaccountsubscription
  path: /business_services/{id}/account_subscription
personas: []
provider_name: PagerDuty
provider_slug: pagerduty
search_terms:
- getautomationaction
- getautomationactionsactionserviceassociations
- putalertgroupingsetting
- createautomationactionsrunner
- pagerduty associate an automation action with a team
- pagerduty test an ability
- api
- pagerduty list invocations
- pagerduty get an alert grouping setting
- pagerduty get raw incidents for a single responder_id
- pagerduty list automation actions
- pagerduty update an alert grouping setting
- getanalyticsmetricsincidentsservice
- pagerduty update an automation action runner
- getautomationactionsactionserviceassociation
- pagerduty get the details of a runner / team relation
- pagerduty delete an add-on
- deleteautomationaction
- pagerduty associate a runner with a team
- getanalyticsmetricsincidentsescalationpolicy
- pagerduty get raw responses from a single incident
- listabilities
- createaddon
- pagerduty get responder data aggregated by team
- pagerduty disassociate an automation action from a service
- pagerduty get aggregated incident data
- getautomationactionsactionteamassociation
- getbusinessservice
- alerting
- getanalyticsincidentsbyid
- createentitytypebyidchangetags
- pagerduty get aggregated team data
- getautomationactionsrunner
- pagerduty get an automation action runner
- pagerduty update an add-on
- pagerduty delete an automation action
- updateautomationactionsrunner
- getaddon
- listautomationactioninvocations
- pagerduty disassociate an automation action from a team
- pagerduty associate an automation action with a service
- pagerduty get aggregated metrics for all teams
- getanalyticsresponderincidents
- pagerduty get all service references associated with an automation action
- pagerduty list abilities
- on-call management
- pagerduty get the details of an automation action / service relation
- getautomationactionsrunnerteamassociation
- pagerduty create an automation action
- pagerduty create business service account subscription
- getentitytypebyidtags
- deleteautomationactionsrunner
- pagerduty get an automation action
- pagerduty delete an alert grouping setting
- pagerduty list business services
- createautomationactionsrunnerteamassociation
- pagerduty install an add-on
- pagerduty update an automation action
- pagerduty get a business service
- updateaddon
- getanalyticsmetricsrespondersall
- getanalyticsmetricsincidentsall
- pagerduty get all team references associated with an automation action
- pagerduty create a business service
- getanalyticsmetricsincidentsteam
- pagerduty delete an automation action runner
- pagerduty assign tags
- pagerduty create an alert grouping setting
- pagerduty create an invocation
- createautomationactioninvocation
- pagerduty list installed add-ons
- pagerduty get aggregated metrics for all services
- deletealertgroupingsetting
- pagerduty list alert grouping settings
- pagerduty get an invocation
- pagerduty get the details of an automation action / team relation
- updatebusinessservice
- getautomationactionsrunners
- deletebusinessservice
- pagerduty get tags for entities
- pagerduty get aggregated service data
- pagerduty get aggregated escalation policy data
- createautomationactionteamassociation
- pagerduty update a business service
- pagerduty
- listalertgroupingsettings
- getanalyticsincidentresponsesbyid
- devops
- createautomationaction
- listaddon
- createbusinessservice
- postalertgroupingsettings
- pagerduty create an automation action runner.
- getautomationactionsrunnerteamassociations
- getanalyticsmetricsincidentsteamall
- getallautomationactions
- deleteaddon
- getalertgroupingsetting
- getanalyticsmetricsincidentsescalationpolicyall
- getautomationactionsactionteamassociations
- removebusinessserviceaccountsubscription
- pagerduty list automation action runners
- deleteautomationactionsrunnerteamassociation
- pagerduty get aggregated metrics for all escalation policies
- pagerduty get an add-on
- pagerduty get raw data - single incident
- pagerduty delete a business service
- listauditrecords
- updateautomationaction
- incident management
- pagerduty disassociate a runner from a team
- deleteautomationactionserviceassociation
- getanalyticsincidents
- getability
- getautomationactionsinvocation
- pagerduty delete business service account subscription
- getanalyticsmetricsincidentsserviceall
- getanalyticsmetricsrespondersteam
- pagerduty get aggregated metrics for all responders
- deleteautomationactionteamassociation
- pagerduty get all team references associated with a runner
- createbusinessserviceaccountsubscription
- pagerduty list audit records
- createautomationactionserviceassocation
- pagerduty get raw data - multiple incidents
- listbusinessservices
slug: pagerduty-capability
source_filename: pagerduty-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PagerDuty API\n  description: This document describes the PagerDuty REST APIs. For guides and examples please visit our [Documentation.](https://developer.pagerduty.com/docs/get-started/getting-started/)\n    Our REST APIs are defined in OpenAPI v3.x. You can view the schema at [github.com/PagerDuty/api-schema](https://github.com/PagerDuty/api-schema).\n    Note that properties in some schemas have fields not shown by default such as `readOnly`, `format`, and `default`. Hover\n    your cursor over the right column that looks like `optional+1` to see the full list of fields.\n  tags:\n  - Pagerduty\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pagerduty\n    baseUri: https://api.pagerduty.com\n    description: PagerDuty API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{PAGERDUTY_TOKEN}}'\n    resources:\n\
  \    - name: entity-type-id-change-tags\n      path: /{entity_type}/{id}/change_tags\n      operations:\n      - name: createentitytypebyidchangetags\n        method: POST\n        description: PagerDuty Assign tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-type-id-tags\n      path: /{entity_type}/{id}/tags\n      operations:\n      - name: getentitytypebyidtags\n        method: GET\n        description: PagerDuty Get tags for entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: abilities\n      path: /abilities\n      operations:\n      - name: listabilities\n        method: GET\n        description: PagerDuty List abilities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: abilities-id\n      path:\
  \ /abilities/{id}\n      operations:\n      - name: getability\n        method: GET\n        description: PagerDuty Test an ability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: addons\n      path: /addons\n      operations:\n      - name: listaddon\n        method: GET\n        description: PagerDuty List installed Add-ons\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaddon\n        method: POST\n        description: PagerDuty Install an Add-on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: addons-id\n      path: /addons/{id}\n      operations:\n      - name: getaddon\n        method: GET\n        description: PagerDuty Get an Add-on\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: deleteaddon\n        method: DELETE\n        description: PagerDuty Delete an Add-on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaddon\n        method: PUT\n        description: PagerDuty Update an Add-on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alert-grouping-settings\n      path: /alert_grouping_settings\n      operations:\n      - name: listalertgroupingsettings\n        method: GET\n        description: PagerDuty List alert grouping settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postalertgroupingsettings\n        method: POST\n        description: PagerDuty Create an Alert Grouping Setting\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alert-grouping-settings-id\n      path: /alert_grouping_settings/{id}\n      operations:\n      - name: getalertgroupingsetting\n        method: GET\n        description: PagerDuty Get an Alert Grouping Setting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletealertgroupingsetting\n        method: DELETE\n        description: PagerDuty Delete an Alert Grouping Setting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putalertgroupingsetting\n        method: PUT\n        description: PagerDuty Update an Alert Grouping Setting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-metrics-incidents-all\n\
  \      path: /analytics/metrics/incidents/all\n      operations:\n      - name: getanalyticsmetricsincidentsall\n        method: POST\n        description: PagerDuty Get aggregated incident data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-metrics-incidents-escalation-policies\n      path: /analytics/metrics/incidents/escalation_policies\n      operations:\n      - name: getanalyticsmetricsincidentsescalationpolicy\n        method: POST\n        description: PagerDuty Get aggregated escalation policy data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-metrics-incidents-escalation-policies-\n      path: /analytics/metrics/incidents/escalation_policies/all\n      operations:\n      - name: getanalyticsmetricsincidentsescalationpolicyall\n        method: POST\n        description: PagerDuty\
  \ Get aggregated metrics for all escalation policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-metrics-incidents-services\n      path: /analytics/metrics/incidents/services\n      operations:\n      - name: getanalyticsmetricsincidentsservice\n        method: POST\n        description: PagerDuty Get aggregated service data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-metrics-incidents-services-all\n      path: /analytics/metrics/incidents/services/all\n      operations:\n      - name: getanalyticsmetricsincidentsserviceall\n        method: POST\n        description: PagerDuty Get aggregated metrics for all services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-metrics-incidents-teams\n\
  \      path: /analytics/metrics/incidents/teams\n      operations:\n      - name: getanalyticsmetricsincidentsteam\n        method: POST\n        description: PagerDuty Get aggregated team data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-metrics-incidents-teams-all\n      path: /analytics/metrics/incidents/teams/all\n      operations:\n      - name: getanalyticsmetricsincidentsteamall\n        method: POST\n        description: PagerDuty Get aggregated metrics for all teams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-metrics-responders-all\n      path: /analytics/metrics/responders/all\n      operations:\n      - name: getanalyticsmetricsrespondersall\n        method: POST\n        description: PagerDuty Get aggregated metrics for all responders\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-metrics-responders-teams\n      path: /analytics/metrics/responders/teams\n      operations:\n      - name: getanalyticsmetricsrespondersteam\n        method: POST\n        description: PagerDuty Get responder data aggregated by team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-raw-incidents\n      path: /analytics/raw/incidents\n      operations:\n      - name: getanalyticsincidents\n        method: POST\n        description: PagerDuty Get raw data - multiple incidents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-raw-incidents-id\n      path: /analytics/raw/incidents/{id}\n      operations:\n      - name: getanalyticsincidentsbyid\n        method: GET\n        description:\
  \ PagerDuty Get raw data - single incident\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-raw-incidents-id-responses\n      path: /analytics/raw/incidents/{id}/responses\n      operations:\n      - name: getanalyticsincidentresponsesbyid\n        method: GET\n        description: PagerDuty Get raw responses from a single incident\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-raw-responders-responder-id-incidents\n      path: /analytics/raw/responders/{responder_id}/incidents\n      operations:\n      - name: getanalyticsresponderincidents\n        method: POST\n        description: PagerDuty Get raw incidents for a single responder_id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audit-records\n\
  \      path: /audit/records\n      operations:\n      - name: listauditrecords\n        method: GET\n        description: PagerDuty List audit records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-actions\n      path: /automation_actions/actions\n      operations:\n      - name: createautomationaction\n        method: POST\n        description: PagerDuty Create an Automation Action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getallautomationactions\n        method: GET\n        description: PagerDuty List Automation Actions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-actions-id\n      path: /automation_actions/actions/{id}\n      operations:\n      - name: getautomationaction\n\
  \        method: GET\n        description: PagerDuty Get an Automation Action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteautomationaction\n        method: DELETE\n        description: PagerDuty Delete an Automation Action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateautomationaction\n        method: PUT\n        description: PagerDuty Update an Automation Action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-actions-id-invocations\n      path: /automation_actions/actions/{id}/invocations\n      operations:\n      - name: createautomationactioninvocation\n        method: POST\n        description: PagerDuty Create an Invocation\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-actions-id-services\n      path: /automation_actions/actions/{id}/services\n      operations:\n      - name: getautomationactionsactionserviceassociations\n        method: GET\n        description: PagerDuty Get all service references associated with an Automation Action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createautomationactionserviceassocation\n        method: POST\n        description: PagerDuty Associate an Automation Action with a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-actions-id-services-service-i\n      path: /automation_actions/actions/{id}/services/{service_id}\n      operations:\n      - name: getautomationactionsactionserviceassociation\n       \
  \ method: GET\n        description: PagerDuty Get the details of an Automation Action / service relation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteautomationactionserviceassociation\n        method: DELETE\n        description: PagerDuty Disassociate an Automation Action from a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-actions-id-teams\n      path: /automation_actions/actions/{id}/teams\n      operations:\n      - name: createautomationactionteamassociation\n        method: POST\n        description: PagerDuty Associate an Automation Action with a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getautomationactionsactionteamassociations\n        method: GET\n  \
  \      description: PagerDuty Get all team references associated with an Automation Action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-actions-id-teams-team-id\n      path: /automation_actions/actions/{id}/teams/{team_id}\n      operations:\n      - name: deleteautomationactionteamassociation\n        method: DELETE\n        description: PagerDuty Disassociate an Automation Action from a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getautomationactionsactionteamassociation\n        method: GET\n        description: PagerDuty Get the details of an Automation Action / team relation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-invocations\n      path: /automation_actions/invocations\n\
  \      operations:\n      - name: listautomationactioninvocations\n        method: GET\n        description: PagerDuty List Invocations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-invocations-id\n      path: /automation_actions/invocations/{id}\n      operations:\n      - name: getautomationactionsinvocation\n        method: GET\n        description: PagerDuty Get an Invocation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-runners\n      path: /automation_actions/runners\n      operations:\n      - name: createautomationactionsrunner\n        method: POST\n        description: PagerDuty Create an Automation Action runner.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ getautomationactionsrunners\n        method: GET\n        description: PagerDuty List Automation Action runners\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-runners-id\n      path: /automation_actions/runners/{id}\n      operations:\n      - name: getautomationactionsrunner\n        method: GET\n        description: PagerDuty Get an Automation Action runner\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateautomationactionsrunner\n        method: PUT\n        description: PagerDuty Update an Automation Action runner\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteautomationactionsrunner\n        method: DELETE\n        description: PagerDuty Delete an Automation Action runner\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-runners-id-teams\n      path: /automation_actions/runners/{id}/teams\n      operations:\n      - name: createautomationactionsrunnerteamassociation\n        method: POST\n        description: PagerDuty Associate a runner with a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getautomationactionsrunnerteamassociations\n        method: GET\n        description: PagerDuty Get all team references associated with a runner\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-actions-runners-id-teams-team-id\n      path: /automation_actions/runners/{id}/teams/{team_id}\n      operations:\n      - name: deleteautomationactionsrunnerteamassociation\n\
  \        method: DELETE\n        description: PagerDuty Disassociate a runner from a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getautomationactionsrunnerteamassociation\n        method: GET\n        description: PagerDuty Get the details of a runner / team relation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: business-services\n      path: /business_services\n      operations:\n      - name: listbusinessservices\n        method: GET\n        description: PagerDuty List Business Services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbusinessservice\n        method: POST\n        description: PagerDuty Create a Business Service\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: business-services-id\n      path: /business_services/{id}\n      operations:\n      - name: getbusinessservice\n        method: GET\n        description: PagerDuty Get a Business Service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebusinessservice\n        method: DELETE\n        description: PagerDuty Delete a Business Service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebusinessservice\n        method: PUT\n        description: PagerDuty Update a Business Service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: business-services-id-account-subscription\n      path: /business_services/{id}/account_subscription\n    \
  \  operations:\n      - name: createbusinessserviceaccountsubscription\n        method: POST\n        description: PagerDuty Create Business Service Account Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removebusinessserviceaccountsubscription\n        method: DELETE\n        description: PagerDuty Delete Business Service Account Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pagerduty-rest\n    description: REST adapter for PagerDuty API.\n    resources:\n    - path: /{entity_type}/{id}/change_tags\n      name: createentitytypebyidchangetags\n      operations:\n      - method: POST\n        name: createentitytypebyidchangetags\n        description: PagerDuty Assign tags\n        call: pagerduty.createentitytypebyidchangetags\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{entity_type}/{id}/tags\n      name: getentitytypebyidtags\n      operations:\n      - method: GET\n        name: getentitytypebyidtags\n        description: PagerDuty Get tags for entities\n        call: pagerduty.getentitytypebyidtags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /abilities\n      name: listabilities\n      operations:\n      - method: GET\n        name: listabilities\n        description: PagerDuty List abilities\n        call: pagerduty.listabilities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /abilities/{id}\n      name: getability\n      operations:\n      - method: GET\n        name: getability\n        description: PagerDuty Test an ability\n        call: pagerduty.getability\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /addons\n      name: listaddon\n\
  \      operations:\n      - method: GET\n        name: listaddon\n        description: PagerDuty List installed Add-ons\n        call: pagerduty.listaddon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /addons\n      name: createaddon\n      operations:\n      - method: POST\n        name: createaddon\n        description: PagerDuty Install an Add-on\n        call: pagerduty.createaddon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /addons/{id}\n      name: getaddon\n      operations:\n      - method: GET\n        name: getaddon\n        description: PagerDuty Get an Add-on\n        call: pagerduty.getaddon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /addons/{id}\n      name: deleteaddon\n      operations:\n      - method: DELETE\n        name: deleteaddon\n        description: PagerDuty Delete an Add-on\n        call: pagerduty.deleteaddon\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /addons/{id}\n      name: updateaddon\n      operations:\n      - method: PUT\n        name: updateaddon\n        description: PagerDuty Update an Add-on\n        call: pagerduty.updateaddon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alert_grouping_settings\n      name: listalertgroupingsettings\n      operations:\n      - method: GET\n        name: listalertgroupingsettings\n        description: PagerDuty List alert grouping settings\n        call: pagerduty.listalertgroupingsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alert_grouping_settings\n      name: postalertgroupingsettings\n      operations:\n      - method: POST\n        name: postalertgroupingsettings\n        description: PagerDuty Create an Alert Grouping Setting\n        call: pagerduty.postalertgroupingsettings\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /alert_grouping_settings/{id}\n      name: getalertgroupingsetting\n      operations:\n      - method: GET\n        name: getalertgroupingsetting\n        description: PagerDuty Get an Alert Grouping Setting\n        call: pagerduty.getalertgroupingsetting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alert_grouping_settings/{id}\n      name: deletealertgroupingsetting\n      operations:\n      - method: DELETE\n        name: deletealertgroupingsetting\n        description: PagerDuty Delete an Alert Grouping Setting\n        call: pagerduty.deletealertgroupingsetting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alert_grouping_settings/{id}\n      name: putalertgroupingsetting\n      operations:\n      - method: PUT\n        name: putalertgroupingsetting\n        description: PagerDuty Update an Alert Grouping Setting\n        call: pagerduty.putalertgroupingsetting\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/metrics/incidents/all\n      name: getanalyticsmetricsincidentsall\n      operations:\n      - method: POST\n        name: getanalyticsmetricsincidentsall\n        description: PagerDuty Get aggregated incident data\n        call: pagerduty.getanalyticsmetricsincidentsall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/metrics/incidents/escalation_policies\n      name: getanalyticsmetricsincidentsescalationpolicy\n      operations:\n      - method: POST\n        name: getanalyticsmetricsincidentsescalationpolicy\n        description: PagerDuty Get aggregated escalation policy data\n        call: pagerduty.getanalyticsmetricsincidentsescalationpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/metrics/incidents/escalation_policies/all\n      name: getanalyticsmetricsincidentsescalationpolicyall\n\
  \      operations:\n      - method: POST\n        name: getanalyticsmetricsincidentsescalationpolicyall\n        description: PagerDuty Get aggregated metrics for all escalation policies\n        call: pagerduty.getanalyticsmetricsincidentsescalationpolicyall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/metrics/incidents/services\n      name: getanalyticsmetricsincidentsservice\n      operations:\n      - method: POST\n        name: getanalyticsmetricsincidentsservice\n        description: PagerDuty Get aggregated service data\n        call: pagerduty.getanalyticsmetricsincidentsservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/metrics/incidents/services/all\n      name: getanalyticsmetricsincidentsserviceall\n      operations:\n      - method: POST\n        name: getanalyticsmetricsincidentsserviceall\n        description: PagerDuty Get aggregated metrics for all services\n   \
  \     call: pagerduty.getanalyticsmetricsincidentsserviceall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/metrics/incidents/teams\n      name: getanalyticsmetricsincidentsteam\n      operations:\n      - method: POST\n        name: getanalyticsmetricsincidentsteam\n        description: PagerDuty Get aggregated team data\n        call: pagerduty.getanalyticsmetricsincidentsteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/metrics/incidents/teams/all\n      name: getanalyticsmetricsincidentsteamall\n      operations:\n      - method: POST\n        name: getanalyticsmetricsincidentsteamall\n        description: PagerDuty Get aggregated metrics for all teams\n        call: pagerduty.getanalyticsmetricsincidentsteamall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/metrics/responders/all\n      name: getanalyticsmetricsrespondersall\n \
  \     operations:\n      - method: POST\n        name: getanalyticsmetricsrespondersall\n        description: PagerDuty Get aggregated metrics for all responders\n        call: pagerduty.getanalyticsmetricsrespondersall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/metrics/responders/teams\n      name: getanalyticsmetricsrespondersteam\n      operations:\n      - method: POST\n        name: getanalyticsmetricsrespondersteam\n        description: PagerDuty Get responder data aggregated by team\n        call: pagerduty.getanalyticsmetricsrespondersteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/raw/incidents\n      name: getanalyticsincidents\n      operations:\n      - method: POST\n        name: getanalyticsincidents\n        description: PagerDuty Get raw data - multiple incidents\n        call: pagerduty.getanalyticsincidents\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /analytics/raw/incidents/{id}\n      name: getanalyticsincidentsbyid\n      operations:\n      - method: GET\n        name: getanalyticsincidentsbyid\n        description: PagerDuty Get raw data - single incident\n        call: pagerduty.getanalyticsincidentsbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/raw/incidents/{id}/responses\n      name: getanalyticsincidentresponsesbyid\n      operations:\n      - method: GET\n        name: getanalyticsincidentresponsesbyid\n        description: PagerDuty Get raw responses from a single incident\n        call: pagerduty.getanalyticsincidentresponsesbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/raw/responders/{responder_id}/incidents\n      name: getanalyticsresponderincidents\n      operations:\n      - method: POST\n        name: getanalyticsresponderincidents\n        description: PagerDuty Get\
  \ raw incidents for a single responder_id\n        call: pagerduty.getanalyticsresponderincidents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /audit/records\n      name: listauditrecords\n      operations:\n      - method: GET\n        name: listauditrecords\n        description: PagerDuty List audit records\n        call: pagerduty.listauditrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /automation_actions/actions\n      name: createautomationaction\n      operations:\n      - method: POST\n        name: createautomationaction\n        description: PagerDuty Create an Automation Action\n        call: pagerduty.createautomationaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /automation_actions/actions\n      name: getallautomationactions\n      operations:\n      - method: GET\n        name: getallautomationactions\n        description: PagerDuty List\
  \ Automation Actions\n        call: pagerduty.getallautomationactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /automation_actions/actions/{id}\n      name: getautomationaction\n      operations:\n      - method: GET\n        name: getautomationaction\n        description: PagerDuty Get an Automation Action\n        call: pagerduty.getautomationaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /automation_actions/actions/{id}\n      name: deleteautomationaction\n      operations:\n      - method: DELETE\n        name: deleteautomationaction\n        description: PagerDuty Delete an Automation Action\n        call: pagerduty.deleteautomationaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /automation_actions/actions/{id}\n      name: updateautomationaction\n      operations:\n      - method: PUT\n        name: updateautomationaction\n        description:\
  \ PagerDuty Update an Automation Action\n        call: pagerduty.updateautomationaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /automation_actions/actions/{id}/invocations\n      name: createautomationactioninvocation\n      operations:\n      - method: POST\n        name: createautomationactioninvocation\n        description: PagerDuty Create an Invocation\n        call: pagerduty.createautomationactioninvocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /automation_actions/actions/{id}/services\n      name: getautomationactionsactionserviceassociations\n      operations:\n      - method: GET\n        name: getautomationactionsactionserviceassociations\n        description: PagerDuty Get all service references associated with an Automation Action\n        call: pagerduty.getautomationactionsactionserviceassociations\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /automation_actions/actions/{id}/services\n      name: createautomationactionserviceassocation\n      operations:\n      - method: POST\n        name: createautomationactionserviceassocation\n        description: PagerDuty Associate an Automation Action with a service\n        call: pagerduty.createautomationactionserviceassocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /automation_actions/actions/{id}/services/{service_id}\n      name: getautomationactionsactionserviceassociation\n      operations:\n      - method: GET\n        name: getautomationactionsactionserviceassociation\n        description: PagerDuty Get the details of\n\n# --- truncated at 32 KB (58 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/pagerduty/refs/heads/main/capabilities/pagerduty-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pagerduty/refs/heads/main/capabilities/pagerduty-capability.yaml
tags:
- Pagerduty
- API
tools:
- description: PagerDuty Assign tags
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createentitytypebyidchangetags
- description: PagerDuty Get tags for entities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getentitytypebyidtags
- description: PagerDuty List abilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listabilities
- description: PagerDuty Test an ability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getability
- description: PagerDuty List installed Add-ons
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaddon
- description: PagerDuty Install an Add-on
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaddon
- description: PagerDuty Get an Add-on
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaddon
- description: PagerDuty Delete an Add-on
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaddon
- description: PagerDuty Update an Add-on
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaddon
- description: PagerDuty List alert grouping settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalertgroupingsettings
- description: PagerDuty Create an Alert Grouping Setting
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postalertgroupingsettings
- description: PagerDuty Get an Alert Grouping Setting
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalertgroupingsetting
- description: PagerDuty Delete an Alert Grouping Setting
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletealertgroupingsetting
- description: PagerDuty Update an Alert Grouping Setting
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putalertgroupingsetting
- description: PagerDuty Get aggregated incident data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsmetricsincidentsall
- description: PagerDuty Get aggregated escalation policy data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsmetricsincidentsescalationpolicy
- description: PagerDuty Get aggregated metrics for all escalation policies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsmetricsincidentsescalationpolicyall
- description: PagerDuty Get aggregated service data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsmetricsincidentsservice
- description: PagerDuty Get aggregated metrics for all services
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsmetricsincidentsserviceall
- description: PagerDuty Get aggregated team data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsmetricsincidentsteam
- description: PagerDuty Get aggregated metrics for all teams
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsmetricsincidentsteamall
- description: PagerDuty Get aggregated metrics for all responders
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsmetricsrespondersall
- description: PagerDuty Get responder data aggregated by team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsmetricsrespondersteam
- description: PagerDuty Get raw data - multiple incidents
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsincidents
- description: PagerDuty Get raw data - single incident
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getanalyticsincidentsbyid
- description: PagerDuty Get raw responses from a single incident
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getanalyticsincidentresponsesbyid
- description: PagerDuty Get raw incidents for a single responder_id
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getanalyticsresponderincidents
- description: PagerDuty List audit records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauditrecords
- description: PagerDuty Create an Automation Action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createautomationaction
- description: PagerDuty List Automation Actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallautomationactions
- description: PagerDuty Get an Automation Action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationaction
- description: PagerDuty Delete an Automation Action
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteautomationaction
- description: PagerDuty Update an Automation Action
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateautomationaction
- description: PagerDuty Create an Invocation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createautomationactioninvocation
- description: PagerDuty Get all service references associated with an Automation Action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationactionsactionserviceassociations
- description: PagerDuty Associate an Automation Action with a service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createautomationactionserviceassocation
- description: PagerDuty Get the details of an Automation Action / service relation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationactionsactionserviceassociation
- description: PagerDuty Disassociate an Automation Action from a service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteautomationactionserviceassociation
- description: PagerDuty Associate an Automation Action with a team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createautomationactionteamassociation
- description: PagerDuty Get all team references associated with an Automation Action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationactionsactionteamassociations
- description: PagerDuty Disassociate an Automation Action from a team
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteautomationactionteamassociation
- description: PagerDuty Get the details of an Automation Action / team relation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationactionsactionteamassociation
- description: PagerDuty List Invocations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listautomationactioninvocations
- description: PagerDuty Get an Invocation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationactionsinvocation
- description: PagerDuty Create an Automation Action runner.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createautomationactionsrunner
- description: PagerDuty List Automation Action runners
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationactionsrunners
- description: PagerDuty Get an Automation Action runner
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationactionsrunner
- description: PagerDuty Update an Automation Action runner
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateautomationactionsrunner
- description: PagerDuty Delete an Automation Action runner
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteautomationactionsrunner
- description: PagerDuty Associate a runner with a team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createautomationactionsrunnerteamassociation
- description: PagerDuty Get all team references associated with a runner
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationactionsrunnerteamassociations
- description: PagerDuty Disassociate a runner from a team
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteautomationactionsrunnerteamassociation
- description: PagerDuty Get the details of a runner / team relation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationactionsrunnerteamassociation
- description: PagerDuty List Business Services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbusinessservices
- description: PagerDuty Create a Business Service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbusinessservice
- description: PagerDuty Get a Business Service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbusinessservice
- description: PagerDuty Delete a Business Service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebusinessservice
- description: PagerDuty Update a Business Service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebusinessservice
- description: PagerDuty Create Business Service Account Subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbusinessserviceaccountsubscription
- description: PagerDuty Delete Business Service Account Subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removebusinessserviceaccountsubscription
---
