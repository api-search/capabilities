---
categories: []
consumed_apis: []
description: A cloud-based REST API that provides programmatic access to Photoshop's image editing capabilities without requiring a local installation. Part of Adobe Firefly Services, the API supports PSD document operations including layer editing, Smart Object replacement, text layer editing, rendition creation, and artboard management. It also provides AI-powered features such as background removal, mask creation, product crop, and depth blur. All operations are asynchronous, returning a polling URL to check job status.
layout: capability
name: Adobe Photoshop API
operations:
- description: Adobe Photoshop Remove Background from an Image
  method: POST
  name: removebackgroundv2
  path: /v2/remove-background
- description: Adobe Photoshop Fill Masked Areas with Generative AI
  method: POST
  name: fillmaskedareas
  path: /v1/fill-masked-areas
- description: Adobe Photoshop Get PSD Document Manifest
  method: POST
  name: getdocumentmanifest
  path: /pie/psdService/documentManifest
- description: Adobe Photoshop Edit a PSD Document
  method: POST
  name: modifydocument
  path: /pie/psdService/documentOperations
- description: Adobe Photoshop Create a New PSD Document
  method: POST
  name: createdocument
  path: /pie/psdService/documentCreate
- description: Adobe Photoshop Create Image Renditions from a PSD
  method: POST
  name: createrendition
  path: /pie/psdService/renditionCreate
- description: Adobe Photoshop Replace Smart Object Content
  method: POST
  name: replacesmartobject
  path: /pie/psdService/smartObject
- description: Adobe Photoshop Edit Text Layers in a PSD
  method: POST
  name: edittextlayer
  path: /pie/psdService/text
- description: Adobe Photoshop Execute Photoshop Action Files
  method: POST
  name: playphotoshopactions
  path: /pie/psdService/photoshopActions
- description: Adobe Photoshop Execute Photoshop Actions via JSON Descriptors
  method: POST
  name: playactionjson
  path: /pie/psdService/actionJSON
- description: Adobe Photoshop Create Documents Using Action JSON Descriptors
  method: POST
  name: createwithactionjson
  path: /pie/psdService/actionJsonCreate
- description: Adobe Photoshop Smart Crop to Product Subject
  method: POST
  name: productcrop
  path: /pie/psdService/productCrop
- description: Adobe Photoshop Apply Depth Blur Effect
  method: POST
  name: depthblur
  path: /pie/psdService/depthBlur
- description: Adobe Photoshop Create Artboards from PSD Inputs
  method: POST
  name: createartboard
  path: /pie/psdService/artboardCreate
- description: Adobe Photoshop Get PSD Service Job Status
  method: GET
  name: getpsdjobstatus
  path: /pie/psdService/status/{jobId}
- description: Adobe Photoshop Get Sensei Service Job Status
  method: GET
  name: getsenseijobstatus
  path: /sensei/status/{jobId}
- description: Adobe Photoshop Service Health Check
  method: GET
  name: healthcheck
  path: /pie/psdService/hello
