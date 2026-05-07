---
categories: []
consumed_apis: []
description: The Ironclad Clickwrap API (formerly PactSafe) lets developers programmatically manage clickwrap and click-through agreements, track user acceptance, and generate audit-ready records of consent for terms, privacy policies, and other legal contracts.
layout: capability
name: Ironclad Clickwrap API
operations:
- description: List sites
  method: GET
  name: listsites
  path: /sites
- description: Get a site
  method: GET
  name: getsite
  path: /sites/{siteId}
- description: List clickwrap groups
  method: GET
  name: listgroups
  path: /groups
- description: Get a clickwrap group
  method: GET
  name: getgroup
  path: /groups/{groupId}
- description: List contracts
  method: GET
  name: listcontracts
  path: /contracts
- description: Get a contract
  method: GET
  name: getcontract
  path: /contracts/{contractId}
- description: List signers
  method: GET
  name: listsigners
  path: /signers
- description: Get a signer
  method: GET
  name: getsigner
  path: /signers/{signerId}
- description: Record an agreement acceptance event
  method: POST
  name: sendagreed
  path: /send/agreed
- description: Record a contract display event
  method: POST
  name: senddisplayed
  path: /send/displayed
- description: Record a page visit event
  method: POST
  name: sendvisited
  path: /send/visited
- description: Retrieve the latest acceptance state for a signer
  method: GET
  name: retrievelatest
  path: /retrieve/latest
