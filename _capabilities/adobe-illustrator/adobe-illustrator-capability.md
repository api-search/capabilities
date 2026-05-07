---
categories: []
consumed_apis: []
description: The Adobe Illustrator Scripting API provides programmatic access to Illustrator's functionality through JavaScript, AppleScript, and VBScript. It allows developers to automate repetitive tasks, manipulate documents, select and edit text, generate art from data, and batch process files. Scripts can control nearly every aspect of Illustrator, from creating and modifying paths and shapes to managing layers, colors, and typography.
layout: capability
name: Adobe Illustrator Scripting API
operations:
- description: Adobe Illustrator Get Application Information
  method: GET
  name: getapplication
  path: /application
- description: Adobe Illustrator Get Application Preferences
  method: GET
  name: getpreferences
  path: /application/preferences
- description: Adobe Illustrator Update Application Preferences
  method: PUT
  name: updatepreferences
  path: /application/preferences
- description: Adobe Illustrator List Open Documents
  method: GET
  name: listdocuments
  path: /documents
- description: Adobe Illustrator Create a New Document
  method: POST
  name: createdocument
  path: /documents
- description: Adobe Illustrator Get a Document
  method: GET
  name: getdocument
  path: /documents/{documentId}
- description: Adobe Illustrator Close a Document
  method: DELETE
  name: closedocument
  path: /documents/{documentId}
- description: Adobe Illustrator Save a Document
  method: POST
  name: savedocument
  path: /documents/{documentId}/save
- description: Adobe Illustrator Export a Document
  method: POST
  name: exportdocument
  path: /documents/{documentId}/export
- description: Adobe Illustrator List Layers in a Document
  method: GET
  name: listlayers
  path: /documents/{documentId}/layers
- description: Adobe Illustrator Create a New Layer
  method: POST
  name: createlayer
  path: /documents/{documentId}/layers
- description: Adobe Illustrator Get a Layer
  method: GET
  name: getlayer
  path: /documents/{documentId}/layers/{layerId}
- description: Adobe Illustrator Update a Layer
  method: PUT
  name: updatelayer
  path: /documents/{documentId}/layers/{layerId}
- description: Adobe Illustrator Delete a Layer
  method: DELETE
  name: deletelayer
  path: /documents/{documentId}/layers/{layerId}
- description: Adobe Illustrator List Artboards in a Document
  method: GET
  name: listartboards
  path: /documents/{documentId}/artboards
- description: Adobe Illustrator Create a New Artboard
  method: POST
  name: createartboard
  path: /documents/{documentId}/artboards
- description: Adobe Illustrator Get an Artboard
  method: GET
  name: getartboard
  path: /documents/{documentId}/artboards/{artboardIndex}
- description: Adobe Illustrator Update an Artboard
  method: PUT
  name: updateartboard
  path: /documents/{documentId}/artboards/{artboardIndex}
- description: Adobe Illustrator Delete an Artboard
  method: DELETE
  name: deleteartboard
  path: /documents/{documentId}/artboards/{artboardIndex}
- description: Adobe Illustrator List Path Items
  method: GET
  name: listpathitems
  path: /documents/{documentId}/pathItems
- description: Adobe Illustrator Create a Path Item
  method: POST
  name: createpathitem
  path: /documents/{documentId}/pathItems
- description: Adobe Illustrator Get a Path Item
  method: GET
  name: getpathitem
  path: /documents/{documentId}/pathItems/{pathItemId}
- description: Adobe Illustrator Update a Path Item
  method: PUT
  name: updatepathitem
  path: /documents/{documentId}/pathItems/{pathItemId}
- description: Adobe Illustrator Delete a Path Item
  method: DELETE
  name: deletepathitem
  path: /documents/{documentId}/pathItems/{pathItemId}
- description: Adobe Illustrator List Text Frames
  method: GET
  name: listtextframes
  path: /documents/{documentId}/textFrames
- description: Adobe Illustrator Create a Text Frame
  method: POST
  name: createtextframe
  path: /documents/{documentId}/textFrames
- description: Adobe Illustrator Get a Text Frame
  method: GET
  name: gettextframe
  path: /documents/{documentId}/textFrames/{textFrameId}
