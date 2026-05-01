---
categories: []
consumed_apis:
- deloitte
description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for Deloitte's audit + advisory practice.
layout: capability
naftiko_layer: proposed
naftiko_partner: Fabrice Marque
name: Deloitte Ccf Continuous Compliance Capability
operations: []
personas: []
provider_name: Deloitte
provider_slug: deloitte
search_terms:
- capability
- that
- activates
- compliance
- frameworks
slug: ccf-continuous-compliance-capability
source_filename: ccf-continuous-compliance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Deloitte Ccf Continuous Compliance Capability
    description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for Deloitte's audit + advisory practice.
    tags:
    - Deloitte
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: deloitte-env
    description: Deloitte credentials.
    keys:
      DELOITTE_API_KEY: DELOITTE_API_KEY
  capability:
    consumes:
    - namespace: deloitte
      type: http
      baseUri: https://api.deloitte.com
      authentication:
        type: bearer
        token: '{{DELOITTE_API_KEY}}'
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
      namespace: ccf-continuous-compliance-capability-rest
      description: REST API for Deloitte Ccf Continuous Compliance Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: deloitte.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: ccf-continuous-compliance-capability-mcp
      description: MCP server exposing Deloitte Ccf Continuous Compliance Capability for AI agents.
      tools:
      - name: example
        description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for Deloitte's audit + advisory practice.
        hints:
          readOnly: true
        call: deloitte.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: ccf-continuous-compliance-capability-skills
      description: Agent Skill bundle for Deloitte Ccf Continuous Compliance Capability.
      skills:
      - name: ccf-continuous-compliance-capability
        description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for Deloitte's audit + advisory practice.
        location: file:///opt/naftiko/skills/ccf-continuous-compliance-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for Deloitte's audit + advisory practice.
          from:
            sourceNamespace: ccf-continuous-compliance-capability-mcp
            action: example
---

A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for Deloitte's audit + advisory practice. Deloitte's value-add is regulated-industry advisory; CCF is the language that lands.
