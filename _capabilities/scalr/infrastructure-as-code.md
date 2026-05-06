---
categories: []
consumed_apis: []
description: Unified workflow capability for managing Terraform and OpenTofu infrastructure as code operations through Scalr's remote execution platform. Combines workspace management, environment management, run execution, cloud management, and account-level configuration for platform teams and DevOps engineers managing infrastructure at scale with policy enforcement and cost estimation.
layout: capability
name: Scalr Infrastructure as Code
operations:
- description: List Scalr environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Create a Scalr environment
  method: POST
  name: create-environment
  path: /v1/environments
- description: Get environment details
  method: GET
  name: get-environment
  path: /v1/environments/{id}
- description: List Scalr farms
  method: GET
  name: list-farms
  path: /v1/farms
- description: Create a Scalr farm
  method: POST
  name: create-farm
  path: /v1/farms
- description: Execute a farm lifecycle action (launch, suspend, terminate)
  method: POST
  name: execute-farm-action
  path: /v1/farms/{id}/actions/{action}
- description: List servers in a farm role
  method: GET
  name: list-servers
  path: /v1/servers
- description: List cloud credentials
  method: GET
  name: list-cloud-credentials
  path: /v1/cloud-credentials
- description: List account roles
  method: GET
  name: list-roles
  path: /v1/roles
- description: List global variables
  method: GET
  name: list-global-variables
  path: /v1/global-variables
