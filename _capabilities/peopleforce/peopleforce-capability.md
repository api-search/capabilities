---
categories: []
consumed_apis: []
description: PeopleForce is an HR platform offering a REST API for managing employees, candidates, leave requests, departments, divisions, positions, and other HR-related entities.
layout: capability
name: PeopleForce API
operations:
- description: List employees
  method: GET
  name: get-employees
  path: /employees
- description: Create an employee
  method: POST
  name: post-employees
  path: /employees
- description: Get an employee
  method: GET
  name: get-employees-id
  path: /employees/{id}
- description: Update an employee
  method: PATCH
  name: patch-employees-id
  path: /employees/{id}
- description: List candidates
  method: GET
  name: get-candidates
  path: /candidates
- description: Create a candidate
  method: POST
  name: post-candidates
  path: /candidates
- description: Get a candidate
  method: GET
  name: get-candidates-id
  path: /candidates/{id}
- description: List vacancies
  method: GET
  name: get-vacancies
  path: /vacancies
- description: Get a vacancy
  method: GET
  name: get-vacancies-id
  path: /vacancies/{id}
- description: List leave requests
  method: GET
  name: get-leave-requests
  path: /leave_requests
- description: Create a leave request
  method: POST
  name: post-leave-requests
  path: /leave_requests
- description: Get a leave request
  method: GET
  name: get-leave-requests-id
  path: /leave_requests/{id}
- description: List departments
  method: GET
  name: get-departments
  path: /departments
- description: List divisions
  method: GET
  name: get-divisions
  path: /divisions
- description: List positions
  method: GET
  name: get-positions
  path: /positions
