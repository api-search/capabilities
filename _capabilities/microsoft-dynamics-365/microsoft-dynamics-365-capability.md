---
categories: []
consumed_apis: []
description: RESTful web service implementing OData v4.0 for interacting with data in Microsoft Dataverse, the underlying data platform for Dynamics 365 and Power Platform applications. This specification covers core CRM entities including accounts, contacts, and opportunities.
layout: capability
name: Microsoft Dynamics 365 Dataverse Web API
operations:
- description: Microsoft Dynamics 365 List accounts
  method: GET
  name: listaccounts
  path: /accounts
- description: Microsoft Dynamics 365 Create an account
  method: POST
  name: createaccount
  path: /accounts
- description: Microsoft Dynamics 365 Retrieve an account
  method: GET
  name: getaccount
  path: /accounts({accountid})
- description: Microsoft Dynamics 365 Update an account
  method: PATCH
  name: updateaccount
  path: /accounts({accountid})
- description: Microsoft Dynamics 365 Delete an account
  method: DELETE
  name: deleteaccount
  path: /accounts({accountid})
- description: Microsoft Dynamics 365 List contacts
  method: GET
  name: listcontacts
  path: /contacts
- description: Microsoft Dynamics 365 Create a contact
  method: POST
  name: createcontact
  path: /contacts
- description: Microsoft Dynamics 365 Retrieve a contact
  method: GET
  name: getcontact
  path: /contacts({contactid})
- description: Microsoft Dynamics 365 Update a contact
  method: PATCH
  name: updatecontact
  path: /contacts({contactid})
- description: Microsoft Dynamics 365 Delete a contact
  method: DELETE
  name: deletecontact
  path: /contacts({contactid})
- description: Microsoft Dynamics 365 List opportunities
  method: GET
  name: listopportunities
  path: /opportunities
- description: Microsoft Dynamics 365 Create an opportunity
  method: POST
  name: createopportunity
  path: /opportunities
- description: Microsoft Dynamics 365 Retrieve an opportunity
  method: GET
  name: getopportunity
  path: /opportunities({opportunityid})
- description: Microsoft Dynamics 365 Update an opportunity
  method: PATCH
  name: updateopportunity
  path: /opportunities({opportunityid})
- description: Microsoft Dynamics 365 Delete an opportunity
  method: DELETE
  name: deleteopportunity
  path: /opportunities({opportunityid})
