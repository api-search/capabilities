---
api_specs:
- filename: terapi-openapi.yml
  format: yaml
  label: terapi
  slug: terapi
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/terapi/refs/heads/main/openapi/terapi-openapi.yml
categories: []
consumed_apis:
- terapi
description: Workflow capability for building native product integrations using Terapi. Combines connection management, integration configuration, data synchronization, action triggering, and authentication to support the full embedded iPaaS lifecycle for SaaS platform engineers building native third-party integrations for their customers.
layout: capability
name: Terapi Embedded Integrations
operations:
- description: List all active connections across all integrations
  method: GET
  name: list-connections
  path: /v1/connections
- description: Create a new integration connection for an end-user
  method: POST
  name: create-connection
  path: /v1/connections
- description: Get details of a connection
  method: GET
  name: get-connection
  path: /v1/connections/{connection_id}
- description: Delete a connection and revoke credentials
  method: DELETE
  name: delete-connection
  path: /v1/connections/{connection_id}
- description: List all configured integration providers
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: Create a new integration provider configuration
  method: POST
  name: create-integration
  path: /v1/integrations
- description: Get details of an integration
  method: GET
  name: get-integration
  path: /v1/integrations/{provider_config_key}
- description: Delete an integration configuration
  method: DELETE
  name: delete-integration
  path: /v1/integrations/{provider_config_key}
- description: Trigger a data sync for a connection
  method: POST
  name: trigger-sync
  path: /v1/sync/trigger
- description: Get status of a specific sync
  method: GET
  name: get-sync-status
  path: /v1/sync/{connection_id}/{sync_name}
- description: Trigger an action on a connected service
  method: POST
  name: trigger-action
  path: /v1/actions/trigger
- description: Get the current authentication token for a connection
  method: GET
  name: get-auth-token
  path: /v1/auth/token/{provider_config_key}/{connection_id}
