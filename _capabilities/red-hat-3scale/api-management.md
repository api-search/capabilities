---
categories: []
consumed_apis: []
description: Unified capability for managing APIs, developer accounts, applications, and monitoring usage through the Red Hat 3scale API Management platform. Combines the Service Management API for gateway authorization with the Account Management API for developer lifecycle operations.
layout: capability
name: Red Hat 3scale API Management
operations:
- description: Authorize an API call against 3scale usage limits
  method: GET
  name: authorize-api-call
  path: /v1/authorize
- description: Authorize and report API usage in one call
  method: GET
  name: authorize-and-report
  path: /v1/authrep
- description: List developer accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create a new developer account
  method: POST
  name: create-account
  path: /v1/accounts
- description: Get developer account details
  method: GET
  name: get-account
  path: /v1/accounts/{id}
- description: Delete a developer account
  method: DELETE
  name: delete-account
  path: /v1/accounts/{id}
- description: List applications for a developer account
  method: GET
  name: list-applications
  path: /v1/accounts/{id}/applications
- description: Subscribe account to an application plan
  method: POST
  name: create-application
  path: /v1/accounts/{id}/applications
personas: []
provider_name: Red Hat 3scale
provider_slug: red-hat-3scale
search_terms:
- list api applications and credentials for a developer account
- delete a developer account
- authorize and report api usage in one call
- subscribe account to an application plan
- api call authorization
- create a new developer account
- developer account management
- red hat
- list applications for a developer account
- developer portal
- delete a developer account and all associated applications
- authorize api call
- get developer account details
- authorize and report
- enterprise
- authorize and report api usage
- get developer account
- subscribe a developer account to an api application plan
- create developer account
- delete developer account
- get details of a specific developer account including subscriptions
- authorize an api call and simultaneously report usage to 3scale
- authorize an api call against 3scale usage limits
- create a new developer account for api access
- list account applications
- api management
- api gateway
- create account
- traffic management
- list accounts
- create application
- list all developer accounts registered in the 3scale developer portal
- get account
- delete account
- individual developer account
- developer account applications
- list applications
- list developer accounts
- authorize an api call by checking application usage limits in 3scale
slug: api-management
source_filename: api-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Red Hat 3scale API Management\n  description: Unified capability for managing APIs, developer accounts, applications, and monitoring usage through the Red\n    Hat 3scale API Management platform. Combines the Service Management API for gateway authorization with the Account Management\n    API for developer lifecycle operations.\n  tags:\n  - API Management\n  - Developer Portal\n  - Red Hat\n  - Traffic Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    THREESCALE_PROVIDER_KEY: THREESCALE_PROVIDER_KEY\n    THREESCALE_ACCESS_TOKEN: THREESCALE_ACCESS_TOKEN\n    THREESCALE_ADMIN_DOMAIN: THREESCALE_ADMIN_DOMAIN\ncapability:\n  consumes:\n  - type: http\n    namespace: threescale-service-mgmt\n    baseUri: https://su1.3scale.net\n    description: 3scale Service Management API for API call authorization and reporting\n    authentication:\n      type: apikey\n      key: provider_key\n      value:\
  \ '{{THREESCALE_PROVIDER_KEY}}'\n      placement: query\n    resources:\n    - name: authorization\n      path: /transactions\n      description: API call authorization and usage reporting\n      operations:\n      - name: authorize-transaction\n        method: GET\n        description: Authorize an API call by checking usage limits\n        inputParameters:\n        - name: user_key\n          in: query\n          type: string\n          required: true\n          description: The API key of the application\n        - name: service_id\n          in: query\n          type: string\n          required: false\n          description: The service ID\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: authorize-and-report\n        method: GET\n        description: Authorize and report usage in a single call\n        inputParameters:\n        - name: user_key\n          in: query\n          type: string\n\
  \          required: true\n          description: The API key of the application\n        - name: service_id\n          in: query\n          type: string\n          required: false\n          description: The service ID\n        - name: usage_hits\n          in: query\n          type: integer\n          required: false\n          description: Number of hits to report\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: report-transactions\n        method: POST\n        description: Report multiple API usage transactions in batch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            provider_key: '{{THREESCALE_PROVIDER_KEY}}'\n  - type: http\n    namespace: threescale-account-mgmt\n    baseUri: https://{{THREESCALE_ADMIN_DOMAIN}}-admin.3scale.net/admin/api\n    description:\
  \ 3scale Account Management API for developer lifecycle operations\n    authentication:\n      type: apikey\n      key: access_token\n      value: '{{THREESCALE_ACCESS_TOKEN}}'\n      placement: query\n    resources:\n    - name: accounts\n      path: /accounts.json\n      description: Developer account management\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all developer accounts\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by account state (approved, pending, rejected)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new developer account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            org_name: '{{tools.org_name}}'\n            username: '{{tools.username}}'\n            email: '{{tools.email}}'\n            password: '{{tools.password}}'\n    - name: account-detail\n      path: /accounts/{id}.json\n      description: Individual account management\n      operations:\n      - name: get-account\n        method: GET\n        description: Get developer account details\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \   - name: delete-account\n        method: DELETE\n        description: Delete a developer account\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /accounts/{account_id}/applications.json\n      description: Application management for a developer account\n      operations:\n      - name: list-applications\n        method: GET\n        description: List applications for an account\n        inputParameters:\n        - name: account_id\n          in: path\n          type: integer\n          required: true\n          description: Developer account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method:\
  \ POST\n        description: Create a new application subscription\n        inputParameters:\n        - name: account_id\n          in: path\n          type: integer\n          required: true\n          description: Developer account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            plan_id: '{{tools.plan_id}}'\n            name: '{{tools.app_name}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: threescale-api-mgmt-rest\n    description: Unified REST API for 3scale API management operations.\n    resources:\n    - path: /v1/authorize\n      name: authorization\n      description: API call authorization\n      operations:\n      - method: GET\n        name: authorize-api-call\n        description: Authorize an API call against 3scale usage limits\n        call: threescale-service-mgmt.authorize-transaction\n        with:\n     \
  \     user_key: rest.user_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/authrep\n      name: authrep\n      description: Authorize and report API usage\n      operations:\n      - method: GET\n        name: authorize-and-report\n        description: Authorize and report API usage in one call\n        call: threescale-service-mgmt.authorize-and-report\n        with:\n          user_key: rest.user_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: Developer account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List developer accounts\n        call: threescale-account-mgmt.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-account\n        description: Create a new developer account\n        call: threescale-account-mgmt.create-account\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{id}\n      name: account\n      description: Individual developer account\n      operations:\n      - method: GET\n        name: get-account\n        description: Get developer account details\n        call: threescale-account-mgmt.get-account\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-account\n        description: Delete a developer account\n        call: threescale-account-mgmt.delete-account\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{id}/applications\n      name: applications\n      description: Developer account applications\n      operations:\n      - method: GET\n        name: list-applications\n        description: List applications for a developer account\n        call: threescale-account-mgmt.list-applications\n\
  \        with:\n          account_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-application\n        description: Subscribe account to an application plan\n        call: threescale-account-mgmt.create-application\n        with:\n          account_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: threescale-api-mgmt-mcp\n    transport: http\n    description: MCP server for AI-assisted 3scale API management.\n    tools:\n    - name: authorize-api-call\n      description: Authorize an API call by checking application usage limits in 3scale\n      hints:\n        readOnly: true\n        openWorld: false\n      call: threescale-service-mgmt.authorize-transaction\n      with:\n        user_key: tools.user_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorize-and-report\n      description:\
  \ Authorize an API call and simultaneously report usage to 3scale\n      hints:\n        readOnly: false\n        openWorld: false\n      call: threescale-service-mgmt.authorize-and-report\n      with:\n        user_key: tools.user_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-developer-accounts\n      description: List all developer accounts registered in the 3scale developer portal\n      hints:\n        readOnly: true\n        openWorld: true\n      call: threescale-account-mgmt.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-developer-account\n      description: Create a new developer account for API access\n      hints:\n        readOnly: false\n        openWorld: false\n      call: threescale-account-mgmt.create-account\n      with:\n        org_name: tools.org_name\n        username: tools.username\n        email: tools.email\n        password: tools.password\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-developer-account\n      description: Get details of a specific developer account including subscriptions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: threescale-account-mgmt.get-account\n      with:\n        id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-account-applications\n      description: List API applications and credentials for a developer account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: threescale-account-mgmt.list-applications\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application\n      description: Subscribe a developer account to an API application plan\n      hints:\n        readOnly: false\n        openWorld: false\n      call: threescale-account-mgmt.create-application\n      with:\n        account_id:\
  \ tools.account_id\n        plan_id: tools.plan_id\n        app_name: tools.app_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-developer-account\n      description: Delete a developer account and all associated applications\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: threescale-account-mgmt.delete-account\n      with:\n        id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/red-hat-3scale/refs/heads/main/capabilities/api-management.yaml
tags:
- API Management
- Developer Portal
- Red Hat
- Traffic Management
tools:
- description: Authorize an API call by checking application usage limits in 3scale
  hints:
    openWorld: false
    readOnly: true
  name: authorize-api-call
- description: Authorize an API call and simultaneously report usage to 3scale
  hints:
    openWorld: false
    readOnly: false
  name: authorize-and-report
- description: List all developer accounts registered in the 3scale developer portal
  hints:
    openWorld: true
    readOnly: true
  name: list-developer-accounts
- description: Create a new developer account for API access
  hints:
    openWorld: false
    readOnly: false
  name: create-developer-account
- description: Get details of a specific developer account including subscriptions
  hints:
    openWorld: true
    readOnly: true
  name: get-developer-account
- description: List API applications and credentials for a developer account
  hints:
    openWorld: true
    readOnly: true
  name: list-account-applications
- description: Subscribe a developer account to an API application plan
  hints:
    openWorld: false
    readOnly: false
  name: create-application
- description: Delete a developer account and all associated applications
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-developer-account
---
