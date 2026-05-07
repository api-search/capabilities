---
categories: []
consumed_apis: []
description: API for accessing and managing media assets, templates, and libraries within TechSmith Camtasia. Provides programmatic access to browse, search, download, and manage video assets, audio tracks, images, templates, themes, and other media resources used in Camtasia projects.
layout: capability
name: Camtasia Asset Library API
operations:
- description: Camtasia List assets
  method: GET
  name: listassets
  path: /assets
- description: Camtasia Upload an asset
  method: POST
  name: uploadasset
  path: /assets
- description: Camtasia Get an asset
  method: GET
  name: getasset
  path: /assets/{assetId}
- description: Camtasia Update an asset
  method: PUT
  name: updateasset
  path: /assets/{assetId}
- description: Camtasia Delete an asset
  method: DELETE
  name: deleteasset
  path: /assets/{assetId}
- description: Camtasia Download an asset file
  method: GET
  name: downloadasset
  path: /assets/{assetId}/download
- description: Camtasia Get asset preview
  method: GET
  name: getassetpreview
  path: /assets/{assetId}/preview
- description: Camtasia List templates
  method: GET
  name: listtemplates
  path: /templates
- description: Camtasia Get a template
  method: GET
  name: gettemplate
  path: /templates/{templateId}
- description: Camtasia Download a template
  method: GET
  name: downloadtemplate
  path: /templates/{templateId}/download
- description: Camtasia List libraries
  method: GET
  name: listlibraries
  path: /libraries
- description: Camtasia Get a library
  method: GET
  name: getlibrary
  path: /libraries/{libraryId}
- description: Camtasia List assets in a library
  method: GET
  name: listlibraryassets
  path: /libraries/{libraryId}/assets
- description: Camtasia List asset categories
  method: GET
  name: listcategories
  path: /categories
- description: Camtasia Get a category
  method: GET
  name: getcategory
  path: /categories/{categoryId}
