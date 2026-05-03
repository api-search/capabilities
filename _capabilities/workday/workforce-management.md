---
api_specs:
- filename: hcm.yml
  format: yaml
  label: workday-hcm
  slug: workday-hcm
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/openapi/hcm.yml
- filename: person.yml
  format: yaml
  label: workday-person
  slug: workday-person
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/openapi/person.yml
- filename: staffing.yml
  format: yaml
  label: workday-staffing
  slug: workday-staffing
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/openapi/staffing.yml
- filename: common.yml
  format: yaml
  label: workday-common
  slug: workday-common
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/openapi/common.yml
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
- list all locations
- hcm
- get a person by id
- staffing create job change
- get work contact information
- staffing list job profiles
- list countries
- hcm get worker history
- hcm list locations
- saas
- workforce management
- list all people
- list all positions
- human resources
- worker management
- list all workers with optional search and pagination
- staffing terminate worker
- list all currencies
- list organizations
- get worker
- get inbox tasks for a worker
- list supervisory organizations
- list all countries
- position management
- get a specific worker by id
- common list currencies
- get change history for a worker
- worker detail
- supervisory organizations
- person get person
- country reference data
- get a worker by id
- hcm get worker
- list all job profiles
- common list countries
- hcm get worker inbox tasks
- workday
- person get work contact
- enterprise software
- list all workers
- staffing list positions
- person list people
- hcm list organizations
- financial management
- list people
- list workers
- create a job change request
- initiate a worker termination
- person get home contact
- list positions
- person data
- hcm list workers
- cloud computing
- get home contact information
slug: workforce-management
source_filename: workforce-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Workforce Management\"\n  description: \"Unified workforce management combining HCM, Person, Staffing, and Common APIs for HR administrators to manage workers, organizations, positions, and reference data.\"\n  tags:\n    - Workday\n    - Workforce Management\n    - Human Resources\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: workday-hcm\n      location: ./shared/hcm.yaml\n    - import: workday-person\n      location: ./shared/person.yaml\n    - import: workday-staffing\n      location: ./shared/staffing.yaml\n    - import: workday-common\n      location: ./shared/common.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workforce-management-api\n      description: \"Unified REST API for workforce management operations.\"\n      resources:\n        - path: /v1/workers\n\
  \          name: workers\n          description: \"Worker management\"\n          operations:\n            - method: GET\n              name: list-workers\n              description: \"List all workers\"\n              call: \"workday-hcm.get-workers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{id}\n          name: worker-detail\n          description: \"Worker detail\"\n          operations:\n            - method: GET\n              name: get-worker\n              description: \"Get a worker by ID\"\n              call: \"workday-hcm.get-worker-by-id\"\n              with:\n                ID: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/people\n          name: people\n          description: \"Person data\"\n          operations:\n            - method: GET\n              name: list-people\n              description:\
  \ \"List all people\"\n              call: \"workday-person.get-people\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/positions\n          name: positions\n          description: \"Position management\"\n          operations:\n            - method: GET\n              name: list-positions\n              description: \"List all positions\"\n              call: \"workday-staffing.get-positions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations\n          name: organizations\n          description: \"Supervisory organizations\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List supervisory organizations\"\n              call: \"workday-hcm.get-supervisory-organizations\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/countries\n          name: countries\n          description: \"Country reference data\"\n          operations:\n            - method: GET\n              name: list-countries\n              description: \"List all countries\"\n              call: \"workday-common.get-countries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: workforce-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted workforce management.\"\n      tools:\n        - name: hcm-list-workers\n          description: \"List all workers with optional search and pagination\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workday-hcm.get-workers\"\n          with:\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n            search: \"tools.search\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: hcm-get-worker\n          description: \"Get a specific worker by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-hcm.get-worker-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hcm-get-worker-history\n          description: \"Get change history for a worker\"\n          hints:\n            readOnly: true\n          call: \"workday-hcm.get-worker-history\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hcm-get-worker-inbox-tasks\n          description: \"Get inbox tasks for a worker\"\n          hints:\n            readOnly: true\n          call: \"workday-hcm.get-worker-inbox-tasks\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: hcm-list-organizations\n          description: \"List supervisory organizations\"\n          hints:\n            readOnly: true\n          call: \"workday-hcm.get-supervisory-organizations\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hcm-list-locations\n          description: \"List all locations\"\n          hints:\n            readOnly: true\n          call: \"workday-hcm.get-locations\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: person-list-people\n          description: \"List all people\"\n          hints:\n            readOnly: true\n          call: \"workday-person.get-people\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n        - name: person-get-person\n          description: \"Get a person by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-person.get-person-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: person-get-home-contact\n          description: \"Get home contact information\"\n          hints:\n            readOnly: true\n          call: \"workday-person.get-home-contact-information\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: person-get-work-contact\n          description: \"Get work contact information\"\n          hints:\n            readOnly: true\n          call: \"workday-person.get-work-contact-information\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n        - name: staffing-list-positions\n          description: \"List all positions\"\n          hints:\n            readOnly: true\n          call: \"workday-staffing.get-positions\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: staffing-list-job-profiles\n          description: \"List all job profiles\"\n          hints:\n            readOnly: true\n          call: \"workday-staffing.get-job-profiles\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: staffing-create-job-change\n          description: \"Create a job change request\"\n          hints:\n            readOnly: false\n          call: \"workday-staffing.create-job-change\"\n          with:\n            worker: \"tools.worker\"\n            proposedJob: \"tools.proposedJob\"\n \
  \         outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: staffing-terminate-worker\n          description: \"Initiate a worker termination\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"workday-staffing.terminate-worker\"\n          with:\n            worker: \"tools.worker\"\n            terminationDate: \"tools.terminationDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: common-list-countries\n          description: \"List all countries\"\n          hints:\n            readOnly: true\n          call: \"workday-common.get-countries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: common-list-currencies\n          description: \"List all currencies\"\n          hints:\n            readOnly: true\n          call: \"workday-common.get-currencies\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/capabilities/workforce-management.yaml
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
