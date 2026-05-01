---
api_specs:
- filename: amazon-app-mesh-openapi.yaml
  format: yaml
  label: amazon-app-mesh
  slug: amazon-app-mesh
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-app-mesh/refs/heads/main/openapi/amazon-app-mesh-openapi.yaml
categories: []
consumed_apis:
- amazon-app-mesh
description: Workflow for managing Amazon App Mesh API resources.
layout: capability
name: App Mesh Management
operations:
- description: List resources.
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon App Mesh
provider_slug: amazon-app-mesh
search_terms:
- list resources
- service mesh
- microservices
- aws
- DevOps Engineer
- amazon
- manage amazon app mesh api resources.
- engineer managing microservices networking infrastructure.
- Platform Engineer
- engineer managing service deployments and traffic routing.
- list resources.
- list amazon app mesh api resources.
- networking
slug: app-mesh-management
source_filename: app-mesh-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: App Mesh Management\n  description: Workflow for managing Amazon App Mesh API resources.\n  tags:\n  - Amazon\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: amazon-app-mesh\n    location: ./shared/amazon-app-mesh.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: app-mesh-management-api\n    resources:\n    - path: /v1/resources\n      name: resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List resources.\n        call: amazon-app-mesh.list-resources\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: app-mesh-management-mcp\n    transport: http\n    tools:\n    - name: list-resources\n\
  \      description: List Amazon App Mesh API resources.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: amazon-app-mesh.list-resources\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-app-mesh/refs/heads/main/capabilities/app-mesh-management.yaml
tags:
- Amazon
tools:
- description: List Amazon App Mesh API resources.
  hints:
    openWorld: false
    readOnly: true
  name: list-resources
---
