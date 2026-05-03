---
categories: []
consumed_apis:
- refinitiv-world-check
- refinitiv-permid
description: Unified workflow capability for compliance officers and KYC analysts screening entities and verifying identities using Refinitiv's World-Check risk intelligence database and PermID entity search. Supports onboarding, due diligence, AML, and ongoing monitoring workflows.
layout: capability
name: Refinitiv Compliance Screening
operations:
- description: Create a case and screen against World-Check.
  method: POST
  name: create-and-screen
  path: /v1/screening/cases
- description: Get screening case details.
  method: GET
  name: get-case
  path: /v1/screening/cases/{caseSystemId}
- description: Delete a screening case.
  method: DELETE
  name: delete-case
  path: /v1/screening/cases/{caseSystemId}
- description: List available screening groups.
  method: GET
  name: list-groups
  path: /v1/screening/groups
- description: Search for organizations and instruments.
  method: GET
  name: search-entities
  path: /v1/entities/search
- description: Tag text with financial entities.
  method: POST
  name: tag-content
  path: /v1/entities/tag
personas: []
provider_name: Refinitiv
provider_slug: refinitiv
search_terms:
- search for organizations and instruments using permid for pre-screening entity research.
- resolve screening result
- create a case and screen against world-check.
- list screening groups
- compliance
- get case
- extract and tag financial entities from document text using intelligent tagging.
- create and screen
- refinitiv
- screening
- screen entity
- screening group configuration.
- delete a screening case.
- resolve and annotate a world-check screening match result with risk determination.
- get screening case
- tag document entities
- list available world-check screening groups and their configurations.
- entity screening cases.
- screen a company or individual against the world-check risk intelligence database for kyc and aml compliance.
- intelligent entity tagging.
- aml
- search entities
- list groups
- search for organizations and instruments.
- world-check
- retrieve the current status and results of a world-check screening case.
- tag text with financial entities.
- get screening case details.
- kyc
- due diligence
- list available screening groups.
- entity search via permid.
- tag content
- delete case
- case details.
slug: compliance-screening
source_filename: compliance-screening.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Refinitiv Compliance Screening\"\n  description: >-\n    Unified workflow capability for compliance officers and KYC analysts\n    screening entities and verifying identities using Refinitiv's World-Check\n    risk intelligence database and PermID entity search. Supports onboarding,\n    due diligence, AML, and ongoing monitoring workflows.\n  tags:\n    - Refinitiv\n    - Compliance\n    - KYC\n    - AML\n    - Screening\n    - Due Diligence\n    - World-Check\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORLD_CHECK_API_KEY: WORLD_CHECK_API_KEY\n      WORLD_CHECK_API_SECRET: WORLD_CHECK_API_SECRET\n      PERMID_APP_KEY: PERMID_APP_KEY\n\ncapability:\n  consumes:\n    - import: refinitiv-world-check\n      location: ./shared/world-check-one.yaml\n    - import: refinitiv-permid\n      location: ./shared/permid.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n     \
  \ namespace: refinitiv-compliance-api\n      description: \"Unified REST API for Refinitiv compliance and screening.\"\n      resources:\n        - path: /v1/screening/cases\n          name: screening-cases\n          description: \"Entity screening cases.\"\n          operations:\n            - method: POST\n              name: create-and-screen\n              description: \"Create a case and screen against World-Check.\"\n              call: \"refinitiv-world-check.create-case-and-screen\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/screening/cases/{caseSystemId}\n          name: screening-case-detail\n          description: \"Case details.\"\n          operations:\n            - method: GET\n              name: get-case\n              description: \"Get screening case details.\"\n              call: \"refinitiv-world-check.get-case\"\n              with:\n                caseSystemId: \"rest.caseSystemId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-case\n              description: \"Delete a screening case.\"\n              call: \"refinitiv-world-check.delete-case\"\n              with:\n                caseSystemId: \"rest.caseSystemId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/screening/groups\n          name: screening-groups\n          description: \"Screening group configuration.\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List available screening groups.\"\n              call: \"refinitiv-world-check.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entities/search\n          name: entity-search\n          description: \"Entity search\
  \ via PermID.\"\n          operations:\n            - method: GET\n              name: search-entities\n              description: \"Search for organizations and instruments.\"\n              call: \"refinitiv-permid.search-entities\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entities/tag\n          name: entity-tagging\n          description: \"Intelligent entity tagging.\"\n          operations:\n            - method: POST\n              name: tag-content\n              description: \"Tag text with financial entities.\"\n              call: \"refinitiv-permid.tag-content\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: refinitiv-compliance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Refinitiv compliance screening.\"\
  \n      tools:\n        - name: screen-entity\n          description: \"Screen a company or individual against the World-Check risk intelligence database for KYC and AML compliance.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"refinitiv-world-check.create-case-and-screen\"\n          with:\n            entityType: \"tools.entityType\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-screening-case\n          description: \"Retrieve the current status and results of a World-Check screening case.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"refinitiv-world-check.get-case\"\n          with:\n            caseSystemId: \"tools.caseSystemId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: resolve-screening-result\n          description:\
  \ \"Resolve and annotate a World-Check screening match result with risk determination.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"refinitiv-world-check.resolve-screening-result\"\n          with:\n            caseSystemId: \"tools.caseSystemId\"\n            resultId: \"tools.resultId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-screening-groups\n          description: \"List available World-Check screening groups and their configurations.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"refinitiv-world-check.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-entities\n          description: \"Search for organizations and instruments using PermID for pre-screening entity research.\"\n          hints:\n            readOnly: true\n           \
  \ openWorld: true\n          call: \"refinitiv-permid.search-entities\"\n          with:\n            q: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: tag-document-entities\n          description: \"Extract and tag financial entities from document text using Intelligent Tagging.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"refinitiv-permid.tag-content\"\n          with:\n            content: \"tools.content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/refinitiv/refs/heads/main/capabilities/compliance-screening.yaml
tags:
- Refinitiv
- Compliance
- KYC
- AML
- Screening
- Due Diligence
- World-Check
tools:
- description: Screen a company or individual against the World-Check risk intelligence database for KYC and AML compliance.
  hints:
    openWorld: false
    readOnly: false
  name: screen-entity
- description: Retrieve the current status and results of a World-Check screening case.
  hints:
    openWorld: false
    readOnly: true
  name: get-screening-case
- description: Resolve and annotate a World-Check screening match result with risk determination.
  hints:
    openWorld: false
    readOnly: false
  name: resolve-screening-result
- description: List available World-Check screening groups and their configurations.
  hints:
    openWorld: false
    readOnly: true
  name: list-screening-groups
- description: Search for organizations and instruments using PermID for pre-screening entity research.
  hints:
    openWorld: true
    readOnly: true
  name: search-entities
- description: Extract and tag financial entities from document text using Intelligent Tagging.
  hints:
    openWorld: false
    readOnly: true
  name: tag-document-entities
---
