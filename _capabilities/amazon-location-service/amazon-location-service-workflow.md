---
categories: []
consumed_apis: []
description: Unified workflow capability for Amazon Location Service combining resource management and operations.
layout: capability
name: Amazon Location Service Workflow
operations: []
personas: []
provider_name: Amazon Location Service
provider_slug: amazon-location-service
search_terms:
- Administrator
- aws
- workflow
- Developer
- integrates api into applications
- retrieves the map resource details.
- map resources create map
- map resources describe map
- routing
- geofencing
- manages resources and configurations
- unified workflow for amazon location service resource management
- maps
- location
- amazon location service
- map resources list maps
- creates a map resource in your aws account.
- geocoding
- lists map resources in your aws account.
slug: amazon-location-service-workflow
source_filename: amazon-location-service-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Location Service Workflow\n  description: Unified workflow capability for Amazon Location Service combining resource management and operations.\n  tags:\n  - Amazon Location Service\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: location-service\n    baseUri: https://geo.us-east-1.amazonaws.com\n    description: Amazon Location Service service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: map-resources\n      path: /maps\n      description: Map resource management\n      operations:\n      - name: createmap\n        method: POST\n        description: Creates a map resource in your AWS account.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listmaps\n        method: GET\n        description: Lists map resources in your AWS account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describemap\n        method: GET\n        description: Retrieves the map resource details.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: location-service-api\n    description: REST API for Amazon Location Service workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: location-service-mcp\n    transport: http\n    description: MCP server for Amazon Location Service.\n    tools:\n    - name: map-resources-create-map\n      description: Creates a map resource in your AWS account.\n \
  \     hints:\n        readOnly: false\n        idempotent: false\n      call: location-service.createmap\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: map-resources-list-maps\n      description: Lists map resources in your AWS account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: location-service.listmaps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: map-resources-describe-map\n      description: Retrieves the map resource details.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: location-service.describemap\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-location-service/refs/heads/main/capabilities/amazon-location-service-workflow.yaml
tags:
- Amazon Location Service
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
