---
api_specs:
- filename: abacus-api-openapi.yaml
  format: yaml
  label: abacus-api
  slug: abacus-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/abacus/refs/heads/main/openapi/abacus-api-openapi.yaml
categories: []
consumed_apis:
- abacus-api
description: Unified workflow for managing employee expenses, reimbursements, and member provisioning. Enables finance teams and administrators to automate expense reporting, track spending by member or category, and manage organizational membership.
layout: capability
name: Abacus Expense Management
operations:
- description: List all organization members
  method: GET
  name: list-members
  path: /v1/members
- description: Invite a new member to the organization
  method: POST
  name: invite-member
  path: /v1/members
- description: Get member details
  method: GET
  name: get-member
  path: /v1/members/{member_id}
- description: Update member role or department
  method: PUT
  name: update-member
  path: /v1/members/{member_id}
- description: Suspend a member
  method: POST
  name: suspend-member
  path: /v1/members/{member_id}/suspend
- description: List expense reports with filters
  method: GET
  name: list-expenses
  path: /v1/expenses
- description: Get expense report details
  method: GET
  name: get-expense
  path: /v1/expenses/{expense_id}
personas: []
provider_name: Abacus
provider_slug: abacus
search_terms:
- get expense report details
- get expense
- invite member
- organization employee submitting expense reports for reimbursement
- invite a new member to the organization with email and role assignment
- finance team member responsible for expense approvals and reimbursements
- update member
- abacus
- individual expense report
- suspend member
- update a member's role, department, or status within the organization
- list expenses
- update member role or department
- suspend an organization member to prevent expense submissions
- finance
- expense report submission, approval, and reimbursement workflows
- list expense reports with filtering by status, member, or date range
- HR Manager
- list expense reports with filters
- list all members in the organization with pagination support
- individual member operations
- Finance Administrator
- get member
- organization member provisioning, role management, and access control
- expense management
- get member details
- accounting
- list members
- organization member management
- unified workflow for member management and expense tracking
- get detailed information for a specific expense report including receipt url
- get detailed information for a specific organization member
- list all organization members
- suspend a member
- reimbursement
- member suspension
- expense report management
- invite a new member to the organization
- hr manager responsible for member provisioning and access management
- members
slug: expense-management
source_filename: expense-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Abacus Expense Management\"\n  description: \"Unified workflow for managing employee expenses, reimbursements, and member provisioning. Enables finance teams and administrators to automate expense reporting, track spending by member or category, and manage organizational membership.\"\n  tags:\n    - Abacus\n    - Expense Management\n    - Finance\n    - Reimbursement\n    - Members\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ABACUS_CLIENT_ID: ABACUS_CLIENT_ID\n      ABACUS_CLIENT_SECRET: ABACUS_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: abacus-api\n      location: ./shared/abacus-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: expense-management-api\n      description: \"Unified REST API for Abacus expense management and member administration.\"\n      resources:\n        - path: /v1/members\n          name: members\n        \
  \  description: \"Organization member management\"\n          operations:\n            - method: GET\n              name: list-members\n              description: \"List all organization members\"\n              call: \"abacus-api.list-members\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: invite-member\n              description: \"Invite a new member to the organization\"\n              call: \"abacus-api.invite-member\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/members/{member_id}\n          name: member\n          description: \"Individual member operations\"\n          operations:\n            - method: GET\n              name: get-member\n              description: \"Get member details\"\n       \
  \       call: \"abacus-api.get-member\"\n              with:\n                member_id: \"rest.member_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-member\n              description: \"Update member role or department\"\n              call: \"abacus-api.update-member\"\n              with:\n                member_id: \"rest.member_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/members/{member_id}/suspend\n          name: suspend-member\n          description: \"Member suspension\"\n          operations:\n            - method: POST\n              name: suspend-member\n              description: \"Suspend a member\"\n              call: \"abacus-api.suspend-member\"\n              with:\n                member_id: \"rest.member_id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/expenses\n          name: expenses\n          description: \"Expense report management\"\n          operations:\n            - method: GET\n              name: list-expenses\n              description: \"List expense reports with filters\"\n              call: \"abacus-api.list-expenses\"\n              with:\n                status: \"rest.status\"\n                member_id: \"rest.member_id\"\n                from_date: \"rest.from_date\"\n                to_date: \"rest.to_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/expenses/{expense_id}\n          name: expense\n          description: \"Individual expense report\"\n          operations:\n            - method: GET\n              name: get-expense\n              description: \"Get expense report details\"\n              call: \"abacus-api.get-expense\"\n              with:\n                expense_id:\
  \ \"rest.expense_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: expense-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted expense management and member administration.\"\n      tools:\n        - name: list-members\n          description: \"List all members in the organization with pagination support\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abacus-api.list-members\"\n          with:\n            page: \"tools.page\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: invite-member\n          description: \"Invite a new member to the organization with email and role assignment\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n \
  \         call: \"abacus-api.invite-member\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-member\n          description: \"Get detailed information for a specific organization member\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abacus-api.get-member\"\n          with:\n            member_id: \"tools.member_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-member\n          description: \"Update a member's role, department, or status within the organization\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"abacus-api.update-member\"\n          with:\n            member_id: \"tools.member_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: suspend-member\n          description:\
  \ \"Suspend an organization member to prevent expense submissions\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"abacus-api.suspend-member\"\n          with:\n            member_id: \"tools.member_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-expenses\n          description: \"List expense reports with filtering by status, member, or date range\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abacus-api.list-expenses\"\n          with:\n            status: \"tools.status\"\n            member_id: \"tools.member_id\"\n            from_date: \"tools.from_date\"\n            to_date: \"tools.to_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-expense\n          description: \"Get detailed information for a specific expense\
  \ report including receipt URL\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abacus-api.get-expense\"\n          with:\n            expense_id: \"tools.expense_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/abacus/refs/heads/main/capabilities/expense-management.yaml
tags:
- Abacus
- Expense Management
- Finance
- Reimbursement
- Members
tools:
- description: List all members in the organization with pagination support
  hints:
    openWorld: false
    readOnly: true
  name: list-members
- description: Invite a new member to the organization with email and role assignment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invite-member
- description: Get detailed information for a specific organization member
  hints:
    openWorld: false
    readOnly: true
  name: get-member
- description: Update a member's role, department, or status within the organization
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-member
- description: Suspend an organization member to prevent expense submissions
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: suspend-member
- description: List expense reports with filtering by status, member, or date range
  hints:
    openWorld: false
    readOnly: true
  name: list-expenses
- description: Get detailed information for a specific expense report including receipt URL
  hints:
    openWorld: false
    readOnly: true
  name: get-expense
---
