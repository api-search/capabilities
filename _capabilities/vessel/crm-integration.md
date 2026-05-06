---
categories: []
consumed_apis: []
description: Unified CRM integration capability composing the Vessel CRM API for embedded CRM workflows. Enables product teams to build native CRM integrations with Salesforce, HubSpot, Zoho, Pipedrive, Close, Freshsales, Microsoft Dynamics, and more through a single REST and MCP interface. Handles authentication, rate limits, data normalization, and pagination automatically.
layout: capability
name: Vessel CRM Integration
operations:
- description: Get All Contacts
  method: GET
  name: get-all-contacts
  path: /v1/contacts
- description: Create a Contact
  method: POST
  name: create-contact
  path: /v1/contacts
- description: Get All Deals
  method: GET
  name: get-all-deals
  path: /v1/deals
- description: Create a Deal
  method: POST
  name: create-deal
  path: /v1/deals
- description: Get All Accounts
  method: GET
  name: get-all-accounts
  path: /v1/accounts
- description: Create an Account
  method: POST
  name: create-account
  path: /v1/accounts
- description: Get All Leads
  method: GET
  name: get-all-leads
  path: /v1/leads
- description: Get All Notes
  method: GET
  name: get-all-notes
  path: /v1/notes
- description: Create a Note
  method: POST
  name: create-note
  path: /v1/notes
- description: Get All Tasks
  method: GET
  name: get-all-tasks
  path: /v1/tasks
- description: Get All Users
  method: GET
  name: get-all-users
  path: /v1/users
