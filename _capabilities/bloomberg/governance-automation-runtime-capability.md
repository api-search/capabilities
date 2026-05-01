---
categories: []
consumed_apis:
- bloomberg
description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for Bloomberg's automation-of-governance thesis.
layout: capability
naftiko_layer: proposed
naftiko_partner: Amit Mahale
name: Bloomberg Governance Automation Runtime Capability
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- capability
- whose
- governance
- ruleset
- spectral
slug: governance-automation-runtime-capability
source_filename: governance-automation-runtime-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Governance Automation Runtime Capability
    description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for Bloomberg's automation-of-governance thesis.
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
      namespace: governance-automation-runtime-capability-rest
      description: REST API for Bloomberg Governance Automation Runtime Capability.
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
      namespace: governance-automation-runtime-capability-mcp
      description: MCP server exposing Bloomberg Governance Automation Runtime Capability for AI agents.
      tools:
      - name: example
        description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for Bloomberg's automation-of-governance thesis.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: governance-automation-runtime-capability-skills
      description: Agent Skill bundle for Bloomberg Governance Automation Runtime Capability.
      skills:
      - name: governance-automation-runtime-capability
        description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for Bloomberg's automation-of-governance thesis.
        location: file:///opt/naftiko/skills/governance-automation-runtime-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for Bloomberg's automation-of-governance thesis.
          from:
            sourceNamespace: governance-automation-runtime-capability-mcp
            action: example
---

A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for Bloomberg's automation-of-governance thesis. His update was specifically about Bloomberg's automation-of-governance work; Naftiko's governance ruleset IS that runtime.
