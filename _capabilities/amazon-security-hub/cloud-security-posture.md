---
categories:
- security
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
- list controls
- import custom security findings into amazon security hub
- import security findings
- list findings
- update findings
- get and filter security findings from amazon security hub
- compliance
- amazon security hub
- cloud security posture and finding management across aws accounts
- list security controls and their compliance status
- list insights
- list security controls
- list compliance standards
- list and filter security findings
- security controls status and configuration
- compliance security standards monitoring
- import findings from custom security tools
- get security findings
- aggregated security insights across your environment
- SOC Analyst
- security
- list standards
- list security insights and trends
- engineers who configure security standards, manage controls, and remediate findings
- update security findings notes and status
- list security controls and check their compliance status
- get aggregated security insights and trend analysis
- get security insights
- security standards compliance monitoring and control management
- list enabled compliance standards
- list enabled compliance standards like cis, pci dss, soc 2
- cspm
- import findings
- analysts who investigate security findings and track remediation workflows
- Cloud Security Engineer
- aws
- monitoring
- security findings from across your aws environment
- centralized cloud security posture management including findings, compliance standards, controls, and insights
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
