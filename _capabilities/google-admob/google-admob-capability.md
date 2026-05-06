---
categories: []
consumed_apis: []
description: The AdMob API provides programmatic access to AdMob account information, including ad units, apps, ad sources, mediation groups, and reporting for mobile app monetization.
layout: capability
name: Google AdMob API
operations:
- description: Google AdMob List accounts
  method: GET
  name: listaccounts
  path: /v1/accounts
- description: Google AdMob List ad units
  method: GET
  name: listadunits
  path: /v1/{parent}/adUnits
- description: Google AdMob Create ad unit
  method: POST
  name: createadunit
  path: /v1/{parent}/adUnits
- description: Google AdMob List apps
  method: GET
  name: listapps
  path: /v1/{parent}/apps
- description: Google AdMob List mediation groups
  method: GET
  name: listmediationgroups
  path: /v1/{parent}/mediationGroups
- description: Google AdMob Generate network report
  method: POST
  name: generatenetworkreport
  path: /v1/{parent}/networkReport:generate
personas: []
provider_name: Google AdMob
provider_slug: google-admob
search_terms:
- listaccounts
- google admob list mediation groups
- mobile apps
- google admob create ad unit
- listapps
- google admob list ad units
- google
- ad mediation
- reports
- listmediationgroups
- listadunits
- google admob list accounts
- app monetization
- api
- createadunit
- google admob generate network report
- admob
- mobile advertising
- google admob list apps
- generatenetworkreport
slug: google-admob-capability
source_filename: google-admob-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google AdMob API\n  description: The AdMob API provides programmatic access to AdMob account information, including ad units, apps, ad sources,\n    mediation groups, and reporting for mobile app monetization.\n  tags:\n  - Google\n  - Admob\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-admob\n    baseUri: https://admob.googleapis.com\n    description: Google AdMob API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ADMOB_TOKEN}}'\n    resources:\n    - name: v1-accounts\n      path: /v1/accounts\n      operations:\n      - name: listaccounts\n        method: GET\n        description: Google AdMob List accounts\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-adunits\n      path: /v1/{parent}/adUnits\n      operations:\n      - name: listadunits\n        method: GET\n        description: Google AdMob List ad units\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createadunit\n        method: POST\n        description: Google AdMob Create ad unit\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-apps\n      path: /v1/{parent}/apps\n      operations:\n      - name: listapps\n        method: GET\n        description: Google AdMob\
  \ List apps\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-mediationgroups\n      path: /v1/{parent}/mediationGroups\n      operations:\n      - name: listmediationgroups\n        method: GET\n        description: Google AdMob List mediation groups\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-networkreport-generate\n      path: /v1/{parent}/networkReport:generate\n      operations:\n      - name: generatenetworkreport\n        method: POST\n        description: Google AdMob Generate network report\n        inputParameters:\n        - name: parent\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-admob-rest\n    description: REST adapter for Google AdMob API.\n    resources:\n    - path: /v1/accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: Google AdMob List accounts\n        call: google-admob.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/adUnits\n      name: listadunits\n      operations:\n      - method: GET\n        name: listadunits\n        description: Google AdMob List ad units\n        call: google-admob.listadunits\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/adUnits\n \
  \     name: createadunit\n      operations:\n      - method: POST\n        name: createadunit\n        description: Google AdMob Create ad unit\n        call: google-admob.createadunit\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/apps\n      name: listapps\n      operations:\n      - method: GET\n        name: listapps\n        description: Google AdMob List apps\n        call: google-admob.listapps\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/mediationGroups\n      name: listmediationgroups\n      operations:\n      - method: GET\n        name: listmediationgroups\n        description: Google AdMob List mediation groups\n        call: google-admob.listmediationgroups\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/{parent}/networkReport:generate\n      name: generatenetworkreport\n      operations:\n      - method: POST\n        name: generatenetworkreport\n        description: Google AdMob Generate network report\n        call: google-admob.generatenetworkreport\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-admob-mcp\n    transport: http\n    description: MCP adapter for Google AdMob API for AI agent use.\n    tools:\n    - name: listaccounts\n      description: Google AdMob List accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admob.listaccounts\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n     \
  \   description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadunits\n      description: Google AdMob List ad units\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admob.listadunits\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createadunit\n      description: Google AdMob Create ad unit\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-admob.createadunit\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapps\n      description:\
  \ Google AdMob List apps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admob.listapps\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmediationgroups\n      description: Google AdMob List mediation groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admob.listmediationgroups\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatenetworkreport\n      description: Google AdMob Generate network report\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: google-admob.generatenetworkreport\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ADMOB_TOKEN: GOOGLE_ADMOB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-admob/refs/heads/main/capabilities/google-admob-capability.yaml
tags:
- Google
- Admob
- API
tools:
- description: Google AdMob List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Google AdMob List ad units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadunits
- description: Google AdMob Create ad unit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createadunit
- description: Google AdMob List apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapps
- description: Google AdMob List mediation groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmediationgroups
- description: Google AdMob Generate network report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatenetworkreport
---
