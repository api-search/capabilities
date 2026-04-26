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
- list mentorships
- recruiting get requisition
- recruiting list postings
- recruiting list candidates
- performance
- list candidates
- performance list reviews
- performance reviews
- list all job applications
- request feedback for a worker
- get a job requisition by id
- list performance reviews
- list all job postings
- cloud computing
- list requisitions
- get a candidate by id
- financial management
- succession plans
- talent list succession plans
- performance get goals
- performance request feedback
- recruiting list requisitions
- get a job application by id
- recruiting list applications
- list all candidates
- list all prospects
- recruiting get application
- get goals for a worker
- saas
- performance list badges
- talent get profile
- workday
- list reviews
- hcm
- performance give badge
- list all job requisitions
- list job requisitions
- candidates
- list feedback badges
- give a feedback badge to a worker
- talent list mentorships
- list succession plans
- enterprise software
- talent management
- recruiting list prospects
- talent get certifications
- get certifications for a worker
- talent get skills
- recruiting
- get skills for a worker
- get talent profile for a worker
- recruiting get candidate
- job requisitions
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
