---
consumed_apis:
- cc-libraries
description: Workflow capability for managing shared Creative Cloud Libraries and design assets for use in Adobe Premiere Pro video editing projects. Designed for video production teams and media asset managers.
layout: capability
name: Adobe Premiere Creative Asset Management
operations:
- description: List all Creative Cloud Libraries.
  method: GET
  name: list-libraries
  path: /v1/libraries
- description: Create a new Creative Cloud Library.
  method: POST
  name: create-library
  path: /v1/libraries
- description: List elements in a library.
  method: GET
  name: list-elements
  path: /v1/libraries/{libraryId}/elements
- description: Add an element to a library.
  method: POST
  name: add-element
  path: /v1/libraries/{libraryId}/elements
personas: []
provider_name: Adobe Premiere Pro
provider_slug: adobe-premiere
search_terms:
- list library elements
- add library element
- add element
- media
- asset management
- video production
- create a new creative cloud library.
- Video Producer
- Media Asset Manager
- creative cloud
- create library
- create a new creative cloud library for organizing video production brand assets.
- premiere pro plugin and extension ecosystem.
- list all creative cloud libraries available for use in adobe premiere pro projects.
- adobe premiere
- premiere pro
- list design elements (colors, graphics, fonts, patterns, videos) within a creative cloud library.
- video editing
- adobe
- list elements in a library.
- list all creative cloud libraries.
- manager responsible for organizing shared brand assets in creative cloud.
- add an element to a library.
- video editor and producer using adobe premiere pro for content creation.
- elements within a creative cloud library.
- manage creative cloud libraries and assets for premiere pro video production.
- automation
- list libraries
- list elements
- add a new design element to a creative cloud library for sharing with the premiere pro team.
- creative cloud libraries for shared production assets.
slug: creative-asset-management
tags:
- Adobe Premiere
- Creative Cloud
- Asset Management
- Video Production
- Media
tools:
- description: List all Creative Cloud Libraries available for use in Adobe Premiere Pro projects.
  hints:
    openWorld: true
    readOnly: true
  name: list-libraries
- description: Create a new Creative Cloud Library for organizing video production brand assets.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-library
- description: List design elements (colors, graphics, fonts, patterns, videos) within a Creative Cloud Library.
  hints:
    openWorld: true
    readOnly: true
  name: list-library-elements
- description: Add a new design element to a Creative Cloud Library for sharing with the Premiere Pro team.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-library-element
---
