---
categories: []
consumed_apis:
- factset-irn-config
- factset-irn-contacts
- factset-irn-symbols
- factset-irn-meetings
- factset-irn-notes
description: Unified workflow for managing internal research notes including configuration, contacts, custom symbols, meetings, and notes. Used by research analysts and relationship managers.
layout: capability
name: FactSet Investment Research Notes
operations:
- description: List IRN contacts.
  method: GET
  name: list-contacts
  path: /v1/irn-contacts
- description: List IRN meetings.
  method: GET
  name: list-meetings
  path: /v1/irn-meetings
- description: List IRN notes.
  method: GET
  name: list-notes
  path: /v1/irn-notes
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- get irn config
- list irn contacts
- investment analytics
- research notes
- list irn notes.
- irn note management.
- list irn contacts.
- list irn meetings
- list contacts
- list irn symbols
- list irn notes
- irn meeting management.
- list irn meetings.
- portfolio analytics
- crm
- financial
- market data
- get irn configuration.
- list notes
- research
- factset
- irn contact management.
- list meetings
- list irn custom symbols.
- irn
- financial data
slug: investment-research-notes
source_filename: investment-research-notes.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Investment Research Notes\"\n  description: \"Unified workflow for managing internal research notes including configuration, contacts, custom symbols, meetings, and notes. Used by research analysts and relationship managers.\"\n  tags:\n    - FactSet\n    - IRN\n    - Research Notes\n    - CRM\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-irn-config\n      location: ./shared/irn-configuration.yaml\n    - import: factset-irn-contacts\n      location: ./shared/irn-contacts.yaml\n    - import: factset-irn-symbols\n      location: ./shared/irn-custom-symbols.yaml\n    - import: factset-irn-meetings\n      location: ./shared/irn-meetings.yaml\n    - import: factset-irn-notes\n      location: ./shared/irn-notes.yaml\n\n  exposes:\n    - type: rest\n\
  \      port: 8086\n      namespace: irn-api\n      description: \"Unified REST API for investment research notes.\"\n      resources:\n        - path: /v1/irn-contacts\n          name: irn-contacts\n          description: \"IRN contact management.\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List IRN contacts.\"\n              call: \"factset-irn-contacts.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/irn-meetings\n          name: irn-meetings\n          description: \"IRN meeting management.\"\n          operations:\n            - method: GET\n              name: list-meetings\n              description: \"List IRN meetings.\"\n              call: \"factset-irn-meetings.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/irn-notes\n          name: irn-notes\n\
  \          description: \"IRN note management.\"\n          operations:\n            - method: GET\n              name: list-notes\n              description: \"List IRN notes.\"\n              call: \"factset-irn-notes.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9086\n      namespace: irn-mcp\n      transport: http\n      description: \"MCP server for AI-assisted investment research notes.\"\n      tools:\n        - name: get-irn-config\n          description: \"Get IRN configuration.\"\n          hints:\n            readOnly: true\n          call: \"factset-irn-config.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-irn-contacts\n          description: \"List IRN contacts.\"\n          hints:\n            readOnly: true\n          call: \"factset-irn-contacts.list\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-irn-symbols\n          description: \"List IRN custom symbols.\"\n          hints:\n            readOnly: true\n          call: \"factset-irn-symbols.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-irn-meetings\n          description: \"List IRN meetings.\"\n          hints:\n            readOnly: true\n          call: \"factset-irn-meetings.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-irn-notes\n          description: \"List IRN notes.\"\n          hints:\n            readOnly: true\n          call: \"factset-irn-notes.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/investment-research-notes.yaml
tags:
- FactSet
- IRN
- Research Notes
- CRM
tools:
- description: Get IRN configuration.
  hints:
    readOnly: true
  name: get-irn-config
- description: List IRN contacts.
  hints:
    readOnly: true
  name: list-irn-contacts
- description: List IRN custom symbols.
  hints:
    readOnly: true
  name: list-irn-symbols
- description: List IRN meetings.
  hints:
    readOnly: true
  name: list-irn-meetings
- description: List IRN notes.
  hints:
    readOnly: true
  name: list-irn-notes
---
