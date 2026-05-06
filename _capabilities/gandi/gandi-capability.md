---
categories: []
consumed_apis: []
description: The Gandi Domain API enables you to register, manage, transfer, and renew domain names registered with Gandi.
layout: capability
name: Gandi Domain API
operations:
- description: Check domain availability
  method: GET
  name: get-check
  path: /check
- description: List domains
  method: GET
  name: get-domains
  path: /domains
- description: Register domain
  method: POST
  name: post-domains
  path: /domains
- description: Get domain
  method: GET
  name: get-domains-domain
  path: /domains/{domain}
- description: Delete domain
  method: DELETE
  name: delete-domains-domain
  path: /domains/{domain}
- description: Reset auth code
  method: PUT
  name: put-domains-domain-authinfo
  path: /domains/{domain}/authinfo
- description: Update autorenew
  method: PATCH
  name: patch-domains-domain-autorenew
  path: /domains/{domain}/autorenew
- description: Get trademark claims
  method: GET
  name: get-domains-domain-claims
  path: /domains/{domain}/claims
- description: Initiate ownership change
  method: POST
  name: post-changeowner-domain
  path: /changeowner/{domain}
- description: Get ownership change status
  method: GET
  name: get-changeowner-domain
  path: /changeowner/{domain}
- description: Resend FOA
  method: POST
  name: post-changeowner-domain-foa
  path: /changeowner/{domain}/foa
