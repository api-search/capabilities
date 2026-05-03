---
categories: []
consumed_apis: []
description: Manage services, AI models, teams, and subscribers across the APIPark developer platform
layout: capability
name: Platform Management
operations:
- description: ''
  method: GET
  name: ''
  path: /services
- description: ''
  method: GET
  name: ''
  path: /ai-models
- description: ''
  method: GET
  name: ''
  path: /teams
- description: ''
  method: GET
  name: ''
  path: /subscribers
personas: []
provider_name: APIPark
provider_slug: apipark
search_terms:
- list services
- list all api services published on the apipark developer platform
- list subscribers
- list all api subscribers on the platform
- list ai models
- open source
- list all api services published on the platform
- api management
- ai gateway
- list teams
- create service
- api gateway
- list all ai models available on the apipark platform including provider and capabilities
- publish a new api service on the apipark platform
- list all ai models available on the platform
- developer portal
- llm
- list all teams registered on the platform
- list all teams registered on the apipark platform with their members and permissions
- list all api subscribers and their active subscriptions on the apipark platform
slug: platform-management
source_filename: platform-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  name: APIPark Platform Management\n  description: Manage services, AI models, teams, and subscribers across the APIPark developer platform\n  version: 1.0.0\n\nimport:\n  - name: apipark\n    location: shared/platform.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8131\n      namespace: apipark-platform-rest\n      resources:\n        - path: \"/services\"\n          name: services\n          label: \"List Services\"\n          description: \"List all API services published on the platform\"\n          operations:\n            - method: GET\n              call: apipark.listServices\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n                  items:\n                    type: object\n\n        - path: \"/ai-models\"\n          name: aiModels\n          label: \"List AI Models\"\n          description: \"List all AI models available on the platform\"\n          operations:\n\
  \            - method: GET\n              call: apipark.listAiModels\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n                  items:\n                    type: object\n\n        - path: \"/teams\"\n          name: teams\n          label: \"List Teams\"\n          description: \"List all teams registered on the platform\"\n          operations:\n            - method: GET\n              call: apipark.listTeams\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n                  items:\n                    type: object\n\n        - path: \"/subscribers\"\n          name: subscribers\n          label: \"List Subscribers\"\n          description: \"List all API subscribers on the platform\"\n          operations:\n            - method: GET\n              call: apipark.listSubscribers\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\
  \                  items:\n                    type: object\n\n    - type: mcp\n      address: \"0.0.0.0\"\n      port: 9131\n      namespace: apipark-management\n      description: \"APIPark platform management — discover services, inspect AI models, list teams, and manage subscribers\"\n      tools:\n        - name: list-services\n          description: \"List all API services published on the APIPark developer platform\"\n          hints:\n            readOnly: true\n          call: apipark.listServices\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n              items:\n                type: object\n\n        - name: create-service\n          description: \"Publish a new API service on the APIPark platform\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: apipark.createService\n          inputParameters:\n            - name: body\n              type: object\n    \
  \          required: true\n              description: \"Service definition including name, description, and API configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ai-models\n          description: \"List all AI models available on the APIPark platform including provider and capabilities\"\n          hints:\n            readOnly: true\n          call: apipark.listAiModels\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n              items:\n                type: object\n\n        - name: list-teams\n          description: \"List all teams registered on the APIPark platform with their members and permissions\"\n          hints:\n            readOnly: true\n          call: apipark.listTeams\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n              items:\n                type: object\n\n        - name: list-subscribers\n         \
  \ description: \"List all API subscribers and their active subscriptions on the APIPark platform\"\n          hints:\n            readOnly: true\n          call: apipark.listSubscribers\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n              items:\n                type: object\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apipark/refs/heads/main/capabilities/platform-management.yaml
tags: []
tools:
- description: List all API services published on the APIPark developer platform
  hints:
    readOnly: true
  name: list-services
- description: Publish a new API service on the APIPark platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-service
- description: List all AI models available on the APIPark platform including provider and capabilities
  hints:
    readOnly: true
  name: list-ai-models
- description: List all teams registered on the APIPark platform with their members and permissions
  hints:
    readOnly: true
  name: list-teams
- description: List all API subscribers and their active subscriptions on the APIPark platform
  hints:
    readOnly: true
  name: list-subscribers
---
