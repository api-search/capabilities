---
categories: []
consumed_apis: []
description: Unified workflow capability for customer-facing operations using StackOne's unified APIs. Combines CRM (contacts, accounts, lists) and Marketing (campaigns, email/push/omni-channel templates) for managing customer relationships and multi-channel communications across platforms. Designed for marketing teams, CRM administrators, and AI agents automating customer outreach.
layout: capability
name: StackOne Customer Engagement
operations:
- description: List CRM contacts
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Create a new contact
  method: POST
  name: create-contact
  path: /v1/contacts
- description: List marketing campaigns
  method: GET
  name: list-campaigns
  path: /v1/campaigns
personas: []
provider_name: StackOne
provider_slug: stackone
search_terms:
- list marketing campaigns
- create contact
- proxy request
- campaigns
- marketing
- proxy a custom request to any connected provider api
- unified api
- crm contacts
- create a new contact in the connected crm system
- list campaigns
- integrations
- crm
- marketing campaigns
- ipaas
- list crm contacts
- list contacts from the connected crm system (salesforce, hubspot, etc.)
- create a new contact
- list marketing campaigns from the connected platform (mailchimp, braze, etc.)
- customer engagement
- list contacts
slug: customer-engagement
source_filename: customer-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: StackOne Customer Engagement\n  description: Unified workflow capability for customer-facing operations using StackOne's unified APIs. Combines CRM (contacts,\n    accounts, lists) and Marketing (campaigns, email/push/omni-channel templates) for managing customer relationships and\n    multi-channel communications across platforms. Designed for marketing teams, CRM administrators, and AI agents automating\n    customer outreach.\n  tags:\n  - CRM\n  - Marketing\n  - Customer Engagement\n  - Unified API\n  - Campaigns\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STACKONE_API_KEY: STACKONE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stackone\n    baseUri: https://api.stackone.com\n    description: StackOne unified integration platform API\n    authentication:\n      type: basic\n      username: '{{STACKONE_API_KEY}}'\n      password: ''\n    resources:\n    - name: accounts\n\
  \      path: /accounts\n      description: Manage linked integration accounts\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all linked integration accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Get a specific linked account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-account\n        method: DELETE\n        description: Remove a linked account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: connect-sessions\n      path: /connect_sessions\n      description: Manage integration connect sessions\n      operations:\n      - name: create-connect-session\n        method: POST\n        description: Create a connect session for onboarding\n        body:\n          type: json\n          data:\n            provider: '{{tools.provider}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hris-employees\n      path: /unified/hris/employees\n      description: HRIS employee management\n      operations:\n      - name: list-employees\n        method: GET\n        description: List employees across HRIS systems\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n          description: StackOne account ID for the HRIS integration\n        - name: page\n          in: query\n          type: integer\n\
  \          required: false\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-employee\n        method: GET\n        description: Get a specific employee\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-employee\n        method: POST\n        description: Create a new employee\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            first_name: '{{tools.first_name}}'\n\
  \            last_name: '{{tools.last_name}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-employee\n        method: PATCH\n        description: Update an employee\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hris-time-off\n      path: /unified/hris/time_off\n      description: HRIS time off request management\n      operations:\n      - name: list-time-off\n        method: GET\n        description: List time off requests\n        inputParameters:\n\
  \        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-time-off\n        method: POST\n        description: Create a time off request\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            employee_id: '{{tools.employee_id}}'\n            type: '{{tools.type}}'\n            start_date: '{{tools.start_date}}'\n            end_date: '{{tools.end_date}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-candidates\n      path: /unified/ats/candidates\n      description: ATS candidate management\n      operations:\n      - name: list-candidates\n        method: GET\n\
  \        description: List candidates across ATS systems\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-candidate\n        method: GET\n        description: Get a specific candidate\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-jobs\n      path: /unified/ats/jobs\n      description: ATS job management\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List jobs across ATS systems\n        inputParameters:\n        - name:\
  \ x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job\n        method: GET\n        description: Get a specific job\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-applications\n      path: /unified/ats/applications\n      description: ATS application tracking\n      operations:\n      - name: list-applications\n        method: GET\n        description: List job applications\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get a specific application\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crm-contacts\n      path: /unified/crm/contacts\n      description: CRM contact management\n      operations:\n      - name: list-contacts\n        method: GET\n        description: List contacts across CRM systems\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a new CRM contact\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: marketing-campaigns\n      path: /unified/marketing/campaigns\n      description: Marketing campaign management\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List campaigns across marketing platforms\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: proxy\n      path: /unified/proxy\n      description: Proxy requests to provider APIs\n      operations:\n      - name: proxy-request\n        method: POST\n        description: Forward a request directly to a provider API\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            path: '{{tools.path}}'\n            method: '{{tools.method}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: stackone-engagement-api\n    description: Unified REST API for CRM and marketing operations.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n      description: CRM contacts\n      operations:\n     \
  \ - method: GET\n        name: list-contacts\n        description: List CRM contacts\n        call: stackone.list-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-contact\n        description: Create a new contact\n        call: stackone.create-contact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns\n      name: campaigns\n      description: Marketing campaigns\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List marketing campaigns\n        call: stackone.list-campaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: stackone-engagement-mcp\n    transport: http\n    description: MCP server for AI-assisted CRM and marketing operations.\n    tools:\n    - name: list-contacts\n      description: List contacts from the connected CRM system (Salesforce,\
  \ HubSpot, etc.)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stackone.list-contacts\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-contact\n      description: Create a new contact in the connected CRM system\n      hints:\n        readOnly: false\n      call: stackone.create-contact\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-campaigns\n      description: List marketing campaigns from the connected platform (Mailchimp, Braze, etc.)\n      hints:\n        readOnly: true\n      call: stackone.list-campaigns\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxy-request\n      description: Proxy a custom request to any connected provider API\n      hints:\n        readOnly: false\n      call:\
  \ stackone.proxy-request\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stackone/refs/heads/main/capabilities/customer-engagement.yaml
tags:
- CRM
- Marketing
- Customer Engagement
- Unified API
- Campaigns
tools:
- description: List contacts from the connected CRM system (Salesforce, HubSpot, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Create a new contact in the connected CRM system
  hints:
    readOnly: false
  name: create-contact
- description: List marketing campaigns from the connected platform (Mailchimp, Braze, etc.)
  hints:
    readOnly: true
  name: list-campaigns
- description: Proxy a custom request to any connected provider API
  hints:
    readOnly: false
  name: proxy-request
---
