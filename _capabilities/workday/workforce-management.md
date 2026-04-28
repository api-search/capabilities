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
- hcm list workers
- list all currencies
- list workers
- cloud computing
- worker management
- list all positions
- get worker
- get a person by id
- human resources
- staffing list job profiles
- list organizations
- position management
- get a worker by id
- staffing list positions
- common list countries
- hcm list locations
- list all locations
- get home contact information
- person get home contact
- person data
- common list currencies
- list countries
- list all workers
- hcm
- list all countries
- list all job profiles
- initiate a worker termination
- staffing terminate worker
- hcm get worker
- workday
- person get person
- staffing create job change
- supervisory organizations
- get change history for a worker
- get work contact information
- saas
- list people
- list all people
- list positions
- enterprise software
- hcm get worker history
- hcm get worker inbox tasks
- person list people
- person get work contact
- country reference data
- list supervisory organizations
- workforce management
- create a job change request
- get inbox tasks for a worker
- financial management
- list all workers with optional search and pagination
- hcm list organizations
- get a specific worker by id
- worker detail
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