personas: []
provider_name: Adobe Photoshop
provider_slug: adobe-photoshop
search_terms:
- adobe photoshop execute photoshop action files
- playactionjson
- adobe photoshop edit a psd document
- createartboard
- photoshop
- adobe photoshop remove background from an image
- playphotoshopactions
- adobe photoshop create image renditions from a psd
- api
- createwithactionjson
- adobe photoshop edit text layers in a psd
- adobe photoshop execute photoshop actions via json descriptors
- depthblur
- replacesmartobject
- adobe photoshop apply depth blur effect
- fillmaskedareas
- plugins
- removebackgroundv2
- createrendition
- createdocument
- scripting
- adobe photoshop create documents using action json descriptors
- adobe photoshop get sensei service job status
- modifydocument
- adobe photoshop create artboards from psd inputs
- edittextlayer
- adobe photoshop replace smart object content
- productcrop
- adobe photoshop smart crop to product subject
- healthcheck
- adobe photoshop get psd service job status
- adobe photoshop service health check
- image editing
- getpsdjobstatus
- ai/ml
- rest api
- adobe photoshop fill masked areas with generative ai
- getdocumentmanifest
- adobe photoshop create a new psd document
- adobe
- getsenseijobstatus
- creative cloud
- adobe photoshop get psd document manifest
slug: adobe-photoshop-capability
source_filename: adobe-photoshop-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Photoshop API\n  description: A cloud-based REST API that provides programmatic access to Photoshop's image editing capabilities without\n    requiring a local installation. Part of Adobe Firefly Services, the API supports PSD document operations including layer\n    editing, Smart Object replacement, text layer editing, rendition creation, and artboard management. It also provides AI-powered\n    features such as background removal, mask creation, product crop, and depth blur. All operations are asynchronous, returning\n    a polling URL to check job status.\n  tags:\n  - Adobe\n  - Photoshop\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: adobe-photoshop\n    baseUri: https://image.adobe.io\n    description: Adobe Photoshop API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ADOBE_PHOTOSHOP_TOKEN}}'\n    resources:\n    - name: v2-remove-background\n\
  \      path: /v2/remove-background\n      operations:\n      - name: removebackgroundv2\n        method: POST\n        description: Adobe Photoshop Remove Background from an Image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-fill-masked-areas\n      path: /v1/fill-masked-areas\n      operations:\n      - name: fillmaskedareas\n        method: POST\n        description: Adobe Photoshop Fill Masked Areas with Generative AI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-documentmanifest\n      path: /pie/psdService/documentManifest\n      operations:\n      - name: getdocumentmanifest\n        method: POST\n        description: Adobe Photoshop Get PSD Document Manifest\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: pie-psdservice-documentoperations\n      path: /pie/psdService/documentOperations\n      operations:\n      - name: modifydocument\n        method: POST\n        description: Adobe Photoshop Edit a PSD Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-documentcreate\n      path: /pie/psdService/documentCreate\n      operations:\n      - name: createdocument\n        method: POST\n        description: Adobe Photoshop Create a New PSD Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-renditioncreate\n      path: /pie/psdService/renditionCreate\n      operations:\n      - name: createrendition\n        method: POST\n        description: Adobe Photoshop Create Image Renditions from a PSD\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-smartobject\n      path: /pie/psdService/smartObject\n      operations:\n      - name: replacesmartobject\n        method: POST\n        description: Adobe Photoshop Replace Smart Object Content\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-text\n      path: /pie/psdService/text\n      operations:\n      - name: edittextlayer\n        method: POST\n        description: Adobe Photoshop Edit Text Layers in a PSD\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-photoshopactions\n      path: /pie/psdService/photoshopActions\n      operations:\n      - name: playphotoshopactions\n        method: POST\n        description: Adobe Photoshop Execute Photoshop Action Files\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-actionjson\n      path: /pie/psdService/actionJSON\n      operations:\n      - name: playactionjson\n        method: POST\n        description: Adobe Photoshop Execute Photoshop Actions via JSON Descriptors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-actionjsoncreate\n      path: /pie/psdService/actionJsonCreate\n      operations:\n      - name: createwithactionjson\n        method: POST\n        description: Adobe Photoshop Create Documents Using Action JSON Descriptors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-productcrop\n      path: /pie/psdService/productCrop\n      operations:\n      - name: productcrop\n        method: POST\n    \
  \    description: Adobe Photoshop Smart Crop to Product Subject\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-depthblur\n      path: /pie/psdService/depthBlur\n      operations:\n      - name: depthblur\n        method: POST\n        description: Adobe Photoshop Apply Depth Blur Effect\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-artboardcreate\n      path: /pie/psdService/artboardCreate\n      operations:\n      - name: createartboard\n        method: POST\n        description: Adobe Photoshop Create Artboards from PSD Inputs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-status-jobid\n      path: /pie/psdService/status/{jobId}\n      operations:\n      - name: getpsdjobstatus\n\
  \        method: GET\n        description: Adobe Photoshop Get PSD Service Job Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sensei-status-jobid\n      path: /sensei/status/{jobId}\n      operations:\n      - name: getsenseijobstatus\n        method: GET\n        description: Adobe Photoshop Get Sensei Service Job Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pie-psdservice-hello\n      path: /pie/psdService/hello\n      operations:\n      - name: healthcheck\n        method: GET\n        description: Adobe Photoshop Service Health Check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: adobe-photoshop-rest\n    description: REST adapter for Adobe Photoshop\
  \ API.\n    resources:\n    - path: /v2/remove-background\n      name: removebackgroundv2\n      operations:\n      - method: POST\n        name: removebackgroundv2\n        description: Adobe Photoshop Remove Background from an Image\n        call: adobe-photoshop.removebackgroundv2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fill-masked-areas\n      name: fillmaskedareas\n      operations:\n      - method: POST\n        name: fillmaskedareas\n        description: Adobe Photoshop Fill Masked Areas with Generative AI\n        call: adobe-photoshop.fillmaskedareas\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/documentManifest\n      name: getdocumentmanifest\n      operations:\n      - method: POST\n        name: getdocumentmanifest\n        description: Adobe Photoshop Get PSD Document Manifest\n        call: adobe-photoshop.getdocumentmanifest\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /pie/psdService/documentOperations\n      name: modifydocument\n      operations:\n      - method: POST\n        name: modifydocument\n        description: Adobe Photoshop Edit a PSD Document\n        call: adobe-photoshop.modifydocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/documentCreate\n      name: createdocument\n      operations:\n      - method: POST\n        name: createdocument\n        description: Adobe Photoshop Create a New PSD Document\n        call: adobe-photoshop.createdocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/renditionCreate\n      name: createrendition\n      operations:\n      - method: POST\n        name: createrendition\n        description: Adobe Photoshop Create Image Renditions from a PSD\n        call: adobe-photoshop.createrendition\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /pie/psdService/smartObject\n      name: replacesmartobject\n      operations:\n      - method: POST\n        name: replacesmartobject\n        description: Adobe Photoshop Replace Smart Object Content\n        call: adobe-photoshop.replacesmartobject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/text\n      name: edittextlayer\n      operations:\n      - method: POST\n        name: edittextlayer\n        description: Adobe Photoshop Edit Text Layers in a PSD\n        call: adobe-photoshop.edittextlayer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/photoshopActions\n      name: playphotoshopactions\n      operations:\n      - method: POST\n        name: playphotoshopactions\n        description: Adobe Photoshop Execute Photoshop Action Files\n        call: adobe-photoshop.playphotoshopactions\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /pie/psdService/actionJSON\n      name: playactionjson\n      operations:\n      - method: POST\n        name: playactionjson\n        description: Adobe Photoshop Execute Photoshop Actions via JSON Descriptors\n        call: adobe-photoshop.playactionjson\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/actionJsonCreate\n      name: createwithactionjson\n      operations:\n      - method: POST\n        name: createwithactionjson\n        description: Adobe Photoshop Create Documents Using Action JSON Descriptors\n        call: adobe-photoshop.createwithactionjson\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/productCrop\n      name: productcrop\n      operations:\n      - method: POST\n        name: productcrop\n        description: Adobe Photoshop Smart Crop to Product Subject\n        call: adobe-photoshop.productcrop\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /pie/psdService/depthBlur\n      name: depthblur\n      operations:\n      - method: POST\n        name: depthblur\n        description: Adobe Photoshop Apply Depth Blur Effect\n        call: adobe-photoshop.depthblur\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/artboardCreate\n      name: createartboard\n      operations:\n      - method: POST\n        name: createartboard\n        description: Adobe Photoshop Create Artboards from PSD Inputs\n        call: adobe-photoshop.createartboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/status/{jobId}\n      name: getpsdjobstatus\n      operations:\n      - method: GET\n        name: getpsdjobstatus\n        description: Adobe Photoshop Get PSD Service Job Status\n        call: adobe-photoshop.getpsdjobstatus\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /sensei/status/{jobId}\n      name: getsenseijobstatus\n      operations:\n      - method: GET\n        name: getsenseijobstatus\n        description: Adobe Photoshop Get Sensei Service Job Status\n        call: adobe-photoshop.getsenseijobstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pie/psdService/hello\n      name: healthcheck\n      operations:\n      - method: GET\n        name: healthcheck\n        description: Adobe Photoshop Service Health Check\n        call: adobe-photoshop.healthcheck\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: adobe-photoshop-mcp\n    transport: http\n    description: MCP adapter for Adobe Photoshop API for AI agent use.\n    tools:\n    - name: removebackgroundv2\n      description: Adobe Photoshop Remove Background from an Image\n      hints:\n        readOnly: false\n        destructive: false\n    \
  \    idempotent: false\n      call: adobe-photoshop.removebackgroundv2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fillmaskedareas\n      description: Adobe Photoshop Fill Masked Areas with Generative AI\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.fillmaskedareas\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdocumentmanifest\n      description: Adobe Photoshop Get PSD Document Manifest\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.getdocumentmanifest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modifydocument\n      description: Adobe Photoshop Edit a PSD Document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.modifydocument\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createdocument\n      description: Adobe Photoshop Create a New PSD Document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.createdocument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrendition\n      description: Adobe Photoshop Create Image Renditions from a PSD\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.createrendition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacesmartobject\n      description: Adobe Photoshop Replace Smart Object Content\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.replacesmartobject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edittextlayer\n      description:\
  \ Adobe Photoshop Edit Text Layers in a PSD\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.edittextlayer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: playphotoshopactions\n      description: Adobe Photoshop Execute Photoshop Action Files\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.playphotoshopactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: playactionjson\n      description: Adobe Photoshop Execute Photoshop Actions via JSON Descriptors\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.playactionjson\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createwithactionjson\n      description: Adobe Photoshop Create Documents Using Action JSON Descriptors\n  \
  \    hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.createwithactionjson\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: productcrop\n      description: Adobe Photoshop Smart Crop to Product Subject\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.productcrop\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: depthblur\n      description: Adobe Photoshop Apply Depth Blur Effect\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.depthblur\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createartboard\n      description: Adobe Photoshop Create Artboards from PSD Inputs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-photoshop.createartboard\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpsdjobstatus\n      description: Adobe Photoshop Get PSD Service Job Status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-photoshop.getpsdjobstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsenseijobstatus\n      description: Adobe Photoshop Get Sensei Service Job Status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-photoshop.getsenseijobstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: healthcheck\n      description: Adobe Photoshop Service Health Check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-photoshop.healthcheck\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ADOBE_PHOTOSHOP_TOKEN:\
  \ ADOBE_PHOTOSHOP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-photoshop/refs/heads/main/capabilities/adobe-photoshop-capability.yaml
