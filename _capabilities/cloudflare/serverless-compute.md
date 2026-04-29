---
categories:
- serverless
consumed_apis:
- cloudflare-workers
- cloudflare-pages
- cloudflare-durable-objects
- cloudflare-queues
description: Deploy and manage serverless applications on Cloudflare's edge network combining Workers scripts, Pages deployments, Durable Objects for state, and Queues for async messaging. Used by developers and platform engineers building edge-first applications.
layout: capability
name: Cloudflare Serverless Compute
operations:
- description: List all Workers.
  method: GET
  name: list-workers
  path: /v1/workers
- description: List Worker scripts.
  method: GET
  name: list-worker-scripts
  path: /v1/scripts
- description: List Worker deployments.
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: List Pages projects.
  method: GET
  name: list-pages-projects
  path: /v1/pages-projects
- description: List Pages deployments.
  method: GET
  name: list-pages-deployments
  path: /v1/pages-deployments
- description: List Durable Object namespaces.
  method: GET
  name: list-durable-object-namespaces
  path: /v1/durable-object-namespaces
- description: List queues.
  method: GET
  name: list-queues
  path: /v1/queues
personas: []
provider_name: Cloudflare
provider_slug: cloudflare
search_terms:
- worker deployment management.
- ddos protection
- list durable object namespaces
- queues pull messages
- durable object namespace management.
- list durable objects in a namespace.
- list worker secrets.
- list worker deployments.
- cdn
- list worker routes.
- get pages project details.
- list worker scripts.
- list pages deployments
- workers create deployment
- ai gateway
- cloud
- web performance
- pages list deployments
- list durable object namespaces.
- list message queues.
- worker script management.
- pull messages from a queue.
- list pages deployments.
- delete a queue.
- delete a worker script.
- queue management.
- create a pages project.
- create a message queue.
- serverless
- deployment
- real-time communication
- edge computing
- containers
- object storage
- send a message to a queue.
- list pages projects.
- queues create queue
- platform
- queues send message
- queues delete queue
- workers list deployments
- pages get project
- workers list routes
- list queues
- list deployments
- pages rollback deployment
- security
- list pages projects
- workers list scripts
- cloudflare
- workers upload script
- workers list workers
- workers delete script
- durable objects list namespaces
- upload a worker script.
- api gateway
- list workers
- queues list queues
- artificial intelligence
- pages deployment management.
- pages create project
- pages list projects
- durable objects list objects
- list queues.
- list worker scripts
- create a worker deployment.
- list all workers for an account.
- rollback a pages deployment.
- pages project management.
- workers list secrets
- list all workers.
- dns
- edge
slug: serverless-compute
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Cloudflare Serverless Compute\"\n  description: \"Deploy and manage serverless applications on Cloudflare's edge network combining Workers scripts, Pages deployments, Durable Objects for state, and Queues for async messaging. Used by developers and platform engineers building edge-first applications.\"\n  tags:\n    - Cloudflare\n    - Serverless\n    - Edge Computing\n    - Deployment\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: cloudflare-workers\n      location: ./shared/workers.yaml\n    - import: cloudflare-pages\n      location: ./shared/pages.yaml\n    - import: cloudflare-durable-objects\n      location: ./shared/durable-objects.yaml\n    - import: cloudflare-queues\n      location: ./shared/queues.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: serverless-compute-api\n\
  \      description: \"Unified REST API for Cloudflare serverless compute management.\"\n      resources:\n        - path: /v1/workers\n          name: workers\n          description: \"Worker script management.\"\n          operations:\n            - method: GET\n              name: list-workers\n              description: \"List all Workers.\"\n              call: \"cloudflare-workers.list-workers\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/scripts\n          name: scripts\n          description: \"Worker script management.\"\n          operations:\n            - method: GET\n              name: list-worker-scripts\n              description: \"List Worker scripts.\"\n              call: \"cloudflare-workers.list-worker-scripts\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n        - path: /v1/deployments\n          name: deployments\n          description: \"Worker deployment management.\"\n          operations:\n            - method: GET\n              name: list-deployments\n              description: \"List Worker deployments.\"\n              call: \"cloudflare-workers.list-deployments\"\n              with:\n                account_id: \"rest.account_id\"\n                script_name: \"rest.script_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages-projects\n          name: pages-projects\n          description: \"Pages project management.\"\n          operations:\n            - method: GET\n              name: list-pages-projects\n              description: \"List Pages projects.\"\n              call: \"cloudflare-pages.list-pages-projects\"\n              with:\n                account_id: \"rest.account_id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages-deployments\n          name: pages-deployments\n          description: \"Pages deployment management.\"\n          operations:\n            - method: GET\n              name: list-pages-deployments\n              description: \"List Pages deployments.\"\n              call: \"cloudflare-pages.list-pages-deployments\"\n              with:\n                account_id: \"rest.account_id\"\n                project_name: \"rest.project_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/durable-object-namespaces\n          name: durable-object-namespaces\n          description: \"Durable Object namespace management.\"\n          operations:\n            - method: GET\n              name: list-durable-object-namespaces\n              description: \"List Durable Object namespaces.\"\n       \
  \       call: \"cloudflare-durable-objects.list-durable-object-namespaces\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queues\n          name: queues\n          description: \"Queue management.\"\n          operations:\n            - method: GET\n              name: list-queues\n              description: \"List queues.\"\n              call: \"cloudflare-queues.list-queues\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: serverless-compute-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Cloudflare serverless compute management.\"\n      tools:\n        - name: workers-list-workers\n          description: \"List all Workers for an account.\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-workers.list-workers\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: workers-list-scripts\n          description: \"List Worker scripts.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-workers.list-worker-scripts\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: workers-upload-script\n          description: \"Upload a Worker script.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloudflare-workers.upload-worker-script\"\n          with:\n            account_id: \"tools.account_id\"\n            script_name: \"tools.script_name\"\n          outputParameters:\n     \
  \       - type: object\n              mapping: \"$.\"\n        - name: workers-delete-script\n          description: \"Delete a Worker script.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-workers.delete-worker-script\"\n          with:\n            account_id: \"tools.account_id\"\n            script_name: \"tools.script_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: workers-list-deployments\n          description: \"List Worker deployments.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-workers.list-deployments\"\n          with:\n            account_id: \"tools.account_id\"\n            script_name: \"tools.script_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: workers-create-deployment\n          description: \"Create a Worker deployment.\"\n          hints:\n\
  \            readOnly: false\n          call: \"cloudflare-workers.create-deployment\"\n          with:\n            account_id: \"tools.account_id\"\n            script_name: \"tools.script_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: workers-list-routes\n          description: \"List Worker routes.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-workers.list-routes\"\n          with:\n            zone_id: \"tools.zone_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: workers-list-secrets\n          description: \"List Worker secrets.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-workers.list-secrets\"\n          with:\n            account_id: \"tools.account_id\"\n            script_name: \"tools.script_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: pages-list-projects\n          description: \"List Pages projects.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-pages.list-pages-projects\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pages-create-project\n          description: \"Create a Pages project.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-pages.create-pages-project\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pages-get-project\n          description: \"Get Pages project details.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-pages.get-pages-project\"\n          with:\n            account_id: \"tools.account_id\"\n            project_name: \"\
  tools.project_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pages-list-deployments\n          description: \"List Pages deployments.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-pages.list-pages-deployments\"\n          with:\n            account_id: \"tools.account_id\"\n            project_name: \"tools.project_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pages-rollback-deployment\n          description: \"Rollback a Pages deployment.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-pages.rollback-pages-deployment\"\n          with:\n            account_id: \"tools.account_id\"\n            project_name: \"tools.project_name\"\n            deployment_id: \"tools.deployment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: durable-objects-list-namespaces\n\
  \          description: \"List Durable Object namespaces.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-durable-objects.list-durable-object-namespaces\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: durable-objects-list-objects\n          description: \"List Durable Objects in a namespace.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-durable-objects.list-durable-objects\"\n          with:\n            account_id: \"tools.account_id\"\n            namespace_id: \"tools.namespace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: queues-list-queues\n          description: \"List message queues.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-queues.list-queues\"\
  \n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: queues-create-queue\n          description: \"Create a message queue.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-queues.create-queue\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: queues-send-message\n          description: \"Send a message to a queue.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-queues.send-message\"\n          with:\n            account_id: \"tools.account_id\"\n            queue_id: \"tools.queue_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: queues-pull-messages\n          description: \"Pull messages from a queue.\"\n          hints:\n           \
  \ readOnly: true\n          call: \"cloudflare-queues.pull-messages\"\n          with:\n            account_id: \"tools.account_id\"\n            queue_id: \"tools.queue_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: queues-delete-queue\n          description: \"Delete a queue.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-queues.delete-queue\"\n          with:\n            account_id: \"tools.account_id\"\n            queue_id: \"tools.queue_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudflare/refs/heads/main/capabilities/serverless-compute.yaml