personas: []
provider_name: Microsoft Dynamics 365
provider_slug: microsoft-dynamics-365
search_terms:
- microsoft dynamics 365 create a contact
- microsoft dynamics 365 delete an opportunity
- listaccounts
- listcontacts
- dynamics
- createaccount
- microsoft dynamics 365 update an account
- microsoft dynamics 365 list contacts
- microsoft dynamics 365 delete a contact
- microsoft dynamics 365 list opportunities
- microsoft dynamics 365 delete an account
- deleteaccount
- createopportunity
- microsoft dynamics 365 create an opportunity
- cloud
- microsoft dynamics 365 retrieve an opportunity
- microsoft dynamics 365 update an opportunity
- enterprise
- '365'
- getaccount
- microsoft dynamics 365 create an account
- updatecontact
- getcontact
- erp
- crm
- createcontact
- deleteopportunity
- microsoft dynamics 365 update a contact
- microsoft dynamics 365 retrieve a contact
- api
- updateaccount
- business applications
- getopportunity
- listopportunities
- microsoft dynamics 365 retrieve an account
- microsoft dynamics 365 list accounts
- updateopportunity
- microsoft
- deletecontact
slug: microsoft-dynamics-365-capability
source_filename: microsoft-dynamics-365-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Dynamics 365 Dataverse Web API\n  description: RESTful web service implementing OData v4.0 for interacting with data in Microsoft Dataverse, the underlying\n    data platform for Dynamics 365 and Power Platform applications. This specification covers core CRM entities including\n    accounts, contacts, and opportunities.\n  tags:\n  - Microsoft\n  - Dynamics\n  - '365'\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-dynamics-365\n    baseUri: https://yourorg.api.crm.dynamics.com/api/data/v9.2\n    description: Microsoft Dynamics 365 Dataverse Web API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_DYNAMICS_365_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      operations:\n      - name: listaccounts\n        method: GET\n        description: Microsoft Dynamics 365 List accounts\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaccount\n        method: POST\n        description: Microsoft Dynamics 365 Create an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid\n      path: /accounts({accountid})\n      operations:\n      - name: getaccount\n        method: GET\n        description: Microsoft Dynamics 365 Retrieve an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n        method: PATCH\n        description: Microsoft Dynamics 365 Update an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaccount\n        method: DELETE\n        description: Microsoft Dynamics\
  \ 365 Delete an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /contacts\n      operations:\n      - name: listcontacts\n        method: GET\n        description: Microsoft Dynamics 365 List contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontact\n        method: POST\n        description: Microsoft Dynamics 365 Create a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-contactid\n      path: /contacts({contactid})\n      operations:\n      - name: getcontact\n        method: GET\n        description: Microsoft Dynamics 365 Retrieve a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n      - name: updatecontact\n        method: PATCH\n        description: Microsoft Dynamics 365 Update a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontact\n        method: DELETE\n        description: Microsoft Dynamics 365 Delete a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: opportunities\n      path: /opportunities\n      operations:\n      - name: listopportunities\n        method: GET\n        description: Microsoft Dynamics 365 List opportunities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createopportunity\n        method: POST\n        description: Microsoft Dynamics 365 Create an opportunity\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: opportunities-opportunityid\n      path: /opportunities({opportunityid})\n      operations:\n      - name: getopportunity\n        method: GET\n        description: Microsoft Dynamics 365 Retrieve an opportunity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateopportunity\n        method: PATCH\n        description: Microsoft Dynamics 365 Update an opportunity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteopportunity\n        method: DELETE\n        description: Microsoft Dynamics 365 Delete an opportunity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-dynamics-365-rest\n\
  \    description: REST adapter for Microsoft Dynamics 365 Dataverse Web API.\n    resources:\n    - path: /accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: Microsoft Dynamics 365 List accounts\n        call: microsoft-dynamics-365.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: createaccount\n      operations:\n      - method: POST\n        name: createaccount\n        description: Microsoft Dynamics 365 Create an account\n        call: microsoft-dynamics-365.createaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts({accountid})\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Microsoft Dynamics 365 Retrieve an account\n        call: microsoft-dynamics-365.getaccount\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /accounts({accountid})\n      name: updateaccount\n      operations:\n      - method: PATCH\n        name: updateaccount\n        description: Microsoft Dynamics 365 Update an account\n        call: microsoft-dynamics-365.updateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts({accountid})\n      name: deleteaccount\n      operations:\n      - method: DELETE\n        name: deleteaccount\n        description: Microsoft Dynamics 365 Delete an account\n        call: microsoft-dynamics-365.deleteaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: listcontacts\n      operations:\n      - method: GET\n        name: listcontacts\n        description: Microsoft Dynamics 365 List contacts\n        call: microsoft-dynamics-365.listcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name:\
  \ createcontact\n      operations:\n      - method: POST\n        name: createcontact\n        description: Microsoft Dynamics 365 Create a contact\n        call: microsoft-dynamics-365.createcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts({contactid})\n      name: getcontact\n      operations:\n      - method: GET\n        name: getcontact\n        description: Microsoft Dynamics 365 Retrieve a contact\n        call: microsoft-dynamics-365.getcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts({contactid})\n      name: updatecontact\n      operations:\n      - method: PATCH\n        name: updatecontact\n        description: Microsoft Dynamics 365 Update a contact\n        call: microsoft-dynamics-365.updatecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts({contactid})\n      name: deletecontact\n      operations:\n      -\
  \ method: DELETE\n        name: deletecontact\n        description: Microsoft Dynamics 365 Delete a contact\n        call: microsoft-dynamics-365.deletecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /opportunities\n      name: listopportunities\n      operations:\n      - method: GET\n        name: listopportunities\n        description: Microsoft Dynamics 365 List opportunities\n        call: microsoft-dynamics-365.listopportunities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /opportunities\n      name: createopportunity\n      operations:\n      - method: POST\n        name: createopportunity\n        description: Microsoft Dynamics 365 Create an opportunity\n        call: microsoft-dynamics-365.createopportunity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /opportunities({opportunityid})\n      name: getopportunity\n      operations:\n      - method: GET\n\
  \        name: getopportunity\n        description: Microsoft Dynamics 365 Retrieve an opportunity\n        call: microsoft-dynamics-365.getopportunity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /opportunities({opportunityid})\n      name: updateopportunity\n      operations:\n      - method: PATCH\n        name: updateopportunity\n        description: Microsoft Dynamics 365 Update an opportunity\n        call: microsoft-dynamics-365.updateopportunity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /opportunities({opportunityid})\n      name: deleteopportunity\n      operations:\n      - method: DELETE\n        name: deleteopportunity\n        description: Microsoft Dynamics 365 Delete an opportunity\n        call: microsoft-dynamics-365.deleteopportunity\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-dynamics-365-mcp\n \
  \   transport: http\n    description: MCP adapter for Microsoft Dynamics 365 Dataverse Web API for AI agent use.\n    tools:\n    - name: listaccounts\n      description: Microsoft Dynamics 365 List accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics-365.listaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createaccount\n      description: Microsoft Dynamics 365 Create an account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics-365.createaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccount\n      description: Microsoft Dynamics 365 Retrieve an account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics-365.getaccount\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: updateaccount\n      description: Microsoft Dynamics 365 Update an account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics-365.updateaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteaccount\n      description: Microsoft Dynamics 365 Delete an account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-dynamics-365.deleteaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontacts\n      description: Microsoft Dynamics 365 List contacts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics-365.listcontacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontact\n      description: Microsoft Dynamics 365 Create a contact\n      hints:\n  \
  \      readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics-365.createcontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontact\n      description: Microsoft Dynamics 365 Retrieve a contact\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics-365.getcontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontact\n      description: Microsoft Dynamics 365 Update a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics-365.updatecontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontact\n      description: Microsoft Dynamics 365 Delete a contact\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-dynamics-365.deletecontact\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listopportunities\n      description: Microsoft Dynamics 365 List opportunities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics-365.listopportunities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createopportunity\n      description: Microsoft Dynamics 365 Create an opportunity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics-365.createopportunity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getopportunity\n      description: Microsoft Dynamics 365 Retrieve an opportunity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics-365.getopportunity\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: updateopportunity\n      description: Microsoft Dynamics 365 Update an opportunity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics-365.updateopportunity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteopportunity\n      description: Microsoft Dynamics 365 Delete an opportunity\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-dynamics-365.deleteopportunity\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_DYNAMICS_365_TOKEN: MICROSOFT_DYNAMICS_365_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-dynamics-365/refs/heads/main/capabilities/microsoft-dynamics-365-capability.yaml
tags:
- Microsoft
- Dynamics
- '365'
- API
tools:
- description: Microsoft Dynamics 365 List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Microsoft Dynamics 365 Create an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccount
- description: Microsoft Dynamics 365 Retrieve an account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Microsoft Dynamics 365 Update an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateaccount
- description: Microsoft Dynamics 365 Delete an account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaccount
- description: Microsoft Dynamics 365 List contacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontacts
- description: Microsoft Dynamics 365 Create a contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontact
- description: Microsoft Dynamics 365 Retrieve a contact
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontact
- description: Microsoft Dynamics 365 Update a contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecontact
- description: Microsoft Dynamics 365 Delete a contact
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontact
- description: Microsoft Dynamics 365 List opportunities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listopportunities
- description: Microsoft Dynamics 365 Create an opportunity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createopportunity
- description: Microsoft Dynamics 365 Retrieve an opportunity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getopportunity
- description: Microsoft Dynamics 365 Update an opportunity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateopportunity
- description: Microsoft Dynamics 365 Delete an opportunity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteopportunity
---
