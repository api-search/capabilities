---
categories: []
consumed_apis: []
description: The Harbor Compliance API enables partners to integrate compliance management capabilities into their platforms. The API provides programmatic access to business licensing, registered agent services, compliance tracking, and entity management workflows. Partners can automate compliance tasks, monitor filing deadlines, manage registered agent appointments, and track licensing requirements across jurisdictions.
layout: capability
name: Harbor Compliance API
operations:
- description: Harbor Compliance List business entities
  method: GET
  name: listentities
  path: /entities
- description: Harbor Compliance Create a business entity
  method: POST
  name: createentity
  path: /entities
- description: Harbor Compliance Get a business entity
  method: GET
  name: getentity
  path: /entities/{entityId}
- description: Harbor Compliance Update a business entity
  method: PATCH
  name: updateentity
  path: /entities/{entityId}
- description: Harbor Compliance Get compliance status for an entity
  method: GET
  name: getentitycompliance
  path: /entities/{entityId}/compliance
- description: Harbor Compliance List business licenses
  method: GET
  name: listlicenses
  path: /licenses
- description: Harbor Compliance Create a license application
  method: POST
  name: createlicense
  path: /licenses
- description: Harbor Compliance Get a business license
  method: GET
  name: getlicense
  path: /licenses/{licenseId}
- description: Harbor Compliance Renew a business license
  method: POST
  name: renewlicense
  path: /licenses/{licenseId}/renew
- description: Harbor Compliance List registered agent appointments
  method: GET
  name: listregisteredagents
  path: /registered-agents
- description: Harbor Compliance Appoint a registered agent
  method: POST
  name: createregisteredagentappointment
  path: /registered-agents
- description: Harbor Compliance Get a registered agent appointment
  method: GET
  name: getregisteredagent
  path: /registered-agents/{agentId}
- description: Harbor Compliance List compliance filings
  method: GET
  name: listfilings
  path: /filings
- description: Harbor Compliance Get a compliance filing
  method: GET
  name: getfiling
  path: /filings/{filingId}
- description: Harbor Compliance List jurisdictions
  method: GET
  name: listjurisdictions
  path: /jurisdictions
- description: Harbor Compliance Get jurisdiction details
  method: GET
  name: getjurisdiction
  path: /jurisdictions/{state}
- description: Harbor Compliance List service orders
  method: GET
  name: listorders
  path: /orders
- description: Harbor Compliance Get a service order
  method: GET
  name: getorder
  path: /orders/{orderId}
