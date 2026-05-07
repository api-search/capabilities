---
categories: []
consumed_apis: []
description: The Google Safe Browsing API enables client applications to check web resources (most commonly URLs) against Google-generated lists of unsafe web resources. It supports threat list management, URL checking, and hash-based lookups.
layout: capability
name: Google Safe Browsing API
operations:
- description: Google Safe Browsing Find Threat Matches
  method: POST
  name: findthreatmatches
  path: /threatMatches:find
- description: Google Safe Browsing List Threat Lists
  method: GET
  name: listthreatlists
  path: /threatLists
- description: Google Safe Browsing Fetch Threat List Updates
  method: POST
  name: fetchthreatlistupdates
  path: /threatListUpdates:fetch
- description: Google Safe Browsing Find Full Hashes
  method: POST
  name: findfullhashes
  path: /fullHashes:find
personas: []
provider_name: Google Safe Browsing
provider_slug: google-safe-browsing
search_terms:
- google safe browsing find threat matches
- browsing
- google safe browsing fetch threat list updates
- listthreatlists
- findthreatmatches
- safe
- google
- google safe browsing list threat lists
- threats
- google safe browsing find full hashes
- fetchthreatlistupdates
- safe browsing
- api
- security
- urls
- malware
- findfullhashes
slug: google-safe-browsing-capability
source_filename: google-safe-browsing-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Safe Browsing API\n  description: The Google Safe Browsing API enables client applications to check web resources (most commonly URLs) against\n    Google-generated lists of unsafe web resources. It supports threat list management, URL checking, and hash-based lookups.\n  tags:\n  - Google\n  - Safe\n  - Browsing\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-safe-browsing\n    baseUri: https://safebrowsing.googleapis.com/v4\n    description: Google Safe Browsing API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{GOOGLE_SAFE_BROWSING_TOKEN}}'\n    resources:\n    - name: threatmatches-find\n      path: /threatMatches:find\n      operations:\n      - name: findthreatmatches\n        method: POST\n        description: Google Safe Browsing Find Threat Matches\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: threatlists\n      path: /threatLists\n      operations:\n      - name: listthreatlists\n        method: GET\n        description: Google Safe Browsing List Threat Lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threatlistupdates-fetch\n      path: /threatListUpdates:fetch\n      operations:\n      - name: fetchthreatlistupdates\n        method: POST\n        description: Google Safe Browsing Fetch Threat List Updates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fullhashes-find\n      path: /fullHashes:find\n      operations:\n      - name: findfullhashes\n        method: POST\n        description: Google Safe Browsing Find Full Hashes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-safe-browsing-rest\n    description: REST adapter for Google Safe Browsing API.\n    resources:\n    - path: /threatMatches:find\n      name: findthreatmatches\n      operations:\n      - method: POST\n        name: findthreatmatches\n        description: Google Safe Browsing Find Threat Matches\n        call: google-safe-browsing.findthreatmatches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threatLists\n      name: listthreatlists\n      operations:\n      - method: GET\n        name: listthreatlists\n        description: Google Safe Browsing List Threat Lists\n        call: google-safe-browsing.listthreatlists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threatListUpdates:fetch\n      name: fetchthreatlistupdates\n      operations:\n      - method: POST\n        name: fetchthreatlistupdates\n\
  \        description: Google Safe Browsing Fetch Threat List Updates\n        call: google-safe-browsing.fetchthreatlistupdates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fullHashes:find\n      name: findfullhashes\n      operations:\n      - method: POST\n        name: findfullhashes\n        description: Google Safe Browsing Find Full Hashes\n        call: google-safe-browsing.findfullhashes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-safe-browsing-mcp\n    transport: http\n    description: MCP adapter for Google Safe Browsing API for AI agent use.\n    tools:\n    - name: findthreatmatches\n      description: Google Safe Browsing Find Threat Matches\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-safe-browsing.findthreatmatches\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listthreatlists\n      description: Google Safe Browsing List Threat Lists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-safe-browsing.listthreatlists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetchthreatlistupdates\n      description: Google Safe Browsing Fetch Threat List Updates\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-safe-browsing.fetchthreatlistupdates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: findfullhashes\n      description: Google Safe Browsing Find Full Hashes\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-safe-browsing.findfullhashes\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_SAFE_BROWSING_TOKEN: GOOGLE_SAFE_BROWSING_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-safe-browsing/refs/heads/main/capabilities/google-safe-browsing-capability.yaml
tags:
- Google
- Safe
- Browsing
- API
tools:
- description: Google Safe Browsing Find Threat Matches
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: findthreatmatches
- description: Google Safe Browsing List Threat Lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listthreatlists
- description: Google Safe Browsing Fetch Threat List Updates
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fetchthreatlistupdates
- description: Google Safe Browsing Find Full Hashes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: findfullhashes
---
