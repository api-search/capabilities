---
categories: []
consumed_apis:
- smithery-registry
description: Workflow capability for discovering, evaluating, and managing Model Context Protocol servers in the Smithery registry. Used by AI developers and platform engineers to find the right MCP capabilities, explore server details, browse skills, and manage server releases.
layout: capability
name: Smithery MCP Server Discovery
operations:
- description: Search and browse MCP servers in the registry
  method: GET
  name: list-servers
  path: /v1/servers
- description: Get full server details including tools and resources
  method: GET
  name: get-server
  path: /v1/servers/{qualifiedName}
- description: List releases for a server
  method: GET
  name: list-releases
  path: /v1/servers/{qualifiedName}/releases
- description: Search and browse available skills
  method: GET
  name: list-skills
  path: /v1/skills
- description: Get skill details
  method: GET
  name: get-skill
  path: /v1/skills/{namespace}/{slug}
- description: Check service health status
  method: GET
  name: check-health
  path: /v1/health
personas: []
provider_name: Smithery
provider_slug: smithery
search_terms:
- list skills
- list servers
- ai agents
- list the release history and versions for an mcp server
- individual skill details
- get skill
- list server releases
- large language models
- server release history
- search for reusable prompt-based skills that extend ai agent capabilities
- search the smithery registry for mcp servers by name, description, or capabilities using full-text and semantic search
- get skill details
- get full server details including tools and resources
- search skills
- check registry health
- check service health status
- registry
- check health
- get server details
- search and browse mcp servers in the registry
- list releases
- developer tools
- get detailed information about a specific smithery skill
- artificial intelligence
- smithery
- mcp server registry search and discovery
- list releases for a server
- mcp
- discovery
- individual mcp server details
- search and browse available skills
- create a service token for machine-to-machine api authentication
- create service token
- reusable ai skills
- service health
- get server
- check whether the smithery registry service is operational
- search servers
- model context protocol
- get complete details about a specific mcp server including its tools, resources, connection methods, and configuration
slug: mcp-server-discovery
source_filename: mcp-server-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Smithery MCP Server Discovery\n  description: >-\n    Workflow capability for discovering, evaluating, and managing Model Context\n    Protocol servers in the Smithery registry. Used by AI developers and platform\n    engineers to find the right MCP capabilities, explore server details, browse\n    skills, and manage server releases.\n  tags:\n    - Smithery\n    - MCP\n    - AI Agents\n    - Registry\n    - Discovery\n    - Developer Tools\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SMITHERY_API_KEY: SMITHERY_API_KEY\n\ncapability:\n  consumes:\n    - import: smithery-registry\n      location: ./shared/registry-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: mcp-discovery-api\n      description: Unified REST API for MCP server discovery and management.\n      resources:\n        - path: /v1/servers\n          name: servers\n          description:\
  \ MCP server registry search and discovery\n          operations:\n            - method: GET\n              name: list-servers\n              description: Search and browse MCP servers in the registry\n              call: \"smithery-registry.list-servers\"\n              with:\n                q: \"rest.q\"\n                page: \"rest.page\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/servers/{qualifiedName}\n          name: server\n          description: Individual MCP server details\n          operations:\n            - method: GET\n              name: get-server\n              description: Get full server details including tools and resources\n              call: \"smithery-registry.get-server\"\n              with:\n                qualifiedName: \"rest.qualifiedName\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/servers/{qualifiedName}/releases\n          name: releases\n          description: Server release history\n          operations:\n            - method: GET\n              name: list-releases\n              description: List releases for a server\n              call: \"smithery-registry.list-releases\"\n              with:\n                qualifiedName: \"rest.qualifiedName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/skills\n          name: skills\n          description: Reusable AI skills\n          operations:\n            - method: GET\n              name: list-skills\n              description: Search and browse available skills\n              call: \"smithery-registry.list-skills\"\n              with:\n                q: \"rest.q\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    \
  \    - path: /v1/skills/{namespace}/{slug}\n          name: skill\n          description: Individual skill details\n          operations:\n            - method: GET\n              name: get-skill\n              description: Get skill details\n              call: \"smithery-registry.get-skill\"\n              with:\n                namespace: \"rest.namespace\"\n                slug: \"rest.slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health\n          name: health\n          description: Service health\n          operations:\n            - method: GET\n              name: check-health\n              description: Check service health status\n              call: \"smithery-registry.check-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: mcp-discovery-mcp\n      transport: http\n      description:\
  \ MCP server for AI-assisted MCP server and skill discovery.\n      tools:\n        - name: search-servers\n          description: >-\n            Search the Smithery registry for MCP servers by name, description,\n            or capabilities using full-text and semantic search\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithery-registry.list-servers\"\n          with:\n            q: \"tools.q\"\n            page: \"tools.page\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-server-details\n          description: >-\n            Get complete details about a specific MCP server including its tools,\n            resources, connection methods, and configuration\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithery-registry.get-server\"\n          with:\n            qualifiedName: \"tools.qualifiedName\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-server-releases\n          description: List the release history and versions for an MCP server\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithery-registry.list-releases\"\n          with:\n            qualifiedName: \"tools.qualifiedName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-skills\n          description: >-\n            Search for reusable prompt-based skills that extend AI agent capabilities\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithery-registry.list-skills\"\n          with:\n            q: \"tools.q\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-skill-details\n          description: Get detailed\
  \ information about a specific Smithery skill\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithery-registry.get-skill\"\n          with:\n            namespace: \"tools.namespace\"\n            slug: \"tools.slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-service-token\n          description: Create a service token for machine-to-machine API authentication\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"smithery-registry.create-token\"\n          with:\n            name: \"tools.name\"\n            scopes: \"tools.scopes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-registry-health\n          description: Check whether the Smithery registry service is operational\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"smithery-registry.check-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/smithery/refs/heads/main/capabilities/mcp-server-discovery.yaml
tags:
- Smithery
- MCP
- AI Agents
- Registry
- Discovery
- Developer Tools
tools:
- description: Search the Smithery registry for MCP servers by name, description, or capabilities using full-text and semantic search
  hints:
    openWorld: true
    readOnly: true
  name: search-servers
- description: Get complete details about a specific MCP server including its tools, resources, connection methods, and configuration
  hints:
    openWorld: true
    readOnly: true
  name: get-server-details
- description: List the release history and versions for an MCP server
  hints:
    openWorld: true
    readOnly: true
  name: list-server-releases
- description: Search for reusable prompt-based skills that extend AI agent capabilities
  hints:
    openWorld: true
    readOnly: true
  name: search-skills
- description: Get detailed information about a specific Smithery skill
  hints:
    openWorld: true
    readOnly: true
  name: get-skill-details
- description: Create a service token for machine-to-machine API authentication
  hints:
    destructive: false
    readOnly: false
  name: create-service-token
- description: Check whether the Smithery registry service is operational
  hints:
    openWorld: true
    readOnly: true
  name: check-registry-health
---
