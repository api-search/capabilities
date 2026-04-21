---
consumed_apis:
- amazon-security-hub
description: Unified capability for cloud security posture management including findings aggregation, compliance standards monitoring, and security insights. Used by Cloud Security Engineers and SOC Analysts.
layout: capability
name: Amazon Security Hub Cloud Security Posture
operations:
- description: List and filter security findings
  method: GET
  name: list-findings
  path: /v1/findings
- description: Import findings from custom security tools
  method: POST
  name: import-findings
  path: /v1/findings
- description: List enabled compliance standards
  method: GET
  name: list-standards
  path: /v1/standards
- description: List security controls and their compliance status
  method: GET
  name: list-controls
  path: /v1/controls
- description: List security insights and trends
  method: GET
  name: list-insights
  path: /v1/insights
personas: []
provider_name: Amazon Security Hub
provider_slug: amazon-security-hub
search_terms:
- analysts who investigate security findings and track remediation workflows
- list controls
- cloud security posture and finding management across aws accounts
- list enabled compliance standards
- update security findings notes and status
- get and filter security findings from amazon security hub
- import findings from custom security tools
- import custom security findings into amazon security hub
- list security controls
- amazon security hub
- update findings
- aggregated security insights across your environment
- list standards
- list security insights and trends
- Cloud Security Engineer
- get aggregated security insights and trend analysis
- security standards compliance monitoring and control management
- compliance security standards monitoring
- cspm
- list security controls and their compliance status
- compliance
- SOC Analyst
- security
- import findings
- import security findings
- list and filter security findings
- engineers who configure security standards, manage controls, and remediate findings
- monitoring
- security controls status and configuration
- aws
- list findings
- get security insights
- security findings from across your aws environment
- centralized cloud security posture management including findings, compliance standards, controls, and insights
- get security findings
- list insights
- list enabled compliance standards like cis, pci dss, soc 2
- list security controls and check their compliance status
- list compliance standards
slug: cloud-security-posture
tags:
- Amazon Security Hub
- Security
- Compliance
- CSPM
- AWS
tools:
- description: Get and filter security findings from Amazon Security Hub
  hints:
    idempotent: true
    readOnly: true
  name: get-security-findings
- description: Import custom security findings into Amazon Security Hub
  hints:
    idempotent: false
    readOnly: false
  name: import-security-findings
- description: Update security findings notes and status
  hints:
    idempotent: false
    readOnly: false
  name: update-findings
- description: List enabled compliance standards like CIS, PCI DSS, SOC 2
  hints:
    idempotent: true
    readOnly: true
  name: list-compliance-standards
- description: List security controls and check their compliance status
  hints:
    idempotent: true
    readOnly: true
  name: list-security-controls
- description: Get aggregated security insights and trend analysis
  hints:
    idempotent: true
    readOnly: true
  name: get-security-insights
---
