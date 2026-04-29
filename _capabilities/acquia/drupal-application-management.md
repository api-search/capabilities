---
api_specs:
- filename: acquia-cloud-applications.yml
  format: yaml
  label: acquia-cloud
  slug: acquia-cloud
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/acquia/refs/heads/main/openapi/acquia-cloud-applications.yml
categories: []
consumed_apis:
- acquia-cloud
description: Unified workflow for managing Drupal applications on Acquia Cloud, including application discovery, environment management, organization administration, and account operations. Used by Drupal developers, DevOps engineers, and platform administrators to automate Acquia Cloud Platform workflows.
layout: capability
name: Acquia Drupal Application Management
operations:
- description: List all accessible Acquia Cloud applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Get application details
  method: GET
  name: get-application
  path: /v1/applications
- description: List environments for an application
  method: GET
  name: list-environments
  path: /v1/environments
- description: Get environment details
  method: GET
  name: get-environment
  path: /v1/environments
- description: List all organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: Get current user account details
  method: GET
  name: get-account
  path: /v1/account
personas: []
provider_name: Acquia
provider_slug: acquia
search_terms:
- drupal application lifecycle management
- organization management
- list environments for an application
- current user account
- Drupal Developer
- applications
- get application
- engineer managing ci/cd pipelines, deployments, and environment configuration
- list applications
- application discovery, environment management, and organization administration
- list all organizations the current acquia user belongs to
- content
- experience
- list all organizations
- get detailed information about a specific acquia cloud application
- list environments
- get environment
- get application details
- acquia
- get the current acquia cloud user account profile and permissions
- DevOps Engineer
- acquia platform admin managing organizations, teams, and subscriptions
- devops
- Platform Administrator
- environments
- list all accessible acquia cloud applications
- get current user account details
- cloud
- list organizations
- developer building and deploying drupal applications on acquia cloud
- get account
- application environment operations
- get environment details
- cloud ide environments and platform notification management
- drupal application hosting lifecycle on acquia cloud platform
- get detailed information about a specific acquia cloud environment
- list all acquia cloud drupal applications the current user can access
- drupal
- user, team, and organizational access control management
- list all environments (dev, staging, prod) for an acquia cloud application
slug: drupal-application-management
source_filename: drupal-application-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Acquia Drupal Application Management\n  description: >-\n    Unified workflow for managing Drupal applications on Acquia Cloud, including application\n    discovery, environment management, organization administration, and account operations.\n    Used by Drupal developers, DevOps engineers, and platform administrators to automate\n    Acquia Cloud Platform workflows.\n  tags:\n    - Acquia\n    - Applications\n    - Cloud\n    - DevOps\n    - Drupal\n    - Environments\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ACQUIA_OAUTH_TOKEN: ACQUIA_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: acquia-cloud\n      location: ./shared/acquia-cloud-applications.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: acquia-management-api\n      description: Unified REST API for Acquia Cloud application and environment management.\n      resources:\n        -\
  \ path: /v1/applications\n          name: applications\n          description: Drupal application lifecycle management\n          operations:\n            - method: GET\n              name: list-applications\n              description: List all accessible Acquia Cloud applications\n              call: \"acquia-cloud.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-application\n              description: Get application details\n              call: \"acquia-cloud.get-application\"\n              with:\n                applicationUuid: \"rest.applicationUuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/environments\n          name: environments\n          description: Application environment operations\n          operations:\n            - method: GET\n              name: list-environments\n\
  \              description: List environments for an application\n              call: \"acquia-cloud.list-environments\"\n              with:\n                applicationUuid: \"rest.applicationUuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-environment\n              description: Get environment details\n              call: \"acquia-cloud.get-environment\"\n              with:\n                environmentId: \"rest.environmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations\n          name: organizations\n          description: Organization management\n          operations:\n            - method: GET\n              name: list-organizations\n              description: List all organizations\n              call: \"acquia-cloud.list-organizations\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n        - path: /v1/account\n          name: account\n          description: Current user account\n          operations:\n            - method: GET\n              name: get-account\n              description: Get current user account details\n              call: \"acquia-cloud.get-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: acquia-management-mcp\n      transport: http\n      description: MCP server for AI-assisted Acquia Cloud Drupal application management.\n      tools:\n        - name: list-applications\n          description: List all Acquia Cloud Drupal applications the current user can access\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acquia-cloud.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: get-application\n          description: Get detailed information about a specific Acquia Cloud application\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"acquia-cloud.get-application\"\n          with:\n            applicationUuid: \"tools.applicationUuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-environments\n          description: List all environments (dev, staging, prod) for an Acquia Cloud application\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acquia-cloud.list-environments\"\n          with:\n            applicationUuid: \"tools.applicationUuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-environment\n          description: Get detailed information about a specific Acquia Cloud environment\n          hints:\n            readOnly: true\n\
  \            idempotent: true\n          call: \"acquia-cloud.get-environment\"\n          with:\n            environmentId: \"tools.environmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-organizations\n          description: List all organizations the current Acquia user belongs to\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"acquia-cloud.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account\n          description: Get the current Acquia Cloud user account profile and permissions\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"acquia-cloud.get-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/acquia/refs/heads/main/capabilities/drupal-application-management.yaml
tags:
- Acquia
- Applications
- Cloud
- DevOps
- Drupal
- Environments
tools:
- description: List all Acquia Cloud Drupal applications the current user can access
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Get detailed information about a specific Acquia Cloud application
  hints:
    idempotent: true
    readOnly: true
  name: get-application
- description: List all environments (dev, staging, prod) for an Acquia Cloud application
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: Get detailed information about a specific Acquia Cloud environment
  hints:
    idempotent: true
    readOnly: true
  name: get-environment
- description: List all organizations the current Acquia user belongs to
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: Get the current Acquia Cloud user account profile and permissions
  hints:
    idempotent: true
    readOnly: true
  name: get-account
---
