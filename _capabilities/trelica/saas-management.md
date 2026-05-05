---
api_specs:
- filename: trelica-rest-api-openapi.yml
  format: yaml
  label: trelica
  slug: trelica
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/trelica/refs/heads/main/openapi/trelica-rest-api-openapi.yml
categories: []
consumed_apis:
- trelica
description: Unified capability for IT teams to discover, manage, and optimize SaaS applications across the organization. Combines application discovery, user license tracking, contract management, workflow automation, and audit logging in a single workflow-oriented interface.
layout: capability
name: Trelica SaaS Management
operations:
- description: List all SaaS applications in the portfolio
  method: GET
  name: list-applications
  path: /v1/applications
- description: Get application details and metadata
  method: GET
  name: get-application
  path: /v1/applications/{appId}
- description: List users for license optimization analysis
  method: GET
  name: list-application-users
  path: /v1/applications/{appId}/users
- description: List people for access review and offboarding
  method: GET
  name: list-people
  path: /v1/people
- description: Onboard a new employee
  method: POST
  name: create-person
  path: /v1/people
- description: Get employee details and application access
  method: GET
  name: get-person
  path: /v1/people/{personId}
- description: Update employee record during lifecycle events
  method: PATCH
  name: update-person
  path: /v1/people/{personId}
- description: List contracts for renewal planning
  method: GET
  name: list-contracts
  path: /v1/contracts
- description: Get contract details and renewal dates
  method: GET
  name: get-contract
  path: /v1/contracts/{contractId}
- description: List automation workflows
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: List managed assets
  method: GET
  name: list-assets
  path: /v1/assets
- description: List audit events for compliance reporting
  method: GET
  name: list-audit-logs
  path: /v1/audit-logs