tags:
- Adobe
- Photoshop
- API
tools:
- description: Adobe Photoshop Remove Background from an Image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: removebackgroundv2
- description: Adobe Photoshop Fill Masked Areas with Generative AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fillmaskedareas
- description: Adobe Photoshop Get PSD Document Manifest
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getdocumentmanifest
- description: Adobe Photoshop Edit a PSD Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: modifydocument
- description: Adobe Photoshop Create a New PSD Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocument
- description: Adobe Photoshop Create Image Renditions from a PSD
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrendition
- description: Adobe Photoshop Replace Smart Object Content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: replacesmartobject
- description: Adobe Photoshop Edit Text Layers in a PSD
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edittextlayer
- description: Adobe Photoshop Execute Photoshop Action Files
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: playphotoshopactions
- description: Adobe Photoshop Execute Photoshop Actions via JSON Descriptors
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: playactionjson
- description: Adobe Photoshop Create Documents Using Action JSON Descriptors
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwithactionjson
- description: Adobe Photoshop Smart Crop to Product Subject
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: productcrop
- description: Adobe Photoshop Apply Depth Blur Effect
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: depthblur
- description: Adobe Photoshop Create Artboards from PSD Inputs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createartboard
- description: Adobe Photoshop Get PSD Service Job Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpsdjobstatus
- description: Adobe Photoshop Get Sensei Service Job Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsenseijobstatus
- description: Adobe Photoshop Service Health Check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: healthcheck
---
