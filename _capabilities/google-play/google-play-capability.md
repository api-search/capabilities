---
categories: []
consumed_apis: []
description: The Google Play Android Developer API allows developers to perform publishing and app-management tasks. It provides access to app publishing workflows, in-app product management, subscription handling, and purchase verification.
layout: capability
name: Google Play Developer API
operations:
- description: Google Play Developer Create a new edit
  method: POST
  name: createedit
  path: /androidpublisher/v3/applications/{packageName}/edits
- description: Google Play Developer List in-app products
  method: GET
  name: listinappproducts
  path: /androidpublisher/v3/applications/{packageName}/inappproducts
- description: Google Play Developer Get purchase status
  method: GET
  name: getpurchasestatus
  path: /androidpublisher/v3/applications/{packageName}/purchases/products/{productId}/tokens/{token}
- description: Google Play Developer Get subscription status
  method: GET
  name: getsubscriptionstatus
  path: /androidpublisher/v3/applications/{packageName}/purchases/subscriptionsv2/tokens/{token}
personas: []
provider_name: Google Play Developer
provider_slug: google-play
search_terms:
- play
- getpurchasestatus
- subscriptions
- android
- apps
- google
- google play developer create a new edit
- createedit
- listinappproducts
- google play developer get purchase status
- google play developer get subscription status
- google play
- api
- google play developer list in-app products
- in-app purchases
- mobile
- publishing
- getsubscriptionstatus
slug: google-play-capability
source_filename: google-play-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Play Developer API\n  description: The Google Play Android Developer API allows developers to perform publishing and app-management tasks. It\n    provides access to app publishing workflows, in-app product management, subscription handling, and purchase verification.\n  tags:\n  - Google\n  - Play\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-play\n    baseUri: https://androidpublisher.googleapis.com\n    description: Google Play Developer API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_PLAY_TOKEN}}'\n    resources:\n    - name: androidpublisher-v3-applications-packagename-edi\n      path: /androidpublisher/v3/applications/{packageName}/edits\n      operations:\n      - name: createedit\n        method: POST\n        description: Google Play Developer Create a new edit\n        inputParameters:\n        - name: packageName\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: androidpublisher-v3-applications-packagename-ina\n      path: /androidpublisher/v3/applications/{packageName}/inappproducts\n      operations:\n      - name: listinappproducts\n        method: GET\n        description: Google Play Developer List in-app products\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: androidpublisher-v3-applications-packagename-pur\n      path: /androidpublisher/v3/applications/{packageName}/purchases/products/{productId}/tokens/{token}\n      operations:\n      - name: getpurchasestatus\n        method: GET\n        description: Google Play\
  \ Developer Get purchase status\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n          required: true\n        - name: productId\n          in: path\n          type: string\n          required: true\n        - name: token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: androidpublisher-v3-applications-packagename-pur\n      path: /androidpublisher/v3/applications/{packageName}/purchases/subscriptionsv2/tokens/{token}\n      operations:\n      - name: getsubscriptionstatus\n        method: GET\n        description: Google Play Developer Get subscription status\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n          required: true\n        - name: token\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-play-rest\n    description: REST adapter for Google Play Developer API.\n    resources:\n    - path: /androidpublisher/v3/applications/{packageName}/edits\n      name: createedit\n      operations:\n      - method: POST\n        name: createedit\n        description: Google Play Developer Create a new edit\n        call: google-play.createedit\n        with:\n          packageName: rest.packageName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /androidpublisher/v3/applications/{packageName}/inappproducts\n      name: listinappproducts\n      operations:\n      - method: GET\n        name: listinappproducts\n        description: Google Play Developer List in-app products\n        call: google-play.listinappproducts\n        with:\n          packageName: rest.packageName\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /androidpublisher/v3/applications/{packageName}/purchases/products/{productId}/tokens/{token}\n      name: getpurchasestatus\n      operations:\n      - method: GET\n        name: getpurchasestatus\n        description: Google Play Developer Get purchase status\n        call: google-play.getpurchasestatus\n        with:\n          packageName: rest.packageName\n          productId: rest.productId\n          token: rest.token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /androidpublisher/v3/applications/{packageName}/purchases/subscriptionsv2/tokens/{token}\n      name: getsubscriptionstatus\n      operations:\n      - method: GET\n        name: getsubscriptionstatus\n        description: Google Play Developer Get subscription status\n        call: google-play.getsubscriptionstatus\n        with:\n          packageName: rest.packageName\n          token: rest.token\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-play-mcp\n    transport: http\n    description: MCP adapter for Google Play Developer API for AI agent use.\n    tools:\n    - name: createedit\n      description: Google Play Developer Create a new edit\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-play.createedit\n      with:\n        packageName: tools.packageName\n      inputParameters:\n      - name: packageName\n        type: string\n        description: packageName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinappproducts\n      description: Google Play Developer List in-app products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-play.listinappproducts\n      with:\n        packageName: tools.packageName\n  \
  \    inputParameters:\n      - name: packageName\n        type: string\n        description: packageName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpurchasestatus\n      description: Google Play Developer Get purchase status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-play.getpurchasestatus\n      with:\n        packageName: tools.packageName\n        productId: tools.productId\n        token: tools.token\n      inputParameters:\n      - name: packageName\n        type: string\n        description: packageName\n        required: true\n      - name: productId\n        type: string\n        description: productId\n        required: true\n      - name: token\n        type: string\n        description: token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubscriptionstatus\n      description: Google\
  \ Play Developer Get subscription status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-play.getsubscriptionstatus\n      with:\n        packageName: tools.packageName\n        token: tools.token\n      inputParameters:\n      - name: packageName\n        type: string\n        description: packageName\n        required: true\n      - name: token\n        type: string\n        description: token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_PLAY_TOKEN: GOOGLE_PLAY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-play/refs/heads/main/capabilities/google-play-capability.yaml
tags:
- Google
- Play
- API
tools:
- description: Google Play Developer Create a new edit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createedit
- description: Google Play Developer List in-app products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinappproducts
- description: Google Play Developer Get purchase status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpurchasestatus
- description: Google Play Developer Get subscription status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscriptionstatus
---
