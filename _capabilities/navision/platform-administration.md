---
categories:
- automation
consumed_apis: []
description: Unified workflow for administering Dynamics 365 Business Central combining the Administration Center API for environment management with the Automation API for company setup, extensions, users, and permissions. Used by platform administrators and IT teams.
layout: capability
name: Dynamics NAV Platform Administration
operations:
- description: List all environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Get environment details
  method: GET
  name: get-environment
  path: /v1/environments/{environmentName}
- description: Create a new environment
  method: PUT
  name: create-environment
  path: /v1/environments/{environmentName}
- description: Delete an environment
  method: DELETE
  name: delete-environment
  path: /v1/environments/{environmentName}
- description: List automation companies
  method: GET
  name: list-companies
  path: /v1/companies
- description: List extensions
  method: GET
  name: list-extensions
  path: /v1/extensions
- description: List users
  method: GET
  name: list-users
  path: /v1/users
- description: List permission sets
  method: GET
  name: list-permission-sets
  path: /v1/permission-sets
- description: Get allowed quotas
  method: GET
  name: get-quotas
  path: /v1/quotas
personas: []
provider_name: Microsoft Dynamics NAV
provider_slug: navision
search_terms:
- create a new environment
- get environment storage
- list permission sets
- automation
- restore an environment from a point in time
- get environment storage usage
- get allowed quotas and limits
- company management
- update user
- get scheduled upgrade information
- dynamics 365
- dynamics nav
- business central
- permission sets
- business management
- storage quotas
- extension management
- uninstall extension
- list automation companies
- inventory
- create automation company
- get environment details
- delete an environment
- uninstall an extension
- restore environment
- list installed apps
- list rapidstart configuration packages
- microsoft
- create a new company
- list environments
- get allowed quotas
- finance
- single environment
- list features
- administration
- list users
- list security groups
- get a user by id
- copy environment
- navision
- install extension
- list scheduled jobs
- get scheduled upgrade
- user management
- get environment
- list all business central environments
- copy an environment
- delete a company
- list business central users
- get user
- erp
- update user properties
- delete automation company
- list published extensions
- list configuration packages
- list extensions
- delete environment
- get quotas
- list installed apps in an environment
- environment management
- create environment
- list companies
- get environment settings
- install an extension
- list scheduled background jobs
- list all environments
slug: platform-administration
source_filename: platform-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Dynamics NAV Platform Administration\n  description: Unified workflow for administering Dynamics 365 Business Central combining the Administration Center API for\n    environment management with the Automation API for company setup, extensions, users, and permissions. Used by platform\n    administrators and IT teams.\n  tags:\n  - Business Central\n  - Dynamics 365\n  - Administration\n  - Automation\n  - Environment Management\n  - User Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BC_ADMIN_OAUTH_TOKEN: BC_ADMIN_OAUTH_TOKEN\n    BC_OAUTH_TOKEN: BC_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: admin-center\n    baseUri: https://api.businesscentral.dynamics.com/admin/v2.28\n    description: Business Central Administration Center API for environment and tenant management.\n    authentication:\n      type: bearer\n      token: '{{BC_ADMIN_OAUTH_TOKEN}}'\n   \
  \ resources:\n    - name: environments\n      path: /applications\n      description: Environment lifecycle management.\n      operations:\n      - name: list-all-environments\n        method: GET\n        description: Returns all environments across all application families.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-environments\n        method: GET\n        description: Returns environments for a specified application family.\n        inputParameters:\n        - name: applicationFamily\n          in: path\n          type: string\n          required: true\n          description: Application family (e.g., BusinessCentral)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-environment\n        method: GET\n        description: Returns properties for a specified environment.\n        inputParameters:\n\
  \        - name: applicationFamily\n          in: path\n          type: string\n          required: true\n          description: Application family\n        - name: environmentName\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-environment\n        method: PUT\n        description: Creates a new environment.\n        inputParameters:\n        - name: applicationFamily\n          in: path\n          type: string\n          required: true\n          description: Application family\n        - name: environmentName\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        body:\n          type: json\n          data:\n            environmentType: '{{tools.environmentType}}'\n            countryCode: '{{tools.countryCode}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-environment\n        method: DELETE\n        description: Soft deletes an environment.\n        inputParameters:\n        - name: applicationFamily\n          in: path\n          type: string\n          required: true\n          description: Application family\n        - name: environmentName\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: copy-environment\n        method: POST\n        description: Creates a copy of an environment.\n        inputParameters:\n        - name: applicationFamily\n          in: path\n          type: string\n          required: true\n          description: Application family\n        - name: environmentName\n\
  \          in: path\n          type: string\n          required: true\n          description: Source environment name\n        body:\n          type: json\n          data:\n            environmentName: '{{tools.targetName}}'\n            type: '{{tools.type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restore-environment\n        method: POST\n        description: Restores an environment from a point in time.\n        inputParameters:\n        - name: applicationFamily\n          in: path\n          type: string\n          required: true\n          description: Application family\n        - name: environmentName\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        body:\n          type: json\n          data:\n            EnvironmentName: '{{tools.targetName}}'\n            PointInTime: '{{tools.pointInTime}}'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-installed-apps\n        method: GET\n        description: Returns apps installed in an environment.\n        inputParameters:\n        - name: applicationFamily\n          in: path\n          type: string\n          required: true\n          description: Application family\n        - name: environmentName\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-environment-settings\n        method: GET\n        description: Returns settings for an environment.\n        inputParameters:\n        - name: applicationFamily\n          in: path\n          type: string\n          required: true\n          description: Application family\n        - name: environmentName\n   \
  \       in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-environment-storage\n        method: GET\n        description: Returns storage usage for an environment.\n        inputParameters:\n        - name: applicationFamily\n          in: path\n          type: string\n          required: true\n          description: Application family\n        - name: environmentName\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-scheduled-upgrade\n        method: GET\n        description: Returns scheduled upgrade information.\n        inputParameters:\n        - name: applicationFamily\n          in: path\n\
  \          type: string\n          required: true\n          description: Application family\n        - name: environmentName\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-quotas\n        method: GET\n        description: Returns allowed quotas and limits.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: automation\n    baseUri: https://api.businesscentral.dynamics.com/v2.0/{environment}/api/microsoft/automation/v2.0\n    description: Business Central Automation API for tenant setup and management.\n    authentication:\n      type: bearer\n      token: '{{BC_OAUTH_TOKEN}}'\n    resources:\n    - name: companies\n      path: /companies\n      description: Company management.\n\
  \      operations:\n      - name: list-companies\n        method: GET\n        description: List companies available for automation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-automation-companies\n        method: GET\n        description: List automation company objects.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-automation-company\n        method: POST\n        description: Create a new company.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        body:\n          type: json\n          data:\n            name:\
  \ '{{tools.name}}'\n            displayName: '{{tools.displayName}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-automation-company\n        method: DELETE\n        description: Delete a company.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: automationCompany_id\n          in: path\n          type: string\n          required: true\n          description: Automation company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extensions\n      path: /companies({company_id})/extensions\n      description: Extension management.\n      operations:\n      - name: list-extensions\n        method: GET\n        description: List extensions published to the tenant.\n        inputParameters:\n\
  \        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: install-extension\n        method: POST\n        description: Install a published extension.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: extension_id\n          in: path\n          type: string\n          required: true\n          description: Extension package ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uninstall-extension\n        method: POST\n        description: Uninstall an extension.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n\
  \          required: true\n          description: Company ID\n        - name: extension_id\n          in: path\n          type: string\n          required: true\n          description: Extension package ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /companies({company_id})/users\n      description: User management.\n      operations:\n      - name: list-users\n        method: GET\n        description: List Business Central users.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user\n        method: GET\n        description: Get a user by ID.\n        inputParameters:\n        - name: company_id\n          in: path\n   \
  \       type: string\n          required: true\n          description: Company ID\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User security ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PATCH\n        description: Update user properties.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User security ID\n        body:\n          type: json\n          data:\n            state: '{{tools.state}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permission-sets\n      path: /companies({company_id})/permissionSets\n\
  \      description: Permission set management.\n      operations:\n      - name: list-permission-sets\n        method: GET\n        description: List available permission sets.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: features\n      path: /companies({company_id})/features\n      description: Feature management.\n      operations:\n      - name: list-features\n        method: GET\n        description: List features in feature management.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration-packages\n\
  \      path: /companies({company_id})/configurationPackages\n      description: RapidStart configuration packages.\n      operations:\n      - name: list-configuration-packages\n        method: GET\n        description: List RapidStart configuration packages.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-groups\n      path: /companies({company_id})/securityGroups\n      description: Security group management.\n      operations:\n      - name: list-security-groups\n        method: GET\n        description: List security groups.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: scheduled-jobs\n      path: /companies({company_id})/scheduledJobs\n      description: Scheduled background jobs.\n      operations:\n      - name: list-scheduled-jobs\n        method: GET\n        description: List scheduled background jobs.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: platform-admin-api\n    description: Unified REST API for Business Central platform administration.\n    resources:\n    - path: /v1/environments\n      name: environments\n      description: Environment management\n      operations:\n      - method: GET\n        name: list-environments\n        description: List all environments\n\
  \        call: admin-center.list-all-environments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environments/{environmentName}\n      name: environment\n      description: Single environment\n      operations:\n      - method: GET\n        name: get-environment\n        description: Get environment details\n        call: admin-center.get-environment\n        with:\n          applicationFamily: rest.applicationFamily\n          environmentName: rest.environmentName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: create-environment\n        description: Create a new environment\n        call: admin-center.create-environment\n        with:\n          applicationFamily: rest.applicationFamily\n          environmentName: rest.environmentName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-environment\n        description:\
  \ Delete an environment\n        call: admin-center.delete-environment\n        with:\n          applicationFamily: rest.applicationFamily\n          environmentName: rest.environmentName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/companies\n      name: companies\n      description: Company management\n      operations:\n      - method: GET\n        name: list-companies\n        description: List automation companies\n        call: automation.list-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extensions\n      name: extensions\n      description: Extension management\n      operations:\n      - method: GET\n        name: list-extensions\n        description: List extensions\n        call: automation.list-extensions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User management\n      operations:\n\
  \      - method: GET\n        name: list-users\n        description: List users\n        call: automation.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/permission-sets\n      name: permission-sets\n      description: Permission sets\n      operations:\n      - method: GET\n        name: list-permission-sets\n        description: List permission sets\n        call: automation.list-permission-sets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quotas\n      name: quotas\n      description: Storage quotas\n      operations:\n      - method: GET\n        name: get-quotas\n        description: Get allowed quotas\n        call: admin-center.get-quotas\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: platform-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted Business Central platform administration.\n\
  \    tools:\n    - name: list-all-environments\n      description: List all Business Central environments\n      hints:\n        readOnly: true\n        idempotent: true\n      call: admin-center.list-all-environments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-environment\n      description: Get environment details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: admin-center.get-environment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-environment\n      description: Create a new environment\n      hints:\n        readOnly: false\n      call: admin-center.create-environment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-environment\n      description: Delete an environment\n      hints:\n        readOnly: false\n        destructive: true\n      call: admin-center.delete-environment\n      outputParameters:\n      - type: object\n    \
  \    mapping: $.\n    - name: copy-environment\n      description: Copy an environment\n      hints:\n        readOnly: false\n      call: admin-center.copy-environment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restore-environment\n      description: Restore an environment from a point in time\n      hints:\n        readOnly: false\n      call: admin-center.restore-environment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-installed-apps\n      description: List installed apps in an environment\n      hints:\n        readOnly: true\n        idempotent: true\n      call: admin-center.list-installed-apps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-environment-settings\n      description: Get environment settings\n      hints:\n        readOnly: true\n        idempotent: true\n      call: admin-center.get-environment-settings\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-environment-storage\n      description: Get environment storage usage\n      hints:\n        readOnly: true\n        idempotent: true\n      call: admin-center.get-environment-storage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-scheduled-upgrade\n      description: Get scheduled upgrade information\n      hints:\n        readOnly: true\n        idempotent: true\n      call: admin-center.get-scheduled-upgrade\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-quotas\n      description: Get allowed quotas and limits\n      hints:\n        readOnly: true\n        idempotent: true\n      call: admin-center.get-quotas\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-companies\n      description: List automation companies\n      hints:\n        readOnly: true\n        idempotent: true\n      call: automation.list-companies\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-automation-company\n      description: Create a new company\n      hints:\n        readOnly: false\n      call: automation.create-automation-company\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-automation-company\n      description: Delete a company\n      hints:\n        readOnly: false\n        destructive: true\n      call: automation.delete-automation-company\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-extensions\n      description: List published extensions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: automation.list-extensions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: install-extension\n      description: Install an extension\n      hints:\n        readOnly: false\n      call: automation.install-extension\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: uninstall-extension\n      description: Uninstall an extension\n      hints:\n        readOnly: false\n        destructive: true\n      call: automation.uninstall-extension\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List Business Central users\n      hints:\n        readOnly: true\n        idempotent: true\n      call: automation.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get a user by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: automation.get-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n      description: Update user properties\n      hints:\n        readOnly: false\n        idempotent: true\n      call: automation.update-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-permission-sets\n     \
  \ description: List permission sets\n      hints:\n        readOnly: true\n        idempotent: true\n      call: automation.list-permission-sets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-features\n      description: List features\n      hints:\n        readOnly: true\n        idempotent: true\n      call: automation.list-features\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-security-groups\n      description: List security groups\n      hints:\n        readOnly: true\n        idempotent: true\n      call: automation.list-security-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-configuration-packages\n      description: List RapidStart configuration packages\n      hints:\n        readOnly: true\n        idempotent: true\n      call: automation.list-configuration-packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-scheduled-jobs\n\
  \      description: List scheduled background jobs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: automation.list-scheduled-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/navision/refs/heads/main/capabilities/platform-administration.yaml
tags:
- Business Central
- Dynamics 365
- Administration
- Automation
- Environment Management
- User Management
tools:
- description: List all Business Central environments
  hints:
    idempotent: true
    readOnly: true
  name: list-all-environments
- description: Get environment details
  hints:
    idempotent: true
    readOnly: true
  name: get-environment
- description: Create a new environment
  hints:
    readOnly: false
  name: create-environment
- description: Delete an environment
  hints:
    destructive: true
    readOnly: false
  name: delete-environment
- description: Copy an environment
  hints:
    readOnly: false
  name: copy-environment
- description: Restore an environment from a point in time
  hints:
    readOnly: false
  name: restore-environment
- description: List installed apps in an environment
  hints:
    idempotent: true
    readOnly: true
  name: list-installed-apps
- description: Get environment settings
  hints:
    idempotent: true
    readOnly: true
  name: get-environment-settings
- description: Get environment storage usage
  hints:
    idempotent: true
    readOnly: true
  name: get-environment-storage
- description: Get scheduled upgrade information
  hints:
    idempotent: true
    readOnly: true
  name: get-scheduled-upgrade
- description: Get allowed quotas and limits
  hints:
    idempotent: true
    readOnly: true
  name: get-quotas
- description: List automation companies
  hints:
    idempotent: true
    readOnly: true
  name: list-companies
- description: Create a new company
  hints:
    readOnly: false
  name: create-automation-company
- description: Delete a company
  hints:
    destructive: true
    readOnly: false
  name: delete-automation-company
- description: List published extensions
  hints:
    idempotent: true
    readOnly: true
  name: list-extensions
- description: Install an extension
  hints:
    readOnly: false
  name: install-extension
- description: Uninstall an extension
  hints:
    destructive: true
    readOnly: false
  name: uninstall-extension
- description: List Business Central users
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Get a user by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-user
- description: Update user properties
  hints:
    idempotent: true
    readOnly: false
  name: update-user
- description: List permission sets
  hints:
    idempotent: true
    readOnly: true
  name: list-permission-sets
- description: List features
  hints:
    idempotent: true
    readOnly: true
  name: list-features
- description: List security groups
  hints:
    idempotent: true
    readOnly: true
  name: list-security-groups
- description: List RapidStart configuration packages
  hints:
    idempotent: true
    readOnly: true
  name: list-configuration-packages
- description: List scheduled background jobs
  hints:
    idempotent: true
    readOnly: true
  name: list-scheduled-jobs
---
