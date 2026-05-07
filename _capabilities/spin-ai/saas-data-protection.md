---
categories: []
consumed_apis: []
description: Workflow capability for managing SaaS data protection and backup entity lifecycle using the Spin.AI SpinOne platform. Enables IT administrators and security teams to audit backup coverage, identify unprotected entities, and manage backup status across Google Workspace, Microsoft 365, Salesforce, and Slack environments.
layout: capability
name: Spin.AI SaaS Data Protection
operations:
- description: Retrieve all backup entities
  method: GET
  name: get-all-entities
  path: /v1/entities
- description: Filter entities by type, status, and platform
  method: POST
  name: filter-entities
  path: /v1/entities/filter
- description: Update backup status for entities
  method: POST
  name: update-entity-status
  path: /v1/entities/status
personas: []
provider_name: Spin.AI
provider_slug: spin-ai
search_terms:
- get all entities
- microsoft 365
- ransomware
- disable entity backup
- spin ai
- update entity status
- compliance
- filter entities by type, status, and platform
- disable backup for one or more entities — backup stops and data retention ceases.
- saas security
- data protection
- backup
- retrieve all users, groups, and drives managed by spinone backup. filter by platform (google_workspace, microsoft_365, salesforce, slack).
- archive entity backup
- filter entities
- filtered entity retrieval
- entity backup status management
- activate entity backup
- backup entity management
- update backup status for entities
- google workspace
- enable backup for one or more entities by setting their status to active.
- filter backup entities
- retrieve all backup entities
- archive one or more entities in spinone — backup stops but existing data is retained.
- get all backup entities
- search and filter backup entities by type (user/group/drive), status (active/archived/disabled), and platform. use for auditing backup coverage gaps.
slug: saas-data-protection
source_filename: saas-data-protection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spin.AI SaaS Data Protection\n  description: Workflow capability for managing SaaS data protection and backup entity lifecycle using the Spin.AI SpinOne\n    platform. Enables IT administrators and security teams to audit backup coverage, identify unprotected entities, and manage\n    backup status across Google Workspace, Microsoft 365, Salesforce, and Slack environments.\n  tags:\n  - Spin AI\n  - SaaS Security\n  - Data Protection\n  - Backup\n  - Compliance\n  - Google Workspace\n  - Microsoft 365\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPIN_AI_APP_ID: SPIN_AI_APP_ID\n    SPIN_AI_API_KEY: SPIN_AI_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: spin-ai\n    baseUri: https://apg-1.spin.ai\n    description: Spin.AI SpinOne SaaS data protection REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: SPIN_API X-APP-ID={{SPIN_AI_APP_ID}},X-API-KEY={{SPIN_AI_API_KEY}}\n\
  \      placement: header\n    resources:\n    - name: entities-all\n      path: /api/v1/integration/backup/entities/all\n      description: Retrieve all backup entities\n      operations:\n      - name: get-all-entities\n        method: GET\n        description: Retrieve all entities managed by SpinOne backup\n        inputParameters:\n        - name: platform\n          in: query\n          type: string\n          required: false\n          description: Filter by SaaS platform (google_workspace, microsoft_365, etc.)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities-filter\n      path: /api/v1/integration/backup/entities/filter\n      description: Filter backup entities by criteria\n      operations:\n      - name: filter-entities\n        method: POST\n        description: Retrieve filtered entities by type, status, and platform\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            types: '{{tools.types}}'\n            statuses: '{{tools.statuses}}'\n            platforms: '{{tools.platforms}}'\n            search: '{{tools.search}}'\n    - name: entity-status\n      path: /api/v1/integration/backup/entity/status\n      description: Update entity backup status\n      operations:\n      - name: update-entity-status\n        method: POST\n        description: Update the backup status of one or more entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            entity_ids: '{{tools.entity_ids}}'\n            status: '{{tools.status}}'\n            reason: '{{tools.reason}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: spin-ai-data-protection-api\n    description: Unified REST API\
  \ for Spin.AI SaaS data protection workflows.\n    resources:\n    - path: /v1/entities\n      name: entities\n      description: Backup entity management\n      operations:\n      - method: GET\n        name: get-all-entities\n        description: Retrieve all backup entities\n        call: spin-ai.get-all-entities\n        with:\n          platform: rest.platform\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/filter\n      name: entity-filter\n      description: Filtered entity retrieval\n      operations:\n      - method: POST\n        name: filter-entities\n        description: Filter entities by type, status, and platform\n        call: spin-ai.filter-entities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/status\n      name: entity-status\n      description: Entity backup status management\n      operations:\n      - method: POST\n        name: update-entity-status\n        description:\
  \ Update backup status for entities\n        call: spin-ai.update-entity-status\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: spin-ai-data-protection-mcp\n    transport: http\n    description: MCP server for AI-assisted SaaS data protection management.\n    tools:\n    - name: get-all-backup-entities\n      description: Retrieve all users, groups, and drives managed by SpinOne backup. Filter by platform (google_workspace,\n        microsoft_365, salesforce, slack).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spin-ai.get-all-entities\n      with:\n        platform: tools.platform\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: filter-backup-entities\n      description: Search and filter backup entities by type (user/group/drive), status (ACTIVE/ARCHIVED/DISABLED), and platform.\n        Use for auditing backup coverage gaps.\n      hints:\n        readOnly:\
  \ true\n        openWorld: false\n      call: spin-ai.filter-entities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-entity-backup\n      description: Enable backup for one or more entities by setting their status to ACTIVE.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: spin-ai.update-entity-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: archive-entity-backup\n      description: Archive one or more entities in SpinOne — backup stops but existing data is retained.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: spin-ai.update-entity-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disable-entity-backup\n      description: Disable backup for one or more entities — backup stops and data retention ceases.\n      hints:\n        readOnly: false\n        idempotent: true\n        destructive: true\n      call:\
  \ spin-ai.update-entity-status\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spin-ai/refs/heads/main/capabilities/saas-data-protection.yaml
tags:
- Spin AI
- SaaS Security
- Data Protection
- Backup
- Compliance
- Google Workspace
- Microsoft 365
tools:
- description: Retrieve all users, groups, and drives managed by SpinOne backup. Filter by platform (google_workspace, microsoft_365, salesforce, slack).
  hints:
    openWorld: true
    readOnly: true
  name: get-all-backup-entities
- description: Search and filter backup entities by type (user/group/drive), status (ACTIVE/ARCHIVED/DISABLED), and platform. Use for auditing backup coverage gaps.
  hints:
    openWorld: false
    readOnly: true
  name: filter-backup-entities
- description: Enable backup for one or more entities by setting their status to ACTIVE.
  hints:
    idempotent: true
    readOnly: false
  name: activate-entity-backup
- description: Archive one or more entities in SpinOne — backup stops but existing data is retained.
  hints:
    idempotent: true
    readOnly: false
  name: archive-entity-backup
- description: Disable backup for one or more entities — backup stops and data retention ceases.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disable-entity-backup
---
