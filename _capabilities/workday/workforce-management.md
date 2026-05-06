---
categories:
- payroll-hr
consumed_apis: []
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
- list all workers with optional search and pagination
- person get person
- initiate a worker termination
- staffing list positions
- create a job change request
- staffing create job change
- hcm get worker inbox tasks
- list organizations
- get a person by id
- hcm list workers
- hcm get worker history
- person get home contact
- hcm get worker
- country reference data
- list countries
- get inbox tasks for a worker
- hcm list organizations
- person get work contact
- list supervisory organizations
- list all job profiles
- list people
- list workers
- staffing terminate worker
- list all workers
- get a specific worker by id
- get home contact information
- common list currencies
- cloud computing
- get change history for a worker
- workday
- person list people
- common list countries
- person data
- financial management
- saas
- list all locations
- hcm
- list positions
- list all countries
- get worker
- staffing list job profiles
- worker detail
- get work contact information
- supervisory organizations
- human resources
- workforce management
- hcm list locations
- list all people
- list all positions
- enterprise software
- worker management
- get a worker by id
- position management
- list all currencies
slug: workforce-management
source_filename: workforce-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Workforce Management\n  description: Unified workforce management combining HCM, Person, Staffing, and Common APIs for HR administrators to manage\n    workers, organizations, positions, and reference data.\n  tags:\n  - Workday\n  - Workforce Management\n  - Human Resources\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-hcm\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}\n    description: Workday HCM REST API for core HR operations.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: workers\n      path: /workers\n      description: Worker data management\n      operations:\n      - name: get-workers\n        method: GET\n        description: Returns a collection of workers with filtering and pagination.\n\
  \        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of results to skip.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term for filtering workers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-worker-by-id\n        method: GET\n        description: Returns a single worker by their unique identifier.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the worker.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: get-worker-history\n        method: GET\n        description: Returns the history of changes for a specific worker.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the worker.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-worker-photo\n        method: GET\n        description: Returns the photo for a specific worker.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the worker.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-worker-business-title-changes\n        method: GET\n        description: Returns\
  \ business title changes for a specific worker.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the worker.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-worker-inbox-tasks\n        method: GET\n        description: Returns inbox tasks for a specific worker.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the worker.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /supervisoryOrganizations\n      description: Supervisory organization management\n      operations:\n      - name: get-supervisory-organizations\n        method: GET\n        description:\
  \ Returns a collection of supervisory organizations.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of results to skip.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-supervisory-organization-by-id\n        method: GET\n        description: Returns a single supervisory organization by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /locations\n\
  \      description: Location management\n      operations:\n      - name: get-locations\n        method: GET\n        description: Returns a collection of locations.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-location-by-id\n        method: GET\n        description: Returns a single location by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the location.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workday-person\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/person\n\
  \    description: Workday Person REST API for personal data management.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: people\n      path: /\n      description: Person data management\n      operations:\n      - name: get-people\n        method: GET\n        description: Returns a collection of people.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-person-by-id\n        method: GET\n        description: Returns a single person by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Person identifier.\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: get-home-contact-information\n        method: GET\n        description: Returns home contact information for a person.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Person identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-work-contact-information\n        method: GET\n        description: Returns work contact information for a person.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Person identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-personal-information\n        method: GET\n        description: Returns personal\
  \ information for a person.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Person identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workday-staffing\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/staffing\n    description: Workday Staffing REST API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: staffing\n      path: /\n      description: Staffing operations\n      operations:\n      - name: get-organization-assignments\n        method: GET\n        description: Returns organization assignments for workers.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job-change\n        method: POST\n        description: Creates a job change request for a worker.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            proposedJob: '{{tools.proposedJob}}'\n      - name: get-job-profiles\n        method: GET\n        description: Returns a collection of job profiles.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job-profile-by-id\n        method: GET\n        description: Returns a job profile by\
  \ ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Job profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-positions\n        method: GET\n        description: Returns a collection of positions.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-position-by-id\n        method: GET\n        description: Returns a position by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Position ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: request-one-time-payment\n        method: POST\n        description: Request a one-time payment for a worker.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            amount: '{{tools.amount}}'\n      - name: terminate-worker\n        method: POST\n        description: Initiate a worker termination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            terminationDate: '{{tools.terminationDate}}'\n  - type: http\n    namespace: workday-common\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/common\n    description: Workday Common\
  \ REST API for reference data.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: reference-data\n      path: /\n      description: Common reference data\n      operations:\n      - name: get-countries\n        method: GET\n        description: Returns a collection of countries.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-country-by-id\n        method: GET\n        description: Returns a country by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Country ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-currencies\n        method: GET\n        description: Returns a collection of currencies.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-currency-by-id\n        method: GET\n        description: Returns a currency by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Currency ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-languages\n        method: GET\n        description: Returns a collection of languages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-genders\n        method: GET\n        description: Returns gender reference values.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-marital-statuses\n        method: GET\n        description: Returns\
  \ marital status reference values.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workforce-management-api\n    description: Unified REST API for workforce management operations.\n    resources:\n    - path: /v1/workers\n      name: workers\n      description: Worker management\n      operations:\n      - method: GET\n        name: list-workers\n        description: List all workers\n        call: workday-hcm.get-workers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workers/{id}\n      name: worker-detail\n      description: Worker detail\n      operations:\n      - method: GET\n        name: get-worker\n        description: Get a worker by ID\n        call: workday-hcm.get-worker-by-id\n        with:\n          ID: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/people\n      name: people\n      description: Person data\n      operations:\n      - method: GET\n        name: list-people\n        description: List all people\n        call: workday-person.get-people\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/positions\n      name: positions\n      description: Position management\n      operations:\n      - method: GET\n        name: list-positions\n        description: List all positions\n        call: workday-staffing.get-positions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations\n      name: organizations\n      description: Supervisory organizations\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List supervisory organizations\n        call: workday-hcm.get-supervisory-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/countries\n\
  \      name: countries\n      description: Country reference data\n      operations:\n      - method: GET\n        name: list-countries\n        description: List all countries\n        call: workday-common.get-countries\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: workforce-management-mcp\n    transport: http\n    description: MCP server for AI-assisted workforce management.\n    tools:\n    - name: hcm-list-workers\n      description: List all workers with optional search and pagination\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-hcm.get-workers\n      with:\n        limit: tools.limit\n        offset: tools.offset\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hcm-get-worker\n      description: Get a specific worker by ID\n      hints:\n        readOnly: true\n      call: workday-hcm.get-worker-by-id\n   \
  \   with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hcm-get-worker-history\n      description: Get change history for a worker\n      hints:\n        readOnly: true\n      call: workday-hcm.get-worker-history\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hcm-get-worker-inbox-tasks\n      description: Get inbox tasks for a worker\n      hints:\n        readOnly: true\n      call: workday-hcm.get-worker-inbox-tasks\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hcm-list-organizations\n      description: List supervisory organizations\n      hints:\n        readOnly: true\n      call: workday-hcm.get-supervisory-organizations\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hcm-list-locations\n      description: List all\
  \ locations\n      hints:\n        readOnly: true\n      call: workday-hcm.get-locations\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: person-list-people\n      description: List all people\n      hints:\n        readOnly: true\n      call: workday-person.get-people\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: person-get-person\n      description: Get a person by ID\n      hints:\n        readOnly: true\n      call: workday-person.get-person-by-id\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: person-get-home-contact\n      description: Get home contact information\n      hints:\n        readOnly: true\n      call: workday-person.get-home-contact-information\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ person-get-work-contact\n      description: Get work contact information\n      hints:\n        readOnly: true\n      call: workday-person.get-work-contact-information\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: staffing-list-positions\n      description: List all positions\n      hints:\n        readOnly: true\n      call: workday-staffing.get-positions\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: staffing-list-job-profiles\n      description: List all job profiles\n      hints:\n        readOnly: true\n      call: workday-staffing.get-job-profiles\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: staffing-create-job-change\n      description: Create a job change request\n      hints:\n        readOnly: false\n      call: workday-staffing.create-job-change\n      with:\n\
  \        worker: tools.worker\n        proposedJob: tools.proposedJob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: staffing-terminate-worker\n      description: Initiate a worker termination\n      hints:\n        readOnly: false\n        destructive: true\n      call: workday-staffing.terminate-worker\n      with:\n        worker: tools.worker\n        terminationDate: tools.terminationDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: common-list-countries\n      description: List all countries\n      hints:\n        readOnly: true\n      call: workday-common.get-countries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: common-list-currencies\n      description: List all currencies\n      hints:\n        readOnly: true\n      call: workday-common.get-currencies\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
