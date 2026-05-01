---
categories: []
consumed_apis: []
description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Joyce Stack
name: Sagemaker Research Context Mcp
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
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
  title: Sagemaker Research Context Mcp
  description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
  tags:
  Naftiko
  created:'2026-05-01'
  modified:'2026-05-01'
  binds:
  namespace: naftiko-env
  description: Naftiko credentials.
  keys:
  NAFTIKO_API_KEY: NAFTIKO_API_KEY
  capability:
  consumes:
  namespace: naftiko
  type: http
  baseUri: https://api.naftiko.com
  authentication:
  type: bearer
  token:'{{NAFTIKO_API_KEY}}'
  resources:
  name: example
  path: /example
  operations:
  name: example-op
  method: GET
  exposes:
  type: rest
  address: 0.0.0.0
  port: 8080
  namespace: sagemaker-research-context-mcp-rest
  description: REST API for Sagemaker Research Context Mcp.
  resources:
  name: example
  path: /example
  operations:
  method: GET
  name: example-op
  call: naftiko.example-op
  type: mcp
  address: 0.0.0.0
  port: 3010
  namespace: sagemaker-research-context-mcp-mcp
  description: MCP server exposing Sagemaker Research Context Mcp for AI agents.
  tools:
  name: example
  description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: sagemaker-research-context-mcp-skills
  description: Agent Skill bundle for Sagemaker Research Context Mcp.
  skills:
  name: sagemaker-research-context-mcp
  description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
  location: file:///opt/naftiko/skills/sagemaker-research-context-mcp
  allowed-tools: example
  tools:
  name: example
  description: A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
  from:
  sourceNamespace: sagemaker-research-context-mcp-mcp
  action: example
---

A capability over Amazon SageMaker model endpoints exposing inference as MCP tools with shaped output for a research-AI assistant.
