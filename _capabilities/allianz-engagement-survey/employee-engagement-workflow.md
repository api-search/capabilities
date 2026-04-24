---
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
- get analytics
- create engagement survey
- add participants
- insurance
- create action plan
- People Analytics Analyst
- add survey participants
- list action plans
- get details and configuration of a specific engagement survey
- create a new engagement survey
- survey management for hr teams
- analytics
- list participants and track who has responded to a survey
- employee experience
- HR Business Partner
- list all allianz employee engagement surveys with status and type filtering
- get survey analytics
- list improvement action plans created from survey findings
- people manager who reviews team-level results and creates action plans
- Team Manager
- human resources
- get engagement analytics for a survey
- action plan management
- list survey participants
- creating and tracking improvement initiatives from survey findings
- analyst who interprets engagement data and generates insights and recommendations
- create an action plan from survey insights
- end-to-end workflow for hr teams running engagement surveys
- survey analytics and reporting
- create an action plan to address employee engagement survey findings
- add employees as survey participants
- list surveys
- list participants
- analyzing survey results and generating engagement insights
- add employees to a survey and send invitation emails
- list participants and response status
- create survey
- participant management for a survey
- get engagement survey
- hr professional responsible for running engagement surveys and following up with business units
- create a new annual, pulse, onboarding, or exit engagement survey
- creating and managing employee engagement surveys
- list engagement surveys
- list all engagement surveys
- get aggregated engagement scores, participation rates, and insights for a survey
- surveys
- list action plans for a survey
- enterprise
slug: employee-engagement-workflow
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
