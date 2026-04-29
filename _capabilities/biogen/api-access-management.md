---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Api Access Management
operations: []
personas: []
provider_name: Biogen
provider_slug: biogen
search_terms:
- life sciences
- api key lifecycle and access management
- neurology
- healthcare
- pharmaceuticals
- discovery of available biogen api services
- developer integrating with biogen pharmaceutical services apis
- biotechnology
- discover and manage access to biogen pharmaceutical apis
slug: api-access-management
source_filename: api-access-management.yaml
source_heading: Capability Spec
source_yaml: "name: API Access Management\ndescription: >-\n  Workflow capability for managing access to Biogen APIs including service\n  discovery and API key lifecycle management.\nversion: v1\n\nimports:\n  - shared/biogen.yaml\n\ntools:\n  - name: list-services\n    import: biogen.list-services\n    description: List all Biogen API services available with your credentials.\n  - name: list-api-keys\n    import: biogen.list-api-keys\n    description: List all API keys for the authenticated developer account with usage statistics.\n  - name: create-api-key\n    import: biogen.create-api-key\n    description: Create a new API key for accessing Biogen services.\n    inputSchema:\n      type: object\n      required:\n        - name\n      properties:\n        name:\n          type: string\n          description: Display name for the API key\n        description:\n          type: string\n          description: Optional description for the key\n\nexpose:\n  rest:\n    port: 8080\n  mcp:\n  \
  \  port: 9080\n\npersonas:\n  - id: developer\n    name: Developer\n    description: Developer integrating with Biogen pharmaceutical services APIs\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/biogen/refs/heads/main/capabilities/api-access-management.yaml
tags: []
tools: []
---
