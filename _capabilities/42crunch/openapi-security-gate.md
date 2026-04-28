---
categories:
- security
- api-management
consumed_apis:
- 42crunch-platform
description: Workflow capability for security teams running the OpenAPI security gate that fires before Apigee publishing in Ford's API pipeline. Combines spec audit submission, score retrieval, severity-filtered findings, remediation, and PDF report export into a single interface so every spec — human-authored or agent-generated — clears a documented security threshold before it becomes a managed proxy.
layout: capability
name: 42Crunch OpenAPI Security Gate
operations:
- description: Submit an OpenAPI specification for an automated security audit
  method: POST
  name: submit-spec-for-audit
  path: /api/v2/apis
- description: Retrieve the overall audit score and grade for a submitted spec
  method: GET
  name: get-audit-score
  path: /api/v2/apis/{apiId}/audits/latest
- description: List audit findings filtered by severity (critical, high, medium, low, info)
  method: GET
  name: list-findings-by-severity
  path: /api/v2/apis/{apiId}/findings
- description: Mark a finding as remediated or apply a suggested fix to the spec
  method: PATCH
  name: remediate-finding
  path: /api/v2/apis/{apiId}/findings/{findingId}
- description: Download the full audit report as a PDF for compliance evidence
  method: GET
  name: get-audit-report-pdf
  path: /api/v2/apis/{apiId}/audits/latest/report.pdf
- description: List every API audited in the workspace with current scores
  method: GET
  name: list-audited-apis
  path: /api/v2/apis
personas:
- Security Team
- API Platform Engineer
provider_name: 42Crunch
provider_slug: 42crunch
search_terms:
- the openapi security gate that runs before apigee publishing
- ford api pipeline security gate
- submit spec for audit
- get audit score
- list findings by severity
- remediate finding
- get audit report pdf
- openapi security audit
- 42crunch platform api
- api security scoring
- pre-publish security gate
- shift-left api security
- governed ai-era integration
- ford api governance pipeline
- openapi audit findings
- api security compliance
- audit report export
- api security threshold
- agent-generated spec audit
- security team workflow
- compliance evidence
- api security
- openapi
- security
- api management
slug: openapi-security-gate
tags:
- API Security
- OpenAPI Audit
- Shift-Left Security
- Compliance
- Security Gate
tools:
- description: Submit an OpenAPI specification for an automated 42Crunch security audit before Apigee publishing
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-spec-for-audit
- description: Retrieve the overall audit score and grade for a submitted spec to evaluate gate pass/fail
  hints:
    openWorld: false
    readOnly: true
  name: get-audit-score
- description: List audit findings filtered by severity (critical, high, medium, low, info) for triage
  hints:
    openWorld: false
    readOnly: true
  name: list-findings-by-severity
- description: Mark a finding as remediated or apply a suggested fix to clear a blocking issue
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: remediate-finding
- description: Download the full audit report as a PDF for compliance evidence and audit trails
  hints:
    openWorld: false
    readOnly: true
  name: get-audit-report-pdf
- description: List every API audited in the workspace with current scores and grades
  hints:
    openWorld: false
    readOnly: true
  name: list-audited-apis
---