- description: List users for provisioning workflows
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Trelica
provider_slug: trelica
search_terms:
- software contracts and renewal management
- get application
- single employee record
- it automation workflows
- single saas application detail
- list all saas applications in the portfolio
- get application details and metadata
- list all saas applications in the portfolio. use for application discovery, spend analysis, and license optimization.
- list users
- list users via scim 2.0 for provisioning integrations and directory sync.
- single contract record
- software and hardware assets
- list managed assets
- create person
- get person
- list users for license optimization analysis
- list assets
- it management
- discovered and managed saas applications
- software asset management
- user directory via scim
- list contracts for renewal planning
- update employee record during lifecycle events
- get contract details including renewal date and annual value for negotiation planning.
- employees and their saas access
- list it automation workflows for onboarding, offboarding, and access management.
- update an employee record for department transfers, role changes, or offboarding.
- list application users
- get detailed information about a specific saas application including user count and cost.
- saas management
- get employee details including their saas application access and licenses.
- list workflows
- list automation workflows
- get contract details and renewal dates
- list users of an application for license optimization. identify inactive users and reduce spend.
- list employees for access reviews, onboarding/offboarding, and license right-sizing.
- list software contracts for renewal planning and spend management.
- list users for provisioning workflows
- list software and hardware assets for asset management and compliance.
- list applications
- list contracts
- get contract
- list audit log entries for compliance reporting, change tracking, and governance.
- update person
- onboard a new employee
- list people for access review and offboarding
- license management
- audit trail for compliance and governance
- get employee details and application access
- onboard a new employee and initialize their software access workflow.
- contract management
- users and license utilization for an application
- list people
- list audit logs
- list audit events for compliance reporting
slug: saas-management
source_filename: saas-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trelica SaaS Management\"\n  description: >-\n    Unified capability for IT teams to discover, manage, and optimize SaaS\n    applications across the organization. Combines application discovery,\n    user license tracking, contract management, workflow automation, and\n    audit logging in a single workflow-oriented interface.\n  tags:\n    - Contract Management\n    - IT Management\n    - License Management\n    - SaaS Management\n    - Software Asset Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRELICA_ACCESS_TOKEN: TRELICA_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: trelica\n      location: ./shared/trelica-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: trelica-saas-management-api\n      description: \"Unified REST API for SaaS portfolio management.\"\n      resources:\n        - path: /v1/applications\n     \
  \     name: applications\n          description: \"Discovered and managed SaaS applications\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all SaaS applications in the portfolio\"\n              call: \"trelica.list-applications\"\n              with:\n                q: \"rest.q\"\n                after: \"rest.after\"\n                limit: \"rest.limit\"\n                since: \"rest.since\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{appId}\n          name: application-detail\n          description: \"Single SaaS application detail\"\n          operations:\n            - method: GET\n              name: get-application\n              description: \"Get application details and metadata\"\n              call: \"trelica.get-application\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{appId}/users\n          name: application-users\n          description: \"Users and license utilization for an application\"\n          operations:\n            - method: GET\n              name: list-application-users\n              description: \"List users for license optimization analysis\"\n              call: \"trelica.list-application-users\"\n              with:\n                appId: \"rest.appId\"\n                q: \"rest.q\"\n                after: \"rest.after\"\n                limit: \"rest.limit\"\n                since: \"rest.since\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/people\n          name: people\n          description: \"Employees and their SaaS access\"\n          operations:\n            - method: GET\n              name: list-people\n              description: \"List people for\
  \ access review and offboarding\"\n              call: \"trelica.list-people\"\n              with:\n                q: \"rest.q\"\n                after: \"rest.after\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-person\n              description: \"Onboard a new employee\"\n              call: \"trelica.create-person\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/people/{personId}\n          name: person-detail\n          description: \"Single employee record\"\n          operations:\n            - method: GET\n              name: get-person\n              description: \"Get employee details and application access\"\n              call: \"trelica.get-person\"\n              with:\n                personId: \"rest.personId\"\n              outputParameters:\n  \
  \              - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-person\n              description: \"Update employee record during lifecycle events\"\n              call: \"trelica.update-person\"\n              with:\n                personId: \"rest.personId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contracts\n          name: contracts\n          description: \"Software contracts and renewal management\"\n          operations:\n            - method: GET\n              name: list-contracts\n              description: \"List contracts for renewal planning\"\n              call: \"trelica.list-contracts\"\n              with:\n                q: \"rest.q\"\n                after: \"rest.after\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contracts/{contractId}\n\
  \          name: contract-detail\n          description: \"Single contract record\"\n          operations:\n            - method: GET\n              name: get-contract\n              description: \"Get contract details and renewal dates\"\n              call: \"trelica.get-contract\"\n              with:\n                contractId: \"rest.contractId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows\n          name: workflows\n          description: \"IT automation workflows\"\n          operations:\n            - method: GET\n              name: list-workflows\n              description: \"List automation workflows\"\n              call: \"trelica.list-workflows\"\n              with:\n                q: \"rest.q\"\n                after: \"rest.after\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets\n          name: assets\n\
  \          description: \"Software and hardware assets\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List managed assets\"\n              call: \"trelica.list-assets\"\n              with:\n                q: \"rest.q\"\n                after: \"rest.after\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audit-logs\n          name: audit-logs\n          description: \"Audit trail for compliance and governance\"\n          operations:\n            - method: GET\n              name: list-audit-logs\n              description: \"List audit events for compliance reporting\"\n              call: \"trelica.list-audit-logs\"\n              with:\n                since: \"rest.since\"\n                after: \"rest.after\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User directory via SCIM\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users for provisioning workflows\"\n              call: \"trelica.list-scim-users\"\n              with:\n                startIndex: \"rest.startIndex\"\n                count: \"rest.count\"\n                filter: \"rest.filter\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: trelica-saas-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SaaS portfolio management and license optimization.\"\n      tools:\n        - name: list-applications\n          description: \"List all SaaS applications in the portfolio. Use for application discovery, spend analysis, and license optimization.\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trelica.list-applications\"\n          with:\n            q: \"tools.q\"\n            after: \"tools.after\"\n            limit: \"tools.limit\"\n            since: \"tools.since\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n          description: \"Get detailed information about a specific SaaS application including user count and cost.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trelica.get-application\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-application-users\n          description: \"List users of an application for license optimization. Identify inactive users and reduce spend.\"\n          hints:\n            readOnly: true\n          \
  \  openWorld: true\n          call: \"trelica.list-application-users\"\n          with:\n            appId: \"tools.appId\"\n            q: \"tools.q\"\n            since: \"tools.since\"\n            after: \"tools.after\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-people\n          description: \"List employees for access reviews, onboarding/offboarding, and license right-sizing.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trelica.list-people\"\n          with:\n            q: \"tools.q\"\n            after: \"tools.after\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-person\n          description: \"Get employee details including their SaaS application access and licenses.\"\n          hints:\n            readOnly: true\n          \
  \  openWorld: false\n          call: \"trelica.get-person\"\n          with:\n            personId: \"tools.personId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-person\n          description: \"Onboard a new employee and initialize their software access workflow.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"trelica.create-person\"\n          with:\n            displayName: \"tools.displayName\"\n            email: \"tools.email\"\n            department: \"tools.department\"\n            jobTitle: \"tools.jobTitle\"\n            active: \"tools.active\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-person\n          description: \"Update an employee record for department transfers, role changes, or offboarding.\"\n          hints:\n            readOnly: false\n      \
  \      destructive: false\n            idempotent: true\n          call: \"trelica.update-person\"\n          with:\n            personId: \"tools.personId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-contracts\n          description: \"List software contracts for renewal planning and spend management.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trelica.list-contracts\"\n          with:\n            q: \"tools.q\"\n            after: \"tools.after\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-contract\n          description: \"Get contract details including renewal date and annual value for negotiation planning.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trelica.get-contract\"\n          with:\n            contractId:\
  \ \"tools.contractId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workflows\n          description: \"List IT automation workflows for onboarding, offboarding, and access management.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trelica.list-workflows\"\n          with:\n            q: \"tools.q\"\n            after: \"tools.after\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-assets\n          description: \"List software and hardware assets for asset management and compliance.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trelica.list-assets\"\n          with:\n            q: \"tools.q\"\n            after: \"tools.after\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: list-audit-logs\n          description: \"List audit log entries for compliance reporting, change tracking, and governance.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trelica.list-audit-logs\"\n          with:\n            since: \"tools.since\"\n            after: \"tools.after\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List users via SCIM 2.0 for provisioning integrations and directory sync.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trelica.list-scim-users\"\n          with:\n            startIndex: \"tools.startIndex\"\n            count: \"tools.count\"\n            filter: \"tools.filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trelica/refs/heads/main/capabilities/saas-management.yaml
