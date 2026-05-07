---
categories: []
consumed_apis: []
description: Access audit logs, security reports, and compliance data within the Workday platform. Provides programmatic access to audit trail information for security monitoring, regulatory compliance, and governance reporting. Supports retrieval of configuration change history, security policy modifications, and access control audit records for maintaining a complete compliance trail.
layout: capability
name: Workday Security Workday Audit and Compliance API
operations:
- description: Workday Security List audit log entries
  method: GET
  name: listauditlogs
  path: /auditLogs
- description: Workday Security Get a specific audit log entry
  method: GET
  name: getauditlogentry
  path: /auditLogs/{auditLogId}
- description: Workday Security List security permission changes
  method: GET
  name: listpermissionchanges
  path: /securityAudit/permissionChanges
- description: Workday Security List compliance reports
  method: GET
  name: listcompliancereports
  path: /complianceReports
personas: []
provider_name: Workday Security
provider_slug: workday-security
search_terms:
- saml
- api
- workday security list compliance reports
- identity management
- workday
- listcompliancereports
- authentication
- workday security get a specific audit log entry
- sso
- workday security list audit log entries
- privacy
- compliance
- access control
- enterprise
- workday security list security permission changes
- listauditlogs
- audit
- security
- listpermissionchanges
- getauditlogentry
slug: workday-security-capability
source_filename: workday-security-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Security Workday Audit and Compliance API\n  description: Access audit logs, security reports, and compliance data within the Workday platform. Provides programmatic\n    access to audit trail information for security monitoring, regulatory compliance, and governance reporting. Supports retrieval\n    of configuration change history, security policy modifications, and access control audit records for maintaining a complete\n    compliance trail.\n  tags:\n  - Workday\n  - Security\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-security\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/your-tenant\n    description: Workday Security Workday Audit and Compliance API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_SECURITY_TOKEN}}'\n    resources:\n    - name: auditlogs\n      path: /auditLogs\n      operations:\n\
  \      - name: listauditlogs\n        method: GET\n        description: Workday Security List audit log entries\n        inputParameters:\n        - name: fromDateTime\n          in: query\n          type: string\n          description: Start of the date range for filtering audit log entries\n        - name: toDateTime\n          in: query\n          type: string\n          description: End of the date range for filtering audit log entries\n        - name: eventType\n          in: query\n          type: string\n          description: Filter by the type of audit event\n        - name: actor\n          in: query\n          type: string\n          description: Filter by the account that performed the audited action\n        - name: target\n          in: query\n          type: string\n          description: Filter by the target resource or object of the audited action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: auditlogs-auditlogid\n      path: /auditLogs/{auditLogId}\n      operations:\n      - name: getauditlogentry\n        method: GET\n        description: Workday Security Get a specific audit log entry\n        inputParameters:\n        - name: auditLogId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the audit log entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: securityaudit-permissionchanges\n      path: /securityAudit/permissionChanges\n      operations:\n      - name: listpermissionchanges\n        method: GET\n        description: Workday Security List security permission changes\n        inputParameters:\n        - name: fromDateTime\n          in: query\n          type: string\n          description: Start of the date range for filtering permission changes\n        - name: toDateTime\n          in: query\n\
  \          type: string\n          description: End of the date range for filtering permission changes\n        - name: changeType\n          in: query\n          type: string\n          description: Filter by the type of permission change\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliancereports\n      path: /complianceReports\n      operations:\n      - name: listcompliancereports\n        method: GET\n        description: Workday Security List compliance reports\n        inputParameters:\n        - name: reportType\n          in: query\n          type: string\n          description: Filter by the type of compliance report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workday-security-rest\n    description: REST adapter for Workday Security Workday\
  \ Audit and Compliance API.\n    resources:\n    - path: /auditLogs\n      name: listauditlogs\n      operations:\n      - method: GET\n        name: listauditlogs\n        description: Workday Security List audit log entries\n        call: workday-security.listauditlogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auditLogs/{auditLogId}\n      name: getauditlogentry\n      operations:\n      - method: GET\n        name: getauditlogentry\n        description: Workday Security Get a specific audit log entry\n        call: workday-security.getauditlogentry\n        with:\n          auditLogId: rest.auditLogId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /securityAudit/permissionChanges\n      name: listpermissionchanges\n      operations:\n      - method: GET\n        name: listpermissionchanges\n        description: Workday Security List security permission changes\n        call: workday-security.listpermissionchanges\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /complianceReports\n      name: listcompliancereports\n      operations:\n      - method: GET\n        name: listcompliancereports\n        description: Workday Security List compliance reports\n        call: workday-security.listcompliancereports\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workday-security-mcp\n    transport: http\n    description: MCP adapter for Workday Security Workday Audit and Compliance API for AI agent use.\n    tools:\n    - name: listauditlogs\n      description: Workday Security List audit log entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-security.listauditlogs\n      with:\n        fromDateTime: tools.fromDateTime\n        toDateTime: tools.toDateTime\n        eventType: tools.eventType\n        actor: tools.actor\n      \
  \  target: tools.target\n      inputParameters:\n      - name: fromDateTime\n        type: string\n        description: Start of the date range for filtering audit log entries\n      - name: toDateTime\n        type: string\n        description: End of the date range for filtering audit log entries\n      - name: eventType\n        type: string\n        description: Filter by the type of audit event\n      - name: actor\n        type: string\n        description: Filter by the account that performed the audited action\n      - name: target\n        type: string\n        description: Filter by the target resource or object of the audited action\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getauditlogentry\n      description: Workday Security Get a specific audit log entry\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-security.getauditlogentry\n      with:\n        auditLogId: tools.auditLogId\n\
  \      inputParameters:\n      - name: auditLogId\n        type: string\n        description: Unique identifier of the audit log entry\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpermissionchanges\n      description: Workday Security List security permission changes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-security.listpermissionchanges\n      with:\n        fromDateTime: tools.fromDateTime\n        toDateTime: tools.toDateTime\n        changeType: tools.changeType\n      inputParameters:\n      - name: fromDateTime\n        type: string\n        description: Start of the date range for filtering permission changes\n      - name: toDateTime\n        type: string\n        description: End of the date range for filtering permission changes\n      - name: changeType\n        type: string\n        description: Filter by the type of permission change\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcompliancereports\n      description: Workday Security List compliance reports\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-security.listcompliancereports\n      with:\n        reportType: tools.reportType\n      inputParameters:\n      - name: reportType\n        type: string\n        description: Filter by the type of compliance report\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_SECURITY_TOKEN: WORKDAY_SECURITY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-security/refs/heads/main/capabilities/workday-security-capability.yaml
tags:
- Workday
- Security
- API
tools:
- description: Workday Security List audit log entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauditlogs
- description: Workday Security Get a specific audit log entry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauditlogentry
- description: Workday Security List security permission changes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpermissionchanges
- description: Workday Security List compliance reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcompliancereports
---
