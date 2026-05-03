---
api_specs:
- filename: spin-ai-openapi.yml
  format: yaml
  label: spin-ai
  slug: spin-ai
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spin-ai/refs/heads/main/openapi/spin-ai-openapi.yml
categories: []
consumed_apis:
- spin-ai
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
- entity backup status management
- spin ai
- saas security
- get all entities
- disable entity backup
- activate entity backup
- enable backup for one or more entities by setting their status to active.
- get all backup entities
- search and filter backup entities by type (user/group/drive), status (active/archived/disabled), and platform. use for auditing backup coverage gaps.
- retrieve all users, groups, and drives managed by spinone backup. filter by platform (google_workspace, microsoft_365, salesforce, slack).
- microsoft 365
- update backup status for entities
- archive entity backup
- google workspace
- filter backup entities
- filter entities
- data protection
- ransomware
- compliance
- backup entity management
- filter entities by type, status, and platform
- filtered entity retrieval
- retrieve all backup entities
- disable backup for one or more entities — backup stops and data retention ceases.
- backup
- update entity status
- archive one or more entities in spinone — backup stops but existing data is retained.
slug: saas-data-protection
source_filename: saas-data-protection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spin.AI SaaS Data Protection\"\n  description: >-\n    Workflow capability for managing SaaS data protection and backup entity lifecycle\n    using the Spin.AI SpinOne platform. Enables IT administrators and security teams\n    to audit backup coverage, identify unprotected entities, and manage backup status\n    across Google Workspace, Microsoft 365, Salesforce, and Slack environments.\n  tags:\n    - Spin AI\n    - SaaS Security\n    - Data Protection\n    - Backup\n    - Compliance\n    - Google Workspace\n    - Microsoft 365\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPIN_AI_APP_ID: SPIN_AI_APP_ID\n      SPIN_AI_API_KEY: SPIN_AI_API_KEY\n\ncapability:\n  consumes:\n    - import: spin-ai\n      location: ./shared/spin-ai.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spin-ai-data-protection-api\n      description: \"Unified REST API for Spin.AI\
  \ SaaS data protection workflows.\"\n      resources:\n        - path: /v1/entities\n          name: entities\n          description: \"Backup entity management\"\n          operations:\n            - method: GET\n              name: get-all-entities\n              description: \"Retrieve all backup entities\"\n              call: \"spin-ai.get-all-entities\"\n              with:\n                platform: \"rest.platform\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities/filter\n          name: entity-filter\n          description: \"Filtered entity retrieval\"\n          operations:\n            - method: POST\n              name: filter-entities\n              description: \"Filter entities by type, status, and platform\"\n              call: \"spin-ai.filter-entities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities/status\n\
  \          name: entity-status\n          description: \"Entity backup status management\"\n          operations:\n            - method: POST\n              name: update-entity-status\n              description: \"Update backup status for entities\"\n              call: \"spin-ai.update-entity-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spin-ai-data-protection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SaaS data protection management.\"\n      tools:\n        - name: get-all-backup-entities\n          description: \"Retrieve all users, groups, and drives managed by SpinOne backup. Filter by platform (google_workspace, microsoft_365, salesforce, slack).\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spin-ai.get-all-entities\"\n          with:\n            platform: \"tools.platform\"\n  \
  \        outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: filter-backup-entities\n          description: \"Search and filter backup entities by type (user/group/drive), status (ACTIVE/ARCHIVED/DISABLED), and platform. Use for auditing backup coverage gaps.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spin-ai.filter-entities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: activate-entity-backup\n          description: \"Enable backup for one or more entities by setting their status to ACTIVE.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"spin-ai.update-entity-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: archive-entity-backup\n          description: \"Archive one or more entities in SpinOne — backup stops but existing\
  \ data is retained.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"spin-ai.update-entity-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: disable-entity-backup\n          description: \"Disable backup for one or more entities — backup stops and data retention ceases.\"\n          hints:\n            readOnly: false\n            idempotent: true\n            destructive: true\n          call: \"spin-ai.update-entity-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