- description: Adobe Illustrator Update a Text Frame
  method: PUT
  name: updatetextframe
  path: /documents/{documentId}/textFrames/{textFrameId}
- description: Adobe Illustrator Delete a Text Frame
  method: DELETE
  name: deletetextframe
  path: /documents/{documentId}/textFrames/{textFrameId}
- description: Adobe Illustrator List Symbols
  method: GET
  name: listsymbols
  path: /documents/{documentId}/symbols
- description: Adobe Illustrator Create a Symbol
  method: POST
  name: createsymbol
  path: /documents/{documentId}/symbols
- description: Adobe Illustrator Get a Symbol
  method: GET
  name: getsymbol
  path: /documents/{documentId}/symbols/{symbolId}
- description: Adobe Illustrator Delete a Symbol
  method: DELETE
  name: deletesymbol
  path: /documents/{documentId}/symbols/{symbolId}
- description: Adobe Illustrator List Swatches
  method: GET
  name: listswatches
  path: /documents/{documentId}/swatches
- description: Adobe Illustrator Create a Swatch
  method: POST
  name: createswatch
  path: /documents/{documentId}/swatches
- description: Adobe Illustrator Get a Swatch
  method: GET
  name: getswatch
  path: /documents/{documentId}/swatches/{swatchName}
- description: Adobe Illustrator Delete a Swatch
  method: DELETE
  name: deleteswatch
  path: /documents/{documentId}/swatches/{swatchName}
- description: Adobe Illustrator List Graphic Styles
  method: GET
  name: listgraphicstyles
  path: /documents/{documentId}/graphicStyles
- description: Adobe Illustrator Get a Graphic Style
  method: GET
  name: getgraphicstyle
  path: /documents/{documentId}/graphicStyles/{graphicStyleName}
- description: Adobe Illustrator Delete a Graphic Style
  method: DELETE
  name: deletegraphicstyle
  path: /documents/{documentId}/graphicStyles/{graphicStyleName}
