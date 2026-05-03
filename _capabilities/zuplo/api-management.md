---
categories: []
consumed_apis:
- zuplo
description: Unified API management workflow combining API key lifecycle management, consumer administration, deployment management, and tunnel configuration. Used by platform engineers and API product teams to programmatically manage their Zuplo infrastructure.
layout: capability
name: Zuplo API Management
operations:
- description: List all API key buckets
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: Create an API key bucket
  method: POST
  name: create-bucket
  path: /v1/buckets
- description: List consumers in a bucket
  method: GET
  name: list-consumers
  path: /v1/consumers
- description: Create a new consumer
  method: POST
  name: create-consumer
  path: /v1/consumers
- description: List API keys for a consumer
  method: GET
  name: list-keys
  path: /v1/keys
- description: Issue a new API key
  method: POST
  name: create-api-key
  path: /v1/keys
- description: Delete an API key
  method: DELETE
  name: delete-api-key
  path: /v1/keys/{keyId}
- description: List all tunnels
  method: GET
  name: list-tunnels
  path: /v1/tunnels
- description: Create a tunnel
  method: POST
  name: create-tunnel
  path: /v1/tunnels
- description: Get tunnel details
  method: GET
  name: get-tunnel
  path: /v1/tunnels/{tunnelId}
- description: Delete a tunnel
  method: DELETE
  name: delete-tunnel
  path: /v1/tunnels/{tunnelId}
- description: List project deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Query audit logs
  method: GET
  name: query-audit-logs
  path: /v1/audit-logs
