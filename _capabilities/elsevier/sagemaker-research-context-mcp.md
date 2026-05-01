---
categories: []
consumed_apis:
- elsevier
description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Joyce Stack
name: Elsevier Sagemaker Research Context Mcp
operations: []
personas: []
provider_name: Elsevier
provider_slug: elsevier
search_terms:
- capability
- over
- amazon
- sagemaker
- model
slug: sagemaker-research-context-mcp
source_filename: sagemaker-research-context-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Elsevier Sagemaker Research Context Mcp
    description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
    tags:
    - Elsevier
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: elsevier-env
    description: Elsevier credentials.
    keys:
      ELSEVIER_API_KEY: ELSEVIER_API_KEY
  capability:
    consumes:
    - namespace: elsevier
      type: http
      baseUri: https://api.elsevier.com
      authentication:
        type: bearer
        token: '{{ELSEVIER_API_KEY}}'
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
      namespace: sagemaker-research-context-mcp-rest
      description: REST API for Elsevier Sagemaker Research Context Mcp.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: elsevier.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: sagemaker-research-context-mcp-mcp
      description: MCP server exposing Elsevier Sagemaker Research Context Mcp for AI agents.
      tools:
      - name: example
        description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
        hints:
          readOnly: true
        call: elsevier.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: sagemaker-research-context-mcp-skills
      description: Agent Skill bundle for Elsevier Sagemaker Research Context Mcp.
      skills:
      - name: sagemaker-research-context-mcp
        description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
        location: file:///opt/naftiko/skills/sagemaker-research-context-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
          from:
            sourceNamespace: sagemaker-research-context-mcp-mcp
            action: example
---

A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant. Research-AI on SageMaker is an Elsevier-shaped surface; agent-callable inference is the dual-track-proposal anchor.
