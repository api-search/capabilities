---
categories: []
consumed_apis: []
description: The Harvest API provides programmatic access to Greenhouse Recruiting data, including candidates, applications, jobs, departments, offices, and users. Authentication uses HTTP Basic Auth with an API token.
layout: capability
name: Greenhouse Harvest API
operations:
- description: List candidates
  method: GET
  name: get-candidates
  path: /candidates
- description: Create candidate
  method: POST
  name: post-candidates
  path: /candidates
- description: Retrieve candidate
  method: GET
  name: get-candidates-id
  path: /candidates/{id}
- description: Update candidate
  method: PATCH
  name: patch-candidates-id
  path: /candidates/{id}
- description: Delete candidate
  method: DELETE
  name: delete-candidates-id
  path: /candidates/{id}
- description: List applications
  method: GET
  name: get-applications
  path: /applications
- description: Retrieve application
  method: GET
  name: get-applications-id
  path: /applications/{id}
- description: Update application
  method: PATCH
  name: patch-applications-id
  path: /applications/{id}
- description: Advance application
  method: POST
  name: post-applications-id-advance
  path: /applications/{id}/advance
- description: Hire application
  method: POST
  name: post-applications-id-hire
  path: /applications/{id}/hire
- description: Reject application
  method: POST
  name: post-applications-id-reject
  path: /applications/{id}/reject
- description: List jobs
  method: GET
  name: get-jobs
  path: /jobs
- description: Retrieve job
  method: GET
  name: get-jobs-id
  path: /jobs/{id}
- description: Update job
  method: PATCH
  name: patch-jobs-id
  path: /jobs/{id}
- description: List departments
  method: GET
  name: get-departments
  path: /departments
- description: List offices
  method: GET
  name: get-offices
  path: /offices
- description: Retrieve office
  method: GET
  name: get-offices-id
  path: /offices/{id}
- description: List users
  method: GET
  name: get-users
  path: /users
- description: Retrieve user
  method: GET
  name: get-users-id
  path: /users/{id}
- description: Update user
  method: PATCH
  name: patch-users-id
  path: /users/{id}
