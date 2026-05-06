---
categories: []
consumed_apis: []
description: Unified workflow for Microsoft Edge browser development combining DevTools Protocol debugging with Add-ons extension lifecycle management. Used by extension developers, web developers, and QA engineers.
layout: capability
name: Microsoft Edge Browser Development
operations:
- description: List all debuggable targets
  method: GET
  name: list-targets
  path: /v1/targets
- description: Open a new browser tab
  method: PUT
  name: create-target
  path: /v1/targets/new
- description: Get browser version info
  method: GET
  name: get-browser-version
  path: /v1/version
- description: List extension products
  method: GET
  name: list-products
  path: /v1/extensions
- description: Get extension details
  method: GET
  name: get-product
  path: /v1/extensions/{productId}
personas: []
provider_name: Microsoft Edge
provider_slug: microsoft-edge
search_terms:
- list all debuggable targets
- get submission status
- develops web applications and uses devtools for debugging
- developer tools
- upload package
- get protocol schema
- get the full devtools protocol schema definition
- Extension Developer
- create new browser target
- webview
- close target
- browser debugging and inspection
- get product
- extension products
- list extensions
- get extension details
- get upload status
- browser development
- list extension products
- open a new browser tab
- bring a browser tab to the foreground
- list all extension products in the edge add-ons store
- upload a new extension package
- close a browser tab
- Web Developer
- get extension
- chromium
- microsoft
- activate target
- get browser version info
- submit an extension for review and publishing
- unified browser development workflow combining debugging and extension management
- get microsoft edge browser version information
- extension lifecycle from development to publication
- microsoft edge
- QA Engineer
- progressive web apps
- open a new browser tab in microsoft edge
- check the status of an extension submission
- list all debuggable browser targets in microsoft edge
- list products
- create submission
- develops and publishes browser extensions for microsoft edge
- tests web applications and extensions using devtools automation
- browser
- list targets
- extensions
- get details of an extension product
- web development
- extension product detail
- debuggable browser targets
- get browser version
- check the status of a package upload
- debugging
- browser version
- edge
- create target
- automation
slug: browser-development
source_filename: browser-development.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Edge Browser Development\n  description: Unified workflow for Microsoft Edge browser development combining DevTools Protocol debugging with Add-ons\n    extension lifecycle management. Used by extension developers, web developers, and QA engineers.\n  tags:\n  - Microsoft Edge\n  - Browser Development\n  - Extensions\n  - Debugging\n  - Automation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    EDGE_DEVTOOLS_HOST: EDGE_DEVTOOLS_HOST\n    EDGE_ADDONS_API_TOKEN: EDGE_ADDONS_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: edge-devtools-api\n    baseUri: http://localhost:9222\n    description: HTTP endpoints for the Microsoft Edge DevTools Protocol based on the Chromium DevTools Protocol.\n    resources:\n    - name: targets\n      path: /json\n      description: Debuggable browser target management\n      operations:\n      - name: listTargets\n        method: GET\n\
  \        path: /list\n        description: Microsoft Edge List Debuggable Targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: createTarget\n        method: PUT\n        path: /new\n        description: Microsoft Edge Create New Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: activateTarget\n        method: POST\n        path: /activate/{targetId}\n        description: Microsoft Edge Activate Target\n        inputParameters:\n        - name: targetId\n          type: string\n          required: true\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n      - name: closeTarget\n        method: POST\n        path: /close/{targetId}\n        description: Microsoft Edge Close Target\n        inputParameters:\n        - name:\
  \ targetId\n          type: string\n          required: true\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: browser\n      path: /json\n      description: Browser information\n      operations:\n      - name: getBrowserVersion\n        method: GET\n        path: /version\n        description: Microsoft Edge Get Browser Version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getProtocolSchema\n        method: GET\n        path: /protocol\n        description: Microsoft Edge Get Protocol Schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: edge-addons-api\n    baseUri: https://api.addons.microsoftedge.microsoft.com\n    description: REST API for managing Microsoft Edge browser extensions through\
  \ the Partner Center.\n    authentication:\n      type: bearer\n      token: '{{EDGE_ADDONS_ACCESS_TOKEN}}'\n    resources:\n    - name: products\n      path: /v1/products\n      description: Extension product management\n      operations:\n      - name: listProducts\n        method: GET\n        description: Microsoft Edge List Products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getProduct\n        method: GET\n        path: /{productId}\n        description: Microsoft Edge Get Product\n        inputParameters:\n        - name: productId\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: submissions\n      path: /v1/products/{productId}/submissions\n      description: Extension submission management\n      operations:\n      - name: createSubmission\n\
  \        method: POST\n        description: Microsoft Edge Create Submission\n        inputParameters:\n        - name: productId\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getSubmission\n        method: GET\n        path: /{submissionId}\n        description: Microsoft Edge Get Submission Status\n        inputParameters:\n        - name: productId\n          type: string\n          required: true\n        - name: submissionId\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packages\n      path: /v1/products/{productId}/submissions/draft/package\n      description: Extension package upload\n      operations:\n      - name: uploadPackage\n        method: POST\n        description: Microsoft Edge Upload\
  \ Package\n        inputParameters:\n        - name: productId\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPackageUploadStatus\n        method: GET\n        path: /operations/{operationId}\n        description: Microsoft Edge Get Package Upload Status\n        inputParameters:\n        - name: productId\n          type: string\n          required: true\n        - name: operationId\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: browser-development-api\n    description: Unified REST API for Microsoft Edge browser development workflows.\n    resources:\n    - path: /v1/targets\n      name: targets\n      description: Debuggable browser targets\n      operations:\n\
  \      - method: GET\n        name: list-targets\n        description: List all debuggable targets\n        call: devtools-api.list-targets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/targets/new\n      name: new-target\n      description: Create new browser target\n      operations:\n      - method: PUT\n        name: create-target\n        description: Open a new browser tab\n        call: devtools-api.create-target\n        with:\n          url: rest.url\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/version\n      name: version\n      description: Browser version\n      operations:\n      - method: GET\n        name: get-browser-version\n        description: Get browser version info\n        call: devtools-api.get-browser-version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extensions\n      name: extensions\n      description: Extension products\n\
  \      operations:\n      - method: GET\n        name: list-products\n        description: List extension products\n        call: addons-api.list-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extensions/{productId}\n      name: extension-detail\n      description: Extension product detail\n      operations:\n      - method: GET\n        name: get-product\n        description: Get extension details\n        call: addons-api.get-product\n        with:\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: browser-development-mcp\n    transport: http\n    description: MCP server for AI-assisted Microsoft Edge browser development.\n    tools:\n    - name: list-targets\n      description: List all debuggable browser targets in Microsoft Edge\n      hints:\n        readOnly: true\n        openWorld: true\n      call: devtools-api.list-targets\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-target\n      description: Open a new browser tab in Microsoft Edge\n      hints:\n        readOnly: false\n      call: devtools-api.create-target\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-target\n      description: Bring a browser tab to the foreground\n      hints:\n        readOnly: false\n      call: devtools-api.activate-target\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: close-target\n      description: Close a browser tab\n      hints:\n        readOnly: false\n        destructive: true\n      call: devtools-api.close-target\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-browser-version\n      description: Get Microsoft Edge browser version information\n      hints:\n        readOnly: true\n        openWorld: true\n      call: devtools-api.get-browser-version\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-protocol-schema\n      description: Get the full DevTools Protocol schema definition\n      hints:\n        readOnly: true\n        openWorld: true\n      call: devtools-api.get-protocol-schema\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-extensions\n      description: List all extension products in the Edge Add-ons store\n      hints:\n        readOnly: true\n        openWorld: true\n      call: addons-api.list-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-extension\n      description: Get details of an extension product\n      hints:\n        readOnly: true\n        openWorld: true\n      call: addons-api.get-product\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-submission\n      description: Submit an extension for review and publishing\n      hints:\n        readOnly: false\n      call: addons-api.create-submission\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-submission-status\n      description: Check the status of an extension submission\n      hints:\n        readOnly: true\n        openWorld: true\n      call: addons-api.get-submission\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-package\n      description: Upload a new extension package\n      hints:\n        readOnly: false\n      call: addons-api.upload-package\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-upload-status\n      description: Check the status of a package upload\n      hints:\n        readOnly: true\n        openWorld: true\n      call: addons-api.get-upload-status\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-edge/refs/heads/main/capabilities/browser-development.yaml
