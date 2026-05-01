---
categories: []
consumed_apis:
- humana
description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.
layout: capability
naftiko_layer: proposed
naftiko_partner: Humana
name: Humana Compliance Payer Grade Capability
operations: []
personas: []
provider_name: Humana
provider_slug: humana
search_terms:
- capability
- activating
- compliance
- frameworks
- nist
slug: compliance-payer-grade-capability
source_filename: compliance-payer-grade-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Humana Compliance Payer Grade Capability
    description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.
    tags:
    - Humana
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: humana-env
    description: Humana credentials.
    keys:
      HUMANA_API_KEY: HUMANA_API_KEY
  capability:
    consumes:
    - namespace: humana
      type: http
      baseUri: https://api.humana.com
      authentication:
        type: bearer
        token: '{{HUMANA_API_KEY}}'
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
      namespace: compliance-payer-grade-capability-rest
      description: REST API for Humana Compliance Payer Grade Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: humana.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: compliance-payer-grade-capability-mcp
      description: MCP server exposing Humana Compliance Payer Grade Capability for AI agents.
      tools:
      - name: example
        description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.
        hints:
          readOnly: true
        call: humana.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: compliance-payer-grade-capability-skills
      description: Agent Skill bundle for Humana Compliance Payer Grade Capability.
      skills:
      - name: compliance-payer-grade-capability
        description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.
        location: file:///opt/naftiko/skills/compliance-payer-grade-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.
          from:
            sourceNamespace: compliance-payer-grade-capability-mcp
            action: example
---

A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance. Payer-grade story; lead with the compliance posture they evaluate first.
