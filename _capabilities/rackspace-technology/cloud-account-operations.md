---
categories: []
consumed_apis: []
description: 'Unified workflow for Rackspace cloud account operators: authenticate with Cloud Identity, look up the customer account (RCN) and contacts, and manage DNS zones and records under the tenant. Combines Cloud Identity, Customer Service, and Cloud DNS into a single REST and MCP surface used by managed-cloud operators and platform admins.'
layout: capability
name: Rackspace Cloud Account Operations
operations:
- description: Authenticate and obtain a service token.
  method: POST
  name: create-session
  path: /v1/sessions
- description: List identity users.
  method: GET
  name: list-users
  path: /v1/users
- description: List customer accounts the caller can access.
  method: GET
  name: list-customer-accounts
  path: /v1/customer-accounts
- description: Get a customer account by RCN.
  method: GET
  name: get-customer-account
  path: /v1/customer-accounts
- description: List contacts for a customer account.
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: List DNS zones for the tenant.
  method: GET
  name: list-dns-zones
  path: /v1/dns-zones
- description: Create one or more DNS zones.
  method: POST
  name: create-dns-zones
  path: /v1/dns-zones
- description: Show DNS zone details.
  method: GET
  name: show-dns-zone
  path: /v1/dns-zones
- description: Delete a DNS zone.
  method: DELETE
  name: delete-dns-zone
  path: /v1/dns-zones
- description: List records in a DNS zone.
  method: GET
  name: list-dns-records
  path: /v1/dns-records
- description: Add records to a DNS zone.
  method: POST
  name: add-dns-records
  path: /v1/dns-records
