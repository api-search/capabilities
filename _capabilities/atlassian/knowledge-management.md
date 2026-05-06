---
categories: []
consumed_apis: []
description: Knowledge management workflow combining Confluence Content, Space, Search, Template, Label, and User APIs for technical writers and team leads to create, organize, and share documentation.
layout: capability
name: Atlassian Knowledge Management
operations:
- description: List Confluence content
  method: GET
  name: list-content
  path: /v1/content
- description: List Confluence spaces
  method: GET
  name: list-spaces
  path: /v1/spaces
- description: Search Confluence content
  method: GET
  name: search-content
  path: /v1/search
personas: []
provider_name: Atlassian
provider_slug: atlassian
search_terms:
- search confluence content using cql
- knowledge management
- search confluence content
- list templates
- confluence
- list confluence content
- space management
- content search
- content management
- software development
- list confluence users
- atlassian
- productivity
- list confluence spaces
- list confluence groups
- code
- list spaces
- search content
- list confluence templates
- list confluence pages and blog posts
- list content
- list users
- platform
- list groups
- collaboration
slug: knowledge-management
source_filename: knowledge-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Atlassian Knowledge Management\n  description: Knowledge management workflow combining Confluence Content, Space, Search, Template, Label, and User APIs for\n    technical writers and team leads to create, organize, and share documentation.\n  tags:\n  - Atlassian\n  - Confluence\n  - Knowledge Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ATLASSIAN_API_TOKEN: ATLASSIAN_API_TOKEN\n    ATLASSIAN_EMAIL: ATLASSIAN_EMAIL\n    ATLASSIAN_SITE: ATLASSIAN_SITE\ncapability:\n  consumes:\n  - type: http\n    namespace: atlassian-admin\n    baseUri: https://api.atlassian.com\n    description: Atlassian Admin API for organization management.\n    authentication:\n      type: bearer\n      token: '{{ATLASSIAN_API_TOKEN}}'\n    resources:\n    - name: organizations\n      path: /v1/orgs\n      description: Organization management\n      operations:\n      - name: list-organizations\n        method:\
  \ GET\n        description: List accessible organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-organization\n        method: GET\n        description: Get organization details\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /v1/orgs/{orgId}/users\n      description: User management within organization\n      operations:\n      - name: list-users\n        method: GET\n        description: List users in organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: domains\n      path: /v1/orgs/{orgId}/domains\n      description: Domain management\n      operations:\n      - name: list-domains\n        method: GET\n        description: List domains in organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /v1/orgs/{orgId}/groups\n      description: Group management\n      operations:\n      - name: list-groups\n        method: GET\n        description: List groups in organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /v1/orgs/{orgId}/policies\n      description: Policy management\n      operations:\n      - name: list-policies\n        method: GET\n        description: List organization policies\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /v1/orgs/{orgId}/events\n      description: Audit events\n      operations:\n      - name: list-events\n        method: GET\n        description: List organization audit events\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: atlassian-knowledge-api\n    description: Unified REST API for Confluence knowledge management.\n    resources:\n    - path: /v1/content\n      name: content\n      description: Content management\n      operations:\n      - method: GET\n        name: list-content\n        description: List Confluence content\n        call: atlassian-admin.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spaces\n      name: spaces\n      description: Space management\n      operations:\n      - method: GET\n        name: list-spaces\n        description: List Confluence spaces\n        call: atlassian-admin.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Content search\n      operations:\n      - method: GET\n\
  \        name: search-content\n        description: Search Confluence content\n        call: atlassian-admin.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: atlassian-knowledge-mcp\n    transport: http\n    description: MCP server for AI-assisted Confluence knowledge management.\n    tools:\n    - name: list-content\n      description: List Confluence pages and blog posts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-content\n      description: Search Confluence content using CQL\n      hints:\n        readOnly: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-spaces\n      description: List Confluence spaces\n      hints:\n        readOnly: true\n      call:\
  \ atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-templates\n      description: List Confluence templates\n      hints:\n        readOnly: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List Confluence groups\n      hints:\n        readOnly: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List Confluence users\n      hints:\n        readOnly: true\n      call: atlassian-admin.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/atlassian/refs/heads/main/capabilities/knowledge-management.yaml
tags:
- Atlassian
- Confluence
- Knowledge Management
tools:
- description: List Confluence pages and blog posts
  hints:
    openWorld: true
    readOnly: true
  name: list-content
- description: Search Confluence content using CQL
  hints:
    readOnly: true
  name: search-content
- description: List Confluence spaces
  hints:
    readOnly: true
  name: list-spaces
- description: List Confluence templates
  hints:
    readOnly: true
  name: list-templates
- description: List Confluence groups
  hints:
    readOnly: true
  name: list-groups
- description: List Confluence users
  hints:
    readOnly: true
  name: list-users
---
