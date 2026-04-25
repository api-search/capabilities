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
- action plan management
- get details and configuration of a specific engagement survey
- analyzing survey results and generating engagement insights
- analytics
- list action plans
- list participants and track who has responded to a survey
- list all allianz employee engagement surveys with status and type filtering
- hr professional responsible for running engagement surveys and following up with business units
- list engagement surveys
- human resources
- participant management for a survey
- HR Business Partner
- add participants
- list all engagement surveys
- Team Manager
- enterprise
- add survey participants
- add employees as survey participants
- create an action plan from survey insights
- creating and tracking improvement initiatives from survey findings
- list participants and response status
- People Analytics Analyst
- get engagement analytics for a survey
- survey management for hr teams
- list participants
- create engagement survey
- creating and managing employee engagement surveys
- get analytics
- get aggregated engagement scores, participation rates, and insights for a survey
- list surveys
- insurance
- list survey participants
- create an action plan to address employee engagement survey findings
- survey analytics and reporting
- employee experience
- create action plan
- create survey
- get survey analytics
- create a new engagement survey
- list improvement action plans created from survey findings
- create a new annual, pulse, onboarding, or exit engagement survey
- analyst who interprets engagement data and generates insights and recommendations
- list action plans for a survey
- surveys
- add employees to a survey and send invitation emails
- end-to-end workflow for hr teams running engagement surveys
- people manager who reviews team-level results and creates action plans
- get engagement survey
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
