---
api_specs:
- filename: campus-solutions.yml
  format: yaml
  label: campus-solutions
  slug: campus-solutions
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/campus-solutions.yml
- filename: approval-workflow-engine.yml
  format: yaml
  label: approval-workflow
  slug: approval-workflow
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/approval-workflow-engine.yml
categories: []
consumed_apis:
- campus-solutions
- approval-workflow
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
- retrieve class schedule and enrollment data.
- crm
- retrieve student records.
- hcm
- erp
- peoplesoft
- financial aid awards
- campus approval requests
- retrieve pending campus approval requests.
- financial aid
- get student
- enterprise software
- list financial aid awards
- list students
- list admission applications
- student records
- individual student details
- list classes
- retrieve financial aid award data.
- financial and supply chain management.
- campus solutions.
- admissions
- higher education
- campus solutions
- individual approval operations
- list pending approvals
- class schedule and enrollment data
- admission applications
- retrieve details for a specific student.
- process approval
- supply chain management
- approve, deny, or push back a campus approval request.
- peopletools platform services.
- retrieve admission applications.
- human capital management.
- financial management
slug: campus-administration
source_filename: campus-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"PeopleSoft Campus Administration\"\n  description: \"Unified workflow for campus administrators combining student records, admissions, enrollment, financial aid, and approval workflows across PeopleSoft Campus Solutions and Approval Workflow Engine APIs.\"\n  tags:\n    - PeopleSoft\n    - Campus Solutions\n    - Higher Education\n    - Student Records\n    - Admissions\n    - Financial Aid\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n      PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\n\ncapability:\n  consumes:\n    - import: campus-solutions\n      location: ./shared/campus-solutions.yaml\n    - import: approval-workflow\n      location: ./shared/approval-workflow-engine.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: campus-api\n      description: \"Unified REST API for PeopleSoft campus administration workflows.\"\
  \n      resources:\n        - path: /v1/students\n          name: students\n          description: \"Student records\"\n          operations:\n            - method: GET\n              name: list-students\n              description: \"Retrieve student records.\"\n              call: \"campus-solutions.list-students\"\n              with:\n                term: \"rest.term\"\n                program: \"rest.program\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/students/{studentId}\n          name: student-detail\n          description: \"Individual student details\"\n          operations:\n            - method: GET\n              name: get-student\n              description: \"Retrieve details for a specific student.\"\n              call: \"campus-solutions.get-student\"\n              with:\n                studentId: \"rest.studentId\"\n              outputParameters:\n                - type: object\n       \
  \           mapping: \"$.\"\n        - path: /v1/admission-applications\n          name: admissions\n          description: \"Admission applications\"\n          operations:\n            - method: GET\n              name: list-admission-applications\n              description: \"Retrieve admission applications.\"\n              call: \"campus-solutions.list-admission-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/classes\n          name: classes\n          description: \"Class schedule and enrollment data\"\n          operations:\n            - method: GET\n              name: list-classes\n              description: \"Retrieve class schedule and enrollment data.\"\n              call: \"campus-solutions.list-classes\"\n              with:\n                term: \"rest.term\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/financial-aid-awards\n\
  \          name: financial-aid\n          description: \"Financial aid awards\"\n          operations:\n            - method: GET\n              name: list-financial-aid-awards\n              description: \"Retrieve financial aid award data.\"\n              call: \"campus-solutions.list-financial-aid-awards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/approvals\n          name: approvals\n          description: \"Campus approval requests\"\n          operations:\n            - method: GET\n              name: list-pending-approvals\n              description: \"Retrieve pending campus approval requests.\"\n              call: \"approval-workflow.list-pending-approvals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/approvals/{approvalId}\n          name: approval-detail\n          description: \"Individual approval operations\"\n    \
  \      operations:\n            - method: PUT\n              name: process-approval\n              description: \"Approve, deny, or push back a campus approval request.\"\n              call: \"approval-workflow.process-approval\"\n              with:\n                approvalId: \"rest.approvalId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: campus-mcp\n      transport: http\n      description: \"MCP server for AI-assisted PeopleSoft campus administration workflows.\"\n      tools:\n        - name: list-students\n          description: \"Retrieve student records.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campus-solutions.list-students\"\n          with:\n            term: \"tools.term\"\n            program: \"tools.program\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: get-student\n          description: \"Retrieve details for a specific student.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campus-solutions.get-student\"\n          with:\n            studentId: \"tools.studentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-admission-applications\n          description: \"Retrieve admission applications.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campus-solutions.list-admission-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-classes\n          description: \"Retrieve class schedule and enrollment data.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campus-solutions.list-classes\"\n          with:\n            term: \"tools.term\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-financial-aid-awards\n          description: \"Retrieve financial aid award data.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campus-solutions.list-financial-aid-awards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pending-approvals\n          description: \"Retrieve pending campus approval requests.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"approval-workflow.list-pending-approvals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-approval\n          description: \"Approve, deny, or push back a campus approval request.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"approval-workflow.process-approval\"\
  \n          with:\n            approvalId: \"tools.approvalId\"\n            action: \"tools.action\"\n            comments: \"tools.comments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