personas: []
provider_name: Harbor Compliance
provider_slug: harbor-compliance
search_terms:
- harbor compliance list registered agent appointments
- harbor compliance create a license application
- createentity
- getlicense
- getregisteredagent
- getentity
- legal
- harbor compliance get a business license
- harbor compliance renew a business license
- listlicenses
- business licensing
- getjurisdiction
- harbor compliance get compliance status for an entity
- getfiling
- createregisteredagentappointment
- harbor compliance get a registered agent appointment
- listentities
- harbor compliance list service orders
- getorder
- compliance
- harbor
- harbor compliance get a service order
- regulatory
- harbor compliance get a compliance filing
- harbor compliance get a business entity
- harbor compliance list compliance filings
- listorders
- harbor compliance create a business entity
- updateentity
- getentitycompliance
- api
- harbor compliance update a business entity
- harbor compliance get jurisdiction details
- listregisteredagents
- harbor compliance list business licenses
- createlicense
- harbor compliance list business entities
- harbor compliance list jurisdictions
- renewlicense
- listfilings
- listjurisdictions
- harbor compliance appoint a registered agent
slug: harbor-compliance-capability
source_filename: harbor-compliance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Harbor Compliance API\n  description: The Harbor Compliance API enables partners to integrate compliance management capabilities into their platforms.\n    The API provides programmatic access to business licensing, registered agent services, compliance tracking, and entity\n    management workflows. Partners can automate compliance tasks, monitor filing deadlines, manage registered agent appointments,\n    and track licensing requirements across jurisdictions.\n  tags:\n  - Harbor\n  - Compliance\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: harbor-compliance\n    baseUri: https://api.harborcompliance.com/v1\n    description: Harbor Compliance API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{HARBOR_COMPLIANCE_TOKEN}}'\n    resources:\n    - name: entities\n      path: /entities\n      operations:\n  \
  \    - name: listentities\n        method: GET\n        description: Harbor Compliance List business entities\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          description: Filter entities by state of formation (two-letter state code).\n        - name: entity_type\n          in: query\n          type: string\n          description: Filter by entity type.\n        - name: status\n          in: query\n          type: string\n          description: Filter by entity status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createentity\n        method: POST\n        description: Harbor Compliance Create a business entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities-entityid\n      path: /entities/{entityId}\n      operations:\n      - name: getentity\n\
  \        method: GET\n        description: Harbor Compliance Get a business entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateentity\n        method: PATCH\n        description: Harbor Compliance Update a business entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities-entityid-compliance\n      path: /entities/{entityId}/compliance\n      operations:\n      - name: getentitycompliance\n        method: GET\n        description: Harbor Compliance Get compliance status for an entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: licenses\n      path: /licenses\n      operations:\n      - name: listlicenses\n        method: GET\n        description: Harbor Compliance List business licenses\n    \
  \    inputParameters:\n        - name: entity_id\n          in: query\n          type: string\n          description: Filter licenses by entity identifier.\n        - name: state\n          in: query\n          type: string\n          description: Filter licenses by state jurisdiction.\n        - name: status\n          in: query\n          type: string\n          description: Filter by license status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlicense\n        method: POST\n        description: Harbor Compliance Create a license application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: licenses-licenseid\n      path: /licenses/{licenseId}\n      operations:\n      - name: getlicense\n        method: GET\n        description: Harbor Compliance Get a business license\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: licenses-licenseid-renew\n      path: /licenses/{licenseId}/renew\n      operations:\n      - name: renewlicense\n        method: POST\n        description: Harbor Compliance Renew a business license\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: registered-agents\n      path: /registered-agents\n      operations:\n      - name: listregisteredagents\n        method: GET\n        description: Harbor Compliance List registered agent appointments\n        inputParameters:\n        - name: entity_id\n          in: query\n          type: string\n          description: Filter by entity identifier.\n        - name: state\n          in: query\n          type: string\n          description: Filter by state jurisdiction.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: createregisteredagentappointment\n        method: POST\n        description: Harbor Compliance Appoint a registered agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: registered-agents-agentid\n      path: /registered-agents/{agentId}\n      operations:\n      - name: getregisteredagent\n        method: GET\n        description: Harbor Compliance Get a registered agent appointment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filings\n      path: /filings\n      operations:\n      - name: listfilings\n        method: GET\n        description: Harbor Compliance List compliance filings\n        inputParameters:\n        - name: entity_id\n          in: query\n          type: string\n          description: Filter filings by entity identifier.\n\
  \        - name: state\n          in: query\n          type: string\n          description: Filter filings by state jurisdiction.\n        - name: status\n          in: query\n          type: string\n          description: Filter by filing status.\n        - name: due_before\n          in: query\n          type: string\n          description: Filter filings due before this date (ISO 8601 date).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filings-filingid\n      path: /filings/{filingId}\n      operations:\n      - name: getfiling\n        method: GET\n        description: Harbor Compliance Get a compliance filing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jurisdictions\n      path: /jurisdictions\n      operations:\n      - name: listjurisdictions\n        method: GET\n        description: Harbor\
  \ Compliance List jurisdictions\n        inputParameters:\n        - name: entity_type\n          in: query\n          type: string\n          description: Filter jurisdictions by supported entity type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jurisdictions-state\n      path: /jurisdictions/{state}\n      operations:\n      - name: getjurisdiction\n        method: GET\n        description: Harbor Compliance Get jurisdiction details\n        inputParameters:\n        - name: state\n          in: path\n          type: string\n          required: true\n          description: Two-letter state code (e.g., CA, NY, DE).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      operations:\n      - name: listorders\n        method: GET\n        description: Harbor Compliance List service\
  \ orders\n        inputParameters:\n        - name: entity_id\n          in: query\n          type: string\n          description: Filter orders by entity identifier.\n        - name: status\n          in: query\n          type: string\n          description: Filter by order status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders-orderid\n      path: /orders/{orderId}\n      operations:\n      - name: getorder\n        method: GET\n        description: Harbor Compliance Get a service order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: harbor-compliance-rest\n    description: REST adapter for Harbor Compliance API.\n    resources:\n    - path: /entities\n      name: listentities\n      operations:\n      - method: GET\n        name: listentities\n   \
  \     description: Harbor Compliance List business entities\n        call: harbor-compliance.listentities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities\n      name: createentity\n      operations:\n      - method: POST\n        name: createentity\n        description: Harbor Compliance Create a business entity\n        call: harbor-compliance.createentity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{entityId}\n      name: getentity\n      operations:\n      - method: GET\n        name: getentity\n        description: Harbor Compliance Get a business entity\n        call: harbor-compliance.getentity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{entityId}\n      name: updateentity\n      operations:\n      - method: PATCH\n        name: updateentity\n        description: Harbor Compliance Update a business entity\n        call: harbor-compliance.updateentity\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{entityId}/compliance\n      name: getentitycompliance\n      operations:\n      - method: GET\n        name: getentitycompliance\n        description: Harbor Compliance Get compliance status for an entity\n        call: harbor-compliance.getentitycompliance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /licenses\n      name: listlicenses\n      operations:\n      - method: GET\n        name: listlicenses\n        description: Harbor Compliance List business licenses\n        call: harbor-compliance.listlicenses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /licenses\n      name: createlicense\n      operations:\n      - method: POST\n        name: createlicense\n        description: Harbor Compliance Create a license application\n        call: harbor-compliance.createlicense\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /licenses/{licenseId}\n      name: getlicense\n      operations:\n      - method: GET\n        name: getlicense\n        description: Harbor Compliance Get a business license\n        call: harbor-compliance.getlicense\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /licenses/{licenseId}/renew\n      name: renewlicense\n      operations:\n      - method: POST\n        name: renewlicense\n        description: Harbor Compliance Renew a business license\n        call: harbor-compliance.renewlicense\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /registered-agents\n      name: listregisteredagents\n      operations:\n      - method: GET\n        name: listregisteredagents\n        description: Harbor Compliance List registered agent appointments\n        call: harbor-compliance.listregisteredagents\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /registered-agents\n      name: createregisteredagentappointment\n      operations:\n      - method: POST\n        name: createregisteredagentappointment\n        description: Harbor Compliance Appoint a registered agent\n        call: harbor-compliance.createregisteredagentappointment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /registered-agents/{agentId}\n      name: getregisteredagent\n      operations:\n      - method: GET\n        name: getregisteredagent\n        description: Harbor Compliance Get a registered agent appointment\n        call: harbor-compliance.getregisteredagent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /filings\n      name: listfilings\n      operations:\n      - method: GET\n        name: listfilings\n        description: Harbor Compliance List compliance filings\n        call: harbor-compliance.listfilings\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /filings/{filingId}\n      name: getfiling\n      operations:\n      - method: GET\n        name: getfiling\n        description: Harbor Compliance Get a compliance filing\n        call: harbor-compliance.getfiling\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jurisdictions\n      name: listjurisdictions\n      operations:\n      - method: GET\n        name: listjurisdictions\n        description: Harbor Compliance List jurisdictions\n        call: harbor-compliance.listjurisdictions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jurisdictions/{state}\n      name: getjurisdiction\n      operations:\n      - method: GET\n        name: getjurisdiction\n        description: Harbor Compliance Get jurisdiction details\n        call: harbor-compliance.getjurisdiction\n        with:\n          state: rest.state\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /orders\n      name: listorders\n      operations:\n      - method: GET\n        name: listorders\n        description: Harbor Compliance List service orders\n        call: harbor-compliance.listorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderId}\n      name: getorder\n      operations:\n      - method: GET\n        name: getorder\n        description: Harbor Compliance Get a service order\n        call: harbor-compliance.getorder\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: harbor-compliance-mcp\n    transport: http\n    description: MCP adapter for Harbor Compliance API for AI agent use.\n    tools:\n    - name: listentities\n      description: Harbor Compliance List business entities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.listentities\n\
  \      with:\n        state: tools.state\n        entity_type: tools.entity_type\n        status: tools.status\n      inputParameters:\n      - name: state\n        type: string\n        description: Filter entities by state of formation (two-letter state code).\n      - name: entity_type\n        type: string\n        description: Filter by entity type.\n      - name: status\n        type: string\n        description: Filter by entity status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createentity\n      description: Harbor Compliance Create a business entity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor-compliance.createentity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getentity\n      description: Harbor Compliance Get a business entity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.getentity\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateentity\n      description: Harbor Compliance Update a business entity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor-compliance.updateentity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getentitycompliance\n      description: Harbor Compliance Get compliance status for an entity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.getentitycompliance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlicenses\n      description: Harbor Compliance List business licenses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.listlicenses\n      with:\n        entity_id: tools.entity_id\n        state: tools.state\n        status: tools.status\n\
  \      inputParameters:\n      - name: entity_id\n        type: string\n        description: Filter licenses by entity identifier.\n      - name: state\n        type: string\n        description: Filter licenses by state jurisdiction.\n      - name: status\n        type: string\n        description: Filter by license status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlicense\n      description: Harbor Compliance Create a license application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor-compliance.createlicense\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlicense\n      description: Harbor Compliance Get a business license\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.getlicense\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renewlicense\n\
  \      description: Harbor Compliance Renew a business license\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor-compliance.renewlicense\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listregisteredagents\n      description: Harbor Compliance List registered agent appointments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.listregisteredagents\n      with:\n        entity_id: tools.entity_id\n        state: tools.state\n      inputParameters:\n      - name: entity_id\n        type: string\n        description: Filter by entity identifier.\n      - name: state\n        type: string\n        description: Filter by state jurisdiction.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createregisteredagentappointment\n      description: Harbor Compliance Appoint a registered agent\n     \
  \ hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor-compliance.createregisteredagentappointment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getregisteredagent\n      description: Harbor Compliance Get a registered agent appointment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.getregisteredagent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfilings\n      description: Harbor Compliance List compliance filings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.listfilings\n      with:\n        entity_id: tools.entity_id\n        state: tools.state\n        status: tools.status\n        due_before: tools.due_before\n      inputParameters:\n      - name: entity_id\n        type: string\n        description: Filter\
  \ filings by entity identifier.\n      - name: state\n        type: string\n        description: Filter filings by state jurisdiction.\n      - name: status\n        type: string\n        description: Filter by filing status.\n      - name: due_before\n        type: string\n        description: Filter filings due before this date (ISO 8601 date).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfiling\n      description: Harbor Compliance Get a compliance filing\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.getfiling\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjurisdictions\n      description: Harbor Compliance List jurisdictions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.listjurisdictions\n      with:\n        entity_type: tools.entity_type\n      inputParameters:\n\
  \      - name: entity_type\n        type: string\n        description: Filter jurisdictions by supported entity type.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjurisdiction\n      description: Harbor Compliance Get jurisdiction details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.getjurisdiction\n      with:\n        state: tools.state\n      inputParameters:\n      - name: state\n        type: string\n        description: Two-letter state code (e.g., CA, NY, DE).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorders\n      description: Harbor Compliance List service orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.listorders\n      with:\n        entity_id: tools.entity_id\n        status: tools.status\n      inputParameters:\n\
  \      - name: entity_id\n        type: string\n        description: Filter orders by entity identifier.\n      - name: status\n        type: string\n        description: Filter by order status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorder\n      description: Harbor Compliance Get a service order\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor-compliance.getorder\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HARBOR_COMPLIANCE_TOKEN: HARBOR_COMPLIANCE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/harbor-compliance/refs/heads/main/capabilities/harbor-compliance-capability.yaml
tags:
- Harbor
- Compliance
- API
tools:
- description: Harbor Compliance List business entities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listentities
- description: Harbor Compliance Create a business entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createentity
- description: Harbor Compliance Get a business entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getentity
- description: Harbor Compliance Update a business entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateentity
- description: Harbor Compliance Get compliance status for an entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getentitycompliance
- description: Harbor Compliance List business licenses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlicenses
- description: Harbor Compliance Create a license application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlicense
- description: Harbor Compliance Get a business license
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlicense
- description: Harbor Compliance Renew a business license
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renewlicense
- description: Harbor Compliance List registered agent appointments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listregisteredagents
- description: Harbor Compliance Appoint a registered agent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createregisteredagentappointment
- description: Harbor Compliance Get a registered agent appointment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getregisteredagent
- description: Harbor Compliance List compliance filings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfilings
- description: Harbor Compliance Get a compliance filing
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfiling
- description: Harbor Compliance List jurisdictions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjurisdictions
- description: Harbor Compliance Get jurisdiction details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjurisdiction
- description: Harbor Compliance List service orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorders
- description: Harbor Compliance Get a service order
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorder
---
