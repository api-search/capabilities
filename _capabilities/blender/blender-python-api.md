---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Blender Python Api
operations: []
personas: []
provider_name: Blender
provider_slug: blender
search_terms:
- python
- animation
- modeling
- game development
- vfx
- open source
- rendering
- 3d
slug: blender-python-api
source_filename: blender-python-api.yaml
source_heading: Capability Spec
source_yaml: "name: Blender Python API Capability\ndescription: >-\n  Naftiko capability definition for the Blender Python API (bpy), documenting\n  key scripting capabilities for automation, addon development, and pipeline integration.\nversion: 1.0.0\ncapabilities:\n  - name: accessSceneData\n    description: Access and modify scene objects, materials, and properties via bpy.data and bpy.context\n    module: bpy.data\n    examples:\n      - \"bpy.data.objects['Cube']\"\n      - \"bpy.context.active_object\"\n  - name: executeOperator\n    description: Execute built-in or custom Blender operators via bpy.ops\n    module: bpy.ops\n    examples:\n      - \"bpy.ops.object.transform_apply(scale=True)\"\n      - \"bpy.ops.render.render(write_still=True)\"\n  - name: createCustomOperator\n    description: Define and register custom operators via bpy.types.Operator subclass\n    module: bpy.types\n  - name: modifyMesh\n    description: Create and edit mesh geometry at the vertex/edge/face level\
  \ via bmesh\n    module: bmesh\n    examples:\n      - \"bm = bmesh.new(); bm.from_mesh(mesh)\"\n  - name: batchRender\n    description: Execute headless rendering via CLI and bpy.ops.render.render\n    module: bpy.ops.render\n    cli: \"blender --background scene.blend --python render.py\"\n  - name: importExport\n    description: Import and export 3D formats (glTF, FBX, OBJ, USD) via bpy.ops\n    module: bpy.ops\n    examples:\n      - \"bpy.ops.export_scene.gltf(filepath='output.glb')\"\n      - \"bpy.ops.wm.usd_export(filepath='scene.usda')\"\n  - name: registerAddon\n    description: Register and package Blender addons for the Extensions Platform\n    module: bpy.utils\n    examples:\n      - \"bpy.utils.register_class(MyOperator)\"\n      - \"bpy.utils.unregister_class(MyOperator)\"\ngovernance:\n  license: GPL-2.0-or-later\n  repository: https://github.com/blender/blender\n  governance: https://www.blender.org/foundation/\n  packageRegistry: https://extensions.blender.org\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/blender/refs/heads/main/capabilities/blender-python-api.yaml
tags: []
tools: []
---
