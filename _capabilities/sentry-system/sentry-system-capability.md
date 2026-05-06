---
categories: []
consumed_apis: []
description: The Alerts API provides endpoints for managing alert rules in Sentry, including creating, retrieving, updating, and deleting metric alert rules and issue alert rules, as well as managing spike protection notification actions.
layout: capability
name: Sentry Alerts API
operations:
- description: Sentry List an organization's metric alert rules
  method: GET
  name: listmetricalertrules
  path: /organizations/{organization_id_or_slug}/alert-rules/
- description: Sentry Create a metric alert rule for an organization
  method: POST
  name: createmetricalertrule
  path: /organizations/{organization_id_or_slug}/alert-rules/
- description: Sentry Retrieve a metric alert rule for an organization
  method: GET
  name: retrievemetricalertrule
  path: /organizations/{organization_id_or_slug}/alert-rules/{alert_rule_id}/
- description: Sentry Update a metric alert rule
  method: PUT
  name: updatemetricalertrule
  path: /organizations/{organization_id_or_slug}/alert-rules/{alert_rule_id}/
- description: Sentry Delete a metric alert rule
  method: DELETE
  name: deletemetricalertrule
  path: /organizations/{organization_id_or_slug}/alert-rules/{alert_rule_id}/
- description: Sentry List a project's issue alert rules
  method: GET
  name: listissuealertrules
  path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/
- description: Sentry Create an issue alert rule for a project
  method: POST
  name: createissuealertrule
  path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/
- description: Sentry Retrieve an issue alert rule for a project
  method: GET
  name: retrieveissuealertrule
  path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/{rule_id}/
- description: Sentry Update an issue alert rule
  method: PUT
  name: updateissuealertrule
  path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/{rule_id}/
- description: Sentry Delete an issue alert rule
  method: DELETE
  name: deleteissuealertrule
  path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/{rule_id}/
- description: Sentry List spike protection notifications
  method: GET
  name: listspikeprotectionnotifications
  path: /organizations/{organization_id_or_slug}/spike-protections/
- description: Sentry Create a spike protection notification action
  method: POST
  name: createspikeprotectionnotification
  path: /organizations/{organization_id_or_slug}/spike-protections/