personas: []
provider_name: Terapi
provider_slug: terapi
search_terms:
- create integration
- trigger action
- saas
- manage a specific integration connection
- list connections
- trigger actions on third-party services
- workflow automation
- integration
- list all configured integration providers
- get integration
- create a new integration provider configuration
- sync status and history
- get status of a specific sync
- open source
- get details and authentication status of a specific integration connection
- native integrations
- get the current authentication token for a connection, with automatic oauth refresh
- terapi
- get details of a connection
- manage a specific integration
- trigger a data sync for a connection
- delete an integration configuration
- get sync status
- delete a connection and revoke credentials
- get the current status and history of a data synchronization
- delete integration
- trigger a write action on a connected third-party service (create record, send message, update resource)
- get the current authentication token for a connection
- connectors
- get auth token
- list all configured integration providers available in this terapi environment
- get details and connection count for a specific integration provider
- delete an integration configuration and all associated connections
- create a new integration provider configuration with oauth credentials
- create connection
- embedded ipaas
- delete an integration connection and revoke associated credentials
- delete connection
- get connection
- list integrations
- list all active integration connections between end-users and third-party services
- list all active connections across all integrations
- authentication token management
- get details of an integration
- create a new integration connection for an end-user with oauth or api key credentials
- authentication
- trigger a data synchronization run to fetch updated data from a third-party service
- trigger an action on a connected service
- integration provider configurations
- end-user integration connections
- create a new integration connection for an end-user
- trigger sync
- trigger data synchronization
slug: embedded-integrations
source_filename: embedded-integrations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Terapi Embedded Integrations\"\n  description: >-\n    Workflow capability for building native product integrations using Terapi.\n    Combines connection management, integration configuration, data\n    synchronization, action triggering, and authentication to support the full\n    embedded iPaaS lifecycle for SaaS platform engineers building native\n    third-party integrations for their customers.\n  tags:\n    - Terapi\n    - Embedded iPaaS\n    - Integration\n    - Open Source\n    - SaaS\n    - Connectors\n    - Workflow Automation\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TERAPI_SECRET_KEY: TERAPI_SECRET_KEY\n\ncapability:\n  consumes:\n    - import: terapi\n      location: ./shared/terapi.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: terapi-integrations-api\n      description: \"Unified REST API for managing embedded third-party integrations.\"\
  \n      resources:\n        - path: /v1/connections\n          name: connections\n          description: \"End-user integration connections\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List all active connections across all integrations\"\n              call: \"terapi.list-connections\"\n              with:\n                provider_config_key: \"rest.provider_config_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-connection\n              description: \"Create a new integration connection for an end-user\"\n              call: \"terapi.create-connection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connections/{connection_id}\n          name: connection\n          description: \"Manage a specific integration connection\"\n\
  \          operations:\n            - method: GET\n              name: get-connection\n              description: \"Get details of a connection\"\n              call: \"terapi.get-connection\"\n              with:\n                connection_id: \"rest.connection_id\"\n                provider_config_key: \"rest.provider_config_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-connection\n              description: \"Delete a connection and revoke credentials\"\n              call: \"terapi.delete-connection\"\n              with:\n                connection_id: \"rest.connection_id\"\n                provider_config_key: \"rest.provider_config_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/integrations\n          name: integrations\n          description: \"Integration provider configurations\"\
  \n          operations:\n            - method: GET\n              name: list-integrations\n              description: \"List all configured integration providers\"\n              call: \"terapi.list-integrations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-integration\n              description: \"Create a new integration provider configuration\"\n              call: \"terapi.create-integration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/integrations/{provider_config_key}\n          name: integration\n          description: \"Manage a specific integration\"\n          operations:\n            - method: GET\n              name: get-integration\n              description: \"Get details of an integration\"\n              call: \"terapi.get-integration\"\n              with:\n                provider_config_key:\
  \ \"rest.provider_config_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-integration\n              description: \"Delete an integration configuration\"\n              call: \"terapi.delete-integration\"\n              with:\n                provider_config_key: \"rest.provider_config_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sync/trigger\n          name: sync-trigger\n          description: \"Trigger data synchronization\"\n          operations:\n            - method: POST\n              name: trigger-sync\n              description: \"Trigger a data sync for a connection\"\n              call: \"terapi.trigger-sync\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sync/{connection_id}/{sync_name}\n          name: sync-status\n\
  \          description: \"Sync status and history\"\n          operations:\n            - method: GET\n              name: get-sync-status\n              description: \"Get status of a specific sync\"\n              call: \"terapi.get-sync-status\"\n              with:\n                connection_id: \"rest.connection_id\"\n                sync_name: \"rest.sync_name\"\n                provider_config_key: \"rest.provider_config_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/actions/trigger\n          name: action-trigger\n          description: \"Trigger actions on third-party services\"\n          operations:\n            - method: POST\n              name: trigger-action\n              description: \"Trigger an action on a connected service\"\n              call: \"terapi.trigger-action\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/auth/token/{provider_config_key}/{connection_id}\n          name: auth-token\n          description: \"Authentication token management\"\n          operations:\n            - method: GET\n              name: get-auth-token\n              description: \"Get the current authentication token for a connection\"\n              call: \"terapi.get-auth-token\"\n              with:\n                provider_config_key: \"rest.provider_config_key\"\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: terapi-integrations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted embedded integration management.\"\n      tools:\n        - name: list-connections\n          description: \"List all active integration connections between end-users and third-party services\"\n          hints:\n            readOnly: true\n  \
  \          openWorld: false\n          call: \"terapi.list-connections\"\n          with:\n            provider_config_key: \"tools.provider_config_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-connection\n          description: \"Create a new integration connection for an end-user with OAuth or API key credentials\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"terapi.create-connection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-connection\n          description: \"Get details and authentication status of a specific integration connection\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terapi.get-connection\"\n          with:\n            connection_id: \"tools.connection_id\"\n            provider_config_key: \"tools.provider_config_key\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-connection\n          description: \"Delete an integration connection and revoke associated credentials\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"terapi.delete-connection\"\n          with:\n            connection_id: \"tools.connection_id\"\n            provider_config_key: \"tools.provider_config_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-integrations\n          description: \"List all configured integration providers available in this Terapi environment\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terapi.list-integrations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-integration\n          description:\
  \ \"Create a new integration provider configuration with OAuth credentials\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"terapi.create-integration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-integration\n          description: \"Get details and connection count for a specific integration provider\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terapi.get-integration\"\n          with:\n            provider_config_key: \"tools.provider_config_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-integration\n          description: \"Delete an integration configuration and all associated connections\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"\
  terapi.delete-integration\"\n          with:\n            provider_config_key: \"tools.provider_config_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: trigger-sync\n          description: \"Trigger a data synchronization run to fetch updated data from a third-party service\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"terapi.trigger-sync\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-sync-status\n          description: \"Get the current status and history of a data synchronization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terapi.get-sync-status\"\n          with:\n            connection_id: \"tools.connection_id\"\n            sync_name: \"tools.sync_name\"\n            provider_config_key: \"tools.provider_config_key\"\n \
  \         outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: trigger-action\n          description: \"Trigger a write action on a connected third-party service (create record, send message, update resource)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"terapi.trigger-action\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-auth-token\n          description: \"Get the current authentication token for a connection, with automatic OAuth refresh\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terapi.get-auth-token\"\n          with:\n            provider_config_key: \"tools.provider_config_key\"\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/terapi/refs/heads/main/capabilities/embedded-integrations.yaml
tags:
- Terapi
- Embedded iPaaS
- Integration
- Open Source
- SaaS
- Connectors
- Workflow Automation
tools:
- description: List all active integration connections between end-users and third-party services
  hints:
    openWorld: false
    readOnly: true
  name: list-connections
- description: Create a new integration connection for an end-user with OAuth or API key credentials
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-connection
- description: Get details and authentication status of a specific integration connection
  hints:
    openWorld: false
    readOnly: true
  name: get-connection
- description: Delete an integration connection and revoke associated credentials
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-connection
- description: List all configured integration providers available in this Terapi environment
  hints:
    openWorld: false
    readOnly: true
  name: list-integrations
- description: Create a new integration provider configuration with OAuth credentials
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-integration
- description: Get details and connection count for a specific integration provider
  hints:
    openWorld: false
    readOnly: true
  name: get-integration
- description: Delete an integration configuration and all associated connections
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-integration
- description: Trigger a data synchronization run to fetch updated data from a third-party service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trigger-sync
- description: Get the current status and history of a data synchronization
  hints:
    openWorld: false
    readOnly: true
  name: get-sync-status
- description: Trigger a write action on a connected third-party service (create record, send message, update resource)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trigger-action
- description: Get the current authentication token for a connection, with automatic OAuth refresh
  hints:
    openWorld: false
    readOnly: true
  name: get-auth-token
---