personas: []
provider_name: Camtasia
provider_slug: camtasia
search_terms:
- camtasia update an asset
- camtasia list assets in a library
- video editing
- camtasia get an asset
- listcategories
- getlibrary
- tutorial creation
- sdk
- api
- deleteasset
- getcategory
- screen recording
- camtasia get a library
- uploadasset
- screencast
- camtasia list libraries
- camtasia list templates
- camtasia download a template
- oembed
- camtasia list asset categories
- downloadasset
- camtasia list assets
- e-learning
- camtasia
- updateasset
- listassets
- camtasia download an asset file
- downloadtemplate
- camtasia get a category
- camtasia upload an asset
- camtasia get asset preview
- listtemplates
- gettemplate
- camtasia delete an asset
- getasset
- camtasia get a template
- listlibraries
- getassetpreview
- listlibraryassets
slug: camtasia-capability
source_filename: camtasia-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Camtasia Asset Library API\n  description: API for accessing and managing media assets, templates, and libraries within TechSmith Camtasia. Provides programmatic\n    access to browse, search, download, and manage video assets, audio tracks, images, templates, themes, and other media\n    resources used in Camtasia projects.\n  tags:\n  - Camtasia\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: camtasia\n    baseUri: https://api.techsmith.com/camtasia/v1\n    description: Camtasia Asset Library API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CAMTASIA_TOKEN}}'\n    resources:\n    - name: assets\n      path: /assets\n      operations:\n      - name: listassets\n        method: GET\n        description: Camtasia List assets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: uploadasset\n        method: POST\n        description: Camtasia Upload an asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-assetid\n      path: /assets/{assetId}\n      operations:\n      - name: getasset\n        method: GET\n        description: Camtasia Get an asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateasset\n        method: PUT\n        description: Camtasia Update an asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteasset\n        method: DELETE\n        description: Camtasia Delete an asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-assetid-download\n\
  \      path: /assets/{assetId}/download\n      operations:\n      - name: downloadasset\n        method: GET\n        description: Camtasia Download an asset file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-assetid-preview\n      path: /assets/{assetId}/preview\n      operations:\n      - name: getassetpreview\n        method: GET\n        description: Camtasia Get asset preview\n        inputParameters:\n        - name: size\n          in: query\n          type: string\n          description: Preview size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates\n      path: /templates\n      operations:\n      - name: listtemplates\n        method: GET\n        description: Camtasia List templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: templates-templateid\n      path: /templates/{templateId}\n      operations:\n      - name: gettemplate\n        method: GET\n        description: Camtasia Get a template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-templateid-download\n      path: /templates/{templateId}/download\n      operations:\n      - name: downloadtemplate\n        method: GET\n        description: Camtasia Download a template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: libraries\n      path: /libraries\n      operations:\n      - name: listlibraries\n        method: GET\n        description: Camtasia List libraries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: libraries-libraryid\n\
  \      path: /libraries/{libraryId}\n      operations:\n      - name: getlibrary\n        method: GET\n        description: Camtasia Get a library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: libraries-libraryid-assets\n      path: /libraries/{libraryId}/assets\n      operations:\n      - name: listlibraryassets\n        method: GET\n        description: Camtasia List assets in a library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /categories\n      operations:\n      - name: listcategories\n        method: GET\n        description: Camtasia List asset categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories-categoryid\n      path: /categories/{categoryId}\n      operations:\n\
  \      - name: getcategory\n        method: GET\n        description: Camtasia Get a category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: camtasia-rest\n    description: REST adapter for Camtasia Asset Library API.\n    resources:\n    - path: /assets\n      name: listassets\n      operations:\n      - method: GET\n        name: listassets\n        description: Camtasia List assets\n        call: camtasia.listassets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets\n      name: uploadasset\n      operations:\n      - method: POST\n        name: uploadasset\n        description: Camtasia Upload an asset\n        call: camtasia.uploadasset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetId}\n      name: getasset\n      operations:\n      - method: GET\n\
  \        name: getasset\n        description: Camtasia Get an asset\n        call: camtasia.getasset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetId}\n      name: updateasset\n      operations:\n      - method: PUT\n        name: updateasset\n        description: Camtasia Update an asset\n        call: camtasia.updateasset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetId}\n      name: deleteasset\n      operations:\n      - method: DELETE\n        name: deleteasset\n        description: Camtasia Delete an asset\n        call: camtasia.deleteasset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetId}/download\n      name: downloadasset\n      operations:\n      - method: GET\n        name: downloadasset\n        description: Camtasia Download an asset file\n        call: camtasia.downloadasset\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /assets/{assetId}/preview\n      name: getassetpreview\n      operations:\n      - method: GET\n        name: getassetpreview\n        description: Camtasia Get asset preview\n        call: camtasia.getassetpreview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates\n      name: listtemplates\n      operations:\n      - method: GET\n        name: listtemplates\n        description: Camtasia List templates\n        call: camtasia.listtemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/{templateId}\n      name: gettemplate\n      operations:\n      - method: GET\n        name: gettemplate\n        description: Camtasia Get a template\n        call: camtasia.gettemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/{templateId}/download\n      name: downloadtemplate\n      operations:\n\
  \      - method: GET\n        name: downloadtemplate\n        description: Camtasia Download a template\n        call: camtasia.downloadtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries\n      name: listlibraries\n      operations:\n      - method: GET\n        name: listlibraries\n        description: Camtasia List libraries\n        call: camtasia.listlibraries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries/{libraryId}\n      name: getlibrary\n      operations:\n      - method: GET\n        name: getlibrary\n        description: Camtasia Get a library\n        call: camtasia.getlibrary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries/{libraryId}/assets\n      name: listlibraryassets\n      operations:\n      - method: GET\n        name: listlibraryassets\n        description: Camtasia List assets in a library\n        call: camtasia.listlibraryassets\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories\n      name: listcategories\n      operations:\n      - method: GET\n        name: listcategories\n        description: Camtasia List asset categories\n        call: camtasia.listcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{categoryId}\n      name: getcategory\n      operations:\n      - method: GET\n        name: getcategory\n        description: Camtasia Get a category\n        call: camtasia.getcategory\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: camtasia-mcp\n    transport: http\n    description: MCP adapter for Camtasia Asset Library API for AI agent use.\n    tools:\n    - name: listassets\n      description: Camtasia List assets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.listassets\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadasset\n      description: Camtasia Upload an asset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: camtasia.uploadasset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getasset\n      description: Camtasia Get an asset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.getasset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateasset\n      description: Camtasia Update an asset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: camtasia.updateasset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteasset\n      description: Camtasia Delete an asset\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: camtasia.deleteasset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloadasset\n      description: Camtasia Download an asset file\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.downloadasset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getassetpreview\n      description: Camtasia Get asset preview\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.getassetpreview\n      with:\n        size: tools.size\n      inputParameters:\n      - name: size\n        type: string\n        description: Preview size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtemplates\n      description: Camtasia List templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.listtemplates\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettemplate\n      description: Camtasia Get a template\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.gettemplate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloadtemplate\n      description: Camtasia Download a template\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.downloadtemplate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlibraries\n      description: Camtasia List libraries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.listlibraries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlibrary\n      description: Camtasia Get a library\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: camtasia.getlibrary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlibraryassets\n      description: Camtasia List assets in a library\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.listlibraryassets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcategories\n      description: Camtasia List asset categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.listcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategory\n      description: Camtasia Get a category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: camtasia.getcategory\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CAMTASIA_TOKEN:\
  \ CAMTASIA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/camtasia/refs/heads/main/capabilities/camtasia-capability.yaml
tags:
- Camtasia
- API
tools:
- description: Camtasia List assets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassets
- description: Camtasia Upload an asset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadasset
- description: Camtasia Get an asset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getasset
- description: Camtasia Update an asset
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateasset
- description: Camtasia Delete an asset
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteasset
- description: Camtasia Download an asset file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadasset
- description: Camtasia Get asset preview
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getassetpreview
- description: Camtasia List templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtemplates
- description: Camtasia Get a template
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettemplate
- description: Camtasia Download a template
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadtemplate
- description: Camtasia List libraries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlibraries
- description: Camtasia Get a library
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlibrary
- description: Camtasia List assets in a library
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlibraryassets
- description: Camtasia List asset categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcategories
- description: Camtasia Get a category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategory
---
