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
- adobe
- automation
- elements within a creative cloud library.
- list elements in a library.
- list elements
- manage creative cloud libraries and assets for premiere pro video production.
- list library elements
- list libraries
- list design elements (colors, graphics, fonts, patterns, videos) within a creative cloud library.
- creative cloud libraries for shared production assets.
- add library element
- list all creative cloud libraries available for use in adobe premiere pro projects.
- create a new creative cloud library.
- premiere pro
- create library
- creative cloud
- list all creative cloud libraries.
- create a new creative cloud library for organizing video production brand assets.
- manager responsible for organizing shared brand assets in creative cloud.
- Video Producer
- asset management
- add element
- add a new design element to a creative cloud library for sharing with the premiere pro team.
- video editor and producer using adobe premiere pro for content creation.
- Media Asset Manager
- add an element to a library.
- video editing
- media
- premiere pro plugin and extension ecosystem.
- adobe premiere
- video production
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
