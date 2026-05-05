---
api_specs:
- filename: spaceapi-collector-openapi.yml
  format: yaml
  label: spaceapi-collector
  slug: spaceapi-collector
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spaceapi/refs/heads/main/openapi/spaceapi-collector-openapi.yml
categories: []
consumed_apis:
- spaceapi-collector
description: Workflow capability for discovering and browsing hackerspaces, makerspaces, fablabs, and community spaces worldwide using the SpaceAPI directory. Useful for applications that want to help users find nearby spaces or display real-time space status.
layout: capability
name: SpaceAPI Space Discovery
operations:
- description: List all registered hackerspaces, makerspaces, and fablabs
  method: GET
  name: list-spaces
  path: /v1/spaces
personas: []
provider_name: SpaceAPI
provider_slug: spaceapi
search_terms:
- community
- list spaces
- directory
- hackerspaces
- list all registered hackerspaces, makerspaces, and fablabs
- event spaces
- all registered spaceapi spaces in the global directory
- maker spaces
- co-working
- open standard
- list all hackerspaces, makerspaces, and fablabs registered in the spaceapi directory
slug: space-discovery
source_filename: space-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: SpaceAPI Space Discovery\n  description: >-\n    Workflow capability for discovering and browsing hackerspaces, makerspaces, fablabs,\n    and community spaces worldwide using the SpaceAPI directory. Useful for applications\n    that want to help users find nearby spaces or display real-time space status.\n  tags:\n    - Co-Working\n    - Maker Spaces\n    - Hackerspaces\n    - Directory\n    - Community\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\ncapability:\n  consumes:\n    - import: spaceapi-collector\n      location: ./shared/spaceapi-collector.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: space-discovery-api\n      description: Unified REST API for discovering community spaces via SpaceAPI.\n      resources:\n        - path: /v1/spaces\n          name: spaces\n          description: All registered SpaceAPI spaces in the global directory\n          operations:\n            - method: GET\n\
  \              name: list-spaces\n              description: List all registered hackerspaces, makerspaces, and fablabs\n              call: \"spaceapi-collector.list-spaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: space-discovery-mcp\n      transport: http\n      description: MCP server for AI-assisted discovery of global community spaces.\n      tools:\n        - name: list-spaces\n          description: List all hackerspaces, makerspaces, and fablabs registered in the SpaceAPI directory\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spaceapi-collector.list-spaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spaceapi/refs/heads/main/capabilities/space-discovery.yaml
tags:
- Co-Working
- Maker Spaces
- Hackerspaces
- Directory
- Community
tools:
- description: List all hackerspaces, makerspaces, and fablabs registered in the SpaceAPI directory
  hints:
    openWorld: true
    readOnly: true
  name: list-spaces
---
