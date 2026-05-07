---
categories: []
consumed_apis: []
description: Unified design management workflow combining design creation, asset management, brand templates, autofill, exports, and collaboration for marketing teams and content creators.
layout: capability
name: Canva Design Management
operations:
- description: List designs.
  method: GET
  name: list-designs
  path: /v1/designs
- description: Create a design.
  method: POST
  name: create-design
  path: /v1/designs
- description: Get an asset.
  method: GET
  name: get-asset
  path: /v1/assets
- description: Delete an asset.
  method: DELETE
  name: delete-asset
  path: /v1/assets
- description: Export a design.
  method: POST
  name: create-export-job
  path: /v1/exports
- description: List brand templates.
  method: GET
  name: list-brand-templates
  path: /v1/brand-templates
- description: Create autofill job.
  method: POST
  name: create-autofill-job
  path: /v1/autofills
personas: []
provider_name: Canva
provider_slug: canva
search_terms:
- list brand templates.
- create a new canva design.
- get brand template
- get export job status and download url.
- automation
- get folder
- canva
- create autofill job
- get brand template dataset
- get an asset by id.
- create a comment on a design.
- create resize job
- asset management.
- get autofill job
- get a folder by id.
- visual content
- design creation and management.
- list folder items
- delete an asset.
- get a specific design by id.
- design
- graphics
- list brand templates
- brand management
- get export job
- collaboration
- get resize job status.
- get a brand template by id.
- brand template access.
- get an asset.
- create comment
- get design
- list available brand templates.
- create a design from a brand template using autofill data.
- templates
- apps
- get autofill job status.
- list designs
- list canva designs accessible to the user.
- export a design to pdf, png, jpg, gif, pptx, or mp4.
- get resize job
- print
- upload asset
- create design
- get the authenticated user profile.
- create a design.
- get users me
- resize a design to different dimensions or preset types.
- get the autofill dataset for a brand template.
- marketing
- list designs.
- get asset
- create autofill job.
- content creation
- design exports.
- upload an asset to canva.
- list items in a folder.
- design autofill.
- delete asset
- create export job
- export a design.
slug: design-management
source_filename: design-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Canva Design Management\n  description: Unified design management workflow combining design creation, asset management, brand templates, autofill,\n    exports, and collaboration for marketing teams and content creators.\n  tags:\n  - Canva\n  - Design\n  - Marketing\n  - Brand Management\n  - Content Creation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CANVA_ACCESS_TOKEN: CANVA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: connect-api\n    baseUri: https://api.canva.com/rest/v1\n    description: Canva Connect API for design management, assets, exports, and collaboration.\n    authentication:\n      type: bearer\n      token: '{{CANVA_ACCESS_TOKEN}}'\n    resources:\n    - name: designs\n      path: /designs\n      description: Create and manage designs.\n      operations:\n      - name: list-designs\n        method: GET\n        description: List designs accessible\
  \ to the authenticated user.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search term to filter designs.\n        - name: ownership\n          in: query\n          type: string\n          required: false\n          description: Filter by ownership (any, owned, shared).\n        - name: sort_by\n          in: query\n          type: string\n          required: false\n          description: Sort field.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-design\n        method: POST\n        description: Create a new Canva design.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            design_type: '{{tools.design_type}}'\n            title: '{{tools.title}}'\n\
  \      - name: get-design\n        method: GET\n        description: Get a specific design by ID.\n        inputParameters:\n        - name: designId\n          in: path\n          type: string\n          required: true\n          description: Design ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /assets\n      description: Manage design assets.\n      operations:\n      - name: get-asset\n        method: GET\n        description: Get an asset by ID.\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: Asset ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-asset\n        method: DELETE\n        description: Delete an asset.\n        inputParameters:\n        - name: assetId\n  \
  \        in: path\n          type: string\n          required: true\n          description: Asset ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-asset-upload-job\n        method: POST\n        description: Upload an asset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: get-asset-upload-job\n        method: GET\n        description: Get asset upload job status.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: folders\n      path: /folders\n      description: Manage\
  \ folders.\n      operations:\n      - name: get-folder\n        method: GET\n        description: Get a folder by ID.\n        inputParameters:\n        - name: folderId\n          in: path\n          type: string\n          required: true\n          description: Folder ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-folder-items\n        method: GET\n        description: List items in a folder.\n        inputParameters:\n        - name: folderId\n          in: path\n          type: string\n          required: true\n          description: Folder ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: move-folder-item\n        method: POST\n        description: Move an item to a folder.\n        inputParameters:\n        - name: folderId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Target folder ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exports\n      path: /exports\n      description: Export designs.\n      operations:\n      - name: create-export-job\n        method: POST\n        description: Create a design export job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            design_id: '{{tools.design_id}}'\n            format: '{{tools.format}}'\n      - name: get-export-job\n        method: GET\n        description: Get export job status.\n        inputParameters:\n        - name: exportId\n          in: path\n          type: string\n          required: true\n          description: Export job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: comments\n      path: /designs/{designId}/comments\n      description: Manage design comments.\n      operations:\n      - name: create-comment\n        method: POST\n        description: Create a comment on a design.\n        inputParameters:\n        - name: designId\n          in: path\n          type: string\n          required: true\n          description: Design ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n      - name: create-reply\n        method: POST\n        description: Reply to a comment.\n        inputParameters:\n        - name: designId\n          in: path\n          type: string\n          required: true\n          description: Design ID.\n        - name: commentId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Comment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n    - name: users\n      path: /users\n      description: User information.\n      operations:\n      - name: get-users-me\n        method: GET\n        description: Get the authenticated user profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: brand-templates\n      path: /brand-templates\n      description: Access brand templates.\n      operations:\n      - name: list-brand-templates\n        method: GET\n        description: List brand templates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-brand-template\n        method: GET\n        description: Get a\
  \ brand template by ID.\n        inputParameters:\n        - name: brandTemplateId\n          in: path\n          type: string\n          required: true\n          description: Brand template ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-brand-template-dataset\n        method: GET\n        description: Get the autofill dataset for a brand template.\n        inputParameters:\n        - name: brandTemplateId\n          in: path\n          type: string\n          required: true\n          description: Brand template ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autofills\n      path: /autofills\n      description: Autofill designs from templates.\n      operations:\n      - name: create-autofill-job\n        method: POST\n        description: Create a design autofill job from a brand template.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            brand_template_id: '{{tools.brand_template_id}}'\n            data: '{{tools.data}}'\n            title: '{{tools.title}}'\n      - name: get-autofill-job\n        method: GET\n        description: Get autofill job status.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Autofill job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resizes\n      path: /resizes\n      description: Resize designs.\n      operations:\n      - name: create-resize-job\n        method: POST\n        description: Create a design resize job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n        body:\n          type: json\n          data:\n            design_id: '{{tools.design_id}}'\n            resize_type: '{{tools.resize_type}}'\n      - name: get-resize-job\n        method: GET\n        description: Get resize job status.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Resize job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: design-management-api\n    description: Unified REST API for Canva design management.\n    resources:\n    - path: /v1/designs\n      name: designs\n      description: Design creation and management.\n      operations:\n      - method: GET\n        name: list-designs\n        description: List designs.\n        call: connect-api.list-designs\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-design\n        description: Create a design.\n        call: connect-api.create-design\n        with:\n          design_type: rest.design_type\n          title: rest.title\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Asset management.\n      operations:\n      - method: GET\n        name: get-asset\n        description: Get an asset.\n        call: connect-api.get-asset\n        with:\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-asset\n        description: Delete an asset.\n        call: connect-api.delete-asset\n        with:\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/exports\n      name: exports\n      description: Design\
  \ exports.\n      operations:\n      - method: POST\n        name: create-export-job\n        description: Export a design.\n        call: connect-api.create-export-job\n        with:\n          design_id: rest.design_id\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/brand-templates\n      name: brand-templates\n      description: Brand template access.\n      operations:\n      - method: GET\n        name: list-brand-templates\n        description: List brand templates.\n        call: connect-api.list-brand-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/autofills\n      name: autofills\n      description: Design autofill.\n      operations:\n      - method: POST\n        name: create-autofill-job\n        description: Create autofill job.\n        call: connect-api.create-autofill-job\n        with:\n          brand_template_id: rest.brand_template_id\n    \
  \      data: rest.data\n          title: rest.title\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: design-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Canva design management, brand templates, and content creation.\n    tools:\n    - name: list-designs\n      description: List Canva designs accessible to the user.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect-api.list-designs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-design\n      description: Create a new Canva design.\n      hints:\n        readOnly: false\n      call: connect-api.create-design\n      with:\n        design_type: tools.design_type\n        title: tools.title\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-design\n      description: Get a specific design by ID.\n      hints:\n        readOnly:\
  \ true\n      call: connect-api.get-design\n      with:\n        designId: tools.designId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description: Get an asset by ID.\n      hints:\n        readOnly: true\n      call: connect-api.get-asset\n      with:\n        assetId: tools.assetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-asset\n      description: Delete an asset.\n      hints:\n        readOnly: false\n        destructive: true\n      call: connect-api.delete-asset\n      with:\n        assetId: tools.assetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-asset\n      description: Upload an asset to Canva.\n      hints:\n        readOnly: false\n      call: connect-api.create-asset-upload-job\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-folder\n      description: Get\
  \ a folder by ID.\n      hints:\n        readOnly: true\n      call: connect-api.get-folder\n      with:\n        folderId: tools.folderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-folder-items\n      description: List items in a folder.\n      hints:\n        readOnly: true\n      call: connect-api.list-folder-items\n      with:\n        folderId: tools.folderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-export-job\n      description: Export a design to PDF, PNG, JPG, GIF, PPTX, or MP4.\n      hints:\n        readOnly: false\n      call: connect-api.create-export-job\n      with:\n        design_id: tools.design_id\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-export-job\n      description: Get export job status and download URL.\n      hints:\n        readOnly: true\n      call: connect-api.get-export-job\n      with:\n        exportId:\
  \ tools.exportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-comment\n      description: Create a comment on a design.\n      hints:\n        readOnly: false\n      call: connect-api.create-comment\n      with:\n        designId: tools.designId\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-users-me\n      description: Get the authenticated user profile.\n      hints:\n        readOnly: true\n      call: connect-api.get-users-me\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-brand-templates\n      description: List available brand templates.\n      hints:\n        readOnly: true\n      call: connect-api.list-brand-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-brand-template\n      description: Get a brand template by ID.\n      hints:\n        readOnly: true\n      call: connect-api.get-brand-template\n\
  \      with:\n        brandTemplateId: tools.brandTemplateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-brand-template-dataset\n      description: Get the autofill dataset for a brand template.\n      hints:\n        readOnly: true\n      call: connect-api.get-brand-template-dataset\n      with:\n        brandTemplateId: tools.brandTemplateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-autofill-job\n      description: Create a design from a brand template using autofill data.\n      hints:\n        readOnly: false\n      call: connect-api.create-autofill-job\n      with:\n        brand_template_id: tools.brand_template_id\n        data: tools.data\n        title: tools.title\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-autofill-job\n      description: Get autofill job status.\n      hints:\n        readOnly: true\n      call: connect-api.get-autofill-job\n     \
  \ with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-resize-job\n      description: Resize a design to different dimensions or preset types.\n      hints:\n        readOnly: false\n      call: connect-api.create-resize-job\n      with:\n        design_id: tools.design_id\n        resize_type: tools.resize_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-resize-job\n      description: Get resize job status.\n      hints:\n        readOnly: true\n      call: connect-api.get-resize-job\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/canva/refs/heads/main/capabilities/design-management.yaml
