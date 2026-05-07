---
categories: []
consumed_apis: []
description: Unified capability for live video production graphics control using SPX-GC. Enables broadcast operators, stream producers, and automation systems to control graphics rundowns, trigger template playback, manage files, persist state for sports scoring and timing, and invoke custom SPX extension logic — all through a unified REST API and MCP server.
layout: capability
name: SPX Live Graphics Production
operations:
- description: Load a rundown file into the SPX system
  method: POST
  name: load-rundown
  path: /v1/rundowns
- description: Set focus to the first rundown item
  method: POST
  name: focus-first-item
  path: /v1/rundowns/focus/first
- description: Advance focus to the next rundown item
  method: POST
  name: focus-next-item
  path: /v1/rundowns/focus/next
- description: Move focus to the previous rundown item
  method: POST
  name: focus-previous-item
  path: /v1/rundowns/focus/previous
- description: Play the currently focused rundown item
  method: POST
  name: play-item
  path: /v1/items/play
- description: Stop the currently focused rundown item
  method: POST
  name: stop-item
  path: /v1/items/stop
- description: Issue continue command to the focused item
  method: POST
  name: continue-item
  path: /v1/items/continue
- description: Update template field values for a specific item
  method: PUT
  name: update-item
  path: /v1/items/{id}
- description: Play/stop/continue a template directly
  method: POST
  name: direct-play-out
  path: /v1/playout
- description: List files in a given ASSETS subfolder
  method: GET
  name: get-file-list
  path: /v1/files
- description: Call a function in a registered SPX extension
  method: POST
  name: invoke-extension-function
  path: /v1/extensions