tags:
- Microsoft Edge
- Browser Development
- Extensions
- Debugging
- Automation
tools:
- description: List all debuggable browser targets in Microsoft Edge
  hints:
    openWorld: true
    readOnly: true
  name: list-targets
- description: Open a new browser tab in Microsoft Edge
  hints:
    readOnly: false
  name: create-target
- description: Bring a browser tab to the foreground
  hints:
    readOnly: false
  name: activate-target
- description: Close a browser tab
  hints:
    destructive: true
    readOnly: false
  name: close-target
- description: Get Microsoft Edge browser version information
  hints:
    openWorld: true
    readOnly: true
  name: get-browser-version
- description: Get the full DevTools Protocol schema definition
  hints:
    openWorld: true
    readOnly: true
  name: get-protocol-schema
- description: List all extension products in the Edge Add-ons store
  hints:
    openWorld: true
    readOnly: true
  name: list-extensions
- description: Get details of an extension product
  hints:
    openWorld: true
    readOnly: true
  name: get-extension
- description: Submit an extension for review and publishing
  hints:
    readOnly: false
  name: create-submission
- description: Check the status of an extension submission
  hints:
    openWorld: true
    readOnly: true
  name: get-submission-status
- description: Upload a new extension package
  hints:
    readOnly: false
  name: upload-package
- description: Check the status of a package upload
  hints:
    openWorld: true
    readOnly: true
  name: get-upload-status
---
