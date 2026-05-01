---
api_specs:
- filename: amazon-app-studio-openapi.yaml
  format: yaml
  label: amazon-app-studio
  slug: amazon-app-studio
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-app-studio/refs/heads/main/openapi/amazon-app-studio-openapi.yaml
categories: []
consumed_apis:
- amazon-app-studio
description: Workflow for managing App Studio low-code applications.
layout: capability
name: Amazon App Studio Application Management
operations:
- description: List applications.
  method: GET
  name: list-apps
  path: /v1/apps
personas: []
provider_name: Amazon App Studio
provider_slug: amazon-app-studio
search_terms:
- list app studio apps
- generative ai
- list all amazon app studio applications in the account.
- list applications.
- get details for a specific app studio application by id.
- manage app studio low-code applications.
- business user building internal tools with app studio.
- Business Developer
- no-code
- list apps
- app studio
- aws
- IT Administrator
- low-code
- internal tools
- it admin managing app studio deployments and access.
- get app studio app
- amazon
slug: app-studio-management
source_filename: app-studio-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon App Studio Application Management\n  description: Workflow for managing App Studio low-code applications.\n  tags:\n  - Amazon\n  - App Studio\n  - AWS\n  - Low-Code\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: amazon-app-studio\n    location: ./shared/amazon-app-studio.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: app-studio-management-api\n    resources:\n    - path: /v1/apps\n      name: apps\n      operations:\n      - method: GET\n        name: list-apps\n        description: List applications.\n        call: amazon-app-studio.list-apps\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: app-studio-management-mcp\n    transport:\
  \ http\n    tools:\n    - name: list-app-studio-apps\n      description: List all Amazon App Studio applications in the account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: amazon-app-studio.list-apps\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-app-studio-app\n      description: Get details for a specific App Studio application by ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: amazon-app-studio.get-app\n      with:\n        appId: tools.appId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-app-studio/refs/heads/main/capabilities/app-studio-management.yaml
tags:
- Amazon
- App Studio
- AWS
- Low-Code
tools:
- description: List all Amazon App Studio applications in the account.
  hints:
    openWorld: false
    readOnly: true
  name: list-app-studio-apps
- description: Get details for a specific App Studio application by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-app-studio-app
---
