---
categories: []
consumed_apis: []
description: REST API for managing GitHub Copilot seat assignments, billing, usage metrics, content exclusion rules, and organizational settings. Covers user management, aggregated metrics, usage reports, and content governance across organizations and enterprises.
layout: capability
name: GitHub Copilot REST API
operations:
- description: Github Copilot Get Copilot Billing Information for an Organization
  method: GET
  name: getcopilotbillingfororganization
  path: /orgs/{org}/copilot/billing
- description: Github Copilot List All Copilot Seat Assignments for an Organization
  method: GET
  name: listcopilotseats
  path: /orgs/{org}/copilot/billing/seats
- description: Github Copilot Add Teams to Copilot Subscription
  method: POST
  name: addteamstocopilotsubscription
  path: /orgs/{org}/copilot/billing/selected_teams
- description: Github Copilot Remove Teams From Copilot Subscription
  method: DELETE
  name: removeteamsfromcopilotsubscription
  path: /orgs/{org}/copilot/billing/selected_teams
- description: Github Copilot Add Users to Copilot Subscription
  method: POST
  name: adduserstocopilotsubscription
  path: /orgs/{org}/copilot/billing/selected_users
- description: Github Copilot Remove Users From Copilot Subscription
  method: DELETE
  name: removeusersfromcopilotsubscription
  path: /orgs/{org}/copilot/billing/selected_users
- description: Github Copilot Get Copilot Seat Assignment Details for a User
  method: GET
  name: getcopilotseatforuser
  path: /orgs/{org}/members/{username}/copilot
- description: Github Copilot Get Copilot Metrics for an Organization
  method: GET
  name: getcopilotmetricsfororganization
  path: /orgs/{org}/copilot/metrics
- description: Github Copilot Get Copilot Metrics for a Team
  method: GET
  name: getcopilotmetricsforteam
  path: /orgs/{org}/team/{team_slug}/copilot/metrics
- description: Github Copilot Get Enterprise Copilot Usage Metrics for a Specific Day
  method: GET
  name: getenterprisecopilotusagedaily
  path: /enterprises/{enterprise}/copilot/metrics/reports/enterprise-1-day
- description: Github Copilot Get Latest 28-day Enterprise Copilot Usage Metrics
  method: GET
  name: getenterprisecopilotusage28day
  path: /enterprises/{enterprise}/copilot/metrics/reports/enterprise-28-day/latest
- description: Github Copilot Get Enterprise User-level Copilot Usage Metrics for a Specific Day
  method: GET
  name: getenterpriseuserscopilotusagedaily
  path: /enterprises/{enterprise}/copilot/metrics/reports/users-1-day
- description: Github Copilot Get Latest 28-day Enterprise User-level Copilot Usage Metrics
  method: GET
  name: getenterpriseuserscopilotusage28day
  path: /enterprises/{enterprise}/copilot/metrics/reports/users-28-day/latest
- description: Github Copilot Get Organization Copilot Usage Metrics for a Specific Day
  method: GET
  name: getorganizationcopilotusagedaily
  path: /orgs/{org}/copilot/metrics/reports/organization-1-day
- description: Github Copilot Get Latest 28-day Organization Copilot Usage Metrics
  method: GET
  name: getorganizationcopilotusage28day
  path: /orgs/{org}/copilot/metrics/reports/organization-28-day/latest
- description: Github Copilot Get Organization User-level Copilot Usage Metrics for a Specific Day
  method: GET
  name: getorganizationuserscopilotusagedaily
  path: /orgs/{org}/copilot/metrics/reports/users-1-day
- description: Github Copilot Get Latest 28-day Organization User-level Copilot Usage Metrics
  method: GET
  name: getorganizationuserscopilotusage28day
  path: /orgs/{org}/copilot/metrics/reports/users-28-day/latest
- description: Github Copilot Get Copilot Content Exclusion Rules for an Organization
  method: GET
  name: getcopilotcontentexclusionrules
  path: /orgs/{org}/copilot/content_exclusion
- description: Github Copilot Set Copilot Content Exclusion Rules for an Organization
  method: PUT
  name: setcopilotcontentexclusionrules
  path: /orgs/{org}/copilot/content_exclusion
