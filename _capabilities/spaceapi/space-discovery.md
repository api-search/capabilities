---
categories: []
consumed_apis: []
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
- directory
- all registered spaceapi spaces in the global directory
- list all registered hackerspaces, makerspaces, and fablabs
- community
- open standard
- maker spaces
- hackerspaces
- co-working
- list all hackerspaces, makerspaces, and fablabs registered in the spaceapi directory
- event spaces
- list spaces
slug: space-discovery
source_filename: space-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SpaceAPI Space Discovery\n  description: Workflow capability for discovering and browsing hackerspaces, makerspaces, fablabs, and community spaces worldwide\n    using the SpaceAPI directory. Useful for applications that want to help users find nearby spaces or display real-time\n    space status.\n  tags:\n  - Co-Working\n  - Maker Spaces\n  - Hackerspaces\n  - Directory\n  - Community\n  created: '2026-05-02'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: spaceapi-collector\n    baseUri: https://collector.spaceapi.io\n    description: SpaceAPI Collector directory API\n    resources:\n    - name: directory\n      path: /\n      description: Full directory of all registered SpaceAPI spaces\n      operations:\n      - name: list-spaces\n        method: GET\n        description: Returns the full list of registered hackerspaces and makerspaces\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: space-discovery-api\n    description: Unified REST API for discovering community spaces via SpaceAPI.\n    resources:\n    - path: /v1/spaces\n      name: spaces\n      description: All registered SpaceAPI spaces in the global directory\n      operations:\n      - method: GET\n        name: list-spaces\n        description: List all registered hackerspaces, makerspaces, and fablabs\n        call: spaceapi-collector.list-spaces\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: space-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted discovery of global community spaces.\n    tools:\n    - name: list-spaces\n      description: List all hackerspaces, makerspaces, and fablabs registered in the SpaceAPI directory\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: spaceapi-collector.list-spaces\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