personas: []
provider_name: Scalr
provider_slug: scalr
search_terms:
- list servers in a farm role
- opa
- execute a farm lifecycle action (launch, suspend, terminate)
- infrastructure as code
- list environments
- create a scalr farm
- get details of a specific scalr environment
- list global variables available across all scalr environments
- execute farm lifecycle actions
- list roles defined globally in scalr
- list roles defined in scalr account
- finops
- devops
- list account roles
- create a new scalr environment
- list cloud provider credentials configured in scalr
- manage a specific environment
- list images available globally across all scalr accounts
- scalr
- list cloud credentials
- environment management (account-level)
- opentofu
- list cloud servers managed by scalr farm role
- create a scalr environment
- kubernetes
- list scalr environments within an account
- list servers
- gitops
- list global images
- role definitions
- cloud management farms (user-level)
- execute a lifecycle action on a scalr farm (launch, suspend, terminate)
- list scalr environments
- execute farm action
- list global roles
- list scalr farms
- cloud provider credentials
- get environment details
- list global variables
- list farms
- create farm
- policy
- list scalr cloud management farms
- cloud servers managed by scalr
- terraform
- create environment
- get environment
- create a new scalr farm
- global variables
- list roles
slug: infrastructure-as-code
source_filename: infrastructure-as-code.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Scalr Infrastructure as Code\n  description: Unified workflow capability for managing Terraform and OpenTofu infrastructure as code operations through Scalr's\n    remote execution platform. Combines workspace management, environment management, run execution, cloud management, and\n    account-level configuration for platform teams and DevOps engineers managing infrastructure at scale with policy enforcement\n    and cost estimation.\n  tags:\n  - DevOps\n  - FinOps\n  - GitOps\n  - Infrastructure as Code\n  - OpenTofu\n  - Policy\n  - Scalr\n  - Terraform\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCALR_TOKEN: SCALR_TOKEN\n    SCALR_API_KEY: SCALR_API_KEY\n    SCALR_ACCOUNT: SCALR_ACCOUNT\ncapability:\n  consumes:\n  - type: http\n    namespace: scalr-user\n    baseUri: https://my.scalr.com/api/v1beta0/user\n    description: Scalr User API for farm and server management\n    authentication:\n\
  \      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALR_API_KEY}}'\n      placement: header\n    resources:\n    - name: farms\n      path: /{envId}/farms\n      description: Farm management\n      operations:\n      - name: list-farms\n        method: GET\n        description: List Farms\n        inputParameters:\n        - name: envId\n          in: path\n          type: string\n          required: true\n          description: Environment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-farm\n        method: POST\n        description: Create Farm\n        inputParameters:\n        - name: envId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n\
  \    - name: farm-actions\n      path: /{envId}/farms/{farmId}/actions/{action}\n      description: Farm lifecycle actions\n      operations:\n      - name: execute-farm-action\n        method: POST\n        description: Execute Farm Action (launch, suspend, terminate)\n        inputParameters:\n        - name: envId\n          in: path\n          type: string\n          required: true\n        - name: farmId\n          in: path\n          type: string\n          required: true\n        - name: action\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: servers\n      path: /{envId}/farm-roles/{farmRoleId}/servers\n      description: Server management\n      operations:\n      - name: list-servers\n        method: GET\n        description: List Servers in Farm Role\n        inputParameters:\n        - name: envId\n          in: path\n\
  \          type: string\n          required: true\n        - name: farmRoleId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: scalr-account\n    baseUri: https://my.scalr.com/api/v1beta0/account\n    description: Scalr Account API for account-level resource management\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALR_API_KEY}}'\n      placement: header\n    resources:\n    - name: environments\n      path: /{accountId}/environments\n      description: Environment management\n      operations:\n      - name: list-environments\n        method: GET\n        description: List Environments\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-environment\n        method: POST\n        description: Create Environment\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: environment\n      path: /{accountId}/environments/{envId}\n      description: Manage a specific environment\n      operations:\n      - name: get-environment\n        method: GET\n        description: Get Environment\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: envId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-environment\n        method: DELETE\n        description: Delete Environment\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: envId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-credentials\n      path: /{accountId}/cloud-credentials\n      description: Cloud credential management\n      operations:\n      - name: list-cloud-credentials\n        method: GET\n        description: List Cloud Credentials\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: roles\n      path: /{accountId}/roles\n      description: Role management\n      operations:\n      - name: list-roles\n        method: GET\n        description: List Roles\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images\n      path: /{accountId}/images\n      description: Image management\n      operations:\n      - name: list-account-images\n        method: GET\n        description: List Images\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: scalr-global\n    baseUri: https://my.scalr.com/api/v1beta0\n\
  \    description: Scalr Global API for installation-wide resources\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALR_API_KEY}}'\n      placement: header\n    resources:\n    - name: global-images\n      path: /images\n      description: Global image management\n      operations:\n      - name: list-global-images\n        method: GET\n        description: List global images available across all accounts\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: global-roles\n      path: /roles\n      description: Global role management\n      operations:\n      - name: list-global-roles\n        method: GET\n        description: List global roles available across all accounts\n        inputParameters:\n        - name: page\n          in: query\n    \
  \      type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: Project management\n      operations:\n      - name: list-global-projects\n        method: GET\n        description: List global projects\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: global-variables\n      path: /global-variables\n      description: Global variable management\n      operations:\n      - name: list-global-variables\n        method: GET\n        description: List global variables\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: scalr-iac-api\n    description: Unified REST API for Scalr IaC platform management.\n    resources:\n    - path: /v1/environments\n      name: environments\n      description: Environment management (account-level)\n      operations:\n      - method: GET\n        name: list-environments\n        description: List Scalr environments\n        call: scalr-account.list-environments\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-environment\n        description: Create a Scalr environment\n        call: scalr-account.create-environment\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environments/{id}\n      name: environment\n      description: Manage a specific environment\n      operations:\n      - method:\
  \ GET\n        name: get-environment\n        description: Get environment details\n        call: scalr-account.get-environment\n        with:\n          accountId: rest.accountId\n          envId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/farms\n      name: farms\n      description: Cloud management farms (user-level)\n      operations:\n      - method: GET\n        name: list-farms\n        description: List Scalr farms\n        call: scalr-user.list-farms\n        with:\n          envId: rest.envId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-farm\n        description: Create a Scalr farm\n        call: scalr-user.create-farm\n        with:\n          envId: rest.envId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/farms/{id}/actions/{action}\n      name: farm-action\n      description: Execute farm lifecycle actions\n\
  \      operations:\n      - method: POST\n        name: execute-farm-action\n        description: Execute a farm lifecycle action (launch, suspend, terminate)\n        call: scalr-user.execute-farm-action\n        with:\n          envId: rest.envId\n          farmId: rest.id\n          action: rest.action\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers\n      name: servers\n      description: Cloud servers managed by Scalr\n      operations:\n      - method: GET\n        name: list-servers\n        description: List servers in a farm role\n        call: scalr-user.list-servers\n        with:\n          envId: rest.envId\n          farmRoleId: rest.farmRoleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cloud-credentials\n      name: cloud-credentials\n      description: Cloud provider credentials\n      operations:\n      - method: GET\n        name: list-cloud-credentials\n        description:\
  \ List cloud credentials\n        call: scalr-account.list-cloud-credentials\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/roles\n      name: roles\n      description: Role definitions\n      operations:\n      - method: GET\n        name: list-roles\n        description: List account roles\n        call: scalr-account.list-roles\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/global-variables\n      name: global-variables\n      description: Global variables\n      operations:\n      - method: GET\n        name: list-global-variables\n        description: List global variables\n        call: scalr-global.list-global-variables\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: scalr-iac-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted Terraform and OpenTofu infrastructure management via Scalr.\n    tools:\n    - name: list-environments\n      description: List Scalr environments within an account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scalr-account.list-environments\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-environment\n      description: Create a new Scalr environment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scalr-account.create-environment\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-environment\n      description: Get details of a specific Scalr environment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scalr-account.get-environment\n      with:\n        accountId: tools.accountId\n\
  \        envId: tools.envId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-farms\n      description: List Scalr cloud management farms\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scalr-user.list-farms\n      with:\n        envId: tools.envId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-farm\n      description: Create a new Scalr farm\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scalr-user.create-farm\n      with:\n        envId: tools.envId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-farm-action\n      description: Execute a lifecycle action on a Scalr farm (launch, suspend, terminate)\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: false\n      call: scalr-user.execute-farm-action\n      with:\n        envId: tools.envId\n      \
  \  farmId: tools.farmId\n        action: tools.action\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-servers\n      description: List cloud servers managed by Scalr farm role\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scalr-user.list-servers\n      with:\n        envId: tools.envId\n        farmRoleId: tools.farmRoleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cloud-credentials\n      description: List cloud provider credentials configured in Scalr\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scalr-account.list-cloud-credentials\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-roles\n      description: List roles defined in Scalr account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scalr-account.list-roles\n      with:\n    \
  \    accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-global-variables\n      description: List global variables available across all Scalr environments\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scalr-global.list-global-variables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-global-images\n      description: List images available globally across all Scalr accounts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scalr-global.list-global-images\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-global-roles\n      description: List roles defined globally in Scalr\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scalr-global.list-global-roles\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scalr/refs/heads/main/capabilities/infrastructure-as-code.yaml