personas: []
provider_name: GitHub Copilot
provider_slug: github-copilot
search_terms:
- getcopilotmetricsfororganization
- github copilot get latest 28-day organization user-level copilot usage metrics
- agents
- getcopilotbillingfororganization
- getenterpriseuserscopilotusage28day
- github copilot get latest 28-day enterprise user-level copilot usage metrics
- developer tools
- listcopilotseats
- coding agent
- code generation
- removeusersfromcopilotsubscription
- github copilot remove users from copilot subscription
- getorganizationcopilotusagedaily
- getenterprisecopilotusagedaily
- adduserstocopilotsubscription
- metrics
- model context protocol
- github copilot get copilot seat assignment details for a user
- ide
- github copilot set copilot content exclusion rules for an organization
- ai
- mcp
- productivity
- setcopilotcontentexclusionrules
- artificial intelligence
- getenterpriseuserscopilotusagedaily
- machine learning
- addteamstocopilotsubscription
- getcopilotseatforuser
- api
- getcopilotmetricsforteam
- github copilot add users to copilot subscription
- github copilot get enterprise user-level copilot usage metrics for a specific day
- github copilot get copilot metrics for a team
- getorganizationcopilotusage28day
- github copilot get latest 28-day organization copilot usage metrics
- getorganizationuserscopilotusagedaily
- github copilot get organization copilot usage metrics for a specific day
- custom instructions
- github copilot get organization user-level copilot usage metrics for a specific day
- getenterprisecopilotusage28day
- github copilot get latest 28-day enterprise copilot usage metrics
- getorganizationuserscopilotusage28day
- copilot
- github copilot get copilot content exclusion rules for an organization
- extensions
- github copilot list all copilot seat assignments for an organization
- code review
- github copilot remove teams from copilot subscription
- github copilot get copilot billing information for an organization
- removeteamsfromcopilotsubscription
- github copilot get enterprise copilot usage metrics for a specific day
- github
- github copilot add teams to copilot subscription
- getcopilotcontentexclusionrules
- github copilot get copilot metrics for an organization
slug: github-copilot-capability
source_filename: github-copilot-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GitHub Copilot REST API\n  description: REST API for managing GitHub Copilot seat assignments, billing, usage metrics, content exclusion rules, and\n    organizational settings. Covers user management, aggregated metrics, usage reports, and content governance across organizations\n    and enterprises.\n  tags:\n  - Github\n  - Copilot\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: github-copilot\n    baseUri: https://api.github.com\n    description: GitHub Copilot REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_COPILOT_TOKEN}}'\n    resources:\n    - name: orgs-org-copilot-billing\n      path: /orgs/{org}/copilot/billing\n      operations:\n      - name: getcopilotbillingfororganization\n        method: GET\n        description: Github Copilot Get Copilot Billing Information for an Organization\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-copilot-billing-seats\n      path: /orgs/{org}/copilot/billing/seats\n      operations:\n      - name: listcopilotseats\n        method: GET\n        description: Github Copilot List All Copilot Seat Assignments for an Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-copilot-billing-selected-teams\n      path: /orgs/{org}/copilot/billing/selected_teams\n      operations:\n      - name: addteamstocopilotsubscription\n        method: POST\n        description: Github Copilot Add Teams to Copilot Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeteamsfromcopilotsubscription\n        method: DELETE\n        description: Github Copilot Remove Teams From Copilot\
  \ Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-copilot-billing-selected-users\n      path: /orgs/{org}/copilot/billing/selected_users\n      operations:\n      - name: adduserstocopilotsubscription\n        method: POST\n        description: Github Copilot Add Users to Copilot Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeusersfromcopilotsubscription\n        method: DELETE\n        description: Github Copilot Remove Users From Copilot Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-members-username-copilot\n      path: /orgs/{org}/members/{username}/copilot\n      operations:\n      - name: getcopilotseatforuser\n        method: GET\n        description:\
  \ Github Copilot Get Copilot Seat Assignment Details for a User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-copilot-metrics\n      path: /orgs/{org}/copilot/metrics\n      operations:\n      - name: getcopilotmetricsfororganization\n        method: GET\n        description: Github Copilot Get Copilot Metrics for an Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-team-team-slug-copilot-metrics\n      path: /orgs/{org}/team/{team_slug}/copilot/metrics\n      operations:\n      - name: getcopilotmetricsforteam\n        method: GET\n        description: Github Copilot Get Copilot Metrics for a Team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enterprises-enterprise-copilot-metrics-reports-e\n\
  \      path: /enterprises/{enterprise}/copilot/metrics/reports/enterprise-1-day\n      operations:\n      - name: getenterprisecopilotusagedaily\n        method: GET\n        description: Github Copilot Get Enterprise Copilot Usage Metrics for a Specific Day\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enterprises-enterprise-copilot-metrics-reports-e\n      path: /enterprises/{enterprise}/copilot/metrics/reports/enterprise-28-day/latest\n      operations:\n      - name: getenterprisecopilotusage28day\n        method: GET\n        description: Github Copilot Get Latest 28-day Enterprise Copilot Usage Metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enterprises-enterprise-copilot-metrics-reports-u\n      path: /enterprises/{enterprise}/copilot/metrics/reports/users-1-day\n      operations:\n     \
  \ - name: getenterpriseuserscopilotusagedaily\n        method: GET\n        description: Github Copilot Get Enterprise User-level Copilot Usage Metrics for a Specific Day\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enterprises-enterprise-copilot-metrics-reports-u\n      path: /enterprises/{enterprise}/copilot/metrics/reports/users-28-day/latest\n      operations:\n      - name: getenterpriseuserscopilotusage28day\n        method: GET\n        description: Github Copilot Get Latest 28-day Enterprise User-level Copilot Usage Metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-copilot-metrics-reports-organization-1-\n      path: /orgs/{org}/copilot/metrics/reports/organization-1-day\n      operations:\n      - name: getorganizationcopilotusagedaily\n        method: GET\n        description:\
  \ Github Copilot Get Organization Copilot Usage Metrics for a Specific Day\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-copilot-metrics-reports-organization-28\n      path: /orgs/{org}/copilot/metrics/reports/organization-28-day/latest\n      operations:\n      - name: getorganizationcopilotusage28day\n        method: GET\n        description: Github Copilot Get Latest 28-day Organization Copilot Usage Metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-copilot-metrics-reports-users-1-day\n      path: /orgs/{org}/copilot/metrics/reports/users-1-day\n      operations:\n      - name: getorganizationuserscopilotusagedaily\n        method: GET\n        description: Github Copilot Get Organization User-level Copilot Usage Metrics for a Specific Day\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-copilot-metrics-reports-users-28-day-la\n      path: /orgs/{org}/copilot/metrics/reports/users-28-day/latest\n      operations:\n      - name: getorganizationuserscopilotusage28day\n        method: GET\n        description: Github Copilot Get Latest 28-day Organization User-level Copilot Usage Metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-org-copilot-content-exclusion\n      path: /orgs/{org}/copilot/content_exclusion\n      operations:\n      - name: getcopilotcontentexclusionrules\n        method: GET\n        description: Github Copilot Get Copilot Content Exclusion Rules for an Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setcopilotcontentexclusionrules\n \
  \       method: PUT\n        description: Github Copilot Set Copilot Content Exclusion Rules for an Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: github-copilot-rest\n    description: REST adapter for GitHub Copilot REST API.\n    resources:\n    - path: /orgs/{org}/copilot/billing\n      name: getcopilotbillingfororganization\n      operations:\n      - method: GET\n        name: getcopilotbillingfororganization\n        description: Github Copilot Get Copilot Billing Information for an Organization\n        call: github-copilot.getcopilotbillingfororganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/billing/seats\n      name: listcopilotseats\n      operations:\n      - method: GET\n        name: listcopilotseats\n        description: Github Copilot List All Copilot\
  \ Seat Assignments for an Organization\n        call: github-copilot.listcopilotseats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/billing/selected_teams\n      name: addteamstocopilotsubscription\n      operations:\n      - method: POST\n        name: addteamstocopilotsubscription\n        description: Github Copilot Add Teams to Copilot Subscription\n        call: github-copilot.addteamstocopilotsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/billing/selected_teams\n      name: removeteamsfromcopilotsubscription\n      operations:\n      - method: DELETE\n        name: removeteamsfromcopilotsubscription\n        description: Github Copilot Remove Teams From Copilot Subscription\n        call: github-copilot.removeteamsfromcopilotsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/billing/selected_users\n\
  \      name: adduserstocopilotsubscription\n      operations:\n      - method: POST\n        name: adduserstocopilotsubscription\n        description: Github Copilot Add Users to Copilot Subscription\n        call: github-copilot.adduserstocopilotsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/billing/selected_users\n      name: removeusersfromcopilotsubscription\n      operations:\n      - method: DELETE\n        name: removeusersfromcopilotsubscription\n        description: Github Copilot Remove Users From Copilot Subscription\n        call: github-copilot.removeusersfromcopilotsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/members/{username}/copilot\n      name: getcopilotseatforuser\n      operations:\n      - method: GET\n        name: getcopilotseatforuser\n        description: Github Copilot Get Copilot Seat Assignment Details for a User\n    \
  \    call: github-copilot.getcopilotseatforuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/metrics\n      name: getcopilotmetricsfororganization\n      operations:\n      - method: GET\n        name: getcopilotmetricsfororganization\n        description: Github Copilot Get Copilot Metrics for an Organization\n        call: github-copilot.getcopilotmetricsfororganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/team/{team_slug}/copilot/metrics\n      name: getcopilotmetricsforteam\n      operations:\n      - method: GET\n        name: getcopilotmetricsforteam\n        description: Github Copilot Get Copilot Metrics for a Team\n        call: github-copilot.getcopilotmetricsforteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /enterprises/{enterprise}/copilot/metrics/reports/enterprise-1-day\n      name: getenterprisecopilotusagedaily\n\
  \      operations:\n      - method: GET\n        name: getenterprisecopilotusagedaily\n        description: Github Copilot Get Enterprise Copilot Usage Metrics for a Specific Day\n        call: github-copilot.getenterprisecopilotusagedaily\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /enterprises/{enterprise}/copilot/metrics/reports/enterprise-28-day/latest\n      name: getenterprisecopilotusage28day\n      operations:\n      - method: GET\n        name: getenterprisecopilotusage28day\n        description: Github Copilot Get Latest 28-day Enterprise Copilot Usage Metrics\n        call: github-copilot.getenterprisecopilotusage28day\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /enterprises/{enterprise}/copilot/metrics/reports/users-1-day\n      name: getenterpriseuserscopilotusagedaily\n      operations:\n      - method: GET\n        name: getenterpriseuserscopilotusagedaily\n        description: Github Copilot\
  \ Get Enterprise User-level Copilot Usage Metrics for a Specific Day\n        call: github-copilot.getenterpriseuserscopilotusagedaily\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /enterprises/{enterprise}/copilot/metrics/reports/users-28-day/latest\n      name: getenterpriseuserscopilotusage28day\n      operations:\n      - method: GET\n        name: getenterpriseuserscopilotusage28day\n        description: Github Copilot Get Latest 28-day Enterprise User-level Copilot Usage Metrics\n        call: github-copilot.getenterpriseuserscopilotusage28day\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/metrics/reports/organization-1-day\n      name: getorganizationcopilotusagedaily\n      operations:\n      - method: GET\n        name: getorganizationcopilotusagedaily\n        description: Github Copilot Get Organization Copilot Usage Metrics for a Specific Day\n        call: github-copilot.getorganizationcopilotusagedaily\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/metrics/reports/organization-28-day/latest\n      name: getorganizationcopilotusage28day\n      operations:\n      - method: GET\n        name: getorganizationcopilotusage28day\n        description: Github Copilot Get Latest 28-day Organization Copilot Usage Metrics\n        call: github-copilot.getorganizationcopilotusage28day\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/metrics/reports/users-1-day\n      name: getorganizationuserscopilotusagedaily\n      operations:\n      - method: GET\n        name: getorganizationuserscopilotusagedaily\n        description: Github Copilot Get Organization User-level Copilot Usage Metrics for a Specific Day\n        call: github-copilot.getorganizationuserscopilotusagedaily\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/metrics/reports/users-28-day/latest\n\
  \      name: getorganizationuserscopilotusage28day\n      operations:\n      - method: GET\n        name: getorganizationuserscopilotusage28day\n        description: Github Copilot Get Latest 28-day Organization User-level Copilot Usage Metrics\n        call: github-copilot.getorganizationuserscopilotusage28day\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/content_exclusion\n      name: getcopilotcontentexclusionrules\n      operations:\n      - method: GET\n        name: getcopilotcontentexclusionrules\n        description: Github Copilot Get Copilot Content Exclusion Rules for an Organization\n        call: github-copilot.getcopilotcontentexclusionrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{org}/copilot/content_exclusion\n      name: setcopilotcontentexclusionrules\n      operations:\n      - method: PUT\n        name: setcopilotcontentexclusionrules\n        description:\
  \ Github Copilot Set Copilot Content Exclusion Rules for an Organization\n        call: github-copilot.setcopilotcontentexclusionrules\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: github-copilot-mcp\n    transport: http\n    description: MCP adapter for GitHub Copilot REST API for AI agent use.\n    tools:\n    - name: getcopilotbillingfororganization\n      description: Github Copilot Get Copilot Billing Information for an Organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getcopilotbillingfororganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcopilotseats\n      description: Github Copilot List All Copilot Seat Assignments for an Organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.listcopilotseats\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: addteamstocopilotsubscription\n      description: Github Copilot Add Teams to Copilot Subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: github-copilot.addteamstocopilotsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeteamsfromcopilotsubscription\n      description: Github Copilot Remove Teams From Copilot Subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: github-copilot.removeteamsfromcopilotsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adduserstocopilotsubscription\n      description: Github Copilot Add Users to Copilot Subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: github-copilot.adduserstocopilotsubscription\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeusersfromcopilotsubscription\n      description: Github Copilot Remove Users From Copilot Subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: github-copilot.removeusersfromcopilotsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcopilotseatforuser\n      description: Github Copilot Get Copilot Seat Assignment Details for a User\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getcopilotseatforuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcopilotmetricsfororganization\n      description: Github Copilot Get Copilot Metrics for an Organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getcopilotmetricsfororganization\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcopilotmetricsforteam\n      description: Github Copilot Get Copilot Metrics for a Team\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getcopilotmetricsforteam\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenterprisecopilotusagedaily\n      description: Github Copilot Get Enterprise Copilot Usage Metrics for a Specific Day\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getenterprisecopilotusagedaily\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenterprisecopilotusage28day\n      description: Github Copilot Get Latest 28-day Enterprise Copilot Usage Metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getenterprisecopilotusage28day\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenterpriseuserscopilotusagedaily\n      description: Github Copilot Get Enterprise User-level Copilot Usage Metrics for a Specific Day\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getenterpriseuserscopilotusagedaily\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenterpriseuserscopilotusage28day\n      description: Github Copilot Get Latest 28-day Enterprise User-level Copilot Usage Metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getenterpriseuserscopilotusage28day\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganizationcopilotusagedaily\n      description: Github Copilot Get Organization Copilot Usage Metrics for a Specific Day\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: github-copilot.getorganizationcopilotusagedaily\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganizationcopilotusage28day\n      description: Github Copilot Get Latest 28-day Organization Copilot Usage Metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getorganizationcopilotusage28day\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganizationuserscopilotusagedaily\n      description: Github Copilot Get Organization User-level Copilot Usage Metrics for a Specific Day\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getorganizationuserscopilotusagedaily\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganizationuserscopilotusage28day\n      description: Github Copilot Get Latest 28-day\
  \ Organization User-level Copilot Usage Metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getorganizationuserscopilotusage28day\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcopilotcontentexclusionrules\n      description: Github Copilot Get Copilot Content Exclusion Rules for an Organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: github-copilot.getcopilotcontentexclusionrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setcopilotcontentexclusionrules\n      description: Github Copilot Set Copilot Content Exclusion Rules for an Organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: github-copilot.setcopilotcontentexclusionrules\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace:\
  \ env\n  keys:\n    GITHUB_COPILOT_TOKEN: GITHUB_COPILOT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/github-copilot/refs/heads/main/capabilities/github-copilot-capability.yaml
