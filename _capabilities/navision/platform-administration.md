---
categories:
- automation
consumed_apis:
- admin-center
- automation
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
- copy environment
- finance
- administration
- get user
- get environment storage usage
- get scheduled upgrade
- get quotas
- get a user by id
- install an extension
- automation
- single environment
- list automation companies
- uninstall an extension
- update user
- install extension
- list rapidstart configuration packages
- list scheduled background jobs
- list scheduled jobs
- navision
- uninstall extension
- environment management
- create environment
- list published extensions
- create a new environment
- microsoft
- list environments
- list configuration packages
- get environment
- list all environments
- list extensions
- company management
- list all business central environments
- restore environment
- update user properties
- list users
- business central
- erp
- dynamics 365
- user management
- list security groups
- get scheduled upgrade information
- list features
- inventory
- get allowed quotas
- permission sets
- list installed apps in an environment
- create automation company
- delete automation company
- restore an environment from a point in time
- get environment storage
- copy an environment
- list companies
- delete a company
- storage quotas
- create a new company
- business management
- dynamics nav
- get environment settings
- get environment details
- list business central users
- delete environment
- delete an environment
- list permission sets
- get allowed quotas and limits
- list installed apps
- extension management
slug: platform-administration
source_filename: platform-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Dynamics NAV Platform Administration\"\n  description: \"Unified workflow for administering Dynamics 365 Business Central combining the Administration Center API for environment management with the Automation API for company setup, extensions, users, and permissions. Used by platform administrators and IT teams.\"\n  tags:\n    - Business Central\n    - Dynamics 365\n    - Administration\n    - Automation\n    - Environment Management\n    - User Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      BC_ADMIN_OAUTH_TOKEN: BC_ADMIN_OAUTH_TOKEN\n      BC_OAUTH_TOKEN: BC_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: admin-center\n      location: ./shared/admin-center.yaml\n    - import: automation\n      location: ./shared/automation.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: platform-admin-api\n      description: \"Unified REST API for\
  \ Business Central platform administration.\"\n      resources:\n        - path: /v1/environments\n          name: environments\n          description: \"Environment management\"\n          operations:\n            - method: GET\n              name: list-environments\n              description: \"List all environments\"\n              call: \"admin-center.list-all-environments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/environments/{environmentName}\n          name: environment\n          description: \"Single environment\"\n          operations:\n            - method: GET\n              name: get-environment\n              description: \"Get environment details\"\n              call: \"admin-center.get-environment\"\n              with:\n                applicationFamily: \"rest.applicationFamily\"\n                environmentName: \"rest.environmentName\"\n              outputParameters:\n             \
  \   - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: create-environment\n              description: \"Create a new environment\"\n              call: \"admin-center.create-environment\"\n              with:\n                applicationFamily: \"rest.applicationFamily\"\n                environmentName: \"rest.environmentName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-environment\n              description: \"Delete an environment\"\n              call: \"admin-center.delete-environment\"\n              with:\n                applicationFamily: \"rest.applicationFamily\"\n                environmentName: \"rest.environmentName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/companies\n          name: companies\n          description: \"Company management\"\
  \n          operations:\n            - method: GET\n              name: list-companies\n              description: \"List automation companies\"\n              call: \"automation.list-companies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/extensions\n          name: extensions\n          description: \"Extension management\"\n          operations:\n            - method: GET\n              name: list-extensions\n              description: \"List extensions\"\n              call: \"automation.list-extensions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users\"\n              call: \"automation.list-users\"\n              outputParameters:\n   \
  \             - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/permission-sets\n          name: permission-sets\n          description: \"Permission sets\"\n          operations:\n            - method: GET\n              name: list-permission-sets\n              description: \"List permission sets\"\n              call: \"automation.list-permission-sets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/quotas\n          name: quotas\n          description: \"Storage quotas\"\n          operations:\n            - method: GET\n              name: get-quotas\n              description: \"Get allowed quotas\"\n              call: \"admin-center.get-quotas\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: platform-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ Business Central platform administration.\"\n      tools:\n        - name: list-all-environments\n          description: \"List all Business Central environments\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"admin-center.list-all-environments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-environment\n          description: \"Get environment details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"admin-center.get-environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-environment\n          description: \"Create a new environment\"\n          hints:\n            readOnly: false\n          call: \"admin-center.create-environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-environment\n\
  \          description: \"Delete an environment\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"admin-center.delete-environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: copy-environment\n          description: \"Copy an environment\"\n          hints:\n            readOnly: false\n          call: \"admin-center.copy-environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: restore-environment\n          description: \"Restore an environment from a point in time\"\n          hints:\n            readOnly: false\n          call: \"admin-center.restore-environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-installed-apps\n          description: \"List installed apps in an environment\"\n          hints:\n            readOnly: true\n        \
  \    idempotent: true\n          call: \"admin-center.list-installed-apps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-environment-settings\n          description: \"Get environment settings\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"admin-center.get-environment-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-environment-storage\n          description: \"Get environment storage usage\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"admin-center.get-environment-storage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-scheduled-upgrade\n          description: \"Get scheduled upgrade information\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call:\
  \ \"admin-center.get-scheduled-upgrade\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-quotas\n          description: \"Get allowed quotas and limits\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"admin-center.get-quotas\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-companies\n          description: \"List automation companies\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"automation.list-companies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-automation-company\n          description: \"Create a new company\"\n          hints:\n            readOnly: false\n          call: \"automation.create-automation-company\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: delete-automation-company\n          description: \"Delete a company\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"automation.delete-automation-company\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-extensions\n          description: \"List published extensions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"automation.list-extensions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: install-extension\n          description: \"Install an extension\"\n          hints:\n            readOnly: false\n          call: \"automation.install-extension\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: uninstall-extension\n          description: \"Uninstall an extension\"\n          hints:\n\
  \            readOnly: false\n            destructive: true\n          call: \"automation.uninstall-extension\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List Business Central users\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"automation.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user\n          description: \"Get a user by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"automation.get-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-user\n          description: \"Update user properties\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"automation.update-user\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-permission-sets\n          description: \"List permission sets\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"automation.list-permission-sets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-features\n          description: \"List features\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"automation.list-features\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-security-groups\n          description: \"List security groups\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"automation.list-security-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-configuration-packages\n\
  \          description: \"List RapidStart configuration packages\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"automation.list-configuration-packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-scheduled-jobs\n          description: \"List scheduled background jobs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"automation.list-scheduled-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
