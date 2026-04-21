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
- get goals for a worker
- get a job application by id
- performance get goals
- list job requisitions
- list all candidates
- get certifications for a worker
- list succession plans
- list all job applications
- give a feedback badge to a worker
- list all job requisitions
- performance
- recruiting list prospects
- list candidates
- performance give badge
- list all job postings
- candidates
- recruiting get requisition
- job requisitions
- list all prospects
- recruiting list candidates
- get a job requisition by id
- get talent profile for a worker
- talent get certifications
- recruiting get candidate
- workday
- recruiting get application
- list reviews
- request feedback for a worker
- talent list succession plans
- performance reviews
- saas
- hcm
- talent get profile
- financial management
- recruiting
- talent management
- get a candidate by id
- recruiting list postings
- get skills for a worker
- list performance reviews
- talent get skills
- list mentorships
- enterprise software
- talent list mentorships
- cloud computing
- list feedback badges
- performance request feedback
- recruiting list requisitions
- recruiting list applications
- performance list badges
- performance list reviews
- succession plans
- list requisitions
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