personas: []
provider_name: Greenhouse
provider_slug: greenhouse
search_terms:
- delete candidates id
- list offices
- get jobs
- post applications id reject
- update job
- list candidates
- retrieve user
- ats
- create candidate
- delete candidate
- api
- update user
- get candidates id
- list departments
- get offices id
- get applications
- post applications id advance
- post candidates
- hr
- patch users id
- get applications id
- retrieve application
- advance application
- patch applications id
- list users
- update application
- recruiting
- patch jobs id
- patch candidates id
- reject application
- hire application
- update candidate
- get jobs id
- list jobs
- list applications
- retrieve job
- get users id
- get candidates
- jobs
- retrieve candidate
- candidates
- greenhouse
- get departments
- retrieve office
- get users
- get offices
- onboarding
- post applications id hire
slug: greenhouse-capability
source_filename: greenhouse-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Greenhouse Harvest API\n  description: The Harvest API provides programmatic access to Greenhouse Recruiting data, including candidates, applications,\n    jobs, departments, offices, and users. Authentication uses HTTP Basic Auth with an API token.\n  tags:\n  - Greenhouse\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: greenhouse\n    baseUri: https://harvest.greenhouse.io/v1\n    description: Greenhouse Harvest API HTTP API.\n    authentication:\n      type: basic\n      username: '{{GREENHOUSE_USERNAME}}'\n      password: '{{GREENHOUSE_PASSWORD}}'\n    resources:\n    - name: candidates\n      path: /candidates\n      operations:\n      - name: get-candidates\n        method: GET\n        description: List candidates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-candidates\n\
  \        method: POST\n        description: Create candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates-id\n      path: /candidates/{id}\n      operations:\n      - name: get-candidates-id\n        method: GET\n        description: Retrieve candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-candidates-id\n        method: PATCH\n        description: Update candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-candidates-id\n        method: DELETE\n        description: Delete candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      operations:\n\
  \      - name: get-applications\n        method: GET\n        description: List applications\n        inputParameters:\n        - name: job_id\n          in: query\n          type: integer\n        - name: status\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-id\n      path: /applications/{id}\n      operations:\n      - name: get-applications-id\n        method: GET\n        description: Retrieve application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-applications-id\n        method: PATCH\n        description: Update application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-id-advance\n      path: /applications/{id}/advance\n  \
  \    operations:\n      - name: post-applications-id-advance\n        method: POST\n        description: Advance application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-id-hire\n      path: /applications/{id}/hire\n      operations:\n      - name: post-applications-id-hire\n        method: POST\n        description: Hire application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-id-reject\n      path: /applications/{id}/reject\n      operations:\n      - name: post-applications-id-reject\n        method: POST\n        description: Reject application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      operations:\n      - name: get-jobs\n        method: GET\n\
  \        description: List jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-id\n      path: /jobs/{id}\n      operations:\n      - name: get-jobs-id\n        method: GET\n        description: Retrieve job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-jobs-id\n        method: PATCH\n        description: Update job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: departments\n      path: /departments\n      operations:\n      - name: get-departments\n        method: GET\n        description: List departments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offices\n      path: /offices\n      operations:\n   \
  \   - name: get-offices\n        method: GET\n        description: List offices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offices-id\n      path: /offices/{id}\n      operations:\n      - name: get-offices-id\n        method: GET\n        description: Retrieve office\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: get-users\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id\n      path: /users/{id}\n      operations:\n      - name: get-users-id\n        method: GET\n        description: Retrieve user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n      - name: patch-users-id\n        method: PATCH\n        description: Update user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: greenhouse-rest\n    description: REST adapter for Greenhouse Harvest API.\n    resources:\n    - path: /candidates\n      name: get-candidates\n      operations:\n      - method: GET\n        name: get-candidates\n        description: List candidates\n        call: greenhouse.get-candidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates\n      name: post-candidates\n      operations:\n      - method: POST\n        name: post-candidates\n        description: Create candidate\n        call: greenhouse.post-candidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/{id}\n      name:\
  \ get-candidates-id\n      operations:\n      - method: GET\n        name: get-candidates-id\n        description: Retrieve candidate\n        call: greenhouse.get-candidates-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/{id}\n      name: patch-candidates-id\n      operations:\n      - method: PATCH\n        name: patch-candidates-id\n        description: Update candidate\n        call: greenhouse.patch-candidates-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/{id}\n      name: delete-candidates-id\n      operations:\n      - method: DELETE\n        name: delete-candidates-id\n        description: Delete candidate\n        call: greenhouse.delete-candidates-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications\n      name: get-applications\n      operations:\n      - method: GET\n        name: get-applications\n        description:\
  \ List applications\n        call: greenhouse.get-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{id}\n      name: get-applications-id\n      operations:\n      - method: GET\n        name: get-applications-id\n        description: Retrieve application\n        call: greenhouse.get-applications-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{id}\n      name: patch-applications-id\n      operations:\n      - method: PATCH\n        name: patch-applications-id\n        description: Update application\n        call: greenhouse.patch-applications-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{id}/advance\n      name: post-applications-id-advance\n      operations:\n      - method: POST\n        name: post-applications-id-advance\n        description: Advance application\n        call: greenhouse.post-applications-id-advance\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{id}/hire\n      name: post-applications-id-hire\n      operations:\n      - method: POST\n        name: post-applications-id-hire\n        description: Hire application\n        call: greenhouse.post-applications-id-hire\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{id}/reject\n      name: post-applications-id-reject\n      operations:\n      - method: POST\n        name: post-applications-id-reject\n        description: Reject application\n        call: greenhouse.post-applications-id-reject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs\n      name: get-jobs\n      operations:\n      - method: GET\n        name: get-jobs\n        description: List jobs\n        call: greenhouse.get-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{id}\n\
  \      name: get-jobs-id\n      operations:\n      - method: GET\n        name: get-jobs-id\n        description: Retrieve job\n        call: greenhouse.get-jobs-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{id}\n      name: patch-jobs-id\n      operations:\n      - method: PATCH\n        name: patch-jobs-id\n        description: Update job\n        call: greenhouse.patch-jobs-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /departments\n      name: get-departments\n      operations:\n      - method: GET\n        name: get-departments\n        description: List departments\n        call: greenhouse.get-departments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /offices\n      name: get-offices\n      operations:\n      - method: GET\n        name: get-offices\n        description: List offices\n        call: greenhouse.get-offices\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /offices/{id}\n      name: get-offices-id\n      operations:\n      - method: GET\n        name: get-offices-id\n        description: Retrieve office\n        call: greenhouse.get-offices-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: get-users\n      operations:\n      - method: GET\n        name: get-users\n        description: List users\n        call: greenhouse.get-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: get-users-id\n      operations:\n      - method: GET\n        name: get-users-id\n        description: Retrieve user\n        call: greenhouse.get-users-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: patch-users-id\n      operations:\n      - method: PATCH\n        name: patch-users-id\n        description: Update user\n\
  \        call: greenhouse.patch-users-id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: greenhouse-mcp\n    transport: http\n    description: MCP adapter for Greenhouse Harvest API for AI agent use.\n    tools:\n    - name: get-candidates\n      description: List candidates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-candidates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-candidates\n      description: Create candidate\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: greenhouse.post-candidates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-candidates-id\n      description: Retrieve candidate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-candidates-id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-candidates-id\n      description: Update candidate\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: greenhouse.patch-candidates-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-candidates-id\n      description: Delete candidate\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: greenhouse.delete-candidates-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-applications\n      description: List applications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-applications\n      with:\n        job_id: tools.job_id\n        status: tools.status\n      inputParameters:\n      - name: job_id\n        type: integer\n        description: job_id\n      -\
  \ name: status\n        type: string\n        description: status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-applications-id\n      description: Retrieve application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-applications-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-applications-id\n      description: Update application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: greenhouse.patch-applications-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-applications-id-advance\n      description: Advance application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: greenhouse.post-applications-id-advance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ post-applications-id-hire\n      description: Hire application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: greenhouse.post-applications-id-hire\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-applications-id-reject\n      description: Reject application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: greenhouse.post-applications-id-reject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-jobs\n      description: List jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-jobs-id\n      description: Retrieve job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-jobs-id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-jobs-id\n      description: Update job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: greenhouse.patch-jobs-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-departments\n      description: List departments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-departments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-offices\n      description: List offices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-offices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-offices-id\n      description: Retrieve office\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: greenhouse.get-offices-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-users\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-users-id\n      description: Retrieve user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: greenhouse.get-users-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-users-id\n      description: Update user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: greenhouse.patch-users-id\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GREENHOUSE_USERNAME: GREENHOUSE_USERNAME\n    GREENHOUSE_PASSWORD: GREENHOUSE_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/greenhouse/refs/heads/main/capabilities/greenhouse-capability.yaml
tags:
- Greenhouse
- API
tools:
- description: List candidates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-candidates
- description: Create candidate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-candidates
- description: Retrieve candidate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-candidates-id
- description: Update candidate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-candidates-id
- description: Delete candidate
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-candidates-id
- description: List applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-applications
- description: Retrieve application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-applications-id
- description: Update application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-applications-id
- description: Advance application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-applications-id-advance
- description: Hire application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-applications-id-hire
- description: Reject application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-applications-id-reject
- description: List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-jobs
- description: Retrieve job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-jobs-id
- description: Update job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-jobs-id
- description: List departments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-departments
- description: List offices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-offices
- description: Retrieve office
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-offices-id
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users
- description: Retrieve user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users-id
- description: Update user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-users-id
---
