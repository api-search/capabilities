---
categories:
- payroll-hr
consumed_apis:
- allianz-engagement-survey
description: Workflow capability for HR teams running employee engagement surveys at Allianz, covering survey planning, participant management, results analysis, and action plan tracking.
layout: capability
name: Allianz Employee Engagement Workflow
operations:
- description: List all engagement surveys
  method: GET
  name: list-surveys
  path: /v1/surveys
- description: Create a new engagement survey
  method: POST
  name: create-survey
  path: /v1/surveys
- description: List participants and response status
  method: GET
  name: list-participants
  path: /v1/surveys/{survey_id}/participants
- description: Add employees as survey participants
  method: POST
  name: add-participants
  path: /v1/surveys/{survey_id}/participants
- description: Get engagement analytics for a survey
  method: GET
  name: get-analytics
  path: /v1/surveys/{survey_id}/analytics
- description: List action plans for a survey
  method: GET
  name: list-action-plans
  path: /v1/surveys/{survey_id}/action-plans
- description: Create an action plan from survey insights
  method: POST
  name: create-action-plan
  path: /v1/surveys/{survey_id}/action-plans
personas: []
provider_name: Allianz Engagement Survey
provider_slug: allianz-engagement-survey
search_terms:
- list engagement surveys
- people manager who reviews team-level results and creates action plans
- analyzing survey results and generating engagement insights
- create survey
- survey management for hr teams
- list participants and response status
- list improvement action plans created from survey findings
- list participants
- list action plans for a survey
- creating and managing employee engagement surveys
- survey analytics and reporting
- add employees to a survey and send invitation emails
- list all engagement surveys
- employee experience
- create engagement survey
- add survey participants
- HR Business Partner
- add employees as survey participants
- get engagement analytics for a survey
- list action plans
- list participants and track who has responded to a survey
- human resources
- create a new engagement survey
- hr professional responsible for running engagement surveys and following up with business units
- analyst who interprets engagement data and generates insights and recommendations
- create action plan
- People Analytics Analyst
- action plan management
- get engagement survey
- add participants
- create a new annual, pulse, onboarding, or exit engagement survey
- list survey participants
- surveys
- create an action plan from survey insights
- get survey analytics
- get analytics
- enterprise
- list surveys
- creating and tracking improvement initiatives from survey findings
- participant management for a survey
- insurance
- analytics
- get details and configuration of a specific engagement survey
- end-to-end workflow for hr teams running engagement surveys
- create an action plan to address employee engagement survey findings
- get aggregated engagement scores, participation rates, and insights for a survey
- list all allianz employee engagement surveys with status and type filtering
- Team Manager
slug: employee-engagement-workflow
source_filename: employee-engagement-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Allianz Employee Engagement Workflow\"\n  description: \"Workflow capability for HR teams running employee engagement surveys at Allianz, covering survey planning, participant management, results analysis, and action plan tracking.\"\n  tags:\n    - Human Resources\n    - Employee Experience\n    - Surveys\n    - Analytics\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALLIANZ_ENGAGEMENT_CLIENT_ID: ALLIANZ_ENGAGEMENT_CLIENT_ID\n      ALLIANZ_ENGAGEMENT_CLIENT_SECRET: ALLIANZ_ENGAGEMENT_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: allianz-engagement-survey\n      location: ./shared/engagement-survey.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: allianz-employee-engagement-api\n      description: \"Unified REST API for Allianz employee engagement survey workflows.\"\n      resources:\n        - path: /v1/surveys\n          name: surveys\n\
  \          description: \"Survey management for HR teams\"\n          operations:\n            - method: GET\n              name: list-surveys\n              description: \"List all engagement surveys\"\n              call: \"allianz-engagement-survey.list-surveys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-survey\n              description: \"Create a new engagement survey\"\n              call: \"allianz-engagement-survey.create-survey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/surveys/{survey_id}/participants\n          name: participants\n          description: \"Participant management for a survey\"\n          operations:\n            - method: GET\n              name: list-participants\n              description: \"List participants and response status\"\n              call: \"allianz-engagement-survey.list-participants\"\
  \n              with:\n                survey_id: \"rest.survey_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-participants\n              description: \"Add employees as survey participants\"\n              call: \"allianz-engagement-survey.add-participants\"\n              with:\n                survey_id: \"rest.survey_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/surveys/{survey_id}/analytics\n          name: analytics\n          description: \"Survey analytics and reporting\"\n          operations:\n            - method: GET\n              name: get-analytics\n              description: \"Get engagement analytics for a survey\"\n              call: \"allianz-engagement-survey.get-survey-analytics\"\n              with:\n                survey_id: \"rest.survey_id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/surveys/{survey_id}/action-plans\n          name: action-plans\n          description: \"Action plan management\"\n          operations:\n            - method: GET\n              name: list-action-plans\n              description: \"List action plans for a survey\"\n              call: \"allianz-engagement-survey.list-action-plans\"\n              with:\n                survey_id: \"rest.survey_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-action-plan\n              description: \"Create an action plan from survey insights\"\n              call: \"allianz-engagement-survey.create-action-plan\"\n              with:\n                survey_id: \"rest.survey_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n     \
  \ port: 9090\n      namespace: allianz-employee-engagement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted employee engagement survey workflows.\"\n      tools:\n        - name: list-engagement-surveys\n          description: \"List all Allianz employee engagement surveys with status and type filtering\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-engagement-survey.list-surveys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-engagement-survey\n          description: \"Create a new annual, pulse, onboarding, or exit engagement survey\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-engagement-survey.create-survey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-engagement-survey\n          description: \"Get details\
  \ and configuration of a specific engagement survey\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-engagement-survey.get-survey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-survey-participants\n          description: \"List participants and track who has responded to a survey\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-engagement-survey.list-participants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-survey-participants\n          description: \"Add employees to a survey and send invitation emails\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-engagement-survey.add-participants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        -\
  \ name: get-survey-analytics\n          description: \"Get aggregated engagement scores, participation rates, and insights for a survey\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-engagement-survey.get-survey-analytics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-action-plans\n          description: \"List improvement action plans created from survey findings\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-engagement-survey.list-action-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-action-plan\n          description: \"Create an action plan to address employee engagement survey findings\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-engagement-survey.create-action-plan\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/allianz-engagement-survey/refs/heads/main/capabilities/employee-engagement-workflow.yaml
tags:
- Human Resources
- Employee Experience
- Surveys
- Analytics
tools:
- description: List all Allianz employee engagement surveys with status and type filtering
  hints:
    openWorld: false
    readOnly: true
  name: list-engagement-surveys
- description: Create a new annual, pulse, onboarding, or exit engagement survey
  hints:
    openWorld: false
    readOnly: false
  name: create-engagement-survey
- description: Get details and configuration of a specific engagement survey
  hints:
    openWorld: false
    readOnly: true
  name: get-engagement-survey
- description: List participants and track who has responded to a survey
  hints:
    openWorld: false
    readOnly: true
  name: list-survey-participants
- description: Add employees to a survey and send invitation emails
  hints:
    openWorld: false
    readOnly: false
  name: add-survey-participants
- description: Get aggregated engagement scores, participation rates, and insights for a survey
  hints:
    openWorld: false
    readOnly: true
  name: get-survey-analytics
- description: List improvement action plans created from survey findings
  hints:
    openWorld: false
    readOnly: true
  name: list-action-plans
- description: Create an action plan to address employee engagement survey findings
  hints:
    openWorld: false
    readOnly: false
  name: create-action-plan
---
