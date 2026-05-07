---
categories: []
consumed_apis: []
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
- screen entity
- case details.
- kyc
- screening
- list groups
- tag text with financial entities.
- extract and tag financial entities from document text using intelligent tagging.
- world-check
- refinitiv
- search for organizations and instruments.
- tag document entities
- compliance
- delete a screening case.
- create and screen
- screening group configuration.
- entity search via permid.
- resolve and annotate a world-check screening match result with risk determination.
- search for organizations and instruments using permid for pre-screening entity research.
- resolve screening result
- entity screening cases.
- delete case
- get case
- aml
- retrieve the current status and results of a world-check screening case.
- list screening groups
- due diligence
- create a case and screen against world-check.
- tag content
- list available screening groups.
- get screening case details.
- get screening case
- screen a company or individual against the world-check risk intelligence database for kyc and aml compliance.
- intelligent entity tagging.
- search entities
- list available world-check screening groups and their configurations.
slug: compliance-screening
source_filename: compliance-screening.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Refinitiv Compliance Screening\n  description: Unified workflow capability for compliance officers and KYC analysts screening entities and verifying identities\n    using Refinitiv's World-Check risk intelligence database and PermID entity search. Supports onboarding, due diligence,\n    AML, and ongoing monitoring workflows.\n  tags:\n  - Refinitiv\n  - Compliance\n  - KYC\n  - AML\n  - Screening\n  - Due Diligence\n  - World-Check\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORLD_CHECK_API_KEY: WORLD_CHECK_API_KEY\n    WORLD_CHECK_API_SECRET: WORLD_CHECK_API_SECRET\n    PERMID_APP_KEY: PERMID_APP_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: refinitiv-world-check\n    baseUri: https://api-worldcheck.refinitiv.com/v2\n    description: World-Check One API for entity risk screening.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: HMAC-SHA256\
  \ {{WORLD_CHECK_API_KEY}}:{{WORLD_CHECK_API_SECRET}}\n      placement: header\n    resources:\n    - name: cases\n      path: /cases\n      description: Case management and screening.\n      operations:\n      - name: create-case-and-screen\n        method: POST\n        description: Create a case and perform synchronous screening.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            entityType: '{{tools.entityType}}'\n            name: '{{tools.name}}'\n            groupId: '{{tools.groupId}}'\n      - name: get-case\n        method: GET\n        description: Get case details.\n        inputParameters:\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: Case system identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: update-case\n        method: PUT\n        description: Update an existing case.\n        inputParameters:\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: Case system identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-case\n        method: DELETE\n        description: Delete a case.\n        inputParameters:\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: Case system identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: screening-results\n      path: /cases\n      description:\
  \ Screening results management.\n      operations:\n      - name: get-screening-results\n        method: GET\n        description: Get screening results for a case.\n        inputParameters:\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: Case system identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resolve-screening-result\n        method: PUT\n        description: Resolve a screening match result.\n        inputParameters:\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: Case system identifier.\n        - name: resultId\n          in: path\n          type: string\n          required: true\n          description: Result identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            riskType: '{{tools.riskType}}'\n            comments: '{{tools.comments}}'\n    - name: groups\n      path: /groups\n      description: Group management.\n      operations:\n      - name: list-groups\n        method: GET\n        description: List available screening groups.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: refinitiv-permid\n    baseUri: https://api-eit.refinitiv.com/permid\n    description: PermID Entity Search REST API.\n    authentication:\n      type: apikey\n      key: x-ag-access-token\n      value: '{{PERMID_APP_KEY}}'\n      placement: header\n    resources:\n    - name: entity-search\n      path: /search\n      description: Entity search and lookup.\n      operations:\n      - name: search-entities\n        method: GET\n        description:\
  \ Search entities by query string.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query.\n        - name: entityType\n          in: query\n          type: string\n          required: false\n          description: Entity type filter (organization, instrument, quote).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: intelligent-tagging\n      path: /calais\n      description: Entity extraction from text.\n      operations:\n      - name: tag-content\n        method: POST\n        description: Tag text content with financial entities.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            content: '{{tools.content}}'\n    - name: record-matching\n\
  \      path: /match\n      description: Match records to PermIDs.\n      operations:\n      - name: match-records\n        method: POST\n        description: Match entity records to PermID identifiers.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            entity: '{{tools.entity}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: refinitiv-compliance-api\n    description: Unified REST API for Refinitiv compliance and screening.\n    resources:\n    - path: /v1/screening/cases\n      name: screening-cases\n      description: Entity screening cases.\n      operations:\n      - method: POST\n        name: create-and-screen\n        description: Create a case and screen against World-Check.\n        call: refinitiv-world-check.create-case-and-screen\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/screening/cases/{caseSystemId}\n      name: screening-case-detail\n      description: Case details.\n      operations:\n      - method: GET\n        name: get-case\n        description: Get screening case details.\n        call: refinitiv-world-check.get-case\n        with:\n          caseSystemId: rest.caseSystemId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-case\n        description: Delete a screening case.\n        call: refinitiv-world-check.delete-case\n        with:\n          caseSystemId: rest.caseSystemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/screening/groups\n      name: screening-groups\n      description: Screening group configuration.\n      operations:\n      - method: GET\n        name: list-groups\n        description: List available screening groups.\n        call: refinitiv-world-check.list-groups\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/entities/search\n      name: entity-search\n      description: Entity search via PermID.\n      operations:\n      - method: GET\n        name: search-entities\n        description: Search for organizations and instruments.\n        call: refinitiv-permid.search-entities\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/tag\n      name: entity-tagging\n      description: Intelligent entity tagging.\n      operations:\n      - method: POST\n        name: tag-content\n        description: Tag text with financial entities.\n        call: refinitiv-permid.tag-content\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: refinitiv-compliance-mcp\n    transport: http\n    description: MCP server for AI-assisted Refinitiv compliance screening.\n    tools:\n    - name: screen-entity\n\
  \      description: Screen a company or individual against the World-Check risk intelligence database for KYC and AML compliance.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: refinitiv-world-check.create-case-and-screen\n      with:\n        entityType: tools.entityType\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-screening-case\n      description: Retrieve the current status and results of a World-Check screening case.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: refinitiv-world-check.get-case\n      with:\n        caseSystemId: tools.caseSystemId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resolve-screening-result\n      description: Resolve and annotate a World-Check screening match result with risk determination.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: refinitiv-world-check.resolve-screening-result\n\
  \      with:\n        caseSystemId: tools.caseSystemId\n        resultId: tools.resultId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-screening-groups\n      description: List available World-Check screening groups and their configurations.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: refinitiv-world-check.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-entities\n      description: Search for organizations and instruments using PermID for pre-screening entity research.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: refinitiv-permid.search-entities\n      with:\n        q: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tag-document-entities\n      description: Extract and tag financial entities from document text using Intelligent Tagging.\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: refinitiv-permid.tag-content\n      with:\n        content: tools.content\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
