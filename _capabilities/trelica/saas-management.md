---
categories: []
consumed_apis: []
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
- list users for provisioning workflows
- update employee record during lifecycle events
- get contract details and renewal dates
- get application details and metadata
- list application users
- list employees for access reviews, onboarding/offboarding, and license right-sizing.
- onboard a new employee
- single contract record
- list managed assets
- get contract
- get person
- list people for access review and offboarding
- license management
- get detailed information about a specific saas application including user count and cost.
- list people
- it management
- list software contracts for renewal planning and spend management.
- onboard a new employee and initialize their software access workflow.
- list it automation workflows for onboarding, offboarding, and access management.
- discovered and managed saas applications
- contract management
- list contracts
- saas management
- list users via scim 2.0 for provisioning integrations and directory sync.
- create person
- list audit log entries for compliance reporting, change tracking, and governance.
- audit trail for compliance and governance
- single saas application detail
- list automation workflows
- user directory via scim
- list audit logs
- list users of an application for license optimization. identify inactive users and reduce spend.
- software contracts and renewal management
- single employee record
- list all saas applications in the portfolio. use for application discovery, spend analysis, and license optimization.
- list users for license optimization analysis
- list software and hardware assets for asset management and compliance.
- get employee details and application access
- employees and their saas access
- list audit events for compliance reporting
- software asset management
- list workflows
- list contracts for renewal planning
- it automation workflows
- list assets
- software and hardware assets
- users and license utilization for an application
- get contract details including renewal date and annual value for negotiation planning.
- update person
- list users
- get employee details including their saas application access and licenses.
- get application
- update an employee record for department transfers, role changes, or offboarding.
- list applications
- list all saas applications in the portfolio
slug: saas-management
source_filename: saas-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trelica SaaS Management\n  description: Unified capability for IT teams to discover, manage, and optimize SaaS applications across the organization.\n    Combines application discovery, user license tracking, contract management, workflow automation, and audit logging in\n    a single workflow-oriented interface.\n  tags:\n  - Contract Management\n  - IT Management\n  - License Management\n  - SaaS Management\n  - Software Asset Management\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRELICA_ACCESS_TOKEN: TRELICA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: trelica\n    baseUri: https://app.trelica.com/api\n    description: Trelica SaaS management REST API\n    authentication:\n      type: bearer\n      token: '{{TRELICA_ACCESS_TOKEN}}'\n    resources:\n    - name: applications\n      path: /apps/v1\n      description: SaaS applications tracked in Trelica\n      operations:\n\
  \      - name: list-applications\n        method: GET\n        description: List SaaS applications\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Free-text search\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results (default 100)\n        - name: since\n          in: query\n          type: string\n          required: false\n          description: Filter by modification date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-detail\n      path: /apps/v1/{appId}\n      description: Single SaaS application\n      operations:\n      - name: get-application\n        method: GET\n       \
  \ description: Get application details\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: Application identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-users\n      path: /apps/v1/{appId}/users\n      description: Users of a specific application\n      operations:\n      - name: list-application-users\n        method: GET\n        description: List users for a specific application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: Application identifier\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Free-text search\n        - name: after\n          in: query\n          type: string\n          required: false\n          description:\
  \ Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results (default 100)\n        - name: since\n          in: query\n          type: string\n          required: false\n          description: Filter by modification date\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: SCIM-style filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people\n      path: /people/v1\n      description: People (employees) in the organization\n      operations:\n      - name: list-people\n        method: GET\n        description: List people in the organization\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Free-text search\n        - name: after\n          in: query\n\
  \          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results (default 100)\n        - name: since\n          in: query\n          type: string\n          required: false\n          description: Filter by modification date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-person\n        method: POST\n        description: Create a new person record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            email: '{{tools.email}}'\n            department: '{{tools.department}}'\n            jobTitle: '{{tools.jobTitle}}'\n            active: '{{tools.active}}'\n\
  \    - name: person-detail\n      path: /people/v1/{personId}\n      description: Single person record\n      operations:\n      - name: get-person\n        method: GET\n        description: Get person details\n        inputParameters:\n        - name: personId\n          in: path\n          type: string\n          required: true\n          description: Person identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-person\n        method: PATCH\n        description: Update person record\n        inputParameters:\n        - name: personId\n          in: path\n          type: string\n          required: true\n          description: Person identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n       \
  \     email: '{{tools.email}}'\n            department: '{{tools.department}}'\n            jobTitle: '{{tools.jobTitle}}'\n            active: '{{tools.active}}'\n    - name: contracts\n      path: /contracts/v1\n      description: Software contracts managed in Trelica\n      operations:\n      - name: list-contracts\n        method: GET\n        description: List software contracts\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Free-text search\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results (default 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contract-detail\n      path: /contracts/v1/{contractId}\n\
  \      description: Single contract record\n      operations:\n      - name: get-contract\n        method: GET\n        description: Get contract details\n        inputParameters:\n        - name: contractId\n          in: path\n          type: string\n          required: true\n          description: Contract identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows\n      path: /workflows/v1\n      description: Automation workflows in Trelica\n      operations:\n      - name: list-workflows\n        method: GET\n        description: List automation workflows\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Free-text search\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in:\
  \ query\n          type: integer\n          required: false\n          description: Max results (default 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /assets/v1\n      description: Software and hardware assets\n      operations:\n      - name: list-assets\n        method: GET\n        description: List assets\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Free-text search\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results (default 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: audit-log\n      path: /audit/v1\n      description: Audit trail of all platform events\n      operations:\n      - name: list-audit-logs\n        method: GET\n        description: List audit log entries\n        inputParameters:\n        - name: since\n          in: query\n          type: string\n          required: false\n          description: Return entries after this date/time\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results (default 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scim-users\n      path: /scim/v2/Users\n      description: User provisioning via SCIM 2.0\n      operations:\n      - name: list-scim-users\n        method: GET\n        description:\
  \ List users using SCIM 2.0 protocol\n        inputParameters:\n        - name: startIndex\n          in: query\n          type: integer\n          required: false\n          description: 1-based start index (default 1)\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Max results (default 100)\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: SCIM filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: trelica-saas-management-api\n    description: Unified REST API for SaaS portfolio management.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: Discovered and managed SaaS applications\n      operations:\n      - method: GET\n        name: list-applications\n  \
  \      description: List all SaaS applications in the portfolio\n        call: trelica.list-applications\n        with:\n          q: rest.q\n          after: rest.after\n          limit: rest.limit\n          since: rest.since\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}\n      name: application-detail\n      description: Single SaaS application detail\n      operations:\n      - method: GET\n        name: get-application\n        description: Get application details and metadata\n        call: trelica.get-application\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{appId}/users\n      name: application-users\n      description: Users and license utilization for an application\n      operations:\n      - method: GET\n        name: list-application-users\n        description: List users for license optimization analysis\n\
  \        call: trelica.list-application-users\n        with:\n          appId: rest.appId\n          q: rest.q\n          after: rest.after\n          limit: rest.limit\n          since: rest.since\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people\n      name: people\n      description: Employees and their SaaS access\n      operations:\n      - method: GET\n        name: list-people\n        description: List people for access review and offboarding\n        call: trelica.list-people\n        with:\n          q: rest.q\n          after: rest.after\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-person\n        description: Onboard a new employee\n        call: trelica.create-person\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people/{personId}\n      name: person-detail\n      description: Single\
  \ employee record\n      operations:\n      - method: GET\n        name: get-person\n        description: Get employee details and application access\n        call: trelica.get-person\n        with:\n          personId: rest.personId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-person\n        description: Update employee record during lifecycle events\n        call: trelica.update-person\n        with:\n          personId: rest.personId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contracts\n      name: contracts\n      description: Software contracts and renewal management\n      operations:\n      - method: GET\n        name: list-contracts\n        description: List contracts for renewal planning\n        call: trelica.list-contracts\n        with:\n          q: rest.q\n          after: rest.after\n          limit: rest.limit\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/contracts/{contractId}\n      name: contract-detail\n      description: Single contract record\n      operations:\n      - method: GET\n        name: get-contract\n        description: Get contract details and renewal dates\n        call: trelica.get-contract\n        with:\n          contractId: rest.contractId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows\n      name: workflows\n      description: IT automation workflows\n      operations:\n      - method: GET\n        name: list-workflows\n        description: List automation workflows\n        call: trelica.list-workflows\n        with:\n          q: rest.q\n          after: rest.after\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Software and hardware assets\n      operations:\n      - method: GET\n        name: list-assets\n      \
  \  description: List managed assets\n        call: trelica.list-assets\n        with:\n          q: rest.q\n          after: rest.after\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audit-logs\n      name: audit-logs\n      description: Audit trail for compliance and governance\n      operations:\n      - method: GET\n        name: list-audit-logs\n        description: List audit events for compliance reporting\n        call: trelica.list-audit-logs\n        with:\n          since: rest.since\n          after: rest.after\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User directory via SCIM\n      operations:\n      - method: GET\n        name: list-users\n        description: List users for provisioning workflows\n        call: trelica.list-scim-users\n        with:\n          startIndex: rest.startIndex\n\
  \          count: rest.count\n          filter: rest.filter\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: trelica-saas-management-mcp\n    transport: http\n    description: MCP server for AI-assisted SaaS portfolio management and license optimization.\n    tools:\n    - name: list-applications\n      description: List all SaaS applications in the portfolio. Use for application discovery, spend analysis, and license\n        optimization.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trelica.list-applications\n      with:\n        q: tools.q\n        after: tools.after\n        limit: tools.limit\n        since: tools.since\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application\n      description: Get detailed information about a specific SaaS application including user count and cost.\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: trelica.get-application\n      with:\n        appId: tools.appId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-application-users\n      description: List users of an application for license optimization. Identify inactive users and reduce spend.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trelica.list-application-users\n      with:\n        appId: tools.appId\n        q: tools.q\n        since: tools.since\n        after: tools.after\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-people\n      description: List employees for access reviews, onboarding/offboarding, and license right-sizing.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trelica.list-people\n      with:\n        q: tools.q\n        after: tools.after\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-person\n      description: Get employee details including their SaaS application access and licenses.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trelica.get-person\n      with:\n        personId: tools.personId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-person\n      description: Onboard a new employee and initialize their software access workflow.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: trelica.create-person\n      with:\n        displayName: tools.displayName\n        email: tools.email\n        department: tools.department\n        jobTitle: tools.jobTitle\n        active: tools.active\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-person\n      description: Update an employee record for department transfers, role changes, or offboarding.\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: true\n      call: trelica.update-person\n      with:\n        personId: tools.personId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contracts\n      description: List software contracts for renewal planning and spend management.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trelica.list-contracts\n      with:\n        q: tools.q\n        after: tools.after\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contract\n      description: Get contract details including renewal date and annual value for negotiation planning.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trelica.get-contract\n      with:\n        contractId: tools.contractId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workflows\n      description: List IT automation workflows\
  \ for onboarding, offboarding, and access management.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trelica.list-workflows\n      with:\n        q: tools.q\n        after: tools.after\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List software and hardware assets for asset management and compliance.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trelica.list-assets\n      with:\n        q: tools.q\n        after: tools.after\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-audit-logs\n      description: List audit log entries for compliance reporting, change tracking, and governance.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trelica.list-audit-logs\n      with:\n        since: tools.since\n        after: tools.after\n        limit: tools.limit\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-users\n      description: List users via SCIM 2.0 for provisioning integrations and directory sync.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trelica.list-scim-users\n      with:\n        startIndex: tools.startIndex\n        count: tools.count\n        filter: tools.filter\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