personas: []
provider_name: PeopleForce
provider_slug: peopleforce
search_terms:
- get divisions
- employees
- get employees id
- get leave requests
- get employees
- update an employee
- get departments
- create an employee
- get candidates id
- patch employees id
- list candidates
- api
- post candidates
- get a leave request
- list positions
- get leave requests id
- list employees
- create a candidate
- peopleforce
- human resources
- list vacancies
- get candidates
- recruitment
- get positions
- get an employee
- get vacancies id
- list divisions
- post employees
- list departments
- hr
- get a candidate
- get a vacancy
- list leave requests
- create a leave request
- get vacancies
- post leave requests
slug: peopleforce-capability
source_filename: peopleforce-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PeopleForce API\n  description: PeopleForce is an HR platform offering a REST API for managing employees, candidates, leave requests, departments,\n    divisions, positions, and other HR-related entities.\n  tags:\n  - Peopleforce\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: peopleforce\n    baseUri: https://app.peopleforce.io/api/public/v2\n    description: PeopleForce API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PEOPLEFORCE_TOKEN}}'\n    resources:\n    - name: employees\n      path: /employees\n      operations:\n      - name: get-employees\n        method: GET\n        description: List employees\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: post-employees\n        method: POST\n        description: Create an employee\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employees-id\n      path: /employees/{id}\n      operations:\n      - name: get-employees-id\n        method: GET\n        description: Get an employee\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-employees-id\n        method: PATCH\n        description: Update an employee\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: candidates\n      path: /candidates\n      operations:\n      - name: get-candidates\n        method: GET\n        description: List candidates\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-candidates\n        method: POST\n        description: Create a candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates-id\n      path: /candidates/{id}\n      operations:\n      - name: get-candidates-id\n        method: GET\n        description: Get a candidate\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vacancies\n      path: /vacancies\n      operations:\n      - name: get-vacancies\n        method: GET\n        description: List vacancies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vacancies-id\n      path: /vacancies/{id}\n      operations:\n      - name: get-vacancies-id\n        method: GET\n        description: Get a vacancy\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leave-requests\n      path: /leave_requests\n      operations:\n      - name: get-leave-requests\n        method: GET\n        description: List leave requests\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-leave-requests\n        method: POST\n        description: Create a leave request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leave-requests-id\n      path: /leave_requests/{id}\n      operations:\n      - name: get-leave-requests-id\n        method: GET\n        description: Get a leave request\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: departments\n      path: /departments\n      operations:\n      - name: get-departments\n        method: GET\n        description: List departments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: divisions\n      path: /divisions\n      operations:\n      - name: get-divisions\n        method: GET\n        description: List divisions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: positions\n      path: /positions\n      operations:\n      - name: get-positions\n        method: GET\n        description: List positions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: peopleforce-rest\n    description: REST adapter for PeopleForce API.\n    resources:\n    - path: /employees\n      name: get-employees\n      operations:\n      - method: GET\n        name: get-employees\n        description: List employees\n        call: peopleforce.get-employees\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /employees\n      name: post-employees\n      operations:\n      - method: POST\n        name: post-employees\n        description: Create an employee\n        call: peopleforce.post-employees\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /employees/{id}\n      name: get-employees-id\n      operations:\n      - method: GET\n        name: get-employees-id\n        description: Get an employee\n        call: peopleforce.get-employees-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /employees/{id}\n      name: patch-employees-id\n      operations:\n      - method: PATCH\n        name: patch-employees-id\n        description: Update an employee\n        call: peopleforce.patch-employees-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates\n      name: get-candidates\n\
  \      operations:\n      - method: GET\n        name: get-candidates\n        description: List candidates\n        call: peopleforce.get-candidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates\n      name: post-candidates\n      operations:\n      - method: POST\n        name: post-candidates\n        description: Create a candidate\n        call: peopleforce.post-candidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/{id}\n      name: get-candidates-id\n      operations:\n      - method: GET\n        name: get-candidates-id\n        description: Get a candidate\n        call: peopleforce.get-candidates-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vacancies\n      name: get-vacancies\n      operations:\n      - method: GET\n        name: get-vacancies\n        description: List vacancies\n    \
  \    call: peopleforce.get-vacancies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vacancies/{id}\n      name: get-vacancies-id\n      operations:\n      - method: GET\n        name: get-vacancies-id\n        description: Get a vacancy\n        call: peopleforce.get-vacancies-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /leave_requests\n      name: get-leave-requests\n      operations:\n      - method: GET\n        name: get-leave-requests\n        description: List leave requests\n        call: peopleforce.get-leave-requests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /leave_requests\n      name: post-leave-requests\n      operations:\n      - method: POST\n        name: post-leave-requests\n        description: Create a leave request\n        call: peopleforce.post-leave-requests\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /leave_requests/{id}\n      name: get-leave-requests-id\n      operations:\n      - method: GET\n        name: get-leave-requests-id\n        description: Get a leave request\n        call: peopleforce.get-leave-requests-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /departments\n      name: get-departments\n      operations:\n      - method: GET\n        name: get-departments\n        description: List departments\n        call: peopleforce.get-departments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /divisions\n      name: get-divisions\n      operations:\n      - method: GET\n        name: get-divisions\n        description: List divisions\n        call: peopleforce.get-divisions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /positions\n      name: get-positions\n      operations:\n\
  \      - method: GET\n        name: get-positions\n        description: List positions\n        call: peopleforce.get-positions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: peopleforce-mcp\n    transport: http\n    description: MCP adapter for PeopleForce API for AI agent use.\n    tools:\n    - name: get-employees\n      description: List employees\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-employees\n      with:\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-employees\n      description: Create an employee\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: peopleforce.post-employees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employees-id\n      description: Get an employee\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-employees-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-employees-id\n      description: Update an employee\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: peopleforce.patch-employees-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-candidates\n\
  \      description: List candidates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-candidates\n      with:\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-candidates\n      description: Create a candidate\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: peopleforce.post-candidates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-candidates-id\n      description: Get a candidate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-candidates-id\n      with:\n        id: tools.id\n      inputParameters:\n\
  \      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vacancies\n      description: List vacancies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-vacancies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vacancies-id\n      description: Get a vacancy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-vacancies-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-leave-requests\n      description: List leave requests\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n  \
  \    call: peopleforce.get-leave-requests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-leave-requests\n      description: Create a leave request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: peopleforce.post-leave-requests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-leave-requests-id\n      description: Get a leave request\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-leave-requests-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-departments\n      description: List departments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-departments\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-divisions\n      description: List divisions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-divisions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-positions\n      description: List positions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: peopleforce.get-positions\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PEOPLEFORCE_TOKEN: PEOPLEFORCE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/peopleforce/refs/heads/main/capabilities/peopleforce-capability.yaml
tags:
- Peopleforce
- API
tools:
- description: List employees
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-employees
- description: Create an employee
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-employees
- description: Get an employee
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-employees-id
- description: Update an employee
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-employees-id
- description: List candidates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-candidates
- description: Create a candidate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-candidates
- description: Get a candidate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-candidates-id
- description: List vacancies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-vacancies
- description: Get a vacancy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-vacancies-id
- description: List leave requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-leave-requests
- description: Create a leave request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-leave-requests
- description: Get a leave request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-leave-requests-id
- description: List departments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-departments
- description: List divisions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-divisions
- description: List positions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-positions
---
