---
categories: []
consumed_apis:
- bloomberg
description: A composite capability that joins Bloomberg AIM + Bloomberg Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Amit Mahale
name: Bloomberg Aim Portfolio Tradeweb Cross Source Composer
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- composite
- capability
- that
- joins
- bloomberg
slug: aim-portfolio-tradeweb-cross-source-composer
source_filename: aim-portfolio-tradeweb-cross-source-composer.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Aim Portfolio Tradeweb Cross Source Composer
    description: A composite capability that joins Bloomberg AIM + Bloomberg Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.
    tags:
    - Bloomberg
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: bloomberg-env
    description: Bloomberg credentials.
    keys:
      BLOOMBERG_API_KEY: BLOOMBERG_API_KEY
  capability:
    consumes:
    - namespace: bloomberg
      type: http
      baseUri: https://api.bloomberg.com
      authentication:
        type: bearer
        token: '{{BLOOMBERG_API_KEY}}'
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
      namespace: aim-portfolio-tradeweb-cross-source-composer-rest
      description: REST API for Bloomberg Aim Portfolio Tradeweb Cross Source Composer.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: bloomberg.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: aim-portfolio-tradeweb-cross-source-composer-mcp
      description: MCP server exposing Bloomberg Aim Portfolio Tradeweb Cross Source Composer for AI agents.
      tools:
      - name: example
        description: A composite capability that joins Bloomberg AIM + Bloomberg Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: aim-portfolio-tradeweb-cross-source-composer-skills
      description: Agent Skill bundle for Bloomberg Aim Portfolio Tradeweb Cross Source Composer.
      skills:
      - name: aim-portfolio-tradeweb-cross-source-composer
        description: A composite capability that joins Bloomberg AIM + Bloomberg Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.
        location: file:///opt/naftiko/skills/aim-portfolio-tradeweb-cross-source-composer
        allowed-tools: example
        tools:
        - name: example
          description: A composite capability that joins Bloomberg AIM + Bloomberg Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.
          from:
            sourceNamespace: aim-portfolio-tradeweb-cross-source-composer-mcp
            action: example
---

A composite capability that joins Bloomberg AIM + Bloomberg Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object. Federation across Bloomberg-internal sources is exactly the Head-of-API-Platform demo at scale.
