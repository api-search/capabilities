---
consumed_apis:
- workday-recruiting
- workday-talent
- workday-performance
description: Unified talent and performance management combining Recruiting, Talent, and Performance Management APIs for HR and talent leads to manage hiring pipelines, career development, and performance evaluations.
layout: capability
name: Workday Talent and Performance
operations:
- description: List job requisitions
  method: GET
  name: list-requisitions
  path: /v1/job-requisitions
- description: List candidates
  method: GET
  name: list-candidates
  path: /v1/candidates
- description: List performance reviews
  method: GET
  name: list-reviews
  path: /v1/performance-reviews
- description: List succession plans
  method: GET
  name: list-succession-plans
  path: /v1/succession-plans
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- list succession plans
- list all job requisitions
- performance
- list candidates
- list performance reviews
- recruiting list prospects
- job requisitions
- recruiting list requisitions
- enterprise software
- give a feedback badge to a worker
- get a candidate by id
- recruiting list applications
- get a job requisition by id
- recruiting list postings
- saas
- talent list mentorships
- talent get certifications
- cloud computing
- list reviews
- list all job postings
- list all prospects
- talent get profile
- recruiting list candidates
- talent list succession plans
- recruiting get requisition
- get certifications for a worker
- recruiting get application
- list requisitions
- hcm
- list mentorships
- list all job applications
- financial management
- list all candidates
- talent management
- get goals for a worker
- list feedback badges
- succession plans
- recruiting get candidate
- performance give badge
- list job requisitions
- request feedback for a worker
- candidates
- talent get skills
- get a job application by id
- get skills for a worker
- performance list reviews
- performance get goals
- performance reviews
- performance request feedback
- get talent profile for a worker
- performance list badges
- recruiting
- workday
slug: talent-and-performance
tags:
- Workday
- Talent Management
- Performance
- Recruiting
tools:
- description: List all job requisitions
  hints:
    readOnly: true
  name: recruiting-list-requisitions
- description: Get a job requisition by ID
  hints:
    readOnly: true
  name: recruiting-get-requisition
- description: List all job postings
  hints:
    readOnly: true
  name: recruiting-list-postings
- description: List all candidates
  hints:
    readOnly: true
  name: recruiting-list-candidates
- description: Get a candidate by ID
  hints:
    readOnly: true
  name: recruiting-get-candidate
- description: List all job applications
  hints:
    readOnly: true
  name: recruiting-list-applications
- description: Get a job application by ID
  hints:
    readOnly: true
  name: recruiting-get-application
- description: List all prospects
  hints:
    readOnly: true
  name: recruiting-list-prospects
- description: Get talent profile for a worker
  hints:
    readOnly: true
  name: talent-get-profile
- description: List mentorships
  hints:
    readOnly: true
  name: talent-list-mentorships
- description: Get skills for a worker
  hints:
    readOnly: true
  name: talent-get-skills
- description: Get certifications for a worker
  hints:
    readOnly: true
  name: talent-get-certifications
- description: List succession plans
  hints:
    readOnly: true
  name: talent-list-succession-plans
- description: Get goals for a worker
  hints:
    readOnly: true
  name: performance-get-goals
- description: List performance reviews
  hints:
    readOnly: true
  name: performance-list-reviews
- description: List feedback badges
  hints:
    readOnly: true
  name: performance-list-badges
- description: Give a feedback badge to a worker
  hints:
    readOnly: false
  name: performance-give-badge
- description: Request feedback for a worker
  hints:
    readOnly: false
  name: performance-request-feedback
---
