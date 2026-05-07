---
categories: []
consumed_apis: []
description: OptScale is an open-source FinOps and cloud cost optimization platform by Hystax. The REST API exposes endpoints for managing organizations, cloud accounts, employees, pools, resources, expenses, recommendations, and optimization runs across AWS, Azure, GCP, Alibaba Cloud, and Kubernetes.
layout: capability
name: OptScale REST API
operations:
- description: Create an authentication token
  method: POST
  name: createtoken
  path: /auth/v2/tokens
- description: List organizations
  method: GET
  name: listorganizations
  path: /organizations
- description: Create an organization
  method: POST
  name: createorganization
  path: /organizations
- description: Get an organization
  method: GET
  name: getorganization
  path: /organizations/{organization_id}
- description: Delete an organization
  method: DELETE
  name: deleteorganization
  path: /organizations/{organization_id}
- description: List cloud accounts for an organization
  method: GET
  name: listcloudaccounts
  path: /organizations/{organization_id}/cloud_accounts
- description: Create a cloud account connection
  method: POST
  name: createcloudaccount
  path: /organizations/{organization_id}/cloud_accounts
- description: Get cloud account
  method: GET
  name: getcloudaccount
  path: /cloud_accounts/{cloud_account_id}
- description: Disconnect a cloud account
  method: DELETE
  name: deletecloudaccount
  path: /cloud_accounts/{cloud_account_id}
- description: List organization employees
  method: GET
  name: listemployees
  path: /organizations/{organization_id}/employees
- description: List pools
  method: GET
  name: listpools
  path: /organizations/{organization_id}/pools
- description: Create a pool
  method: POST
  name: createpool
  path: /organizations/{organization_id}/pools
- description: Get pool
  method: GET
  name: getpool
  path: /pools/{pool_id}
- description: List cloud resources for a cloud account
  method: GET
  name: listcloudresources
  path: /cloud_accounts/{cloud_account_id}/cloud_resources
- description: Query expenses
  method: GET
  name: getexpenses
  path: /organizations/{organization_id}/expenses
- description: List optimization recommendations
  method: GET
  name: listoptimizations
  path: /organizations/{organization_id}/optimizations