tags:
- Github
- Copilot
- API
tools:
- description: Github Copilot Get Copilot Billing Information for an Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcopilotbillingfororganization
- description: Github Copilot List All Copilot Seat Assignments for an Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcopilotseats
- description: Github Copilot Add Teams to Copilot Subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addteamstocopilotsubscription
- description: Github Copilot Remove Teams From Copilot Subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeteamsfromcopilotsubscription
- description: Github Copilot Add Users to Copilot Subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: adduserstocopilotsubscription
- description: Github Copilot Remove Users From Copilot Subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeusersfromcopilotsubscription
- description: Github Copilot Get Copilot Seat Assignment Details for a User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcopilotseatforuser
- description: Github Copilot Get Copilot Metrics for an Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcopilotmetricsfororganization
- description: Github Copilot Get Copilot Metrics for a Team
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcopilotmetricsforteam
- description: Github Copilot Get Enterprise Copilot Usage Metrics for a Specific Day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenterprisecopilotusagedaily
- description: Github Copilot Get Latest 28-day Enterprise Copilot Usage Metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenterprisecopilotusage28day
- description: Github Copilot Get Enterprise User-level Copilot Usage Metrics for a Specific Day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenterpriseuserscopilotusagedaily
- description: Github Copilot Get Latest 28-day Enterprise User-level Copilot Usage Metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenterpriseuserscopilotusage28day
- description: Github Copilot Get Organization Copilot Usage Metrics for a Specific Day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationcopilotusagedaily
- description: Github Copilot Get Latest 28-day Organization Copilot Usage Metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationcopilotusage28day
- description: Github Copilot Get Organization User-level Copilot Usage Metrics for a Specific Day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationuserscopilotusagedaily
- description: Github Copilot Get Latest 28-day Organization User-level Copilot Usage Metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationuserscopilotusage28day
- description: Github Copilot Get Copilot Content Exclusion Rules for an Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcopilotcontentexclusionrules
- description: Github Copilot Set Copilot Content Exclusion Rules for an Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setcopilotcontentexclusionrules
---
