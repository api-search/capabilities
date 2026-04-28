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
- action plan management
- create an action plan from survey insights
- get survey analytics
- list participants
- list action plans
- human resources
- list all engagement surveys
- create survey
- list improvement action plans created from survey findings
- analyst who interprets engagement data and generates insights and recommendations
- list survey participants
- analytics
- create engagement survey
- list participants and track who has responded to a survey
- survey analytics and reporting
- get engagement analytics for a survey
- list all allianz employee engagement surveys with status and type filtering
- list action plans for a survey
- creating and tracking improvement initiatives from survey findings
- enterprise
- surveys
- add survey participants
- survey management for hr teams
- hr professional responsible for running engagement surveys and following up with business units
- analyzing survey results and generating engagement insights
- People Analytics Analyst
- get analytics
- create a new engagement survey
- create a new annual, pulse, onboarding, or exit engagement survey
- create an action plan to address employee engagement survey findings
- get aggregated engagement scores, participation rates, and insights for a survey
- list participants and response status
- HR Business Partner
- end-to-end workflow for hr teams running engagement surveys
- list engagement surveys
- participant management for a survey
- add participants
- create action plan
- add employees to a survey and send invitation emails
- get engagement survey
- creating and managing employee engagement surveys
- add employees as survey participants
- insurance
- list surveys
- Team Manager
- employee experience
- people manager who reviews team-level results and creates action plans
- get details and configuration of a specific engagement survey
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