personas: []
provider_name: Adobe Illustrator
provider_slug: adobe-illustrator
search_terms:
- adobe illustrator get a symbol
- adobe illustrator create a swatch
- api
- adobe illustrator list graphic styles
- adobe illustrator delete a text frame
- adobe illustrator delete a symbol
- adobe illustrator get an artboard
- listlayers
- adobe illustrator list path items
- adobe illustrator delete a swatch
- createdocument
- adobe illustrator update a layer
- deletelayer
- illustrator
- adobe illustrator create a path item
- adobe illustrator update application preferences
- getartboard
- getpathitem
- adobe illustrator create a new artboard
- adobe illustrator create a new layer
- adobe illustrator delete a path item
- adobe illustrator delete a graphic style
- closedocument
- listpathitems
- adobe illustrator list text frames
- deletegraphicstyle
- exportdocument
- adobe illustrator save a document
- adobe illustrator create a text frame
- createpathitem
- adobe illustrator get a document
- listsymbols
- deletepathitem
- getapplication
- adobe illustrator list open documents
- adobe illustrator get application information
- adobe illustrator create a new document
- getsymbol
- deleteswatch
- createartboard
- adobe illustrator get application preferences
- adobe illustrator list symbols
- updatepreferences
- deleteartboard
- updateartboard
- createtextframe
- design
- createsymbol
- listartboards
- adobe illustrator close a document
- updatetextframe
- listgraphicstyles
- adobe illustrator create a symbol
- getpreferences
- adobe illustrator update an artboard
- listtextframes
- vector graphics
- adobe illustrator delete a layer
- getgraphicstyle
- listdocuments
- listswatches
- adobe illustrator get a layer
- getdocument
- creative cloud
- deletetextframe
- adobe illustrator get a path item
- adobe illustrator delete an artboard
- updatelayer
- adobe illustrator list artboards in a document
- adobe illustrator export a document
- createswatch
- getlayer
- adobe illustrator get a graphic style
- updatepathitem
- adobe illustrator list swatches
- createlayer
- deletesymbol
- adobe illustrator update a path item
- adobe illustrator get a swatch
- adobe illustrator update a text frame
- adobe illustrator get a text frame
- getswatch
- adobe illustrator list layers in a document
- gettextframe
- adobe
- savedocument
slug: adobe-illustrator-capability
source_filename: adobe-illustrator-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Illustrator Scripting API\n  description: The Adobe Illustrator Scripting API provides programmatic access to Illustrator's functionality through JavaScript,\n    AppleScript, and VBScript. It allows developers to automate repetitive tasks, manipulate documents, select and edit text,\n    generate art from data, and batch process files. Scripts can control nearly every aspect of Illustrator, from creating\n    and modifying paths and shapes to managing layers, colors, and typography.\n  tags:\n  - Adobe\n  - Illustrator\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: adobe-illustrator\n    baseUri: https://localhost\n    description: Adobe Illustrator Scripting API HTTP API.\n    resources:\n    - name: application\n      path: /application\n      operations:\n      - name: getapplication\n        method: GET\n        description: Adobe Illustrator Get Application\
  \ Information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-preferences\n      path: /application/preferences\n      operations:\n      - name: getpreferences\n        method: GET\n        description: Adobe Illustrator Get Application Preferences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepreferences\n        method: PUT\n        description: Adobe Illustrator Update Application Preferences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /documents\n      operations:\n      - name: listdocuments\n        method: GET\n        description: Adobe Illustrator List Open Documents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n      - name: createdocument\n        method: POST\n        description: Adobe Illustrator Create a New Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid\n      path: /documents/{documentId}\n      operations:\n      - name: getdocument\n        method: GET\n        description: Adobe Illustrator Get a Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: closedocument\n        method: DELETE\n        description: Adobe Illustrator Close a Document\n        inputParameters:\n        - name: saveChanges\n          in: query\n          type: string\n          description: Whether to save changes before closing.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: documents-documentid-save\n      path: /documents/{documentId}/save\n      operations:\n      - name: savedocument\n        method: POST\n        description: Adobe Illustrator Save a Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-export\n      path: /documents/{documentId}/export\n      operations:\n      - name: exportdocument\n        method: POST\n        description: Adobe Illustrator Export a Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-layers\n      path: /documents/{documentId}/layers\n      operations:\n      - name: listlayers\n        method: GET\n        description: Adobe Illustrator List Layers in a Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: createlayer\n        method: POST\n        description: Adobe Illustrator Create a New Layer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-layers-layerid\n      path: /documents/{documentId}/layers/{layerId}\n      operations:\n      - name: getlayer\n        method: GET\n        description: Adobe Illustrator Get a Layer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelayer\n        method: PUT\n        description: Adobe Illustrator Update a Layer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelayer\n        method: DELETE\n        description: Adobe Illustrator Delete a Layer\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-artboards\n      path: /documents/{documentId}/artboards\n      operations:\n      - name: listartboards\n        method: GET\n        description: Adobe Illustrator List Artboards in a Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createartboard\n        method: POST\n        description: Adobe Illustrator Create a New Artboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-artboards-artboardindex\n      path: /documents/{documentId}/artboards/{artboardIndex}\n      operations:\n      - name: getartboard\n        method: GET\n        description: Adobe Illustrator Get an Artboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n      - name: updateartboard\n        method: PUT\n        description: Adobe Illustrator Update an Artboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteartboard\n        method: DELETE\n        description: Adobe Illustrator Delete an Artboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-pathitems\n      path: /documents/{documentId}/pathItems\n      operations:\n      - name: listpathitems\n        method: GET\n        description: Adobe Illustrator List Path Items\n        inputParameters:\n        - name: layerId\n          in: query\n          type: string\n          description: Filter path items by layer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: createpathitem\n        method: POST\n        description: Adobe Illustrator Create a Path Item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-pathitems-pathitemid\n      path: /documents/{documentId}/pathItems/{pathItemId}\n      operations:\n      - name: getpathitem\n        method: GET\n        description: Adobe Illustrator Get a Path Item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepathitem\n        method: PUT\n        description: Adobe Illustrator Update a Path Item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepathitem\n        method: DELETE\n        description: Adobe Illustrator Delete a Path Item\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-textframes\n      path: /documents/{documentId}/textFrames\n      operations:\n      - name: listtextframes\n        method: GET\n        description: Adobe Illustrator List Text Frames\n        inputParameters:\n        - name: layerId\n          in: query\n          type: string\n          description: Filter text frames by layer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtextframe\n        method: POST\n        description: Adobe Illustrator Create a Text Frame\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-textframes-textframeid\n      path: /documents/{documentId}/textFrames/{textFrameId}\n      operations:\n      - name: gettextframe\n        method: GET\n      \
  \  description: Adobe Illustrator Get a Text Frame\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetextframe\n        method: PUT\n        description: Adobe Illustrator Update a Text Frame\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetextframe\n        method: DELETE\n        description: Adobe Illustrator Delete a Text Frame\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-symbols\n      path: /documents/{documentId}/symbols\n      operations:\n      - name: listsymbols\n        method: GET\n        description: Adobe Illustrator List Symbols\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n     \
  \ - name: createsymbol\n        method: POST\n        description: Adobe Illustrator Create a Symbol\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-symbols-symbolid\n      path: /documents/{documentId}/symbols/{symbolId}\n      operations:\n      - name: getsymbol\n        method: GET\n        description: Adobe Illustrator Get a Symbol\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesymbol\n        method: DELETE\n        description: Adobe Illustrator Delete a Symbol\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-swatches\n      path: /documents/{documentId}/swatches\n      operations:\n      - name: listswatches\n        method: GET\n        description: Adobe\
  \ Illustrator List Swatches\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createswatch\n        method: POST\n        description: Adobe Illustrator Create a Swatch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-swatches-swatchname\n      path: /documents/{documentId}/swatches/{swatchName}\n      operations:\n      - name: getswatch\n        method: GET\n        description: Adobe Illustrator Get a Swatch\n        inputParameters:\n        - name: swatchName\n          in: path\n          type: string\n          required: true\n          description: Name of the swatch.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteswatch\n        method: DELETE\n        description: Adobe Illustrator\
  \ Delete a Swatch\n        inputParameters:\n        - name: swatchName\n          in: path\n          type: string\n          required: true\n          description: Name of the swatch.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-graphicstyles\n      path: /documents/{documentId}/graphicStyles\n      operations:\n      - name: listgraphicstyles\n        method: GET\n        description: Adobe Illustrator List Graphic Styles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-graphicstyles-graphicstylen\n      path: /documents/{documentId}/graphicStyles/{graphicStyleName}\n      operations:\n      - name: getgraphicstyle\n        method: GET\n        description: Adobe Illustrator Get a Graphic Style\n        inputParameters:\n        - name: graphicStyleName\n   \
  \       in: path\n          type: string\n          required: true\n          description: Name of the graphic style.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegraphicstyle\n        method: DELETE\n        description: Adobe Illustrator Delete a Graphic Style\n        inputParameters:\n        - name: graphicStyleName\n          in: path\n          type: string\n          required: true\n          description: Name of the graphic style.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: adobe-illustrator-rest\n    description: REST adapter for Adobe Illustrator Scripting API.\n    resources:\n    - path: /application\n      name: getapplication\n      operations:\n      - method: GET\n        name: getapplication\n        description: Adobe Illustrator\
  \ Get Application Information\n        call: adobe-illustrator.getapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /application/preferences\n      name: getpreferences\n      operations:\n      - method: GET\n        name: getpreferences\n        description: Adobe Illustrator Get Application Preferences\n        call: adobe-illustrator.getpreferences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /application/preferences\n      name: updatepreferences\n      operations:\n      - method: PUT\n        name: updatepreferences\n        description: Adobe Illustrator Update Application Preferences\n        call: adobe-illustrator.updatepreferences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents\n      name: listdocuments\n      operations:\n      - method: GET\n        name: listdocuments\n        description: Adobe Illustrator List Open Documents\n  \
  \      call: adobe-illustrator.listdocuments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents\n      name: createdocument\n      operations:\n      - method: POST\n        name: createdocument\n        description: Adobe Illustrator Create a New Document\n        call: adobe-illustrator.createdocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}\n      name: getdocument\n      operations:\n      - method: GET\n        name: getdocument\n        description: Adobe Illustrator Get a Document\n        call: adobe-illustrator.getdocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}\n      name: closedocument\n      operations:\n      - method: DELETE\n        name: closedocument\n        description: Adobe Illustrator Close a Document\n        call: adobe-illustrator.closedocument\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /documents/{documentId}/save\n      name: savedocument\n      operations:\n      - method: POST\n        name: savedocument\n        description: Adobe Illustrator Save a Document\n        call: adobe-illustrator.savedocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/export\n      name: exportdocument\n      operations:\n      - method: POST\n        name: exportdocument\n        description: Adobe Illustrator Export a Document\n        call: adobe-illustrator.exportdocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/layers\n      name: listlayers\n      operations:\n      - method: GET\n        name: listlayers\n        description: Adobe Illustrator List Layers in a Document\n        call: adobe-illustrator.listlayers\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /documents/{documentId}/layers\n      name: createlayer\n      operations:\n      - method: POST\n        name: createlayer\n        description: Adobe Illustrator Create a New Layer\n        call: adobe-illustrator.createlayer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/layers/{layerId}\n      name: getlayer\n      operations:\n      - method: GET\n        name: getlayer\n        description: Adobe Illustrator Get a Layer\n        call: adobe-illustrator.getlayer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/layers/{layerId}\n      name: updatelayer\n      operations:\n      - method: PUT\n        name: updatelayer\n        description: Adobe Illustrator Update a Layer\n        call: adobe-illustrator.updatelayer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/layers/{layerId}\n \
  \     name: deletelayer\n      operations:\n      - method: DELETE\n        name: deletelayer\n        description: Adobe Illustrator Delete a Layer\n        call: adobe-illustrator.deletelayer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/artboards\n      name: listartboards\n      operations:\n      - method: GET\n        name: listartboards\n        description: Adobe Illustrator List Artboards in a Document\n        call: adobe-illustrator.listartboards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/artboards\n      name: createartboard\n      operations:\n      - method: POST\n        name: createartboard\n        description: Adobe Illustrator Create a New Artboard\n        call: adobe-illustrator.createartboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/artboards/{artboardIndex}\n    \
  \  name: getartboard\n      operations:\n      - method: GET\n        name: getartboard\n        description: Adobe Illustrator Get an Artboard\n        call: adobe-illustrator.getartboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/artboards/{artboardIndex}\n      name: updateartboard\n      operations:\n      - method: PUT\n        name: updateartboard\n        description: Adobe Illustrator Update an Artboard\n        call: adobe-illustrator.updateartboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/artboards/{artboardIndex}\n      name: deleteartboard\n      operations:\n      - method: DELETE\n        name: deleteartboard\n        description: Adobe Illustrator Delete an Artboard\n        call: adobe-illustrator.deleteartboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/pathItems\n \
  \     name: listpathitems\n      operations:\n      - method: GET\n        name: listpathitems\n        description: Adobe Illustrator List Path Items\n        call: adobe-illustrator.listpathitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/pathItems\n      name: createpathitem\n      operations:\n      - method: POST\n        name: createpathitem\n        description: Adobe Illustrator Create a Path Item\n        call: adobe-illustrator.createpathitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/pathItems/{pathItemId}\n      name: getpathitem\n      operations:\n      - method: GET\n        name: getpathitem\n        description: Adobe Illustrator Get a Path Item\n        call: adobe-illustrator.getpathitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/pathItems/{pathItemId}\n      name: updatepathitem\n\
  \      operations:\n      - method: PUT\n        name: updatepathitem\n        description: Adobe Illustrator Update a Path Item\n        call: adobe-illustrator.updatepathitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/pathItems/{pathItemId}\n      name: deletepathitem\n      operations:\n      - method: DELETE\n        name: deletepathitem\n        description: Adobe Illustrator Delete a Path Item\n        call: adobe-illustrator.deletepathitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/textFrames\n      name: listtextframes\n      operations:\n      - method: GET\n        name: listtextframes\n        description: Adobe Illustrator List Text Frames\n        call: adobe-illustrator.listtextframes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/textFrames\n      name: createtextframe\n   \
  \   operations:\n      - method: POST\n        name: createtextframe\n        description: Adobe Illustrator Create a Text Frame\n        call: adobe-illustrator.createtextframe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/textFrames/{textFrameId}\n      name: gettextframe\n      operations:\n      - method: GET\n        name: gettextframe\n        description: Adobe Illustrator Get a Text Frame\n        call: adobe-illustrator.gettextframe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/textFrames/{textFrameId}\n      name: updatetextframe\n      operations:\n      - method: PUT\n        name: updatetextframe\n        description: Adobe Illustrator Update a Text Frame\n        call: adobe-illustrator.updatetextframe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/textFrames/{textFrameId}\n      name:\
  \ deletetextframe\n      operations:\n      - method: DELETE\n        name: deletetextframe\n        description: Adobe Illustrator Delete a Text Frame\n        call: adobe-illustrator.deletetextframe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/symbols\n      name: listsymbols\n      operations:\n      - method: GET\n        name: listsymbols\n        description: Adobe Illustrator List Symbols\n        call: adobe-illustrator.listsymbols\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/symbols\n      name: createsymbol\n      operations:\n      - method: POST\n        name: createsymbol\n        description: Adobe Illustrator Create a Symbol\n        call: adobe-illustrator.createsymbol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/symbols/{symbolId}\n      name: getsymbol\n      operations:\n\
  \      - method: GET\n        name: getsymbol\n        description: Adobe Illustrator Get a Symbol\n        call: adobe-illustrator.getsymbol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/symbols/{symbolId}\n      name: deletesymbol\n      operations:\n      - method: DELETE\n        name: deletesymbol\n        description: Adobe Illustrator Delete a Symbol\n        call: adobe-illustrator.deletesymbol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/swatches\n      name: listswatches\n      operations:\n      - method: GET\n        name: listswatches\n        description: Adobe Illustrator List Swatches\n        call: adobe-illustrator.listswatches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/swatches\n      name: createswatch\n      operations:\n      - method: POST\n        name: createswatch\n\
  \        description: Adobe Illustrator Create a Swatch\n        call: adobe-illustrator.createswatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/swatches/{swatchName}\n      name: getswatch\n      operations:\n      - method: GET\n        name: getswatch\n        description: Adobe Illustrator Get a Swatch\n        call: adobe-illustrator.getswatch\n        with:\n          swatchName: rest.swatchName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/swatches/{swatchName}\n      name: deleteswatch\n      operations:\n      - method: DELETE\n        name: deleteswatch\n        description: Adobe Illustrator Delete a Swatch\n        call: adobe-illustrator.deleteswatch\n        with:\n          swatchName: rest.swatchName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/graphicStyles\n      name: listgraphicstyles\n\
  \      operations:\n      - method: GET\n        name: listgraphicstyles\n        description: Adobe Illustrator List Graphic Styles\n        call: adobe-illustrator.listgraphicstyles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/graphicStyles/{graphicStyleName}\n      name: getgraphicstyle\n      operations:\n      - method: GET\n        name: getgraphicstyle\n        description: Adobe Illustrator Get a Graphic Style\n        call: adobe-illustrator.getgraphicstyle\n        with:\n          graphicStyleName: rest.graphicStyleName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{documentId}/graphicStyles/{graphicStyleName}\n      name: deletegraphicstyle\n      operations:\n      - method: DELETE\n        name: deletegraphicstyle\n        description: Adobe Illustrator Delete a Graphic Style\n        call: adobe-illustrator.deletegraphicstyle\n        with:\n          graphicStyleName:\
  \ rest.graphicStyleName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: adobe-illustrator-mcp\n    transport: http\n    description: MCP adapter for Adobe Illustrator Scripting API for AI agent use.\n    tools:\n    - name: getapplication\n      description: Adobe Illustrator Get Application Information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.getapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpreferences\n      description: Adobe Illustrator Get Application Preferences\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.getpreferences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepreferences\n      description: Adobe Illustrator Update Application Preferences\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.updatepreferences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdocuments\n      description: Adobe Illustrator List Open Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.listdocuments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdocument\n      description: Adobe Illustrator Create a New Document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-illustrator.createdocument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdocument\n      description: Adobe Illustrator Get a Document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.getdocument\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: closedocument\n      description: Adobe Illustrator Close a Document\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: adobe-illustrator.closedocument\n      with:\n        saveChanges: tools.saveChanges\n      inputParameters:\n      - name: saveChanges\n        type: string\n        description: Whether to save changes before closing.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: savedocument\n      description: Adobe Illustrator Save a Document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-illustrator.savedocument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exportdocument\n      description: Adobe Illustrator Export a Document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: adobe-illustrator.exportdocument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlayers\n      description: Adobe Illustrator List Layers in a Document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.listlayers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlayer\n      description: Adobe Illustrator Create a New Layer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-illustrator.createlayer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlayer\n      description: Adobe Illustrator Get a Layer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.getlayer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatelayer\n      description:\
  \ Adobe Illustrator Update a Layer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.updatelayer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletelayer\n      description: Adobe Illustrator Delete a Layer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: adobe-illustrator.deletelayer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listartboards\n      description: Adobe Illustrator List Artboards in a Document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.listartboards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createartboard\n      description: Adobe Illustrator Create a New Artboard\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: adobe-illustrator.createartboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getartboard\n      description: Adobe Illustrator Get an Artboard\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.getartboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateartboard\n      description: Adobe Illustrator Update an Artboard\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.updateartboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteartboard\n      description: Adobe Illustrator Delete an Artboard\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: adobe-illustrator.deleteartboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpathitems\n\
  \      description: Adobe Illustrator List Path Items\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-illustrator.listpathitems\n      with:\n        layerId: tools.layerId\n      inputParameters:\n      - name: layerId\n        type: string\n        description: Filter path items by layer.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpathitem\n      description: Adobe Illustrator Create a Path Item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-illustrator.createpathitem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpathitem\n      description: Adobe Illustrator Get a Path Item\n      hints:\n   \n\n# --- truncated at 32 KB (37 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/adobe-illustrator/refs/heads/main/capabilities/adobe-illustrator-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-illustrator/refs/heads/main/capabilities/adobe-illustrator-capability.yaml
