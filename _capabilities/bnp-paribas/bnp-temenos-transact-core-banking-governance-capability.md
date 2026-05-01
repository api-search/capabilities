---
categories: []
consumed_apis:
- bnp-paribas
description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Cedric MONIER
name: BNP Paribas Bnp Temenos Transact Core Banking Governance Capability
operations: []
personas: []
provider_name: BNP Paribas
provider_slug: bnp-paribas
search_terms:
- capability
- over
- temenos
- transact
- core
slug: bnp-temenos-transact-core-banking-governance-capability
source_filename: bnp-temenos-transact-core-banking-governance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: BNP Paribas Bnp Temenos Transact Core Banking Governance Capability
    description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.
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
      namespace: bnp-temenos-transact-core-banking-governance-capability-rest
      description: REST API for BNP Paribas Bnp Temenos Transact Core Banking Governance Capability.
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
      namespace: bnp-temenos-transact-core-banking-governance-capability-mcp
      description: MCP server exposing BNP Paribas Bnp Temenos Transact Core Banking Governance Capability for AI agents.
      tools:
      - name: example
        description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.
        hints:
          readOnly: true
        call: bnp-paribas.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bnp-temenos-transact-core-banking-governance-capability-skills
      description: Agent Skill bundle for BNP Paribas Bnp Temenos Transact Core Banking Governance Capability.
      skills:
      - name: bnp-temenos-transact-core-banking-governance-capability
        description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.
        location: file:///opt/naftiko/skills/bnp-temenos-transact-core-banking-governance-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.
          from:
            sourceNamespace: bnp-temenos-transact-core-banking-governance-capability-mcp
            action: example
---

A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language. French Tier-1 banking + API-First = governance-on-core-banking is the highest-stakes door-opener.
