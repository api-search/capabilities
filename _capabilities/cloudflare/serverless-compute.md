---
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
- list queues
- workers list workers
- queues create queue
- cdn
- pages list projects
- dns
- list worker scripts
- create a worker deployment.
- edge computing
- durable object namespace management.
- queue management.
- send a message to a queue.
- object storage
- queues pull messages
- edge
- pull messages from a queue.
- ddos protection
- list pages deployments
- workers list deployments
- delete a queue.
- queues list queues
- list pages deployments.
- pages list deployments
- list durable object namespaces.
- serverless
- create a message queue.
- workers list secrets
- list worker deployments.
- deployment
- list worker scripts.
- platform
- api gateway
- pages project management.
- list durable object namespaces
- worker deployment management.
- upload a worker script.
- workers list routes
- artificial intelligence
- pages deployment management.
- list all workers for an account.
- containers
- list deployments
- durable objects list objects
- workers create deployment
- list workers
- list durable objects in a namespace.
- ai gateway
- cloudflare
- pages create project
- queues send message
- cloud
- durable objects list namespaces
- workers delete script
- list all workers.
- pages get project
- list queues.
- worker script management.
- real-time communication
- create a pages project.
- list pages projects.
- rollback a pages deployment.
- security
- delete a worker script.
- workers upload script
- list worker routes.
- get pages project details.
- pages rollback deployment
- workers list scripts
- list worker secrets.
- web performance
- list pages projects
- list message queues.
- queues delete queue
slug: serverless-compute
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