tags:
- Contract Management
- IT Management
- License Management
- SaaS Management
- Software Asset Management
tools:
- description: List all SaaS applications in the portfolio. Use for application discovery, spend analysis, and license optimization.
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Get detailed information about a specific SaaS application including user count and cost.
  hints:
    openWorld: false
    readOnly: true
  name: get-application
- description: List users of an application for license optimization. Identify inactive users and reduce spend.
  hints:
    openWorld: true
    readOnly: true
  name: list-application-users
- description: List employees for access reviews, onboarding/offboarding, and license right-sizing.
  hints:
    openWorld: true
    readOnly: true
  name: list-people
- description: Get employee details including their SaaS application access and licenses.
  hints:
    openWorld: false
    readOnly: true
  name: get-person
- description: Onboard a new employee and initialize their software access workflow.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-person
- description: Update an employee record for department transfers, role changes, or offboarding.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-person
- description: List software contracts for renewal planning and spend management.
  hints:
    openWorld: true
    readOnly: true
  name: list-contracts
- description: Get contract details including renewal date and annual value for negotiation planning.
  hints:
    openWorld: false
    readOnly: true
  name: get-contract
- description: List IT automation workflows for onboarding, offboarding, and access management.
  hints:
    openWorld: true
    readOnly: true
  name: list-workflows
- description: List software and hardware assets for asset management and compliance.
  hints:
    openWorld: true
    readOnly: true
  name: list-assets
- description: List audit log entries for compliance reporting, change tracking, and governance.
  hints:
    openWorld: true
    readOnly: true
  name: list-audit-logs
- description: List users via SCIM 2.0 for provisioning integrations and directory sync.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
---