tags:
- Cloudflare
- Serverless
- Edge Computing
- Deployment
tools:
- description: List all Workers for an account.
  hints:
    openWorld: true
    readOnly: true
  name: workers-list-workers
- description: List Worker scripts.
  hints:
    readOnly: true
  name: workers-list-scripts
- description: Upload a Worker script.
  hints:
    idempotent: true
    readOnly: false
  name: workers-upload-script
- description: Delete a Worker script.
  hints:
    destructive: true
    idempotent: true
  name: workers-delete-script
- description: List Worker deployments.
  hints:
    readOnly: true
  name: workers-list-deployments
- description: Create a Worker deployment.
  hints:
    readOnly: false
  name: workers-create-deployment
- description: List Worker routes.
  hints:
    readOnly: true
  name: workers-list-routes
- description: List Worker secrets.
  hints:
    readOnly: true
  name: workers-list-secrets
- description: List Pages projects.
  hints:
    openWorld: true
    readOnly: true
  name: pages-list-projects
- description: Create a Pages project.
  hints:
    readOnly: false
  name: pages-create-project
- description: Get Pages project details.
  hints:
    readOnly: true
  name: pages-get-project
- description: List Pages deployments.
  hints:
    readOnly: true
  name: pages-list-deployments
- description: Rollback a Pages deployment.
  hints:
    readOnly: false
  name: pages-rollback-deployment
- description: List Durable Object namespaces.
  hints:
    openWorld: true
    readOnly: true
  name: durable-objects-list-namespaces
- description: List Durable Objects in a namespace.
  hints:
    readOnly: true
  name: durable-objects-list-objects
- description: List message queues.
  hints:
    openWorld: true
    readOnly: true
  name: queues-list-queues
- description: Create a message queue.
  hints:
    readOnly: false
  name: queues-create-queue
- description: Send a message to a queue.
  hints:
    readOnly: false
  name: queues-send-message
- description: Pull messages from a queue.
  hints:
    readOnly: true
  name: queues-pull-messages
- description: Delete a queue.
  hints:
    destructive: true
    idempotent: true
  name: queues-delete-queue
---
