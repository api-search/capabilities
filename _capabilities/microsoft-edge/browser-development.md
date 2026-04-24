---
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
- tests web applications and extensions using devtools automation
- upload package
- Extension Developer
- microsoft edge
- browser
- get browser version info
- get submission status
- open a new browser tab in microsoft edge
- debugging
- chromium
- browser development
- get the full devtools protocol schema definition
- unified browser development workflow combining debugging and extension management
- activate target
- list extension products
- submit an extension for review and publishing
- check the status of a package upload
- webview
- get browser version
- browser version
- Web Developer
- web development
- extension products
- develops web applications and uses devtools for debugging
- check the status of an extension submission
- get upload status
- list all extension products in the edge add-ons store
- list all debuggable browser targets in microsoft edge
- list targets
- create target
- extensions
- get product
- open a new browser tab
- get extension
- automation
- list all debuggable targets
- edge
- get microsoft edge browser version information
- developer tools
- create submission
- get protocol schema
- list products
- bring a browser tab to the foreground
- get extension details
- progressive web apps
- microsoft
- get details of an extension product
- close target
- develops and publishes browser extensions for microsoft edge
- browser debugging and inspection
- extension lifecycle from development to publication
- create new browser target
- upload a new extension package
- QA Engineer
- list extensions
- extension product detail
- debuggable browser targets
- close a browser tab
slug: browser-development
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
