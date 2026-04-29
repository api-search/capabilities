---
categories: []
consumed_apis:
- devtools-api
- addons-api
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
- get the full devtools protocol schema definition
- extension products
- microsoft edge
- list products
- develops and publishes browser extensions for microsoft edge
- develops web applications and uses devtools for debugging
- browser version
- list targets
- automation
- bring a browser tab to the foreground
- list all debuggable targets
- get protocol schema
- developer tools
- Extension Developer
- list all extension products in the edge add-ons store
- list extensions
- list extension products
- submit an extension for review and publishing
- webview
- open a new browser tab
- browser
- activate target
- list all debuggable browser targets in microsoft edge
- get microsoft edge browser version information
- upload package
- get extension details
- extension product detail
- check the status of an extension submission
- Web Developer
- microsoft
- get browser version
- open a new browser tab in microsoft edge
- create submission
- extension lifecycle from development to publication
- web development
- get details of an extension product
- close target
- QA Engineer
- chromium
- debuggable browser targets
- browser development
- extensions
- create new browser target
- debugging
- get browser version info
- get product
- get submission status
- check the status of a package upload
- get upload status
- get extension
- close a browser tab
- upload a new extension package
- unified browser development workflow combining debugging and extension management
- tests web applications and extensions using devtools automation
- progressive web apps
- browser debugging and inspection
- create target
- edge
slug: browser-development
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Edge Browser Development\"\n  description: \"Unified workflow for Microsoft Edge browser development combining DevTools Protocol debugging with Add-ons extension lifecycle management. Used by extension developers, web developers, and QA engineers.\"\n  tags:\n    - Microsoft Edge\n    - Browser Development\n    - Extensions\n    - Debugging\n    - Automation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      EDGE_DEVTOOLS_HOST: EDGE_DEVTOOLS_HOST\n      EDGE_ADDONS_API_TOKEN: EDGE_ADDONS_API_TOKEN\n\ncapability:\n  consumes:\n    - import: devtools-api\n      location: ./shared/devtools-api.yaml\n    - import: addons-api\n      location: ./shared/addons-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: browser-development-api\n      description: \"Unified REST API for Microsoft Edge browser development workflows.\"\n      resources:\n     \
  \   - path: /v1/targets\n          name: targets\n          description: \"Debuggable browser targets\"\n          operations:\n            - method: GET\n              name: list-targets\n              description: \"List all debuggable targets\"\n              call: \"devtools-api.list-targets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/targets/new\n          name: new-target\n          description: \"Create new browser target\"\n          operations:\n            - method: PUT\n              name: create-target\n              description: \"Open a new browser tab\"\n              call: \"devtools-api.create-target\"\n              with:\n                url: \"rest.url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/version\n          name: version\n          description: \"Browser version\"\n          operations:\n            - method:\
  \ GET\n              name: get-browser-version\n              description: \"Get browser version info\"\n              call: \"devtools-api.get-browser-version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/extensions\n          name: extensions\n          description: \"Extension products\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List extension products\"\n              call: \"addons-api.list-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/extensions/{productId}\n          name: extension-detail\n          description: \"Extension product detail\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get extension details\"\n              call: \"addons-api.get-product\"\n              with:\n \
  \               productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: browser-development-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Microsoft Edge browser development.\"\n      tools:\n        - name: list-targets\n          description: \"List all debuggable browser targets in Microsoft Edge\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"devtools-api.list-targets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-target\n          description: \"Open a new browser tab in Microsoft Edge\"\n          hints:\n            readOnly: false\n          call: \"devtools-api.create-target\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: activate-target\n          description:\
  \ \"Bring a browser tab to the foreground\"\n          hints:\n            readOnly: false\n          call: \"devtools-api.activate-target\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: close-target\n          description: \"Close a browser tab\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"devtools-api.close-target\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-browser-version\n          description: \"Get Microsoft Edge browser version information\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"devtools-api.get-browser-version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-protocol-schema\n          description: \"Get the full DevTools Protocol schema definition\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"devtools-api.get-protocol-schema\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-extensions\n          description: \"List all extension products in the Edge Add-ons store\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"addons-api.list-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-extension\n          description: \"Get details of an extension product\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"addons-api.get-product\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-submission\n          description: \"Submit an extension for review and publishing\"\n          hints:\n            readOnly: false\n          call: \"addons-api.create-submission\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-submission-status\n          description: \"Check the status of an extension submission\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"addons-api.get-submission\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: upload-package\n          description: \"Upload a new extension package\"\n          hints:\n            readOnly: false\n          call: \"addons-api.upload-package\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-upload-status\n          description: \"Check the status of a package upload\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"addons-api.get-upload-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
