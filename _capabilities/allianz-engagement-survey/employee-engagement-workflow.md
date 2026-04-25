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
- HR Business Partner
- list participants and response status
- create engagement survey
- get details and configuration of a specific engagement survey
- creating and tracking improvement initiatives from survey findings
- create survey
- get analytics
- create action plan
- analytics
- add employees to a survey and send invitation emails
- list engagement surveys
- Team Manager
- create a new annual, pulse, onboarding, or exit engagement survey
- list all engagement surveys
- enterprise
- employee experience
- analyst who interprets engagement data and generates insights and recommendations
- list participants
- human resources
- list action plans
- add survey participants
- action plan management
- list surveys
- create an action plan from survey insights
- creating and managing employee engagement surveys
- add employees as survey participants
- analyzing survey results and generating engagement insights
- insurance
- hr professional responsible for running engagement surveys and following up with business units
- get aggregated engagement scores, participation rates, and insights for a survey
- create a new engagement survey
- list action plans for a survey
- get engagement analytics for a survey
- People Analytics Analyst
- list all allianz employee engagement surveys with status and type filtering
- end-to-end workflow for hr teams running engagement surveys
- add participants
- list participants and track who has responded to a survey
- surveys
- list improvement action plans created from survey findings
- people manager who reviews team-level results and creates action plans
- get engagement survey
- create an action plan to address employee engagement survey findings
- survey management for hr teams
- survey analytics and reporting
- participant management for a survey
- get survey analytics
- list survey participants
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