personas: []
provider_name: Zuplo
provider_slug: zuplo
search_terms:
- create a new consumer
- delete tunnel
- list api keys
- list tunnels
- list all api consumers within a bucket
- get deployment
- create a new api key consumer in a bucket
- manage api consumers
- list keys
- create a tunnel
- delete consumer
- list all deployments for a project
- who am i
- list buckets
- individual api key operations
- get details for a specific api consumer
- manage tunnels to private backends
- list all api key buckets
- delete an api consumer and all their keys
- create tunnel
- create a new api key bucket for grouping consumers
- create consumer
- list all api keys issued to a consumer
- get deployment details and status
- redeploy deployment
- delete a zuplo deployment
- list consumers in a bucket
- identify the current api key caller and account
- api management
- deployments
- manage api key buckets
- list project deployments
- get tunnel details and connection status
- rotate tunnel token
- get tunnel details
- rotate the authentication token for a tunnel connection
- ai gateway
- trigger a re-deployment of an existing deployment
- query account audit logs for compliance and security review
- delete deployment
- list consumers
- gateways
- deployment management
- audit log access for compliance
- list all tunnels
- issue a new api key to a consumer
- create a new tunnel for private backend connectivity
- list all api key buckets in a zuplo account
- create an api key bucket
- create api key
- delete an api key
- individual tunnel operations
- issue a new api key
- revoke and delete an api key
- roll consumer keys
- query audit logs
- list deployments
- delete api key
- platform
- manage api keys for consumers
- get tunnel
- list all tunnels connected to private backends
- get consumer
- rotate all api keys for a consumer to new values
- list api keys for a consumer
- create bucket
- delete a tunnel
- api keys
slug: api-management
source_filename: api-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Zuplo API Management\"\n  description: >-\n    Unified API management workflow combining API key lifecycle management,\n    consumer administration, deployment management, and tunnel configuration.\n    Used by platform engineers and API product teams to programmatically\n    manage their Zuplo infrastructure.\n  tags:\n    - API Management\n    - API Keys\n    - Gateways\n    - Deployments\n    - Platform\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      ZUPLO_API_KEY: ZUPLO_API_KEY\n\ncapability:\n  consumes:\n    - import: zuplo\n      location: ./shared/zuplo-developer-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: zuplo-management-api\n      description: \"Unified REST API for Zuplo API management workflows.\"\n      resources:\n        - path: /v1/buckets\n          name: buckets\n          description: \"Manage API key buckets\"\n        \
  \  operations:\n            - method: GET\n              name: list-buckets\n              description: \"List all API key buckets\"\n              call: \"zuplo.list-buckets\"\n              with:\n                accountName: \"rest.accountName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-bucket\n              description: \"Create an API key bucket\"\n              call: \"zuplo.create-bucket\"\n              with:\n                accountName: \"rest.accountName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/consumers\n          name: consumers\n          description: \"Manage API consumers\"\n          operations:\n            - method: GET\n              name: list-consumers\n              description: \"List consumers in a bucket\"\n              call: \"zuplo.list-consumers\"\n            \
  \  with:\n                accountName: \"rest.accountName\"\n                bucketName: \"rest.bucketName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-consumer\n              description: \"Create a new consumer\"\n              call: \"zuplo.create-consumer\"\n              with:\n                accountName: \"rest.accountName\"\n                bucketName: \"rest.bucketName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/keys\n          name: api-keys\n          description: \"Manage API keys for consumers\"\n          operations:\n            - method: GET\n              name: list-keys\n              description: \"List API keys for a consumer\"\n              call: \"zuplo.list-keys\"\n              with:\n                accountName: \"rest.accountName\"\n                bucketName: \"rest.bucketName\"\
  \n                consumerName: \"rest.consumerName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api-key\n              description: \"Issue a new API key\"\n              call: \"zuplo.create-api-key\"\n              with:\n                accountName: \"rest.accountName\"\n                bucketName: \"rest.bucketName\"\n                consumerName: \"rest.consumerName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/keys/{keyId}\n          name: api-key\n          description: \"Individual API key operations\"\n          operations:\n            - method: DELETE\n              name: delete-api-key\n              description: \"Delete an API key\"\n              call: \"zuplo.delete-api-key\"\n              with:\n                accountName: \"rest.accountName\"\n                bucketName: \"rest.bucketName\"\
  \n                consumerName: \"rest.consumerName\"\n                keyId: \"rest.keyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tunnels\n          name: tunnels\n          description: \"Manage tunnels to private backends\"\n          operations:\n            - method: GET\n              name: list-tunnels\n              description: \"List all tunnels\"\n              call: \"zuplo.list-tunnels\"\n              with:\n                accountName: \"rest.accountName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-tunnel\n              description: \"Create a tunnel\"\n              call: \"zuplo.create-tunnel\"\n              with:\n                accountName: \"rest.accountName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n       \
  \ - path: /v1/tunnels/{tunnelId}\n          name: tunnel\n          description: \"Individual tunnel operations\"\n          operations:\n            - method: GET\n              name: get-tunnel\n              description: \"Get tunnel details\"\n              call: \"zuplo.get-tunnel\"\n              with:\n                accountName: \"rest.accountName\"\n                tunnelId: \"rest.tunnelId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-tunnel\n              description: \"Delete a tunnel\"\n              call: \"zuplo.delete-tunnel\"\n              with:\n                accountName: \"rest.accountName\"\n                tunnelId: \"rest.tunnelId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments\n          name: deployments\n          description: \"Deployment management\"\n   \
  \       operations:\n            - method: GET\n              name: list-deployments\n              description: \"List project deployments\"\n              call: \"zuplo.list-deployments\"\n              with:\n                accountName: \"rest.accountName\"\n                projectName: \"rest.projectName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/audit-logs\n          name: audit-logs\n          description: \"Audit log access for compliance\"\n          operations:\n            - method: GET\n              name: query-audit-logs\n              description: \"Query audit logs\"\n              call: \"zuplo.query-audit-logs\"\n              with:\n                accountName: \"rest.accountName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: zuplo-management-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted Zuplo API management.\"\n      tools:\n        - name: list-buckets\n          description: \"List all API key buckets in a Zuplo account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"zuplo.list-buckets\"\n          with:\n            accountName: \"tools.accountName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bucket\n          description: \"Create a new API key bucket for grouping consumers\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"zuplo.create-bucket\"\n          with:\n            accountName: \"tools.accountName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-consumers\n          description: \"List all API consumers within a bucket\"\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"zuplo.list-consumers\"\n          with:\n            accountName: \"tools.accountName\"\n            bucketName: \"tools.bucketName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-consumer\n          description: \"Create a new API key consumer in a bucket\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"zuplo.create-consumer\"\n          with:\n            accountName: \"tools.accountName\"\n            bucketName: \"tools.bucketName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-consumer\n          description: \"Get details for a specific API consumer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"zuplo.get-consumer\"\n          with:\n            accountName: \"tools.accountName\"\
  \n            bucketName: \"tools.bucketName\"\n            consumerName: \"tools.consumerName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-consumer\n          description: \"Delete an API consumer and all their keys\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"zuplo.delete-consumer\"\n          with:\n            accountName: \"tools.accountName\"\n            bucketName: \"tools.bucketName\"\n            consumerName: \"tools.consumerName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-keys\n          description: \"List all API keys issued to a consumer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"zuplo.list-keys\"\n          with:\n            accountName: \"tools.accountName\"\n            bucketName: \"tools.bucketName\"\
  \n            consumerName: \"tools.consumerName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-api-key\n          description: \"Issue a new API key to a consumer\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"zuplo.create-api-key\"\n          with:\n            accountName: \"tools.accountName\"\n            bucketName: \"tools.bucketName\"\n            consumerName: \"tools.consumerName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-api-key\n          description: \"Revoke and delete an API key\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"zuplo.delete-api-key\"\n          with:\n            accountName: \"tools.accountName\"\n            bucketName: \"tools.bucketName\"\n            consumerName:\
  \ \"tools.consumerName\"\n            keyId: \"tools.keyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: roll-consumer-keys\n          description: \"Rotate all API keys for a consumer to new values\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"zuplo.roll-consumer-keys\"\n          with:\n            accountName: \"tools.accountName\"\n            bucketName: \"tools.bucketName\"\n            consumerName: \"tools.consumerName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tunnels\n          description: \"List all tunnels connected to private backends\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"zuplo.list-tunnels\"\n          with:\n            accountName: \"tools.accountName\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: create-tunnel\n          description: \"Create a new tunnel for private backend connectivity\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"zuplo.create-tunnel\"\n          with:\n            accountName: \"tools.accountName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-tunnel\n          description: \"Get tunnel details and connection status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"zuplo.get-tunnel\"\n          with:\n            accountName: \"tools.accountName\"\n            tunnelId: \"tools.tunnelId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-tunnel\n          description: \"Delete a tunnel\"\n          hints:\n            readOnly: false\n            destructive:\
  \ true\n            idempotent: true\n          call: \"zuplo.delete-tunnel\"\n          with:\n            accountName: \"tools.accountName\"\n            tunnelId: \"tools.tunnelId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: rotate-tunnel-token\n          description: \"Rotate the authentication token for a tunnel connection\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"zuplo.rotate-tunnel-token\"\n          with:\n            accountName: \"tools.accountName\"\n            tunnelId: \"tools.tunnelId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-deployments\n          description: \"List all deployments for a project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"zuplo.list-deployments\"\n          with:\n            accountName:\
  \ \"tools.accountName\"\n            projectName: \"tools.projectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-deployment\n          description: \"Get deployment details and status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"zuplo.get-deployment\"\n          with:\n            deploymentName: \"tools.deploymentName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: redeploy-deployment\n          description: \"Trigger a re-deployment of an existing deployment\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"zuplo.redeploy-deployment\"\n          with:\n            deploymentName: \"tools.deploymentName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-deployment\n  \
  \        description: \"Delete a Zuplo deployment\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"zuplo.delete-deployment\"\n          with:\n            deploymentName: \"tools.deploymentName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-audit-logs\n          description: \"Query account audit logs for compliance and security review\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"zuplo.query-audit-logs\"\n          with:\n            accountName: \"tools.accountName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: who-am-i\n          description: \"Identify the current API key caller and account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"zuplo.who-am-i\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zuplo/refs/heads/main/capabilities/api-management.yaml
