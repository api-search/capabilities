---
categories: []
consumed_apis: []
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
- member suspension
- get detailed information for a specific organization member
- unified workflow for member management and expense tracking
- expense management
- accounting
- get expense
- finance team member responsible for expense approvals and reimbursements
- get member details
- invite member
- list expense reports with filters
- list members
- individual expense report
- expense report submission, approval, and reimbursement workflows
- organization member management
- update member role or department
- hr manager responsible for member provisioning and access management
- finance
- Finance Administrator
- individual member operations
- members
- update a member's role, department, or status within the organization
- list expenses
- reimbursement
- suspend a member
- organization member provisioning, role management, and access control
- get expense report details
- get detailed information for a specific expense report including receipt url
- get member
- invite a new member to the organization
- suspend an organization member to prevent expense submissions
- list all members in the organization with pagination support
- suspend member
- organization employee submitting expense reports for reimbursement
- HR Manager
- list expense reports with filtering by status, member, or date range
- list all organization members
- invite a new member to the organization with email and role assignment
- expense report management
- update member
- abacus
slug: expense-management
source_filename: expense-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Abacus Expense Management\n  description: Unified workflow for managing employee expenses, reimbursements, and member provisioning. Enables finance teams\n    and administrators to automate expense reporting, track spending by member or category, and manage organizational membership.\n  tags:\n  - Abacus\n  - Expense Management\n  - Finance\n  - Reimbursement\n  - Members\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ABACUS_CLIENT_ID: ABACUS_CLIENT_ID\n    ABACUS_CLIENT_SECRET: ABACUS_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: abacus-api\n    baseUri: https://api.abacus.com\n    description: Abacus expense management API\n    authentication:\n      type: bearer\n      token: '{{ABACUS_ACCESS_TOKEN}}'\n    resources:\n    - name: members\n      path: /members\n      description: Member management operations\n      operations:\n      - name: list-members\n        method:\
  \ GET\n        description: List all organization members\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invite-member\n        method: POST\n        description: Invite a new member to the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: member\n      path: /members/{member_id}\n      description: Individual member operations\n      operations:\n      - name: get-member\n        method: GET\n        description: Get details for a specific member\n        inputParameters:\n        - name: member_id\n\
  \          in: path\n          type: string\n          required: true\n          description: Member identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-member\n        method: PUT\n        description: Update a member's details\n        inputParameters:\n        - name: member_id\n          in: path\n          type: string\n          required: true\n          description: Member identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: suspend-member\n      path: /members/{member_id}/suspend\n      description: Member suspension operations\n      operations:\n      - name: suspend-member\n        method: POST\n        description: Suspend a member from the organization\n        inputParameters:\n        - name: member_id\n          in: path\n          type: string\n          required: true\n\
  \          description: Member identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: expenses\n      path: /expenses\n      description: Expense report operations\n      operations:\n      - name: list-expenses\n        method: GET\n        description: List expense reports with filtering options\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by expense status\n        - name: member_id\n          in: query\n          type: string\n          required: false\n          description: Filter by member ID\n        - name: from_date\n          in: query\n          type: string\n          required: false\n          description: Filter from date\n        - name: to_date\n\
  \          in: query\n          type: string\n          required: false\n          description: Filter to date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: expense\n      path: /expenses/{expense_id}\n      description: Individual expense operations\n      operations:\n      - name: get-expense\n        method: GET\n        description: Get details for a specific expense report\n        inputParameters:\n        - name: expense_id\n          in: path\n          type: string\n          required: true\n          description: Expense identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: expense-management-api\n    description: Unified REST API for Abacus expense management and member administration.\n    resources:\n    - path: /v1/members\n      name: members\n\
  \      description: Organization member management\n      operations:\n      - method: GET\n        name: list-members\n        description: List all organization members\n        call: abacus-api.list-members\n        with:\n          page: rest.page\n          per_page: rest.per_page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: invite-member\n        description: Invite a new member to the organization\n        call: abacus-api.invite-member\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{member_id}\n      name: member\n      description: Individual member operations\n      operations:\n      - method: GET\n        name: get-member\n        description: Get member details\n        call: abacus-api.get-member\n        with:\n          member_id: rest.member_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name:\
  \ update-member\n        description: Update member role or department\n        call: abacus-api.update-member\n        with:\n          member_id: rest.member_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{member_id}/suspend\n      name: suspend-member\n      description: Member suspension\n      operations:\n      - method: POST\n        name: suspend-member\n        description: Suspend a member\n        call: abacus-api.suspend-member\n        with:\n          member_id: rest.member_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/expenses\n      name: expenses\n      description: Expense report management\n      operations:\n      - method: GET\n        name: list-expenses\n        description: List expense reports with filters\n        call: abacus-api.list-expenses\n        with:\n          status: rest.status\n          member_id: rest.member_id\n          from_date: rest.from_date\n\
  \          to_date: rest.to_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/expenses/{expense_id}\n      name: expense\n      description: Individual expense report\n      operations:\n      - method: GET\n        name: get-expense\n        description: Get expense report details\n        call: abacus-api.get-expense\n        with:\n          expense_id: rest.expense_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: expense-management-mcp\n    transport: http\n    description: MCP server for AI-assisted expense management and member administration.\n    tools:\n    - name: list-members\n      description: List all members in the organization with pagination support\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abacus-api.list-members\n      with:\n        page: tools.page\n        per_page: tools.per_page\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: invite-member\n      description: Invite a new member to the organization with email and role assignment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: abacus-api.invite-member\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member\n      description: Get detailed information for a specific organization member\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abacus-api.get-member\n      with:\n        member_id: tools.member_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-member\n      description: Update a member's role, department, or status within the organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: abacus-api.update-member\n      with:\n        member_id: tools.member_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: suspend-member\n      description: Suspend an organization member to prevent expense submissions\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: abacus-api.suspend-member\n      with:\n        member_id: tools.member_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-expenses\n      description: List expense reports with filtering by status, member, or date range\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abacus-api.list-expenses\n      with:\n        status: tools.status\n        member_id: tools.member_id\n        from_date: tools.from_date\n        to_date: tools.to_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-expense\n      description: Get detailed information for a specific expense report including receipt URL\n      hints:\n        readOnly: true\n    \
  \    openWorld: false\n      call: abacus-api.get-expense\n      with:\n        expense_id: tools.expense_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
