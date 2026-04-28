---
categories:
- payroll-hr
consumed_apis:
- workday-hcm
- workday-person
- workday-staffing
- workday-common
description: Unified workforce management combining HCM, Person, Staffing, and Common APIs for HR administrators to manage workers, organizations, positions, and reference data.
layout: capability
name: Workday Workforce Management
operations:
- description: List all workers
  method: GET
  name: list-workers
  path: /v1/workers
- description: Get a worker by ID
  method: GET
  name: get-worker
  path: /v1/workers/{id}
- description: List all people
  method: GET
  name: list-people
  path: /v1/people
- description: List all positions
  method: GET
  name: list-positions
  path: /v1/positions
- description: List supervisory organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List all countries
  method: GET
  name: list-countries
  path: /v1/countries
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- get worker
- list all people
- hcm list workers
- list all currencies
- list all locations
- list supervisory organizations
- get change history for a worker
- person get home contact
- hcm get worker inbox tasks
- hcm list locations
- staffing list positions
- initiate a worker termination
- person get work contact
- list workers
- worker management
- country reference data
- hcm get worker
- list all countries
- person list people
- staffing list job profiles
- get home contact information
- get a worker by id
- workday
- list all positions
- list people
- human resources
- worker detail
- list all workers
- get work contact information
- list all workers with optional search and pagination
- enterprise software
- financial management
- position management
- list countries
- hcm list organizations
- list positions
- create a job change request
- cloud computing
- saas
- staffing terminate worker
- person data
- get a specific worker by id
- list organizations
- get inbox tasks for a worker
- person get person
- hcm get worker history
- list all job profiles
- common list currencies
- workforce management
- get a person by id
- common list countries
- hcm
- staffing create job change
- supervisory organizations
slug: workforce-management
tags:
- Workday
- Workforce Management
- Human Resources
tools:
- description: List all workers with optional search and pagination
  hints:
    openWorld: true
    readOnly: true
  name: hcm-list-workers
- description: Get a specific worker by ID
  hints:
    readOnly: true
  name: hcm-get-worker
- description: Get change history for a worker
  hints:
    readOnly: true
  name: hcm-get-worker-history
- description: Get inbox tasks for a worker
  hints:
    readOnly: true
  name: hcm-get-worker-inbox-tasks
- description: List supervisory organizations
  hints:
    readOnly: true
  name: hcm-list-organizations
- description: List all locations
  hints:
    readOnly: true
  name: hcm-list-locations
- description: List all people
  hints:
    readOnly: true
  name: person-list-people
- description: Get a person by ID
  hints:
    readOnly: true
  name: person-get-person
- description: Get home contact information
  hints:
    readOnly: true
  name: person-get-home-contact
- description: Get work contact information
  hints:
    readOnly: true
  name: person-get-work-contact
- description: List all positions
  hints:
    readOnly: true
  name: staffing-list-positions
- description: List all job profiles
  hints:
    readOnly: true
  name: staffing-list-job-profiles
- description: Create a job change request
  hints:
    readOnly: false
  name: staffing-create-job-change
- description: Initiate a worker termination
  hints:
    destructive: true
    readOnly: false
  name: staffing-terminate-worker
- description: List all countries
  hints:
    readOnly: true
  name: common-list-countries
- description: List all currencies
  hints:
    readOnly: true
  name: common-list-currencies
---