tags:
- DevOps
- FinOps
- GitOps
- Infrastructure as Code
- OpenTofu
- Policy
- Scalr
- Terraform
tools:
- description: List Scalr environments within an account
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: Create a new Scalr environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-environment
- description: Get details of a specific Scalr environment
  hints:
    openWorld: false
    readOnly: true
  name: get-environment
- description: List Scalr cloud management farms
  hints:
    openWorld: true
    readOnly: true
  name: list-farms
- description: Create a new Scalr farm
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-farm
- description: Execute a lifecycle action on a Scalr farm (launch, suspend, terminate)
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: execute-farm-action
- description: List cloud servers managed by Scalr farm role
  hints:
    openWorld: false
    readOnly: true
  name: list-servers
- description: List cloud provider credentials configured in Scalr
  hints:
    openWorld: true
    readOnly: true
  name: list-cloud-credentials
- description: List roles defined in Scalr account
  hints:
    openWorld: true
    readOnly: true
  name: list-roles
- description: List global variables available across all Scalr environments
  hints:
    openWorld: true
    readOnly: true
  name: list-global-variables
- description: List images available globally across all Scalr accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-global-images
- description: List roles defined globally in Scalr
  hints:
    openWorld: true
    readOnly: true
  name: list-global-roles
---
