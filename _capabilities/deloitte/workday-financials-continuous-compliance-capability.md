---
categories: []
consumed_apis:
- deloitte
description: A capability over Workday Financials that activates Continuous Compliance (CCF-style) with NIST/SOC2/PCI/GDPR scoring as the audit-practice artifact.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Fabrice Marque
name: Deloitte Workday Financials Continuous Compliance Capability
operations: []
personas: []
provider_name: Deloitte
provider_slug: deloitte
search_terms:
- capability
- over
- workday
- financials
- that
slug: workday-financials-continuous-compliance-capability
source_filename: workday-financials-continuous-compliance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Deloitte Workday Financials Continuous Compliance Capability
    description: A capability over Workday Financials that activates Continuous Compliance (CCF-style) with NIST/SOC2/PCI/GDPR scoring as the audit-practice artifact.
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
      namespace: workday-financials-continuous-compliance-capability-rest
      description: REST API for Deloitte Workday Financials Continuous Compliance Capability.
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
      namespace: workday-financials-continuous-compliance-capability-mcp
      description: MCP server exposing Deloitte Workday Financials Continuous Compliance Capability for AI agents.
      tools:
      - name: example
        description: A capability over Workday Financials that activates Continuous Compliance (CCF-style) with NIST/SOC2/PCI/GDPR scoring as the audit-practice artifact.
        hints:
          readOnly: true
        call: deloitte.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: workday-financials-continuous-compliance-capability-skills
      description: Agent Skill bundle for Deloitte Workday Financials Continuous Compliance Capability.
      skills:
      - name: workday-financials-continuous-compliance-capability
        description: A capability over Workday Financials that activates Continuous Compliance (CCF-style) with NIST/SOC2/PCI/GDPR scoring as the audit-practice artifact.
        location: file:///opt/naftiko/skills/workday-financials-continuous-compliance-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Workday Financials that activates Continuous Compliance (CCF-style) with NIST/SOC2/PCI/GDPR scoring as the audit-practice artifact.
          from:
            sourceNamespace: workday-financials-continuous-compliance-capability-mcp
            action: example
---

A capability over Workday Financials that activates Continuous Compliance (CCF-style) with NIST/SOC2/PCI/GDPR scoring as the audit-practice artifact. Workday Financials is the CFO-suite system Deloitte audits; CCF on it lands directly with audit + advisory.
