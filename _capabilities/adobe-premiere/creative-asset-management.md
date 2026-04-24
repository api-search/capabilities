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
- Media Asset Manager
- list libraries
- add library element
- create library
- add element
- list all creative cloud libraries.
- list all creative cloud libraries available for use in adobe premiere pro projects.
- video production
- premiere pro plugin and extension ecosystem.
- elements within a creative cloud library.
- create a new creative cloud library for organizing video production brand assets.
- Video Producer
- list elements in a library.
- automation
- add an element to a library.
- media
- list design elements (colors, graphics, fonts, patterns, videos) within a creative cloud library.
- manager responsible for organizing shared brand assets in creative cloud.
- list library elements
- video editing
- creative cloud libraries for shared production assets.
- create a new creative cloud library.
- manage creative cloud libraries and assets for premiere pro video production.
- asset management
- adobe
- adobe premiere
- add a new design element to a creative cloud library for sharing with the premiere pro team.
- premiere pro
- list elements
- creative cloud
- video editor and producer using adobe premiere pro for content creation.
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