tags:
- Canva
- Design
- Marketing
- Brand Management
- Content Creation
tools:
- description: List Canva designs accessible to the user.
  hints:
    openWorld: true
    readOnly: true
  name: list-designs
- description: Create a new Canva design.
  hints:
    readOnly: false
  name: create-design
- description: Get a specific design by ID.
  hints:
    readOnly: true
  name: get-design
- description: Get an asset by ID.
  hints:
    readOnly: true
  name: get-asset
- description: Delete an asset.
  hints:
    destructive: true
    readOnly: false
  name: delete-asset
- description: Upload an asset to Canva.
  hints:
    readOnly: false
  name: upload-asset
- description: Get a folder by ID.
  hints:
    readOnly: true
  name: get-folder
- description: List items in a folder.
  hints:
    readOnly: true
  name: list-folder-items
- description: Export a design to PDF, PNG, JPG, GIF, PPTX, or MP4.
  hints:
    readOnly: false
  name: create-export-job
- description: Get export job status and download URL.
  hints:
    readOnly: true
  name: get-export-job
- description: Create a comment on a design.
  hints:
    readOnly: false
  name: create-comment
- description: Get the authenticated user profile.
  hints:
    readOnly: true
  name: get-users-me
- description: List available brand templates.
  hints:
    readOnly: true
  name: list-brand-templates
- description: Get a brand template by ID.
  hints:
    readOnly: true
  name: get-brand-template
- description: Get the autofill dataset for a brand template.
  hints:
    readOnly: true
  name: get-brand-template-dataset
- description: Create a design from a brand template using autofill data.
  hints:
    readOnly: false
  name: create-autofill-job
- description: Get autofill job status.
  hints:
    readOnly: true
  name: get-autofill-job
- description: Resize a design to different dimensions or preset types.
  hints:
    readOnly: false
  name: create-resize-job
- description: Get resize job status.
  hints:
    readOnly: true
  name: get-resize-job
---
