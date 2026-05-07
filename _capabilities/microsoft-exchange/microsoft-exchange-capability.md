---
categories: []
consumed_apis: []
description: REST-based administrative API that enables a focused set of Exchange cmdlets and parameters as POST-only endpoints. Provides access to key tasks previously available through Exchange Web Services (EWS), including organization configuration, accepted domains, mailbox properties, mailbox folder permissions, and distribution group membership. Built as a complementary REST-first surface for specific administrative tasks caused by the EWS deprecation planned for October 2026.
layout: capability
name: Microsoft Exchange Exchange Online Admin API
operations:
- description: Microsoft Exchange Get organization configuration
  method: POST
  name: getorganizationconfig
  path: /OrganizationConfig
- description: Microsoft Exchange Get accepted domains
  method: POST
  name: getaccepteddomains
  path: /AcceptedDomain
- description: Microsoft Exchange Manage mailbox
  method: POST
  name: managemailbox
  path: /Mailbox
- description: Microsoft Exchange Manage mailbox folder permissions
  method: POST
  name: managemailboxfolderpermission
  path: /MailboxFolderPermission
- description: Microsoft Exchange Get distribution group members
  method: POST
  name: getdistributiongroupmembers
  path: /DistributionGroupMember
- description: Microsoft Exchange Get dynamic distribution group members
  method: POST
  name: getdynamicdistributiongroupmembers
  path: /DynamicDistributionGroupMember
personas: []
provider_name: Microsoft Exchange
provider_slug: microsoft-exchange
search_terms:
- microsoft exchange get dynamic distribution group members
- managemailboxfolderpermission
- microsoft exchange manage mailbox folder permissions
- microsoft exchange get accepted domains
- api
- managemailbox
- getdynamicdistributiongroupmembers
- microsoft
- collaboration
- contacts
- exchange
- microsoft exchange manage mailbox
- email
- enterprise
- microsoft exchange get distribution group members
- getaccepteddomains
- microsoft exchange get organization configuration
- getdistributiongroupmembers
- getorganizationconfig
- calendar
slug: microsoft-exchange-capability
source_filename: microsoft-exchange-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Exchange Exchange Online Admin API\n  description: REST-based administrative API that enables a focused set of Exchange cmdlets and parameters as POST-only endpoints.\n    Provides access to key tasks previously available through Exchange Web Services (EWS), including organization configuration,\n    accepted domains, mailbox properties, mailbox folder permissions, and distribution group membership. Built as a complementary\n    REST-first surface for specific administrative tasks caused by the EWS deprecation planned for October 2026.\n  tags:\n  - Microsoft\n  - Exchange\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-exchange\n    baseUri: https://outlook.office365.com/adminapi/v2.0\n    description: Microsoft Exchange Exchange Online Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_EXCHANGE_TOKEN}}'\n   \
  \ resources:\n    - name: organizationconfig\n      path: /OrganizationConfig\n      operations:\n      - name: getorganizationconfig\n        method: POST\n        description: Microsoft Exchange Get organization configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accepteddomain\n      path: /AcceptedDomain\n      operations:\n      - name: getaccepteddomains\n        method: POST\n        description: Microsoft Exchange Get accepted domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mailbox\n      path: /Mailbox\n      operations:\n      - name: managemailbox\n        method: POST\n        description: Microsoft Exchange Manage mailbox\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mailboxfolderpermission\n\
  \      path: /MailboxFolderPermission\n      operations:\n      - name: managemailboxfolderpermission\n        method: POST\n        description: Microsoft Exchange Manage mailbox folder permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: distributiongroupmember\n      path: /DistributionGroupMember\n      operations:\n      - name: getdistributiongroupmembers\n        method: POST\n        description: Microsoft Exchange Get distribution group members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dynamicdistributiongroupmember\n      path: /DynamicDistributionGroupMember\n      operations:\n      - name: getdynamicdistributiongroupmembers\n        method: POST\n        description: Microsoft Exchange Get dynamic distribution group members\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-exchange-rest\n    description: REST adapter for Microsoft Exchange Exchange Online Admin API.\n    resources:\n    - path: /OrganizationConfig\n      name: getorganizationconfig\n      operations:\n      - method: POST\n        name: getorganizationconfig\n        description: Microsoft Exchange Get organization configuration\n        call: microsoft-exchange.getorganizationconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /AcceptedDomain\n      name: getaccepteddomains\n      operations:\n      - method: POST\n        name: getaccepteddomains\n        description: Microsoft Exchange Get accepted domains\n        call: microsoft-exchange.getaccepteddomains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Mailbox\n      name: managemailbox\n      operations:\n      -\
  \ method: POST\n        name: managemailbox\n        description: Microsoft Exchange Manage mailbox\n        call: microsoft-exchange.managemailbox\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /MailboxFolderPermission\n      name: managemailboxfolderpermission\n      operations:\n      - method: POST\n        name: managemailboxfolderpermission\n        description: Microsoft Exchange Manage mailbox folder permissions\n        call: microsoft-exchange.managemailboxfolderpermission\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DistributionGroupMember\n      name: getdistributiongroupmembers\n      operations:\n      - method: POST\n        name: getdistributiongroupmembers\n        description: Microsoft Exchange Get distribution group members\n        call: microsoft-exchange.getdistributiongroupmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DynamicDistributionGroupMember\n\
  \      name: getdynamicdistributiongroupmembers\n      operations:\n      - method: POST\n        name: getdynamicdistributiongroupmembers\n        description: Microsoft Exchange Get dynamic distribution group members\n        call: microsoft-exchange.getdynamicdistributiongroupmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-exchange-mcp\n    transport: http\n    description: MCP adapter for Microsoft Exchange Exchange Online Admin API for AI agent use.\n    tools:\n    - name: getorganizationconfig\n      description: Microsoft Exchange Get organization configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-exchange.getorganizationconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccepteddomains\n      description: Microsoft Exchange Get accepted domains\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: microsoft-exchange.getaccepteddomains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: managemailbox\n      description: Microsoft Exchange Manage mailbox\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-exchange.managemailbox\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: managemailboxfolderpermission\n      description: Microsoft Exchange Manage mailbox folder permissions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-exchange.managemailboxfolderpermission\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdistributiongroupmembers\n      description: Microsoft Exchange Get distribution group members\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: microsoft-exchange.getdistributiongroupmembers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdynamicdistributiongroupmembers\n      description: Microsoft Exchange Get dynamic distribution group members\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-exchange.getdynamicdistributiongroupmembers\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_EXCHANGE_TOKEN: MICROSOFT_EXCHANGE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-exchange/refs/heads/main/capabilities/microsoft-exchange-capability.yaml
tags:
- Microsoft
- Exchange
- API
tools:
- description: Microsoft Exchange Get organization configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getorganizationconfig
- description: Microsoft Exchange Get accepted domains
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getaccepteddomains
- description: Microsoft Exchange Manage mailbox
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: managemailbox
- description: Microsoft Exchange Manage mailbox folder permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: managemailboxfolderpermission
- description: Microsoft Exchange Get distribution group members
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getdistributiongroupmembers
- description: Microsoft Exchange Get dynamic distribution group members
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getdynamicdistributiongroupmembers
---
