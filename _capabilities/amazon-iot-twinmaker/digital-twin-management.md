---
categories:
- iot
consumed_apis:
- iot-twinmaker
description: Unified capability for Solutions Architect, Industrial Engineer to manage create digital twins of physical systems and environments operations.
layout: capability
name: Amazon IoT TwinMaker - Digital Twin Management
operations:
- description: List Workspaces
  method: GET
  name: list-workspaces
  path: /v1/resources
personas: []
provider_name: Amazon IoT TwinMaker
provider_slug: amazon-iot-twinmaker
search_terms:
- list components
- list scenes
- create workspace
- amazon iot twinmaker resources
- amazon iot twinmaker list components
- update entity
- create digital twins of physical systems and environments.
- iot
- list workspaces
- amazon iot twinmaker list scenes
- manages amazon iot twinmaker resources and operations
- amazon iot twinmaker list workspaces
- amazon iot twinmaker create entity
- amazon iot twinmaker update entity
- amazon iot twinmaker create workspace
- list entities
- amazon iot twinmaker create scene
- create scene
- digital twin
- Industrial Engineer
- create entity
- Solutions Architect
- aws
- industrial iot
- 3d visualization
- amazon iot twinmaker list entities
slug: digital-twin-management
source_filename: digital-twin-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon IoT TwinMaker - Digital Twin Management\n  description: Unified capability for Solutions Architect, Industrial Engineer to manage create digital twins of physical systems and environments operations.\n  tags:\n    - IoT\n    - AWS\n    - Digital Twin\n    - Industrial IoT\n    - 3D Visualization\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: iot-twinmaker\n      location: ./shared/iot-twinmaker.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: digital-twin-management-api\n      description: Unified REST API for digital twin management.\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: Amazon IoT TwinMaker resources\n          operations:\n            - method: GET\n        \
  \      name: list-workspaces\n              description: List Workspaces\n              call: \"iot-twinmaker.list-workspaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: digital-twin-management-mcp\n      transport: http\n      description: MCP server for AI-assisted digital twin management.\n      tools:\n        - name: list-workspaces\n          description: Amazon IoT TwinMaker List Workspaces\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-twinmaker.list-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-workspace\n          description: Amazon IoT TwinMaker Create Workspace\n          hints:\n            readOnly: false\n            \n          call: \"iot-twinmaker.create-workspace\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n\n        - name: list-scenes\n          description: Amazon IoT TwinMaker List Scenes\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-twinmaker.list-scenes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-scene\n          description: Amazon IoT TwinMaker Create Scene\n          hints:\n            readOnly: false\n            \n          call: \"iot-twinmaker.create-scene\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-entities\n          description: Amazon IoT TwinMaker List Entities\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-twinmaker.list-entities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-entity\n          description: Amazon IoT TwinMaker Create\
  \ Entity\n          hints:\n            readOnly: false\n            \n          call: \"iot-twinmaker.create-entity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-components\n          description: Amazon IoT TwinMaker List Components\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-twinmaker.list-components\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-entity\n          description: Amazon IoT TwinMaker Update Entity\n          hints:\n            readOnly: false\n            \n          call: \"iot-twinmaker.update-entity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iot-twinmaker/refs/heads/main/capabilities/digital-twin-management.yaml
tags:
- IoT
- Digital Twin
- Industrial IoT
- 3D Visualization
tools:
- description: Amazon IoT TwinMaker List Workspaces
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: Amazon IoT TwinMaker Create Workspace
  hints:
    readOnly: false
  name: create-workspace
- description: Amazon IoT TwinMaker List Scenes
  hints:
    openWorld: true
    readOnly: true
  name: list-scenes
- description: Amazon IoT TwinMaker Create Scene
  hints:
    readOnly: false
  name: create-scene
- description: Amazon IoT TwinMaker List Entities
  hints:
    openWorld: true
    readOnly: true
  name: list-entities
- description: Amazon IoT TwinMaker Create Entity
  hints:
    readOnly: false
  name: create-entity
- description: Amazon IoT TwinMaker List Components
  hints:
    openWorld: true
    readOnly: true
  name: list-components
- description: Amazon IoT TwinMaker Update Entity
  hints:
    readOnly: false
  name: update-entity
---
