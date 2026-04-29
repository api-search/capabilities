---
categories: []
consumed_apis:
- location-service
description: Unified workflow capability for Amazon Location Service combining resource management and operations.
layout: capability
name: Amazon Location Service Workflow
operations: []
personas: []
provider_name: Amazon Location Service
provider_slug: amazon-location-service
search_terms:
- geocoding
- lists map resources in your aws account.
- geofencing
- map resources create map
- maps
- creates a map resource in your aws account.
- workflow
- retrieves the map resource details.
- map resources list maps
- unified workflow for amazon location service resource management
- map resources describe map
- manages resources and configurations
- integrates api into applications
- routing
- amazon location service
- aws
- Developer
- Administrator
- location
slug: amazon-location-service-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Location Service Workflow\n  description: Unified workflow capability for Amazon Location Service combining resource management and operations.\n  tags:\n  - Amazon Location Service\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: location-service\n    location: ./shared/location-service.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: location-service-api\n    description: REST API for Amazon Location Service workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: location-service-mcp\n    transport: http\n    description: MCP server for Amazon Location Service.\n    tools:\n    - name: map-resources-create-map\n      description: Creates a map resource in your AWS account.\n      hints:\n        readOnly:\
  \ false\n        idempotent: false\n      call: location-service.createmap\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: map-resources-list-maps\n      description: Lists map resources in your AWS account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: location-service.listmaps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: map-resources-describe-map\n      description: Retrieves the map resource details.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: location-service.describemap\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-location-service/refs/heads/main/capabilities/amazon-location-service-workflow.yaml
tags:
- Amazon Location Service
- AWS
- Workflow
tools:
- description: Creates a map resource in your AWS account.
  hints:
    idempotent: false
    readOnly: false
  name: map-resources-create-map
- description: Lists map resources in your AWS account.
  hints:
    idempotent: true
    readOnly: true
  name: map-resources-list-maps
- description: Retrieves the map resource details.
  hints:
    idempotent: true
    readOnly: true
  name: map-resources-describe-map
---
