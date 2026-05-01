---
categories: []
consumed_apis:
- bnp-paribas
description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Cedric MONIER
name: BNP Paribas Bnp Simcorp Bloomberg Portfolio Deterministic Bridge
operations: []
personas: []
provider_name: BNP Paribas
provider_slug: bnp-paribas
search_terms:
- composed
- capability
- over
- simcorp
- dimension
slug: bnp-simcorp-bloomberg-portfolio-deterministic-bridge
source_filename: bnp-simcorp-bloomberg-portfolio-deterministic-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: BNP Paribas Bnp Simcorp Bloomberg Portfolio Deterministic Bridge
    description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.
    tags:
    - BNP Paribas
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: bnp-paribas-env
    description: BNP Paribas credentials.
    keys:
      BNP_PARIBAS_API_KEY: BNP_PARIBAS_API_KEY
  capability:
    consumes:
    - namespace: bnp-paribas
      type: http
      baseUri: https://api.bnp-paribas.com
      authentication:
        type: bearer
        token: '{{BNP_PARIBAS_API_KEY}}'
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
      namespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-rest
      description: REST API for BNP Paribas Bnp Simcorp Bloomberg Portfolio Deterministic Bridge.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: bnp-paribas.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-mcp
      description: MCP server exposing BNP Paribas Bnp Simcorp Bloomberg Portfolio Deterministic Bridge for AI agents.
      tools:
      - name: example
        description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.
        hints:
          readOnly: true
        call: bnp-paribas.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-skills
      description: Agent Skill bundle for BNP Paribas Bnp Simcorp Bloomberg Portfolio Deterministic Bridge.
      skills:
      - name: bnp-simcorp-bloomberg-portfolio-deterministic-bridge
        description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.
        location: file:///opt/naftiko/skills/bnp-simcorp-bloomberg-portfolio-deterministic-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent.
          from:
            sourceNamespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-mcp
            action: example
---

A composed capability over SimCorp Dimension + Bloomberg AIM that returns a deterministic, schema-strict portfolio context object for an investment-bank agent. SimCorp + Bloomberg is BNP's investment-banking spine; deterministic bridges between them is the agent-era API-First proof.
