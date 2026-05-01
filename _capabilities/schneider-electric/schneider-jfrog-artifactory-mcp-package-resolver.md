---
categories: []
consumed_apis:
- schneider-electric
description: A capability that resolves an MCP-server allow-list entry to its JFrog Artifactory download URL with provenance + supply-chain-attestation tags.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider Jfrog Artifactory Mcp Package Resolver
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- that
- resolves
- server
- allow
slug: schneider-jfrog-artifactory-mcp-package-resolver
source_filename: schneider-jfrog-artifactory-mcp-package-resolver.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Jfrog Artifactory Mcp Package Resolver
    description: A capability that resolves an MCP-server allow-list entry to its JFrog Artifactory download URL with provenance + supply-chain-attestation tags.
    tags:
    - Schneider Electric
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: schneider-electric-env
    description: Schneider Electric credentials.
    keys:
      SCHNEIDER_ELECTRIC_API_KEY: SCHNEIDER_ELECTRIC_API_KEY
  capability:
    consumes:
    - namespace: schneider-electric
      type: http
      baseUri: https://api.schneider-electric.com
      authentication:
        type: bearer
        token: '{{SCHNEIDER_ELECTRIC_API_KEY}}'
      resources:
      - name: example
        path: /example
        operations:
        - name: example-op
          method: GET
    exposes:
    - type: rest
      address: 0.0.0.0
      port: 8080
      namespace: schneider-jfrog-artifactory-mcp-package-resolver-rest
      description: REST API for Schneider Electric Schneider Jfrog Artifactory Mcp Package Resolver.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: schneider-electric.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: schneider-jfrog-artifactory-mcp-package-resolver-mcp
      description: MCP server exposing Schneider Electric Schneider Jfrog Artifactory Mcp Package Resolver for AI agents.
      tools:
      - name: example
        description: A capability that resolves an MCP-server allow-list entry to its JFrog Artifactory download URL with provenance + supply-chain-attestation tags.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-jfrog-artifactory-mcp-package-resolver-skills
      description: Agent Skill bundle for Schneider Electric Schneider Jfrog Artifactory Mcp Package Resolver.
      skills:
      - name: schneider-jfrog-artifactory-mcp-package-resolver
        description: A capability that resolves an MCP-server allow-list entry to its JFrog Artifactory download URL with provenance + supply-chain-attestation tags.
        location: file:///opt/naftiko/skills/schneider-jfrog-artifactory-mcp-package-resolver
        allowed-tools: example
        tools:
        - name: example
          description: A capability that resolves an MCP-server allow-list entry to its JFrog Artifactory download URL with provenance + supply-chain-attestation tags.
          from:
            sourceNamespace: schneider-jfrog-artifactory-mcp-package-resolver-mcp
            action: example
---

A capability that resolves an MCP-server allow-list entry to its JFrog Artifactory download URL with provenance + supply-chain-attestation tags. He explicitly named JFrog as the package layer; bridging registry → JFrog is the second half of his architecture.