tags:
- Adobe
- Illustrator
- API
tools:
- description: Adobe Illustrator Get Application Information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Adobe Illustrator Get Application Preferences
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpreferences
- description: Adobe Illustrator Update Application Preferences
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepreferences
- description: Adobe Illustrator List Open Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocuments
- description: Adobe Illustrator Create a New Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocument
- description: Adobe Illustrator Get a Document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocument
- description: Adobe Illustrator Close a Document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: closedocument
- description: Adobe Illustrator Save a Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: savedocument
- description: Adobe Illustrator Export a Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exportdocument
- description: Adobe Illustrator List Layers in a Document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlayers
- description: Adobe Illustrator Create a New Layer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlayer
- description: Adobe Illustrator Get a Layer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlayer
- description: Adobe Illustrator Update a Layer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelayer
- description: Adobe Illustrator Delete a Layer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelayer
- description: Adobe Illustrator List Artboards in a Document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listartboards
- description: Adobe Illustrator Create a New Artboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createartboard
- description: Adobe Illustrator Get an Artboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getartboard
- description: Adobe Illustrator Update an Artboard
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateartboard
- description: Adobe Illustrator Delete an Artboard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteartboard
- description: Adobe Illustrator List Path Items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpathitems
- description: Adobe Illustrator Create a Path Item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpathitem
- description: Adobe Illustrator Get a Path Item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpathitem
- description: Adobe Illustrator Update a Path Item
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepathitem
- description: Adobe Illustrator Delete a Path Item
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepathitem
- description: Adobe Illustrator List Text Frames
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtextframes
- description: Adobe Illustrator Create a Text Frame
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtextframe
- description: Adobe Illustrator Get a Text Frame
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettextframe
- description: Adobe Illustrator Update a Text Frame
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetextframe
- description: Adobe Illustrator Delete a Text Frame
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetextframe
- description: Adobe Illustrator List Symbols
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsymbols
- description: Adobe Illustrator Create a Symbol
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsymbol
- description: Adobe Illustrator Get a Symbol
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsymbol
- description: Adobe Illustrator Delete a Symbol
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesymbol
- description: Adobe Illustrator List Swatches
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listswatches
- description: Adobe Illustrator Create a Swatch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createswatch
- description: Adobe Illustrator Get a Swatch
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getswatch
- description: Adobe Illustrator Delete a Swatch
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteswatch
- description: Adobe Illustrator List Graphic Styles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgraphicstyles
- description: Adobe Illustrator Get a Graphic Style
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgraphicstyle
- description: Adobe Illustrator Delete a Graphic Style
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegraphicstyle
---