personas: []
provider_name: SPX Graphics
provider_slug: spx
search_terms:
- load a rundown file into the spx system
- streaming
- advance the rundown focus to the next item.
- update graphic data
- play item
- direct play out
- focus next item
- load a rundown file into spx. specify the project and rundown name in 'projectname/rundownname' format.
- advance focus to the next rundown item
- video production
- update item
- trigger playback of the currently focused rundown item, making the graphic visible in the live output.
- continue graphic
- continue item
- stop and remove the currently focused graphic from the live output.
- browse media asset files
- load rundown
- set focus to the first rundown item
- move focus to the previous rundown item
- direct template playout without rundown
- play/stop/continue a template directly
- list files available in a given subfolder of the spx assets directory. useful for populating template dropdowns or media selection.
- call a named function in a custom spx extension. used for advanced graphics like sports scoring, live timing, and custom data-driven graphics.
- update data fields for a rundown item
- invoke custom spx extension functions
- direct playout
- graphics
- update the text, images, or other template field values for a specific rundown item identified by project, rundown, and item index.
- move rundown focus backward
- live production
- issue continue command to the focused item
- move rundown focus forward
- stop the focused graphic
- trigger playback of the focused graphic
- load and manage spx rundowns
- play the currently focused rundown item
- list files in a given assets subfolder
- stop the currently focused rundown item
- issue a continue command to advance the currently focused graphic to its next animation state or page.
- move the rundown focus back to the previous item.
- stop graphic
- get file list
- invoke extension function
- stop item
- play graphic
- focus first item
- media
- focus previous item
- move the rundown focus to the very first item.
- list asset files
- move rundown focus to the first item
- directly play, continue, or stop a graphics template without needing it in a rundown. useful for ad-hoc graphics or automated triggers.
- call a function in a registered spx extension
- advance the focused graphic animation
- update template field values for a specific item
- broadcast
slug: live-graphics-production
source_filename: live-graphics-production.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SPX Live Graphics Production\n  description: Unified capability for live video production graphics control using SPX-GC. Enables broadcast operators, stream\n    producers, and automation systems to control graphics rundowns, trigger template playback, manage files, persist state\n    for sports scoring and timing, and invoke custom SPX extension logic — all through a unified REST API and MCP server.\n  tags:\n  - Broadcast\n  - Graphics\n  - Live Production\n  - Media\n  - Streaming\n  - Video Production\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPX_API_KEY: SPX_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: spx-graphics\n    baseUri: http://localhost:5656\n    description: SPX Graphics Controller local REST API\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{SPX_API_KEY}}'\n      placement: query\n    resources:\n    - name: rundown\n   \
  \   path: /api/v1/rundown\n      description: Rundown loading and focus control\n      operations:\n      - name: load-rundown\n        method: GET\n        description: Load a rundown file from the given project\n        inputParameters:\n        - name: file\n          in: query\n          type: string\n          required: true\n          description: Project/Rundown path (e.g., MyProject/MyRundown)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: focus-first-item\n        method: GET\n        description: Move focus to the first item in the rundown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: focus-next-item\n        method: GET\n        description: Move focus to the next item in the rundown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: focus-previous-item\n        method: GET\n        description: Move focus to the previous item in the rundown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: item\n      path: /api/v1/item\n      description: Individual rundown item control\n      operations:\n      - name: play-item\n        method: GET\n        description: Issue play command to the focused item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-item\n        method: GET\n        description: Issue stop command to the focused item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: continue-item\n        method: GET\n        description: Issue continue command to the focused item\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-item\n        method: POST\n        description: Update data fields of a specific rundown item\n        body:\n          type: json\n          data:\n            project: '{{tools.project}}'\n            rundown: '{{tools.rundown}}'\n            item: '{{tools.item}}'\n            fields: '{{tools.fields}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: direct-playout\n      path: /api/v1/directplayout\n      description: Direct template playout without rundown context\n      operations:\n      - name: direct-play-out\n        method: POST\n        description: Execute play/continue/stop command directly to a template\n        body:\n          type: json\n          data:\n            command: '{{tools.command}}'\n            template: '{{tools.template}}'\n            fields: '{{tools.fields}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files\n      path: /api/v1/getFileList\n      description: File listing from ASSETS folder\n      operations:\n      - name: get-file-list\n        method: GET\n        description: List files in a given ASSETS subfolder\n        inputParameters:\n        - name: folder\n          in: query\n          type: string\n          required: true\n          description: Subfolder path relative to ASSETS\n        outputRawFormat: json\n        outputParameters:\n        - name: files\n          type: array\n          value: $.files\n    - name: data\n      path: /api/v1/saveCustomJSON\n      description: Custom JSON data persistence\n      operations:\n      - name: save-custom-json\n        method: POST\n        description: Save arbitrary JSON data to disk for persistence\n        body:\n          type: json\n          data:\n            filename: '{{tools.filename}}'\n\
  \            data: '{{tools.data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extensions\n      path: /api/v1/invokeExtensionFunction\n      description: SPX extension function invocation\n      operations:\n      - name: invoke-extension-function\n        method: POST\n        description: Invoke a function in a custom SPX extension\n        body:\n          type: json\n          data:\n            extension: '{{tools.extension}}'\n            function: '{{tools.function}}'\n            params: '{{tools.params}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: live-graphics-api\n    description: Unified REST API for live graphics production control via SPX-GC.\n    resources:\n    - path: /v1/rundowns\n      name: rundowns\n      description: Load and\
  \ manage SPX rundowns\n      operations:\n      - method: POST\n        name: load-rundown\n        description: Load a rundown file into the SPX system\n        call: spx-graphics.load-rundown\n        with:\n          file: rest.file\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rundowns/focus/first\n      name: focus-first\n      description: Move rundown focus to the first item\n      operations:\n      - method: POST\n        name: focus-first-item\n        description: Set focus to the first rundown item\n        call: spx-graphics.focus-first-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rundowns/focus/next\n      name: focus-next\n      description: Move rundown focus forward\n      operations:\n      - method: POST\n        name: focus-next-item\n        description: Advance focus to the next rundown item\n        call: spx-graphics.focus-next-item\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /v1/rundowns/focus/previous\n      name: focus-previous\n      description: Move rundown focus backward\n      operations:\n      - method: POST\n        name: focus-previous-item\n        description: Move focus to the previous rundown item\n        call: spx-graphics.focus-previous-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items/play\n      name: item-play\n      description: Trigger playback of the focused graphic\n      operations:\n      - method: POST\n        name: play-item\n        description: Play the currently focused rundown item\n        call: spx-graphics.play-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items/stop\n      name: item-stop\n      description: Stop the focused graphic\n      operations:\n      - method: POST\n        name: stop-item\n        description: Stop the currently focused rundown item\n     \
  \   call: spx-graphics.stop-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items/continue\n      name: item-continue\n      description: Advance the focused graphic animation\n      operations:\n      - method: POST\n        name: continue-item\n        description: Issue continue command to the focused item\n        call: spx-graphics.continue-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items/{id}\n      name: item-update\n      description: Update data fields for a rundown item\n      operations:\n      - method: PUT\n        name: update-item\n        description: Update template field values for a specific item\n        call: spx-graphics.update-item\n        with:\n          project: rest.project\n          rundown: rest.rundown\n          item: rest.id\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/playout\n\
  \      name: direct-playout\n      description: Direct template playout without rundown\n      operations:\n      - method: POST\n        name: direct-play-out\n        description: Play/stop/continue a template directly\n        call: spx-graphics.direct-play-out\n        with:\n          command: rest.command\n          template: rest.template\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/files\n      name: assets\n      description: Browse media asset files\n      operations:\n      - method: GET\n        name: get-file-list\n        description: List files in a given ASSETS subfolder\n        call: spx-graphics.get-file-list\n        with:\n          folder: rest.folder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extensions\n      name: extensions\n      description: Invoke custom SPX extension functions\n      operations:\n      - method: POST\n        name: invoke-extension-function\n\
  \        description: Call a function in a registered SPX extension\n        call: spx-graphics.invoke-extension-function\n        with:\n          extension: rest.extension\n          function: rest.function\n          params: rest.params\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: live-graphics-mcp\n    transport: http\n    description: MCP server for AI-assisted live graphics production control.\n    tools:\n    - name: load-rundown\n      description: Load a rundown file into SPX. Specify the project and rundown name in 'ProjectName/RundownName' format.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: spx-graphics.load-rundown\n      with:\n        file: tools.file\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: focus-first-item\n      description: Move the rundown focus to the very first item.\n      hints:\n        readOnly: false\n        idempotent:\
  \ true\n      call: spx-graphics.focus-first-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: focus-next-item\n      description: Advance the rundown focus to the next item.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: spx-graphics.focus-next-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: focus-previous-item\n      description: Move the rundown focus back to the previous item.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: spx-graphics.focus-previous-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: play-graphic\n      description: Trigger playback of the currently focused rundown item, making the graphic visible in the live output.\n      hints:\n        readOnly: false\n        destructive: false\n      call: spx-graphics.play-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ stop-graphic\n      description: Stop and remove the currently focused graphic from the live output.\n      hints:\n        readOnly: false\n        destructive: false\n      call: spx-graphics.stop-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: continue-graphic\n      description: Issue a continue command to advance the currently focused graphic to its next animation state or page.\n      hints:\n        readOnly: false\n        destructive: false\n      call: spx-graphics.continue-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-graphic-data\n      description: Update the text, images, or other template field values for a specific rundown item identified by project,\n        rundown, and item index.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: spx-graphics.update-item\n      with:\n        project: tools.project\n        rundown: tools.rundown\n        item: tools.item\n\
  \        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: direct-playout\n      description: Directly play, continue, or stop a graphics template without needing it in a rundown. Useful for ad-hoc\n        graphics or automated triggers.\n      hints:\n        readOnly: false\n        destructive: false\n      call: spx-graphics.direct-play-out\n      with:\n        command: tools.command\n        template: tools.template\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-asset-files\n      description: List files available in a given subfolder of the SPX ASSETS directory. Useful for populating template dropdowns\n        or media selection.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: spx-graphics.get-file-list\n      with:\n        folder: tools.folder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: invoke-extension-function\n\
  \      description: Call a named function in a custom SPX extension. Used for advanced graphics like sports scoring, live timing,\n        and custom data-driven graphics.\n      hints:\n        readOnly: false\n        destructive: false\n      call: spx-graphics.invoke-extension-function\n      with:\n        extension: tools.extension\n        function: tools.function\n        params: tools.params\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spx/refs/heads/main/capabilities/live-graphics-production.yaml
tags:
- Broadcast
- Graphics
- Live Production
- Media
- Streaming
- Video Production
tools:
- description: Load a rundown file into SPX. Specify the project and rundown name in 'ProjectName/RundownName' format.
  hints:
    idempotent: true
    readOnly: false
  name: load-rundown
- description: Move the rundown focus to the very first item.
  hints:
    idempotent: true
    readOnly: false
  name: focus-first-item
- description: Advance the rundown focus to the next item.
  hints:
    idempotent: false
    readOnly: false
  name: focus-next-item
- description: Move the rundown focus back to the previous item.
  hints:
    idempotent: false
    readOnly: false
  name: focus-previous-item
- description: Trigger playback of the currently focused rundown item, making the graphic visible in the live output.
  hints:
    destructive: false
    readOnly: false
  name: play-graphic
- description: Stop and remove the currently focused graphic from the live output.
  hints:
    destructive: false
    readOnly: false
  name: stop-graphic
- description: Issue a continue command to advance the currently focused graphic to its next animation state or page.
  hints:
    destructive: false
    readOnly: false
  name: continue-graphic
- description: Update the text, images, or other template field values for a specific rundown item identified by project, rundown, and item index.
  hints:
    idempotent: true
    readOnly: false
  name: update-graphic-data
- description: Directly play, continue, or stop a graphics template without needing it in a rundown. Useful for ad-hoc graphics or automated triggers.
  hints:
    destructive: false
    readOnly: false
  name: direct-playout
- description: List files available in a given subfolder of the SPX ASSETS directory. Useful for populating template dropdowns or media selection.
  hints:
    idempotent: true
    readOnly: true
  name: list-asset-files
- description: Call a named function in a custom SPX extension. Used for advanced graphics like sports scoring, live timing, and custom data-driven graphics.
  hints:
    destructive: false
    readOnly: false
  name: invoke-extension-function
---