personas: []
provider_name: Ironclad Clickwrap
provider_slug: ironclad-clickwrap
search_terms:
- ironclad
- record an agreement acceptance event
- get a signer
- clickwrap
- list clickwrap groups
- get a contract
- api
- listcontracts
- getsite
- listsites
- contracts
- list signers
- retrieve the latest acceptance state for a signer
- compliance
- list sites
- getgroup
- listgroups
- list contracts
- getsigner
- get a site
- get a clickwrap group
- record a contract display event
- sendvisited
- record a page visit event
- agreements
- retrievelatest
- senddisplayed
- getcontract
- legal
- sendagreed
- listsigners
slug: ironclad-clickwrap-capability
source_filename: ironclad-clickwrap-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ironclad Clickwrap API\n  description: The Ironclad Clickwrap API (formerly PactSafe) lets developers programmatically manage clickwrap and click-through\n    agreements, track user acceptance, and generate audit-ready records of consent for terms, privacy policies, and other\n    legal contracts.\n  tags:\n  - Ironclad\n  - Clickwrap\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ironclad-clickwrap\n    baseUri: https://pactsafe.io\n    description: Ironclad Clickwrap API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{IRONCLAD_CLICKWRAP_TOKEN}}'\n    resources:\n    - name: sites\n      path: /sites\n      operations:\n      - name: listsites\n        method: GET\n        description: List sites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-siteid\n\
  \      path: /sites/{siteId}\n      operations:\n      - name: getsite\n        method: GET\n        description: Get a site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: List clickwrap groups\n        inputParameters:\n        - name: sid\n          in: query\n          type: integer\n          description: Site ID filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-groupid\n      path: /groups/{groupId}\n      operations:\n      - name: getgroup\n        method: GET\n        description: Get a clickwrap group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts\n      path: /contracts\n\
  \      operations:\n      - name: listcontracts\n        method: GET\n        description: List contracts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts-contractid\n      path: /contracts/{contractId}\n      operations:\n      - name: getcontract\n        method: GET\n        description: Get a contract\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signers\n      path: /signers\n      operations:\n      - name: listsigners\n        method: GET\n        description: List signers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signers-signerid\n      path: /signers/{signerId}\n      operations:\n      - name: getsigner\n        method: GET\n        description: Get a signer\n        inputParameters:\n  \
  \      - name: signerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: send-agreed\n      path: /send/agreed\n      operations:\n      - name: sendagreed\n        method: POST\n        description: Record an agreement acceptance event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: send-displayed\n      path: /send/displayed\n      operations:\n      - name: senddisplayed\n        method: POST\n        description: Record a contract display event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: send-visited\n      path: /send/visited\n      operations:\n      - name: sendvisited\n        method: POST\n        description: Record a page visit event\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: retrieve-latest\n      path: /retrieve/latest\n      operations:\n      - name: retrievelatest\n        method: GET\n        description: Retrieve the latest acceptance state for a signer\n        inputParameters:\n        - name: sig\n          in: query\n          type: string\n          required: true\n          description: Signer identifier.\n        - name: gkey\n          in: query\n          type: string\n          description: Group key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ironclad-clickwrap-rest\n    description: REST adapter for Ironclad Clickwrap API.\n    resources:\n    - path: /sites\n      name: listsites\n      operations:\n      - method: GET\n        name: listsites\n        description:\
  \ List sites\n        call: ironclad-clickwrap.listsites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}\n      name: getsite\n      operations:\n      - method: GET\n        name: getsite\n        description: Get a site\n        call: ironclad-clickwrap.getsite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: List clickwrap groups\n        call: ironclad-clickwrap.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{groupId}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n        description: Get a clickwrap group\n        call: ironclad-clickwrap.getgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contracts\n      name: listcontracts\n  \
  \    operations:\n      - method: GET\n        name: listcontracts\n        description: List contracts\n        call: ironclad-clickwrap.listcontracts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contracts/{contractId}\n      name: getcontract\n      operations:\n      - method: GET\n        name: getcontract\n        description: Get a contract\n        call: ironclad-clickwrap.getcontract\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /signers\n      name: listsigners\n      operations:\n      - method: GET\n        name: listsigners\n        description: List signers\n        call: ironclad-clickwrap.listsigners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /signers/{signerId}\n      name: getsigner\n      operations:\n      - method: GET\n        name: getsigner\n        description: Get a signer\n        call: ironclad-clickwrap.getsigner\n        with:\n  \
  \        signerId: rest.signerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /send/agreed\n      name: sendagreed\n      operations:\n      - method: POST\n        name: sendagreed\n        description: Record an agreement acceptance event\n        call: ironclad-clickwrap.sendagreed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /send/displayed\n      name: senddisplayed\n      operations:\n      - method: POST\n        name: senddisplayed\n        description: Record a contract display event\n        call: ironclad-clickwrap.senddisplayed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /send/visited\n      name: sendvisited\n      operations:\n      - method: POST\n        name: sendvisited\n        description: Record a page visit event\n        call: ironclad-clickwrap.sendvisited\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /retrieve/latest\n      name: retrievelatest\n      operations:\n      - method: GET\n        name: retrievelatest\n        description: Retrieve the latest acceptance state for a signer\n        call: ironclad-clickwrap.retrievelatest\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ironclad-clickwrap-mcp\n    transport: http\n    description: MCP adapter for Ironclad Clickwrap API for AI agent use.\n    tools:\n    - name: listsites\n      description: List sites\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ironclad-clickwrap.listsites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsite\n      description: Get a site\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ironclad-clickwrap.getsite\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: listgroups\n      description: List clickwrap groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ironclad-clickwrap.listgroups\n      with:\n        sid: tools.sid\n      inputParameters:\n      - name: sid\n        type: integer\n        description: Site ID filter.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgroup\n      description: Get a clickwrap group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ironclad-clickwrap.getgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontracts\n      description: List contracts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ironclad-clickwrap.listcontracts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontract\n      description: Get a contract\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ironclad-clickwrap.getcontract\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsigners\n      description: List signers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ironclad-clickwrap.listsigners\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsigner\n      description: Get a signer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ironclad-clickwrap.getsigner\n      with:\n        signerId: tools.signerId\n      inputParameters:\n      - name: signerId\n        type: string\n        description: signerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendagreed\n      description: Record an agreement acceptance event\n      hints:\n       \
  \ readOnly: false\n        destructive: false\n        idempotent: false\n      call: ironclad-clickwrap.sendagreed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: senddisplayed\n      description: Record a contract display event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ironclad-clickwrap.senddisplayed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendvisited\n      description: Record a page visit event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ironclad-clickwrap.sendvisited\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievelatest\n      description: Retrieve the latest acceptance state for a signer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ironclad-clickwrap.retrievelatest\n      with:\n\
  \        sig: tools.sig\n        gkey: tools.gkey\n      inputParameters:\n      - name: sig\n        type: string\n        description: Signer identifier.\n        required: true\n      - name: gkey\n        type: string\n        description: Group key.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    IRONCLAD_CLICKWRAP_TOKEN: IRONCLAD_CLICKWRAP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ironclad-clickwrap/refs/heads/main/capabilities/ironclad-clickwrap-capability.yaml
tags:
- Ironclad
- Clickwrap
- API
tools:
- description: List sites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsites
- description: Get a site
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsite
- description: List clickwrap groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Get a clickwrap group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: List contracts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontracts
- description: Get a contract
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontract
- description: List signers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsigners
- description: Get a signer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsigner
- description: Record an agreement acceptance event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendagreed
- description: Record a contract display event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: senddisplayed
- description: Record a page visit event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendvisited
- description: Retrieve the latest acceptance state for a signer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievelatest
---
