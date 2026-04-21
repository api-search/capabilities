---
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
- staffing terminate worker
- create a job change request
- hcm list workers
- country reference data
- worker management
- list all countries
- list positions
- list all people
- hcm get worker inbox tasks
- person get work contact
- financial management
- list countries
- common list currencies
- workday
- list workers
- saas
- position management
- list organizations
- get a worker by id
- get home contact information
- hcm
- hcm list locations
- get work contact information
- person list people
- staffing create job change
- list all job profiles
- enterprise software
- get a specific worker by id
- initiate a worker termination
- get inbox tasks for a worker
- list all currencies
- list all workers
- hcm get worker history
- person data
- list people
- staffing list positions
- worker detail
- list all positions
- list supervisory organizations
- list all locations
- person get home contact
- supervisory organizations
- workforce management
- list all workers with optional search and pagination
- common list countries
- hcm list organizations
- get a person by id
- staffing list job profiles
- hcm get worker
- cloud computing
- get worker
- get change history for a worker
- human resources
- person get person
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