tags:
- API Management
- API Keys
- Gateways
- Deployments
- Platform
tools:
- description: List all API key buckets in a Zuplo account
  hints:
    openWorld: false
    readOnly: true
  name: list-buckets
- description: Create a new API key bucket for grouping consumers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-bucket
- description: List all API consumers within a bucket
  hints:
    openWorld: false
    readOnly: true
  name: list-consumers
- description: Create a new API key consumer in a bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-consumer
- description: Get details for a specific API consumer
  hints:
    openWorld: false
    readOnly: true
  name: get-consumer
- description: Delete an API consumer and all their keys
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-consumer
- description: List all API keys issued to a consumer
  hints:
    openWorld: false
    readOnly: true
  name: list-api-keys
- description: Issue a new API key to a consumer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-key
- description: Revoke and delete an API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-key
- description: Rotate all API keys for a consumer to new values
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: roll-consumer-keys
- description: List all tunnels connected to private backends
  hints:
    openWorld: false
    readOnly: true
  name: list-tunnels
- description: Create a new tunnel for private backend connectivity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-tunnel
- description: Get tunnel details and connection status
  hints:
    openWorld: false
    readOnly: true
  name: get-tunnel
- description: Delete a tunnel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-tunnel
- description: Rotate the authentication token for a tunnel connection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rotate-tunnel-token
- description: List all deployments for a project
  hints:
    openWorld: false
    readOnly: true
  name: list-deployments
- description: Get deployment details and status
  hints:
    openWorld: false
    readOnly: true
  name: get-deployment
- description: Trigger a re-deployment of an existing deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: redeploy-deployment
- description: Delete a Zuplo deployment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-deployment
- description: Query account audit logs for compliance and security review
  hints:
    openWorld: false
    readOnly: true
  name: query-audit-logs
- description: Identify the current API key caller and account
  hints:
    openWorld: false
    readOnly: true
  name: who-am-i
---