personas: []
provider_name: Sentry
provider_slug: sentry-system
search_terms:
- error tracking
- real-time monitoring
- sentry update an issue alert rule
- apm
- sentry create a metric alert rule for an organization
- developer tools
- deleteissuealertrule
- createspikeprotectionnotification
- updateissuealertrule
- retrievemetricalertrule
- bug tracking
- sentry list spike protection notifications
- listspikeprotectionnotifications
- sentry retrieve an issue alert rule for a project
- sentry delete a metric alert rule
- retrieveissuealertrule
- application monitoring
- createmetricalertrule
- deletemetricalertrule
- api
- sentry update a metric alert rule
- listissuealertrules
- observability
- updatemetricalertrule
- sentry delete an issue alert rule
- sentry list a project's issue alert rules
- sentry list an organization's metric alert rules
- system
- createissuealertrule
- performance monitoring
- sentry create a spike protection notification action
- sentry
- listmetricalertrules
- sentry retrieve a metric alert rule for an organization
- sentry create an issue alert rule for a project
slug: sentry-system-capability
source_filename: sentry-system-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sentry Alerts API\n  description: The Alerts API provides endpoints for managing alert rules in Sentry, including creating, retrieving, updating,\n    and deleting metric alert rules and issue alert rules, as well as managing spike protection notification actions.\n  tags:\n  - Sentry\n  - System\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: sentry-system\n    baseUri: https://sentry.io/api/0\n    description: Sentry Alerts API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{SENTRY_SYSTEM_TOKEN}}'\n    resources:\n    - name: organizations-organization-id-or-slug-alert-rule\n      path: /organizations/{organization_id_or_slug}/alert-rules/\n      operations:\n      - name: listmetricalertrules\n        method: GET\n        description: Sentry List an organization's metric alert rules\n        inputParameters:\n        - name: cursor\n          in:\
  \ query\n          type: string\n          description: Pagination cursor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmetricalertrule\n        method: POST\n        description: Sentry Create a metric alert rule for an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-id-or-slug-alert-rule\n      path: /organizations/{organization_id_or_slug}/alert-rules/{alert_rule_id}/\n      operations:\n      - name: retrievemetricalertrule\n        method: GET\n        description: Sentry Retrieve a metric alert rule for an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemetricalertrule\n        method: PUT\n        description: Sentry Update a metric alert\
  \ rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemetricalertrule\n        method: DELETE\n        description: Sentry Delete a metric alert rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-organization-id-or-slug-project-id-or-s\n      path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/\n      operations:\n      - name: listissuealertrules\n        method: GET\n        description: Sentry List a project's issue alert rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createissuealertrule\n        method: POST\n        description: Sentry Create an issue alert rule for a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: projects-organization-id-or-slug-project-id-or-s\n      path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/{rule_id}/\n      operations:\n      - name: retrieveissuealertrule\n        method: GET\n        description: Sentry Retrieve an issue alert rule for a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateissuealertrule\n        method: PUT\n        description: Sentry Update an issue alert rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteissuealertrule\n        method: DELETE\n        description: Sentry Delete an issue alert rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-id-or-slug-spike-prot\n\
  \      path: /organizations/{organization_id_or_slug}/spike-protections/\n      operations:\n      - name: listspikeprotectionnotifications\n        method: GET\n        description: Sentry List spike protection notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createspikeprotectionnotification\n        method: POST\n        description: Sentry Create a spike protection notification action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sentry-system-rest\n    description: REST adapter for Sentry Alerts API.\n    resources:\n    - path: /organizations/{organization_id_or_slug}/alert-rules/\n      name: listmetricalertrules\n      operations:\n      - method: GET\n        name: listmetricalertrules\n        description: Sentry List an organization's\
  \ metric alert rules\n        call: sentry-system.listmetricalertrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id_or_slug}/alert-rules/\n      name: createmetricalertrule\n      operations:\n      - method: POST\n        name: createmetricalertrule\n        description: Sentry Create a metric alert rule for an organization\n        call: sentry-system.createmetricalertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id_or_slug}/alert-rules/{alert_rule_id}/\n      name: retrievemetricalertrule\n      operations:\n      - method: GET\n        name: retrievemetricalertrule\n        description: Sentry Retrieve a metric alert rule for an organization\n        call: sentry-system.retrievemetricalertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id_or_slug}/alert-rules/{alert_rule_id}/\n\
  \      name: updatemetricalertrule\n      operations:\n      - method: PUT\n        name: updatemetricalertrule\n        description: Sentry Update a metric alert rule\n        call: sentry-system.updatemetricalertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id_or_slug}/alert-rules/{alert_rule_id}/\n      name: deletemetricalertrule\n      operations:\n      - method: DELETE\n        name: deletemetricalertrule\n        description: Sentry Delete a metric alert rule\n        call: sentry-system.deletemetricalertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/\n      name: listissuealertrules\n      operations:\n      - method: GET\n        name: listissuealertrules\n        description: Sentry List a project's issue alert rules\n        call: sentry-system.listissuealertrules\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/\n      name: createissuealertrule\n      operations:\n      - method: POST\n        name: createissuealertrule\n        description: Sentry Create an issue alert rule for a project\n        call: sentry-system.createissuealertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/{rule_id}/\n      name: retrieveissuealertrule\n      operations:\n      - method: GET\n        name: retrieveissuealertrule\n        description: Sentry Retrieve an issue alert rule for a project\n        call: sentry-system.retrieveissuealertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/{rule_id}/\n      name: updateissuealertrule\n      operations:\n      - method: PUT\n        name:\
  \ updateissuealertrule\n        description: Sentry Update an issue alert rule\n        call: sentry-system.updateissuealertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{organization_id_or_slug}/{project_id_or_slug}/rules/{rule_id}/\n      name: deleteissuealertrule\n      operations:\n      - method: DELETE\n        name: deleteissuealertrule\n        description: Sentry Delete an issue alert rule\n        call: sentry-system.deleteissuealertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id_or_slug}/spike-protections/\n      name: listspikeprotectionnotifications\n      operations:\n      - method: GET\n        name: listspikeprotectionnotifications\n        description: Sentry List spike protection notifications\n        call: sentry-system.listspikeprotectionnotifications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /organizations/{organization_id_or_slug}/spike-protections/\n      name: createspikeprotectionnotification\n      operations:\n      - method: POST\n        name: createspikeprotectionnotification\n        description: Sentry Create a spike protection notification action\n        call: sentry-system.createspikeprotectionnotification\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sentry-system-mcp\n    transport: http\n    description: MCP adapter for Sentry Alerts API for AI agent use.\n    tools:\n    - name: listmetricalertrules\n      description: Sentry List an organization's metric alert rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sentry-system.listmetricalertrules\n      with:\n        cursor: tools.cursor\n      inputParameters:\n      - name: cursor\n        type: string\n        description: Pagination cursor.\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createmetricalertrule\n      description: Sentry Create a metric alert rule for an organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sentry-system.createmetricalertrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievemetricalertrule\n      description: Sentry Retrieve a metric alert rule for an organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sentry-system.retrievemetricalertrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatemetricalertrule\n      description: Sentry Update a metric alert rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: sentry-system.updatemetricalertrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemetricalertrule\n\
  \      description: Sentry Delete a metric alert rule\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sentry-system.deletemetricalertrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listissuealertrules\n      description: Sentry List a project's issue alert rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sentry-system.listissuealertrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createissuealertrule\n      description: Sentry Create an issue alert rule for a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sentry-system.createissuealertrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieveissuealertrule\n      description: Sentry Retrieve an issue alert rule for a project\n      hints:\n \
  \       readOnly: true\n        destructive: false\n        idempotent: true\n      call: sentry-system.retrieveissuealertrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateissuealertrule\n      description: Sentry Update an issue alert rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: sentry-system.updateissuealertrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteissuealertrule\n      description: Sentry Delete an issue alert rule\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sentry-system.deleteissuealertrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listspikeprotectionnotifications\n      description: Sentry List spike protection notifications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ sentry-system.listspikeprotectionnotifications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createspikeprotectionnotification\n      description: Sentry Create a spike protection notification action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sentry-system.createspikeprotectionnotification\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    SENTRY_SYSTEM_TOKEN: SENTRY_SYSTEM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sentry-system/refs/heads/main/capabilities/sentry-system-capability.yaml
tags:
- Sentry
- System
- API
tools:
- description: Sentry List an organization's metric alert rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmetricalertrules
- description: Sentry Create a metric alert rule for an organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmetricalertrule
- description: Sentry Retrieve a metric alert rule for an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievemetricalertrule
- description: Sentry Update a metric alert rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemetricalertrule
- description: Sentry Delete a metric alert rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemetricalertrule
- description: Sentry List a project's issue alert rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listissuealertrules
- description: Sentry Create an issue alert rule for a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createissuealertrule
- description: Sentry Retrieve an issue alert rule for a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieveissuealertrule
- description: Sentry Update an issue alert rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateissuealertrule
- description: Sentry Delete an issue alert rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteissuealertrule
- description: Sentry List spike protection notifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listspikeprotectionnotifications
- description: Sentry Create a spike protection notification action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspikeprotectionnotification
---