personas: []
provider_name: Vessel
provider_slug: vessel
search_terms:
- crm contacts unified across all connected crm systems
- create a deal
- get all contacts
- get all leads
- create crm contact
- hubspot
- create contact
- embedded integrations
- tasks
- get crm contacts
- create a new deal/opportunity in the user's connected crm.
- vessel
- get crm deals
- notes
- create deal
- list all company accounts from the user's connected crm.
- get crm tasks
- create a new contact in the user's connected crm with first name, last name, email, phone, and company information.
- deals
- contacts
- list all contacts from the user's connected crm. works with salesforce, hubspot, zoho, pipedrive, close, freshsales, microsoft dynamics, and affinity. all dates are iso 8601, all ids are normalized to strings.
- unified api
- gtm
- crm tasks
- crm notes and activity log
- accounts
- create crm note
- sales engagement
- crm deals and opportunities
- get all notes
- create crm deal
- create a contact
- crm users
- create an account
- create a new note in the user's connected crm.
- integrations
- crm
- create a note
- get all deals
- list all leads from the user's connected crm.
- ipaas
- list all users from the user's connected crm.
- list all deals/opportunities from the user's connected crm. returns deal name, amount, stage, close date, and assigned owner.
- list all notes from the user's connected crm.
- get crm notes
- list all tasks from the user's connected crm.
- get crm accounts
- crm leads
- create account
- get all accounts
- leads
- get all users
- get crm leads
- crm company accounts
- create note
- get all tasks
- salesforce
- get crm users
slug: crm-integration
source_filename: crm-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vessel CRM Integration\n  description: Unified CRM integration capability composing the Vessel CRM API for embedded CRM workflows. Enables product\n    teams to build native CRM integrations with Salesforce, HubSpot, Zoho, Pipedrive, Close, Freshsales, Microsoft Dynamics,\n    and more through a single REST and MCP interface. Handles authentication, rate limits, data normalization, and pagination\n    automatically.\n  tags:\n  - Accounts\n  - CRM\n  - Contacts\n  - Deals\n  - Embedded Integrations\n  - GTM\n  - HubSpot\n  - Leads\n  - Notes\n  - Salesforce\n  - Tasks\n  - Unified API\n  - Vessel\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VESSEL_API_TOKEN: VESSEL_API_TOKEN\n    VESSEL_ACCESS_TOKEN: VESSEL_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: vessel-crm\n    baseUri: https://api.vessel.land\n    description: Vessel CRM API for unified CRM operations\n    authentication:\n\
  \      type: apikey\n      key: vessel-api-token\n      value: '{{env.VESSEL_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: contacts\n      path: /crm/contacts\n      description: CRM contacts\n      operations:\n      - name: get-all-contacts\n        method: GET\n        description: Get All Contacts\n        inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n          required: true\n          description: User connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a Contact\n        inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n          required: true\n          description:\
  \ User connection access token\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deals\n      path: /crm/deals\n      description: CRM deals\n      operations:\n      - name: get-all-deals\n        method: GET\n        description: Get All Deals\n        inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n          required: true\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deal\n        method: POST\n        description: Create a Deal\n        inputParameters:\n        - name: accessToken\n\
  \          in: query\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            amount: '{{tools.amount}}'\n            stage: '{{tools.stage}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /crm/accounts\n      description: CRM accounts\n      operations:\n      - name: get-all-accounts\n        method: GET\n        description: Get All Accounts\n        inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n          required: true\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create an Account\n\
  \        inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            domain: '{{tools.domain}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leads\n      path: /crm/leads\n      description: CRM leads\n      operations:\n      - name: get-all-leads\n        method: GET\n        description: Get All Leads\n        inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notes\n      path: /crm/notes\n      description: CRM notes\n      operations:\n      - name: get-all-notes\n        method: GET\n        description: Get All Notes\n      \
  \  inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-note\n        method: POST\n        description: Create a Note\n        inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            content: '{{tools.content}}'\n            contactId: '{{tools.contactId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /crm/tasks\n      description: CRM tasks\n      operations:\n      - name: get-all-tasks\n        method: GET\n        description: Get All Tasks\n        inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /crm/users\n      description: CRM users\n      operations:\n      - name: get-all-users\n        method: GET\n        description: Get All Users\n        inputParameters:\n        - name: accessToken\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: crm-integration-api\n    description: Unified REST API for embedded CRM integration across Salesforce, HubSpot, and 8+ CRM systems.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n      description: CRM contacts unified across all connected CRM systems\n      operations:\n      - method: GET\n        name: get-all-contacts\n        description:\
  \ Get All Contacts\n        call: vessel-crm.get-all-contacts\n        with:\n          accessToken: rest.accessToken\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-contact\n        description: Create a Contact\n        call: vessel-crm.create-contact\n        with:\n          accessToken: rest.accessToken\n          firstName: rest.firstName\n          lastName: rest.lastName\n          email: rest.email\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deals\n      name: deals\n      description: CRM deals and opportunities\n      operations:\n      - method: GET\n        name: get-all-deals\n        description: Get All Deals\n        call: vessel-crm.get-all-deals\n        with:\n          accessToken: rest.accessToken\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n\
  \        name: create-deal\n        description: Create a Deal\n        call: vessel-crm.create-deal\n        with:\n          accessToken: rest.accessToken\n          name: rest.name\n          amount: rest.amount\n          stage: rest.stage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: CRM company accounts\n      operations:\n      - method: GET\n        name: get-all-accounts\n        description: Get All Accounts\n        call: vessel-crm.get-all-accounts\n        with:\n          accessToken: rest.accessToken\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-account\n        description: Create an Account\n        call: vessel-crm.create-account\n        with:\n          accessToken: rest.accessToken\n          name: rest.name\n          domain: rest.domain\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /v1/leads\n      name: leads\n      description: CRM leads\n      operations:\n      - method: GET\n        name: get-all-leads\n        description: Get All Leads\n        call: vessel-crm.get-all-leads\n        with:\n          accessToken: rest.accessToken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/notes\n      name: notes\n      description: CRM notes and activity log\n      operations:\n      - method: GET\n        name: get-all-notes\n        description: Get All Notes\n        call: vessel-crm.get-all-notes\n        with:\n          accessToken: rest.accessToken\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-note\n        description: Create a Note\n        call: vessel-crm.create-note\n        with:\n          accessToken: rest.accessToken\n          content: rest.content\n          contactId: rest.contactId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: CRM tasks\n      operations:\n      - method: GET\n        name: get-all-tasks\n        description: Get All Tasks\n        call: vessel-crm.get-all-tasks\n        with:\n          accessToken: rest.accessToken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: CRM users\n      operations:\n      - method: GET\n        name: get-all-users\n        description: Get All Users\n        call: vessel-crm.get-all-users\n        with:\n          accessToken: rest.accessToken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: crm-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted CRM operations across Salesforce, HubSpot, and 8+ CRM systems.\n    tools:\n    - name: get-crm-contacts\n\
  \      description: List all contacts from the user's connected CRM. Works with Salesforce, HubSpot, Zoho, Pipedrive, Close,\n        Freshsales, Microsoft Dynamics, and Affinity. All dates are ISO 8601, all IDs are normalized to strings.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vessel-crm.get-all-contacts\n      with:\n        accessToken: tools.accessToken\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-crm-contact\n      description: Create a new contact in the user's connected CRM with first name, last name, email, phone, and company\n        information.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: vessel-crm.create-contact\n      with:\n        accessToken: tools.accessToken\n        firstName: tools.firstName\n        lastName: tools.lastName\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: get-crm-deals\n      description: List all deals/opportunities from the user's connected CRM. Returns deal name, amount, stage, close date,\n        and assigned owner.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vessel-crm.get-all-deals\n      with:\n        accessToken: tools.accessToken\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-crm-deal\n      description: Create a new deal/opportunity in the user's connected CRM.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: vessel-crm.create-deal\n      with:\n        accessToken: tools.accessToken\n        name: tools.name\n        amount: tools.amount\n        stage: tools.stage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-crm-accounts\n      description: List all company accounts from the user's connected CRM.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: vessel-crm.get-all-accounts\n      with:\n        accessToken: tools.accessToken\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-crm-leads\n      description: List all leads from the user's connected CRM.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vessel-crm.get-all-leads\n      with:\n        accessToken: tools.accessToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-crm-notes\n      description: List all notes from the user's connected CRM.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vessel-crm.get-all-notes\n      with:\n        accessToken: tools.accessToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-crm-note\n      description: Create a new note in the user's connected CRM.\n      hints:\n        readOnly: false\n        openWorld: false\n      call:\
  \ vessel-crm.create-note\n      with:\n        accessToken: tools.accessToken\n        content: tools.content\n        contactId: tools.contactId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-crm-tasks\n      description: List all tasks from the user's connected CRM.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vessel-crm.get-all-tasks\n      with:\n        accessToken: tools.accessToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-crm-users\n      description: List all users from the user's connected CRM.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vessel-crm.get-all-users\n      with:\n        accessToken: tools.accessToken\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/capabilities/crm-integration.yaml
tags:
- Accounts
- CRM
- Contacts
- Deals
- Embedded Integrations
- GTM
- HubSpot
- Leads
- Notes
- Salesforce
- Tasks
- Unified API
- Vessel
tools:
- description: List all contacts from the user's connected CRM. Works with Salesforce, HubSpot, Zoho, Pipedrive, Close, Freshsales, Microsoft Dynamics, and Affinity. All dates are ISO 8601, all IDs are normalized to strings.
  hints:
    openWorld: true
    readOnly: true
  name: get-crm-contacts
- description: Create a new contact in the user's connected CRM with first name, last name, email, phone, and company information.
  hints:
    openWorld: false
    readOnly: false
  name: create-crm-contact
- description: List all deals/opportunities from the user's connected CRM. Returns deal name, amount, stage, close date, and assigned owner.
  hints:
    openWorld: true
    readOnly: true
  name: get-crm-deals
- description: Create a new deal/opportunity in the user's connected CRM.
  hints:
    openWorld: false
    readOnly: false
  name: create-crm-deal
- description: List all company accounts from the user's connected CRM.
  hints:
    openWorld: true
    readOnly: true
  name: get-crm-accounts
- description: List all leads from the user's connected CRM.
  hints:
    openWorld: true
    readOnly: true
  name: get-crm-leads
- description: List all notes from the user's connected CRM.
  hints:
    openWorld: true
    readOnly: true
  name: get-crm-notes
- description: Create a new note in the user's connected CRM.
  hints:
    openWorld: false
    readOnly: false
  name: create-crm-note
- description: List all tasks from the user's connected CRM.
  hints:
    openWorld: true
    readOnly: true
  name: get-crm-tasks
- description: List all users from the user's connected CRM.
  hints:
    openWorld: true
    readOnly: true
  name: get-crm-users
---
