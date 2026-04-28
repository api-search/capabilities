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
- staffing create job change
- person get person
- cloud computing
- hcm list organizations
- get a person by id
- create a job change request
- initiate a worker termination
- list all countries
- country reference data
- list all workers with optional search and pagination
- list all locations
- get a worker by id
- hcm get worker
- list all job profiles
- get change history for a worker
- hcm get worker history
- financial management
- get worker
- position management
- staffing terminate worker
- list supervisory organizations
- worker detail
- hcm list workers
- workforce management
- list countries
- supervisory organizations
- hcm get worker inbox tasks
- list all workers
- list all people
- get a specific worker by id
- person list people
- worker management
- human resources
- get work contact information
- staffing list positions
- hcm
- get home contact information
- list all positions
- person get home contact
- common list countries
- list workers
- list all currencies
- common list currencies
- workday
- list organizations
- staffing list job profiles
- list positions
- enterprise software
- list people
- person get work contact
- get inbox tasks for a worker
- hcm list locations
- saas
- person data
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
