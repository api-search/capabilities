---
categories: []
consumed_apis:
- threescale-service-mgmt
- threescale-account-mgmt
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
- get developer account details
- authorize an api call against 3scale usage limits
- delete a developer account
- developer account applications
- developer account management
- list all developer accounts registered in the 3scale developer portal
- api gateway
- authorize api call
- authorize and report api usage
- authorize and report api usage in one call
- individual developer account
- list account applications
- enterprise
- delete a developer account and all associated applications
- create developer account
- get account
- get details of a specific developer account including subscriptions
- api call authorization
- create a new developer account
- subscribe account to an application plan
- list accounts
- authorize an api call and simultaneously report usage to 3scale
- list developer accounts
- create application
- delete developer account
- red hat
- subscribe a developer account to an api application plan
- api management
- create account
- create a new developer account for api access
- list applications for a developer account
- delete account
- authorize and report
- get developer account
- traffic management
- list applications
- list api applications and credentials for a developer account
- authorize an api call by checking application usage limits in 3scale
- developer portal
slug: api-management
source_filename: api-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Red Hat 3scale API Management\"\n  description: >-\n    Unified capability for managing APIs, developer accounts, applications,\n    and monitoring usage through the Red Hat 3scale API Management platform.\n    Combines the Service Management API for gateway authorization with the\n    Account Management API for developer lifecycle operations.\n  tags:\n    - API Management\n    - Developer Portal\n    - Red Hat\n    - Traffic Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      THREESCALE_PROVIDER_KEY: THREESCALE_PROVIDER_KEY\n      THREESCALE_ACCESS_TOKEN: THREESCALE_ACCESS_TOKEN\n      THREESCALE_ADMIN_DOMAIN: THREESCALE_ADMIN_DOMAIN\n\ncapability:\n  consumes:\n    - import: threescale-service-mgmt\n      location: ./shared/service-management-api.yaml\n    - import: threescale-account-mgmt\n      location: ./shared/account-management-api.yaml\n\n  exposes:\n    -\
  \ type: rest\n      port: 8080\n      namespace: threescale-api-mgmt-rest\n      description: \"Unified REST API for 3scale API management operations.\"\n      resources:\n        - path: /v1/authorize\n          name: authorization\n          description: \"API call authorization\"\n          operations:\n            - method: GET\n              name: authorize-api-call\n              description: \"Authorize an API call against 3scale usage limits\"\n              call: \"threescale-service-mgmt.authorize-transaction\"\n              with:\n                user_key: \"rest.user_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/authrep\n          name: authrep\n          description: \"Authorize and report API usage\"\n          operations:\n            - method: GET\n              name: authorize-and-report\n              description: \"Authorize and report API usage in one call\"\n              call: \"threescale-service-mgmt.authorize-and-report\"\
  \n              with:\n                user_key: \"rest.user_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts\n          name: accounts\n          description: \"Developer account management\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List developer accounts\"\n              call: \"threescale-account-mgmt.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: \"Create a new developer account\"\n              call: \"threescale-account-mgmt.create-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{id}\n          name: account\n          description: \"Individual developer account\"\n      \
  \    operations:\n            - method: GET\n              name: get-account\n              description: \"Get developer account details\"\n              call: \"threescale-account-mgmt.get-account\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-account\n              description: \"Delete a developer account\"\n              call: \"threescale-account-mgmt.delete-account\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{id}/applications\n          name: applications\n          description: \"Developer account applications\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List applications for a developer account\"\n \
  \             call: \"threescale-account-mgmt.list-applications\"\n              with:\n                account_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-application\n              description: \"Subscribe account to an application plan\"\n              call: \"threescale-account-mgmt.create-application\"\n              with:\n                account_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: threescale-api-mgmt-mcp\n      transport: http\n      description: \"MCP server for AI-assisted 3scale API management.\"\n      tools:\n        - name: authorize-api-call\n          description: \"Authorize an API call by checking application usage limits in 3scale\"\n          hints:\n            readOnly: true\n            openWorld: false\n\
  \          call: \"threescale-service-mgmt.authorize-transaction\"\n          with:\n            user_key: \"tools.user_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: authorize-and-report\n          description: \"Authorize an API call and simultaneously report usage to 3scale\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"threescale-service-mgmt.authorize-and-report\"\n          with:\n            user_key: \"tools.user_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-developer-accounts\n          description: \"List all developer accounts registered in the 3scale developer portal\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"threescale-account-mgmt.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n   \
  \     - name: create-developer-account\n          description: \"Create a new developer account for API access\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"threescale-account-mgmt.create-account\"\n          with:\n            org_name: \"tools.org_name\"\n            username: \"tools.username\"\n            email: \"tools.email\"\n            password: \"tools.password\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-developer-account\n          description: \"Get details of a specific developer account including subscriptions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"threescale-account-mgmt.get-account\"\n          with:\n            id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-account-applications\n          description: \"List\
  \ API applications and credentials for a developer account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"threescale-account-mgmt.list-applications\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-application\n          description: \"Subscribe a developer account to an API application plan\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"threescale-account-mgmt.create-application\"\n          with:\n            account_id: \"tools.account_id\"\n            plan_id: \"tools.plan_id\"\n            app_name: \"tools.app_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-developer-account\n          description: \"Delete a developer account and all associated applications\"\n          hints:\n      \
  \      readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"threescale-account-mgmt.delete-account\"\n          with:\n            id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
