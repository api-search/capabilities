---
categories: []
consumed_apis: []
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
- check health
- mcp server registry search and discovery
- get skill details
- developer tools
- get complete details about a specific mcp server including its tools, resources, connection methods, and configuration
- check whether the smithery registry service is operational
- get server details
- list the release history and versions for an mcp server
- service health
- create service token
- large language models
- check registry health
- list skills
- smithery
- search and browse available skills
- get skill
- model context protocol
- search servers
- get full server details including tools and resources
- reusable ai skills
- mcp
- registry
- artificial intelligence
- list servers
- create a service token for machine-to-machine api authentication
- list server releases
- list releases for a server
- get server
- ai agents
- discovery
- search and browse mcp servers in the registry
- individual skill details
- server release history
- get detailed information about a specific smithery skill
- individual mcp server details
- search for reusable prompt-based skills that extend ai agent capabilities
- search skills
- list releases
- check service health status
- search the smithery registry for mcp servers by name, description, or capabilities using full-text and semantic search
slug: mcp-server-discovery
source_filename: mcp-server-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Smithery MCP Server Discovery\n  description: Workflow capability for discovering, evaluating, and managing Model Context Protocol servers in the Smithery\n    registry. Used by AI developers and platform engineers to find the right MCP capabilities, explore server details, browse\n    skills, and manage server releases.\n  tags:\n  - Smithery\n  - MCP\n  - AI Agents\n  - Registry\n  - Discovery\n  - Developer Tools\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SMITHERY_API_KEY: SMITHERY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: smithery-registry\n    baseUri: https://api.smithery.ai\n    description: Smithery Registry API for MCP server and skill management\n    authentication:\n      type: bearer\n      token: '{{SMITHERY_API_KEY}}'\n    resources:\n    - name: servers\n      path: /servers\n      description: MCP server registry\n      operations:\n      - name: list-servers\n\
  \        method: GET\n        description: Search and browse public MCP servers in the registry\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Full-text and semantic search query\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number (1-indexed)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page (1-100, default 10)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: server\n      path: /servers/{qualifiedName}\n      description: Individual MCP server management\n      operations:\n      - name: get-server\n        method: GET\n        description: Retrieve server details including tools and connections\n        inputParameters:\n        - name:\
  \ qualifiedName\n          in: path\n          type: string\n          required: true\n          description: The server qualified name (namespace/server)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-server\n        method: DELETE\n        description: Permanently delete a server and its resources\n        inputParameters:\n        - name: qualifiedName\n          in: path\n          type: string\n          required: true\n          description: The server qualified name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: server-releases\n      path: /servers/{qualifiedName}/releases\n      description: Server release management\n      operations:\n      - name: list-releases\n        method: GET\n        description: List releases ordered by most recent first\n        inputParameters:\n        -\
  \ name: qualifiedName\n          in: path\n          type: string\n          required: true\n          description: The server qualified name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: skills\n      path: /skills\n      description: Reusable skill discovery\n      operations:\n      - name: list-skills\n        method: GET\n        description: Search and browse reusable skills\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query for skills\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: skill\n      path: /skills/{namespace}/{slug}\n      description: Individual skill management\n\
  \      operations:\n      - name: get-skill\n        method: GET\n        description: Get a single skill by namespace and slug\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: The skill namespace\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: The skill slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens\n      path: /tokens\n      description: Service token management\n      operations:\n      - name: create-token\n        method: POST\n        description: Create a service token for machine-to-machine authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n\
  \            scopes: '{{tools.scopes}}'\n    - name: health\n      path: /health\n      description: Service health check\n      operations:\n      - name: check-health\n        method: GET\n        description: Check if the service is running\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mcp-discovery-api\n    description: Unified REST API for MCP server discovery and management.\n    resources:\n    - path: /v1/servers\n      name: servers\n      description: MCP server registry search and discovery\n      operations:\n      - method: GET\n        name: list-servers\n        description: Search and browse MCP servers in the registry\n        call: smithery-registry.list-servers\n        with:\n          q: rest.q\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/servers/{qualifiedName}\n      name: server\n      description: Individual MCP server details\n      operations:\n      - method: GET\n        name: get-server\n        description: Get full server details including tools and resources\n        call: smithery-registry.get-server\n        with:\n          qualifiedName: rest.qualifiedName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{qualifiedName}/releases\n      name: releases\n      description: Server release history\n      operations:\n      - method: GET\n        name: list-releases\n        description: List releases for a server\n        call: smithery-registry.list-releases\n        with:\n          qualifiedName: rest.qualifiedName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/skills\n      name: skills\n      description: Reusable AI skills\n      operations:\n      - method: GET\n        name: list-skills\n   \
  \     description: Search and browse available skills\n        call: smithery-registry.list-skills\n        with:\n          q: rest.q\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/skills/{namespace}/{slug}\n      name: skill\n      description: Individual skill details\n      operations:\n      - method: GET\n        name: get-skill\n        description: Get skill details\n        call: smithery-registry.get-skill\n        with:\n          namespace: rest.namespace\n          slug: rest.slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health\n      name: health\n      description: Service health\n      operations:\n      - method: GET\n        name: check-health\n        description: Check service health status\n        call: smithery-registry.check-health\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace:\
  \ mcp-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted MCP server and skill discovery.\n    tools:\n    - name: search-servers\n      description: Search the Smithery registry for MCP servers by name, description, or capabilities using full-text and\n        semantic search\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithery-registry.list-servers\n      with:\n        q: tools.q\n        page: tools.page\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-details\n      description: Get complete details about a specific MCP server including its tools, resources, connection methods, and\n        configuration\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithery-registry.get-server\n      with:\n        qualifiedName: tools.qualifiedName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-server-releases\n\
  \      description: List the release history and versions for an MCP server\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithery-registry.list-releases\n      with:\n        qualifiedName: tools.qualifiedName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-skills\n      description: Search for reusable prompt-based skills that extend AI agent capabilities\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithery-registry.list-skills\n      with:\n        q: tools.q\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-skill-details\n      description: Get detailed information about a specific Smithery skill\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithery-registry.get-skill\n      with:\n        namespace: tools.namespace\n        slug: tools.slug\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: create-service-token\n      description: Create a service token for machine-to-machine API authentication\n      hints:\n        readOnly: false\n        destructive: false\n      call: smithery-registry.create-token\n      with:\n        name: tools.name\n        scopes: tools.scopes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-registry-health\n      description: Check whether the Smithery registry service is operational\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithery-registry.check-health\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