personas: []
provider_name: OptScale
provider_slug: optscale
search_terms:
- createcloudaccount
- listcloudaccounts
- createorganization
- finops
- get pool
- optscale
- getexpenses
- api
- listorganizations
- create a cloud account connection
- get an organization
- cost optimization
- createtoken
- deletecloudaccount
- list cloud resources for a cloud account
- listcloudresources
- open source
- create an authentication token
- list pools
- getcloudaccount
- createpool
- query expenses
- list optimization recommendations
- create an organization
- list organization employees
- kubernetes
- listpools
- list organizations
- listoptimizations
- cloud
- listemployees
- list cloud accounts for an organization
- getpool
- get cloud account
- disconnect a cloud account
- deleteorganization
- getorganization
- delete an organization
- create a pool
slug: optscale-capability
source_filename: optscale-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OptScale REST API\n  description: OptScale is an open-source FinOps and cloud cost optimization platform by Hystax. The REST API exposes endpoints\n    for managing organizations, cloud accounts, employees, pools, resources, expenses, recommendations, and optimization runs\n    across AWS, Azure, GCP, Alibaba Cloud, and Kubernetes.\n  tags:\n  - Optscale\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: optscale\n    baseUri: https://my.optscale.com/restapi/v2\n    description: OptScale REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OPTSCALE_TOKEN}}'\n    resources:\n    - name: auth-v2-tokens\n      path: /auth/v2/tokens\n      operations:\n      - name: createtoken\n        method: POST\n        description: Create an authentication token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: organizations\n      path: /organizations\n      operations:\n      - name: listorganizations\n        method: GET\n        description: List organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorganization\n        method: POST\n        description: Create an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-id\n      path: /organizations/{organization_id}\n      operations:\n      - name: getorganization\n        method: GET\n        description: Get an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteorganization\n        method: DELETE\n        description: Delete an organization\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-id-cloud-accounts\n      path: /organizations/{organization_id}/cloud_accounts\n      operations:\n      - name: listcloudaccounts\n        method: GET\n        description: List cloud accounts for an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcloudaccount\n        method: POST\n        description: Create a cloud account connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-accounts-cloud-account-id\n      path: /cloud_accounts/{cloud_account_id}\n      operations:\n      - name: getcloudaccount\n        method: GET\n        description: Get cloud account\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: deletecloudaccount\n        method: DELETE\n        description: Disconnect a cloud account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-id-employees\n      path: /organizations/{organization_id}/employees\n      operations:\n      - name: listemployees\n        method: GET\n        description: List organization employees\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-id-pools\n      path: /organizations/{organization_id}/pools\n      operations:\n      - name: listpools\n        method: GET\n        description: List pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpool\n   \
  \     method: POST\n        description: Create a pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pools-pool-id\n      path: /pools/{pool_id}\n      operations:\n      - name: getpool\n        method: GET\n        description: Get pool\n        inputParameters:\n        - name: pool_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-accounts-cloud-account-id-cloud-resources\n      path: /cloud_accounts/{cloud_account_id}/cloud_resources\n      operations:\n      - name: listcloudresources\n        method: GET\n        description: List cloud resources for a cloud account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-id-expenses\n\
  \      path: /organizations/{organization_id}/expenses\n      operations:\n      - name: getexpenses\n        method: GET\n        description: Query expenses\n        inputParameters:\n        - name: start_date\n          in: query\n          type: integer\n        - name: end_date\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-id-optimizations\n      path: /organizations/{organization_id}/optimizations\n      operations:\n      - name: listoptimizations\n        method: GET\n        description: List optimization recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: optscale-rest\n    description: REST adapter for OptScale REST API.\n    resources:\n    - path: /auth/v2/tokens\n\
  \      name: createtoken\n      operations:\n      - method: POST\n        name: createtoken\n        description: Create an authentication token\n        call: optscale.createtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations\n      name: listorganizations\n      operations:\n      - method: GET\n        name: listorganizations\n        description: List organizations\n        call: optscale.listorganizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations\n      name: createorganization\n      operations:\n      - method: POST\n        name: createorganization\n        description: Create an organization\n        call: optscale.createorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}\n      name: getorganization\n      operations:\n      - method: GET\n        name: getorganization\n        description:\
  \ Get an organization\n        call: optscale.getorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}\n      name: deleteorganization\n      operations:\n      - method: DELETE\n        name: deleteorganization\n        description: Delete an organization\n        call: optscale.deleteorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}/cloud_accounts\n      name: listcloudaccounts\n      operations:\n      - method: GET\n        name: listcloudaccounts\n        description: List cloud accounts for an organization\n        call: optscale.listcloudaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}/cloud_accounts\n      name: createcloudaccount\n      operations:\n      - method: POST\n        name: createcloudaccount\n        description: Create a cloud\
  \ account connection\n        call: optscale.createcloudaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cloud_accounts/{cloud_account_id}\n      name: getcloudaccount\n      operations:\n      - method: GET\n        name: getcloudaccount\n        description: Get cloud account\n        call: optscale.getcloudaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cloud_accounts/{cloud_account_id}\n      name: deletecloudaccount\n      operations:\n      - method: DELETE\n        name: deletecloudaccount\n        description: Disconnect a cloud account\n        call: optscale.deletecloudaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}/employees\n      name: listemployees\n      operations:\n      - method: GET\n        name: listemployees\n        description: List organization employees\n        call: optscale.listemployees\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}/pools\n      name: listpools\n      operations:\n      - method: GET\n        name: listpools\n        description: List pools\n        call: optscale.listpools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}/pools\n      name: createpool\n      operations:\n      - method: POST\n        name: createpool\n        description: Create a pool\n        call: optscale.createpool\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pools/{pool_id}\n      name: getpool\n      operations:\n      - method: GET\n        name: getpool\n        description: Get pool\n        call: optscale.getpool\n        with:\n          pool_id: rest.pool_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cloud_accounts/{cloud_account_id}/cloud_resources\n\
  \      name: listcloudresources\n      operations:\n      - method: GET\n        name: listcloudresources\n        description: List cloud resources for a cloud account\n        call: optscale.listcloudresources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}/expenses\n      name: getexpenses\n      operations:\n      - method: GET\n        name: getexpenses\n        description: Query expenses\n        call: optscale.getexpenses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization_id}/optimizations\n      name: listoptimizations\n      operations:\n      - method: GET\n        name: listoptimizations\n        description: List optimization recommendations\n        call: optscale.listoptimizations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: optscale-mcp\n    transport: http\n \
  \   description: MCP adapter for OptScale REST API for AI agent use.\n    tools:\n    - name: createtoken\n      description: Create an authentication token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: optscale.createtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorganizations\n      description: List organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optscale.listorganizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorganization\n      description: Create an organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: optscale.createorganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganization\n      description: Get an organization\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: optscale.getorganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteorganization\n      description: Delete an organization\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: optscale.deleteorganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcloudaccounts\n      description: List cloud accounts for an organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optscale.listcloudaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcloudaccount\n      description: Create a cloud account connection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: optscale.createcloudaccount\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getcloudaccount\n      description: Get cloud account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optscale.getcloudaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecloudaccount\n      description: Disconnect a cloud account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: optscale.deletecloudaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listemployees\n      description: List organization employees\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optscale.listemployees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpools\n      description: List pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optscale.listpools\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpool\n      description: Create a pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: optscale.createpool\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpool\n      description: Get pool\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optscale.getpool\n      with:\n        pool_id: tools.pool_id\n      inputParameters:\n      - name: pool_id\n        type: string\n        description: pool_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcloudresources\n      description: List cloud resources for a cloud account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optscale.listcloudresources\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getexpenses\n      description: Query expenses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optscale.getexpenses\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      inputParameters:\n      - name: start_date\n        type: integer\n        description: start_date\n      - name: end_date\n        type: integer\n        description: end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listoptimizations\n      description: List optimization recommendations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optscale.listoptimizations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPTSCALE_TOKEN: OPTSCALE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/optscale/refs/heads/main/capabilities/optscale-capability.yaml
tags:
- Optscale
- API
tools:
- description: Create an authentication token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtoken
- description: List organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizations
- description: Create an organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorganization
- description: Get an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganization
- description: Delete an organization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteorganization
- description: List cloud accounts for an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcloudaccounts
- description: Create a cloud account connection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcloudaccount
- description: Get cloud account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcloudaccount
- description: Disconnect a cloud account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecloudaccount
- description: List organization employees
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listemployees
- description: List pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpools
- description: Create a pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpool
- description: Get pool
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpool
- description: List cloud resources for a cloud account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcloudresources
- description: Query expenses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexpenses
- description: List optimization recommendations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoptimizations
---
