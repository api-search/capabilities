---
categories: []
consumed_apis: []
description: Unified workflow for campus administrators combining student records, admissions, enrollment, financial aid, and approval workflows across PeopleSoft Campus Solutions and Approval Workflow Engine APIs.
layout: capability
name: PeopleSoft Campus Administration
operations:
- description: Retrieve student records.
  method: GET
  name: list-students
  path: /v1/students
- description: Retrieve details for a specific student.
  method: GET
  name: get-student
  path: /v1/students/{studentId}
- description: Retrieve admission applications.
  method: GET
  name: list-admission-applications
  path: /v1/admission-applications
- description: Retrieve class schedule and enrollment data.
  method: GET
  name: list-classes
  path: /v1/classes
- description: Retrieve financial aid award data.
  method: GET
  name: list-financial-aid-awards
  path: /v1/financial-aid-awards
- description: Retrieve pending campus approval requests.
  method: GET
  name: list-pending-approvals
  path: /v1/approvals
- description: Approve, deny, or push back a campus approval request.
  method: PUT
  name: process-approval
  path: /v1/approvals/{approvalId}
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- approve, deny, or push back a campus approval request.
- list financial aid awards
- supply chain management
- individual student details
- list pending approvals
- peopletools platform services.
- peoplesoft
- process approval
- admission applications
- retrieve class schedule and enrollment data.
- financial aid awards
- retrieve details for a specific student.
- campus solutions.
- list students
- financial and supply chain management.
- individual approval operations
- human capital management.
- erp
- financial management
- campus approval requests
- higher education
- get student
- crm
- admissions
- retrieve student records.
- class schedule and enrollment data
- retrieve financial aid award data.
- retrieve pending campus approval requests.
- list admission applications
- hcm
- retrieve admission applications.
- financial aid
- campus solutions
- enterprise software
- student records
- list classes
slug: campus-administration
source_filename: campus-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PeopleSoft Campus Administration\n  description: Unified workflow for campus administrators combining student records, admissions, enrollment, financial aid,\n    and approval workflows across PeopleSoft Campus Solutions and Approval Workflow Engine APIs.\n  tags:\n  - PeopleSoft\n  - Campus Solutions\n  - Higher Education\n  - Student Records\n  - Admissions\n  - Financial Aid\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n    PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: campus-solutions\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/campus/v1\n    description: PeopleSoft Campus Solutions API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: students\n      path: /students\n\
  \      description: Student record operations\n      operations:\n      - name: list-students\n        method: GET\n        description: Retrieve student records.\n        inputParameters:\n        - name: term\n          in: query\n          type: string\n          required: false\n          description: Academic term filter\n        - name: program\n          in: query\n          type: string\n          required: false\n          description: Academic program filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-student\n        method: GET\n        description: Retrieve details for a specific student.\n        inputParameters:\n        - name: studentId\n          in: path\n          type: string\n          required: true\n          description: The student identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: admissions\n      path: /admissions\n      description: Admissions operations\n      operations:\n      - name: list-admission-applications\n        method: GET\n        description: Retrieve admission applications.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enrollment\n      path: /enrollment\n      description: Enrollment operations\n      operations:\n      - name: list-classes\n        method: GET\n        description: Retrieve class schedule and enrollment data.\n        inputParameters:\n        - name: term\n          in: query\n          type: string\n          required: false\n          description: Academic term\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: financial-aid\n      path: /financial-aid\n      description: Financial aid operations\n      operations:\n      -\
  \ name: list-financial-aid-awards\n        method: GET\n        description: Retrieve financial aid award data.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: approval-workflow\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/approvals/v1\n    description: PeopleSoft Approval Workflow Engine API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: approvals\n      path: /approvals\n      description: Approval workflow operations\n      operations:\n      - name: list-pending-approvals\n        method: GET\n        description: Retrieve a list of pending approval requests for the current user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: process-approval\n     \
  \   method: PUT\n        description: Approve, deny, or push back an approval request.\n        inputParameters:\n        - name: approvalId\n          in: path\n          type: string\n          required: true\n          description: The approval request identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n            comments: '{{tools.comments}}'\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: campus-api\n    description: Unified REST API for PeopleSoft campus administration workflows.\n    resources:\n    - path: /v1/students\n      name: students\n      description: Student records\n      operations:\n      - method: GET\n        name: list-students\n        description: Retrieve student records.\n        call: campus-solutions.list-students\n        with:\n          term: rest.term\n       \
  \   program: rest.program\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/students/{studentId}\n      name: student-detail\n      description: Individual student details\n      operations:\n      - method: GET\n        name: get-student\n        description: Retrieve details for a specific student.\n        call: campus-solutions.get-student\n        with:\n          studentId: rest.studentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/admission-applications\n      name: admissions\n      description: Admission applications\n      operations:\n      - method: GET\n        name: list-admission-applications\n        description: Retrieve admission applications.\n        call: campus-solutions.list-admission-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/classes\n      name: classes\n      description: Class schedule and enrollment data\n     \
  \ operations:\n      - method: GET\n        name: list-classes\n        description: Retrieve class schedule and enrollment data.\n        call: campus-solutions.list-classes\n        with:\n          term: rest.term\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/financial-aid-awards\n      name: financial-aid\n      description: Financial aid awards\n      operations:\n      - method: GET\n        name: list-financial-aid-awards\n        description: Retrieve financial aid award data.\n        call: campus-solutions.list-financial-aid-awards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/approvals\n      name: approvals\n      description: Campus approval requests\n      operations:\n      - method: GET\n        name: list-pending-approvals\n        description: Retrieve pending campus approval requests.\n        call: approval-workflow.list-pending-approvals\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/approvals/{approvalId}\n      name: approval-detail\n      description: Individual approval operations\n      operations:\n      - method: PUT\n        name: process-approval\n        description: Approve, deny, or push back a campus approval request.\n        call: approval-workflow.process-approval\n        with:\n          approvalId: rest.approvalId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: campus-mcp\n    transport: http\n    description: MCP server for AI-assisted PeopleSoft campus administration workflows.\n    tools:\n    - name: list-students\n      description: Retrieve student records.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campus-solutions.list-students\n      with:\n        term: tools.term\n        program: tools.program\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-student\n\
  \      description: Retrieve details for a specific student.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campus-solutions.get-student\n      with:\n        studentId: tools.studentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-admission-applications\n      description: Retrieve admission applications.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campus-solutions.list-admission-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-classes\n      description: Retrieve class schedule and enrollment data.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campus-solutions.list-classes\n      with:\n        term: tools.term\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-financial-aid-awards\n      description: Retrieve financial aid award data.\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: campus-solutions.list-financial-aid-awards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pending-approvals\n      description: Retrieve pending campus approval requests.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: approval-workflow.list-pending-approvals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-approval\n      description: Approve, deny, or push back a campus approval request.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: approval-workflow.process-approval\n      with:\n        approvalId: tools.approvalId\n        action: tools.action\n        comments: tools.comments\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/capabilities/campus-administration.yaml
tags:
- PeopleSoft
- Campus Solutions
- Higher Education
- Student Records
- Admissions
- Financial Aid
tools:
- description: Retrieve student records.
  hints:
    openWorld: true
    readOnly: true
  name: list-students
- description: Retrieve details for a specific student.
  hints:
    openWorld: true
    readOnly: true
  name: get-student
- description: Retrieve admission applications.
  hints:
    openWorld: true
    readOnly: true
  name: list-admission-applications
- description: Retrieve class schedule and enrollment data.
  hints:
    openWorld: true
    readOnly: true
  name: list-classes
- description: Retrieve financial aid award data.
  hints:
    openWorld: true
    readOnly: true
  name: list-financial-aid-awards
- description: Retrieve pending campus approval requests.
  hints:
    openWorld: true
    readOnly: true
  name: list-pending-approvals
- description: Approve, deny, or push back a campus approval request.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: process-approval
---