personas: []
provider_name: Gandi
provider_slug: gandi
search_terms:
- resend foa
- delete domain
- dns
- domains
- post domains
- get check
- gandi
- check domain availability
- get trademark claims
- get changeowner domain
- domain registrar
- get domain
- post changeowner domain foa
- register domain
- put domains domain authinfo
- hosting
- api
- reset auth code
- get domains domain claims
- get ownership change status
- patch domains domain autorenew
- get domains
- list domains
- delete domains domain
- email
- get domains domain
- initiate ownership change
- certificates
- update autorenew
- post changeowner domain
slug: gandi-capability
source_filename: gandi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Gandi Domain API\n  description: The Gandi Domain API enables you to register, manage, transfer, and renew domain names registered with Gandi.\n  tags:\n  - Gandi\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: gandi\n    baseUri: https://api.gandi.net/v5/domain\n    description: Gandi Domain API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GANDI_TOKEN}}'\n    resources:\n    - name: check\n      path: /check\n      operations:\n      - name: get-check\n        method: GET\n        description: Check domain availability\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains\n      path: /domains\n      operations:\n      - name: get-domains\n\
  \        method: GET\n        description: List domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-domains\n        method: POST\n        description: Register domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains-domain\n      path: /domains/{domain}\n      operations:\n      - name: get-domains-domain\n        method: GET\n        description: Get domain\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-domains-domain\n        method: DELETE\n        description: Delete domain\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains-domain-authinfo\n      path: /domains/{domain}/authinfo\n      operations:\n      - name: put-domains-domain-authinfo\n        method: PUT\n        description: Reset auth code\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains-domain-autorenew\n      path: /domains/{domain}/autorenew\n      operations:\n      - name: patch-domains-domain-autorenew\n        method: PATCH\n        description: Update autorenew\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: domains-domain-claims\n      path: /domains/{domain}/claims\n      operations:\n      - name: get-domains-domain-claims\n        method: GET\n        description: Get trademark claims\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: changeowner-domain\n      path: /changeowner/{domain}\n      operations:\n      - name: post-changeowner-domain\n        method: POST\n        description: Initiate ownership change\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-changeowner-domain\n        method: GET\n        description:\
  \ Get ownership change status\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: changeowner-domain-foa\n      path: /changeowner/{domain}/foa\n      operations:\n      - name: post-changeowner-domain-foa\n        method: POST\n        description: Resend FOA\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gandi-rest\n    description: REST adapter for Gandi Domain API.\n    resources:\n    - path: /check\n      name: get-check\n      operations:\n      - method: GET\n        name: get-check\n        description: Check domain availability\n\
  \        call: gandi.get-check\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains\n      name: get-domains\n      operations:\n      - method: GET\n        name: get-domains\n        description: List domains\n        call: gandi.get-domains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains\n      name: post-domains\n      operations:\n      - method: POST\n        name: post-domains\n        description: Register domain\n        call: gandi.post-domains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domain}\n      name: get-domains-domain\n      operations:\n      - method: GET\n        name: get-domains-domain\n        description: Get domain\n        call: gandi.get-domains-domain\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domain}\n      name: delete-domains-domain\n\
  \      operations:\n      - method: DELETE\n        name: delete-domains-domain\n        description: Delete domain\n        call: gandi.delete-domains-domain\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domain}/authinfo\n      name: put-domains-domain-authinfo\n      operations:\n      - method: PUT\n        name: put-domains-domain-authinfo\n        description: Reset auth code\n        call: gandi.put-domains-domain-authinfo\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domain}/autorenew\n      name: patch-domains-domain-autorenew\n      operations:\n      - method: PATCH\n        name: patch-domains-domain-autorenew\n        description: Update autorenew\n        call: gandi.patch-domains-domain-autorenew\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /domains/{domain}/claims\n      name: get-domains-domain-claims\n      operations:\n      - method: GET\n        name: get-domains-domain-claims\n        description: Get trademark claims\n        call: gandi.get-domains-domain-claims\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /changeowner/{domain}\n      name: post-changeowner-domain\n      operations:\n      - method: POST\n        name: post-changeowner-domain\n        description: Initiate ownership change\n        call: gandi.post-changeowner-domain\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /changeowner/{domain}\n      name: get-changeowner-domain\n      operations:\n      - method: GET\n        name: get-changeowner-domain\n        description: Get ownership change status\n        call: gandi.get-changeowner-domain\n\
  \        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /changeowner/{domain}/foa\n      name: post-changeowner-domain-foa\n      operations:\n      - method: POST\n        name: post-changeowner-domain-foa\n        description: Resend FOA\n        call: gandi.post-changeowner-domain-foa\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gandi-mcp\n    transport: http\n    description: MCP adapter for Gandi Domain API for AI agent use.\n    tools:\n    - name: get-check\n      description: Check domain availability\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gandi.get-check\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-domains\n      description: List domains\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gandi.get-domains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-domains\n      description: Register domain\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: gandi.post-domains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-domains-domain\n      description: Get domain\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gandi.get-domains-domain\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-domains-domain\n\
  \      description: Delete domain\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: gandi.delete-domains-domain\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-domains-domain-authinfo\n      description: Reset auth code\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: gandi.put-domains-domain-authinfo\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-domains-domain-autorenew\n      description: Update autorenew\n      hints:\n        readOnly: false\n        destructive: false\n  \
  \      idempotent: false\n      call: gandi.patch-domains-domain-autorenew\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-domains-domain-claims\n      description: Get trademark claims\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gandi.get-domains-domain-claims\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-changeowner-domain\n      description: Initiate ownership change\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: gandi.post-changeowner-domain\n      with:\n        domain:\
  \ tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-changeowner-domain\n      description: Get ownership change status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gandi.get-changeowner-domain\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-changeowner-domain-foa\n      description: Resend FOA\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: gandi.post-changeowner-domain-foa\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description:\
  \ domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GANDI_TOKEN: GANDI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gandi/refs/heads/main/capabilities/gandi-capability.yaml
tags:
- Gandi
- API
tools:
- description: Check domain availability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-check
- description: List domains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-domains
- description: Register domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-domains
- description: Get domain
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-domains-domain
- description: Delete domain
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-domains-domain
- description: Reset auth code
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-domains-domain-authinfo
- description: Update autorenew
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-domains-domain-autorenew
- description: Get trademark claims
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-domains-domain-claims
- description: Initiate ownership change
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-changeowner-domain
- description: Get ownership change status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-changeowner-domain
- description: Resend FOA
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-changeowner-domain-foa
---
