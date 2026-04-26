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
- get submission status
- browser debugging and inspection
- extensions
- get browser version info
- check the status of an extension submission
- list all debuggable browser targets in microsoft edge
- list extensions
- list all extension products in the edge add-ons store
- browser
- microsoft edge
- check the status of a package upload
- list targets
- submit an extension for review and publishing
- create submission
- get extension
- get the full devtools protocol schema definition
- webview
- debuggable browser targets
- get details of an extension product
- browser development
- create target
- get extension details
- edge
- list products
- progressive web apps
- extension products
- open a new browser tab in microsoft edge
- chromium
- upload a new extension package
- debugging
- list all debuggable targets
- browser version
- bring a browser tab to the foreground
- unified browser development workflow combining debugging and extension management
- develops and publishes browser extensions for microsoft edge
- upload package
- microsoft
- open a new browser tab
- Web Developer
- extension product detail
- get upload status
- tests web applications and extensions using devtools automation
- close a browser tab
- get browser version
- extension lifecycle from development to publication
- web development
- close target
- QA Engineer
- get product
- get microsoft edge browser version information
- list extension products
- develops web applications and uses devtools for debugging
- get protocol schema
- developer tools
- create new browser target
- activate target
- Extension Developer
- automation
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