personas: []
provider_name: Rackspace Technology
provider_slug: rackspace-technology
search_terms:
- delete dns zone
- authenticate to rackspace cloud identity using configured credentials and obtain a service token.
- multicloud
- authentication sessions.
- dns zones (domains) under the tenant.
- list rackspace customer accounts (rcns) accessible to the caller.
- create one or more dns zones.
- identity
- dns
- infrastructure
- list identity users.
- list rackspace cloud dns zones for the configured tenant.
- devops
- list dns records
- create session
- customer account lookups.
- get customer account
- list records in a dns zone.
- add records to a dns zone.
- customer contact lookups.
- cloud
- add dns records to a rackspace cloud dns zone.
- list records in a rackspace cloud dns zone.
- dns records within a zone.
- identity user lookups.
- authenticate rackspace
- create dns zones
- show dns zone
- add dns records
- managed services
- delete a dns zone.
- get a rackspace customer account by rcn.
- list customer accounts the caller can access.
- authenticate and obtain a service token.
- show dns zone details.
- account
- list customer accounts
- list users
- list contacts
- list dns zones
- list contacts for a customer account.
- get a customer account by rcn.
- rackspace
- list dns zones for the tenant.
slug: cloud-account-operations
source_filename: cloud-account-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rackspace Cloud Account Operations\n  description: 'Unified workflow for Rackspace cloud account operators: authenticate with Cloud Identity, look up the customer\n    account (RCN) and contacts, and manage DNS zones and records under the tenant. Combines Cloud Identity, Customer Service,\n    and Cloud DNS into a single REST and MCP surface used by managed-cloud operators and platform admins.'\n  tags:\n  - Rackspace\n  - Cloud\n  - Identity\n  - Account\n  - DNS\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RACKSPACE_USERNAME: RACKSPACE_USERNAME\n    RACKSPACE_API_KEY: RACKSPACE_API_KEY\n    RACKSPACE_AUTH_TOKEN: RACKSPACE_AUTH_TOKEN\n    RACKSPACE_ACCOUNT_ID: RACKSPACE_ACCOUNT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: cloud-identity\n    baseUri: https://identity.api.rackspacecloud.com\n    description: Rackspace Cloud Identity v2.0 API.\n    authentication:\n      type:\
  \ header\n      header: X-Auth-Token\n      value: '{{env.RACKSPACE_AUTH_TOKEN}}'\n    resources:\n    - name: tokens\n      path: /v2.0/tokens\n      description: Authentication tokens.\n      operations:\n      - name: authenticate\n        method: POST\n        description: Authenticate with username and API key, return a service token.\n        body:\n          type: json\n          data:\n            auth:\n              RAX-KSKEY:apiKeyCredentials:\n                username: '{{env.RACKSPACE_USERNAME}}'\n                apiKey: '{{env.RACKSPACE_API_KEY}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: token\n          type: string\n          value: $.access.token.id\n        - name: serviceCatalog\n          type: array\n          value: $.access.serviceCatalog\n      - name: validate-token\n        method: GET\n        description: Validate a token and return associated user/roles.\n        inputParameters:\n        - name: tokenId\n          in: path\n\
  \          type: string\n          required: true\n          description: Token to validate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /v2.0/users\n      description: Identity users.\n      operations:\n      - name: list-users\n        method: GET\n        description: List users accessible to the caller.\n        outputRawFormat: json\n        outputParameters:\n        - name: users\n          type: array\n          value: $.users\n      - name: get-user\n        method: GET\n        description: Get a user by ID.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.user\n    - name: roles\n      path: /v2.0/users/{userId}/roles\n      description:\
  \ Role assignments for a user.\n      operations:\n      - name: list-user-roles\n        method: GET\n        description: List global roles assigned to a user.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: roles\n          type: array\n          value: $.roles\n  - type: http\n    namespace: customer-service\n    baseUri: https://accounts.api.rackspacecloud.com\n    description: Rackspace Customer Service v1 API.\n    authentication:\n      type: header\n      header: X-Auth-Token\n      value: '{{env.RACKSPACE_AUTH_TOKEN}}'\n    resources:\n    - name: customer-accounts\n      path: /v1/customer_accounts\n      description: Customer accounts the caller can access.\n      operations:\n      - name: list-customer-accounts\n        method: GET\n        description: List customer accounts accessible\
  \ to the caller.\n        outputRawFormat: json\n        outputParameters:\n        - name: accounts\n          type: array\n          value: $.customer_accounts\n      - name: get-customer-account\n        method: GET\n        description: Get a customer account by RCN.\n        inputParameters:\n        - name: rcn\n          in: path\n          type: string\n          required: true\n          description: Rackspace Customer Number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /v1/customer_accounts/{rcn}/contacts\n      description: Contacts associated with a customer account.\n      operations:\n      - name: list-contacts\n        method: GET\n        description: List contacts for a customer account.\n        inputParameters:\n        - name: rcn\n          in: path\n          type: string\n          required: true\n          description: Rackspace Customer Number.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: contacts\n          type: array\n          value: $.contacts\n  - type: http\n    namespace: cloud-dns\n    baseUri: https://dns.api.rackspacecloud.com/v1.0\n    description: Rackspace Cloud DNS API v1.0.\n    authentication:\n      type: header\n      header: X-Auth-Token\n      value: '{{env.RACKSPACE_AUTH_TOKEN}}'\n    resources:\n    - name: domains\n      path: /{accountId}/domains\n      description: DNS zones.\n      operations:\n      - name: list-domains\n        method: GET\n        description: List all DNS domains for the account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Tenant ID.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results (<=100).\n        - name: offset\n          in: query\n          type: integer\n \
  \         required: false\n          description: Pagination offset.\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-domains\n        method: POST\n        description: Create one or more DNS domains.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Tenant ID.\n        body:\n          type: json\n          data:\n            domains: '{{tools.domains}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: show-domain\n        method: GET\n        description: Get details for a single DNS domain.\n        inputParameters:\n        - name: accountId\n          in: path\n \
  \         type: string\n          required: true\n          description: Tenant ID.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-domain\n        method: DELETE\n        description: Delete a DNS domain.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Tenant ID.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain ID.\n        - name: deleteSubdomains\n          in: query\n          type: boolean\n          required: false\n          description: Also delete subdomains.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: records\n      path: /{accountId}/domains/{domainId}/records\n      description: DNS records within a domain.\n      operations:\n      - name: list-records\n        method: GET\n        description: List DNS records for a domain.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Tenant ID.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain ID.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Record type filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-records\n        method: POST\n        description: Add DNS records to a domain.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n\
  \          required: true\n          description: Tenant ID.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain ID.\n        body:\n          type: json\n          data:\n            records: '{{tools.records}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: cloud-account-operations-api\n    description: Unified REST API for Rackspace cloud account operations.\n    resources:\n    - path: /v1/sessions\n      name: sessions\n      description: Authentication sessions.\n      operations:\n      - method: POST\n        name: create-session\n        description: Authenticate and obtain a service token.\n        call: cloud-identity.authenticate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description:\
  \ Identity user lookups.\n      operations:\n      - method: GET\n        name: list-users\n        description: List identity users.\n        call: cloud-identity.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customer-accounts\n      name: customer-accounts\n      description: Customer account lookups.\n      operations:\n      - method: GET\n        name: list-customer-accounts\n        description: List customer accounts the caller can access.\n        call: customer-service.list-customer-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-customer-account\n        description: Get a customer account by RCN.\n        call: customer-service.get-customer-account\n        with:\n          rcn: rest.rcn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts\n      name: contacts\n      description: Customer contact lookups.\n\
  \      operations:\n      - method: GET\n        name: list-contacts\n        description: List contacts for a customer account.\n        call: customer-service.list-contacts\n        with:\n          rcn: rest.rcn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dns-zones\n      name: dns-zones\n      description: DNS zones (domains) under the tenant.\n      operations:\n      - method: GET\n        name: list-dns-zones\n        description: List DNS zones for the tenant.\n        call: cloud-dns.list-domains\n        with:\n          accountId: '{{env.RACKSPACE_ACCOUNT_ID}}'\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dns-zones\n        description: Create one or more DNS zones.\n        call: cloud-dns.create-domains\n        with:\n          accountId: '{{env.RACKSPACE_ACCOUNT_ID}}'\n          domains: rest.domains\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: GET\n        name: show-dns-zone\n        description: Show DNS zone details.\n        call: cloud-dns.show-domain\n        with:\n          accountId: '{{env.RACKSPACE_ACCOUNT_ID}}'\n          domainId: rest.domainId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-dns-zone\n        description: Delete a DNS zone.\n        call: cloud-dns.delete-domain\n        with:\n          accountId: '{{env.RACKSPACE_ACCOUNT_ID}}'\n          domainId: rest.domainId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dns-records\n      name: dns-records\n      description: DNS records within a zone.\n      operations:\n      - method: GET\n        name: list-dns-records\n        description: List records in a DNS zone.\n        call: cloud-dns.list-records\n        with:\n          accountId: '{{env.RACKSPACE_ACCOUNT_ID}}'\n          domainId: rest.domainId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-dns-records\n        description: Add records to a DNS zone.\n        call: cloud-dns.add-records\n        with:\n          accountId: '{{env.RACKSPACE_ACCOUNT_ID}}'\n          domainId: rest.domainId\n          records: rest.records\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 8082\n    namespace: cloud-account-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted Rackspace cloud account operations.\n    tools:\n    - name: authenticate-rackspace\n      description: Authenticate to Rackspace Cloud Identity using configured credentials and obtain a service token.\n      hints:\n        readOnly: false\n        openWorld: true\n      call: cloud-identity.authenticate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customer-accounts\n      description: List\
  \ Rackspace customer accounts (RCNs) accessible to the caller.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: customer-service.list-customer-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer-account\n      description: Get a Rackspace customer account by RCN.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: customer-service.get-customer-account\n      with:\n        rcn: tools.rcn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dns-zones\n      description: List Rackspace Cloud DNS zones for the configured tenant.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-dns.list-domains\n      with:\n        accountId: '{{env.RACKSPACE_ACCOUNT_ID}}'\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dns-records\n      description: List records in a Rackspace Cloud DNS zone.\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: cloud-dns.list-records\n      with:\n        accountId: '{{env.RACKSPACE_ACCOUNT_ID}}'\n        domainId: tools.domainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-dns-records\n      description: Add DNS records to a Rackspace Cloud DNS zone.\n      hints:\n        readOnly: false\n        openWorld: true\n      call: cloud-dns.add-records\n      with:\n        accountId: '{{env.RACKSPACE_ACCOUNT_ID}}'\n        domainId: tools.domainId\n        records: tools.records\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rackspace-technology/refs/heads/main/capabilities/cloud-account-operations.yaml
tags:
- Rackspace
- Cloud
- Identity
- Account
- DNS
tools:
- description: Authenticate to Rackspace Cloud Identity using configured credentials and obtain a service token.
  hints:
    openWorld: true
    readOnly: false
  name: authenticate-rackspace
- description: List Rackspace customer accounts (RCNs) accessible to the caller.
  hints:
    openWorld: true
    readOnly: true
  name: list-customer-accounts
- description: Get a Rackspace customer account by RCN.
  hints:
    openWorld: true
    readOnly: true
  name: get-customer-account
- description: List Rackspace Cloud DNS zones for the configured tenant.
  hints:
    openWorld: true
    readOnly: true
  name: list-dns-zones
- description: List records in a Rackspace Cloud DNS zone.
  hints:
    openWorld: true
    readOnly: true
  name: list-dns-records
- description: Add DNS records to a Rackspace Cloud DNS zone.
  hints:
    openWorld: true
    readOnly: false
  name: add-dns-records
---
