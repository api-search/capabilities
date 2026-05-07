---
categories: []
consumed_apis: []
description: Unified capability for Rightsline rights and royalties management. Enables rights licensing workflows, content availability checking, royalty tracking, workflow automation, and audit trail access for media and entertainment rights management teams.
layout: capability
name: Rightsline Rights and Royalties Management
operations:
- description: List rights and license records
  method: GET
  name: list-rights
  path: /v1/rights
- description: Get rights record by ID
  method: GET
  name: get-right
  path: /v1/rights/{id}
- description: Update a rights record
  method: PUT
  name: update-right
  path: /v1/rights/{id}
- description: Delete a rights record
  method: DELETE
  name: delete-right
  path: /v1/rights/{id}
- description: Validate content availability for a territory and platform
  method: GET
  name: check-availability
  path: /v1/availability
- description: Execute workflow action on records
  method: POST
  name: execute-workflow-action
  path: /v1/workflows/{workflowId}/actions
- description: Get record change history
  method: GET
  name: get-audit-trail
  path: /v1/audit/{recordId}
personas: []
provider_name: Rightsline
provider_slug: rightsline
search_terms:
- validate content availability for a territory and platform
- create a new rights record for a content title, territory, and platform
- rights and license management
- workflow automation
- check availability
- delete right
- execute a rightsline workflow action on one or more records (e.g., generate delivery request)
- list rights and license records, optionally filtered by modification date
- get record change history
- get audit trail
- get the change history and audit trail for a specific rights or royalty record
- list rights
- content availability checking
- execute workflow
- check whether content is available for distribution in a territory and platform window
- get rights record by id
- availability
- update right
- entertainment
- individual rights record
- royalties
- media
- get right
- content management
- rights management
- delete a rights record
- get full details of a rights or license record including territory and window
- create right
- workflows
- list rights and license records
- audit trail
- rightsline
- execute workflow action
- update a rights record
- execute workflow action on records
- update an existing rights record's terms, dates, or territory
slug: rights-royalties-management
source_filename: rights-royalties-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rightsline Rights and Royalties Management\n  description: Unified capability for Rightsline rights and royalties management. Enables rights licensing workflows, content\n    availability checking, royalty tracking, workflow automation, and audit trail access for media and entertainment rights\n    management teams.\n  tags:\n  - Availability\n  - Content Management\n  - Entertainment\n  - Media\n  - Rights Management\n  - Rightsline\n  - Royalties\n  - Workflows\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RIGHTSLINE_API_KEY: RIGHTSLINE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: rightsline-rights\n    baseUri: https://app.rightsline.com/v4\n    description: Rightsline Rights API for rights, availability, and workflow management.\n    authentication:\n      type: bearer\n      token: '{{RIGHTSLINE_API_KEY}}'\n    resources:\n    - name: rights\n      path: /rights\n \
  \     description: Rights and license records\n      operations:\n      - name: list-rights\n        method: GET\n        description: List rights records with pagination\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page (max 100)\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: modifiedAfter\n          in: query\n          type: string\n          required: false\n          description: Filter by modification date\n        outputRawFormat: json\n        outputParameters:\n        - name: rights\n          type: object\n          value: $.\n      - name: create-right\n        method: POST\n        description: Create a new rights record\n        outputRawFormat: json\n        outputParameters:\n        - name: right\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            contentId: '{{tools.contentId}}'\n            territory: '{{tools.territory}}'\n            platform: '{{tools.platform}}'\n            startDate: '{{tools.startDate}}'\n            endDate: '{{tools.endDate}}'\n      - name: get-right\n        method: GET\n        description: Get a rights record by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Rights record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: right\n          type: object\n          value: $.\n      - name: update-right\n        method: PUT\n        description: Update an existing rights record\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Rights record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: right\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            territory: '{{tools.territory}}'\n            platform: '{{tools.platform}}'\n            endDate: '{{tools.endDate}}'\n      - name: delete-right\n        method: DELETE\n        description: Delete a rights record\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Rights record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: availability\n      path: /availability\n      description: Content availability checking\n      operations:\n      - name: check-availability\n        method: GET\n        description: Check content availability for a territory, platform, and time window\n        inputParameters:\n        - name: contentId\n          in: query\n          type: string\n          required: true\n          description:\
  \ Content identifier\n        - name: territory\n          in: query\n          type: string\n          required: false\n          description: Territory code\n        - name: platform\n          in: query\n          type: string\n          required: false\n          description: Distribution platform\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Window start date\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: Window end date\n        outputRawFormat: json\n        outputParameters:\n        - name: availability\n          type: object\n          value: $.\n    - name: workflows\n      path: /workflows\n      description: Workflow automation\n      operations:\n      - name: execute-workflow-action\n        method: POST\n        description: Execute a workflow action on up to 100 records\n        inputParameters:\n        - name: workflowId\n\
  \          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: results\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            recordIds: '{{tools.recordIds}}'\n    - name: audit\n      path: /audit\n      description: Audit trail\n      operations:\n      - name: get-audit-trail\n        method: GET\n        description: Get audit history for a record\n        inputParameters:\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: Record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: audit\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rightsline-management-api\n    description: Unified REST API for Rightsline rights, royalties, and availability management.\n   \
  \ resources:\n    - path: /v1/rights\n      name: rights\n      description: Rights and license management\n      operations:\n      - method: GET\n        name: list-rights\n        description: List rights and license records\n        call: rightsline-rights.list-rights\n        with:\n          limit: rest.limit\n          offset: rest.offset\n          modifiedAfter: rest.modifiedAfter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rights/{id}\n      name: right\n      description: Individual rights record\n      operations:\n      - method: GET\n        name: get-right\n        description: Get rights record by ID\n        call: rightsline-rights.get-right\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-right\n        description: Update a rights record\n        call: rightsline-rights.update-right\n        with:\n          id: rest.id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-right\n        description: Delete a rights record\n        call: rightsline-rights.delete-right\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/availability\n      name: availability\n      description: Content availability checking\n      operations:\n      - method: GET\n        name: check-availability\n        description: Validate content availability for a territory and platform\n        call: rightsline-rights.check-availability\n        with:\n          contentId: rest.contentId\n          territory: rest.territory\n          platform: rest.platform\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{workflowId}/actions\n      name: workflow-actions\n      description:\
  \ Workflow automation\n      operations:\n      - method: POST\n        name: execute-workflow-action\n        description: Execute workflow action on records\n        call: rightsline-rights.execute-workflow-action\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audit/{recordId}\n      name: audit\n      description: Audit trail\n      operations:\n      - method: GET\n        name: get-audit-trail\n        description: Get record change history\n        call: rightsline-rights.get-audit-trail\n        with:\n          recordId: rest.recordId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: rightsline-management-mcp\n    transport: http\n    description: MCP server for AI-assisted rights management and availability validation workflows.\n    tools:\n    - name: list-rights\n      description: List rights and license records,\
  \ optionally filtered by modification date\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rightsline-rights.list-rights\n      with:\n        limit: tools.limit\n        offset: tools.offset\n        modifiedAfter: tools.modifiedAfter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-right\n      description: Get full details of a rights or license record including territory and window\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rightsline-rights.get-right\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-right\n      description: Create a new rights record for a content title, territory, and platform\n      hints:\n        readOnly: false\n        destructive: false\n      call: rightsline-rights.create-right\n      with:\n        contentId: tools.contentId\n        territory: tools.territory\n        platform: tools.platform\n\
  \        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-right\n      description: Update an existing rights record's terms, dates, or territory\n      hints:\n        readOnly: false\n        idempotent: true\n      call: rightsline-rights.update-right\n      with:\n        id: tools.id\n        territory: tools.territory\n        platform: tools.platform\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-right\n      description: Delete a rights record\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: rightsline-rights.delete-right\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-availability\n      description: Check whether content is available for distribution in a territory and platform window\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: rightsline-rights.check-availability\n      with:\n        contentId: tools.contentId\n        territory: tools.territory\n        platform: tools.platform\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-workflow\n      description: Execute a Rightsline workflow action on one or more records (e.g., generate delivery request)\n      hints:\n        readOnly: false\n        destructive: false\n      call: rightsline-rights.execute-workflow-action\n      with:\n        workflowId: tools.workflowId\n        recordIds: tools.recordIds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-audit-trail\n      description: Get the change history and audit trail for a specific rights or royalty record\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rightsline-rights.get-audit-trail\n\
  \      with:\n        recordId: tools.recordId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rightsline/refs/heads/main/capabilities/rights-royalties-management.yaml
tags:
- Availability
- Content Management
- Entertainment
- Media
- Rights Management
- Rightsline
- Royalties
- Workflows
tools:
- description: List rights and license records, optionally filtered by modification date
  hints:
    openWorld: true
    readOnly: true
  name: list-rights
- description: Get full details of a rights or license record including territory and window
  hints:
    openWorld: true
    readOnly: true
  name: get-right
- description: Create a new rights record for a content title, territory, and platform
  hints:
    destructive: false
    readOnly: false
  name: create-right
- description: Update an existing rights record's terms, dates, or territory
  hints:
    idempotent: true
    readOnly: false
  name: update-right
- description: Delete a rights record
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-right
- description: Check whether content is available for distribution in a territory and platform window
  hints:
    openWorld: true
    readOnly: true
  name: check-availability
- description: Execute a Rightsline workflow action on one or more records (e.g., generate delivery request)
  hints:
    destructive: false
    readOnly: false
  name: execute-workflow
- description: Get the change history and audit trail for a specific rights or royalty record
  hints:
    openWorld: true
    readOnly: true
  name: get-audit-trail
---
