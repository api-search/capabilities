---
categories:
- serverless
consumed_apis: []
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
- list worker deployments.
- workers list workers
- worker script management.
- workers list deployments
- pages rollback deployment
- queue management.
- dns
- object storage
- list all workers for an account.
- delete a worker script.
- send a message to a queue.
- list durable object namespaces.
- queues pull messages
- list pages projects
- list durable object namespaces
- pages list projects
- delete a queue.
- workers upload script
- list workers
- get pages project details.
- serverless
- list pages projects.
- cloud
- deployment
- upload a worker script.
- list message queues.
- list deployments
- list queues
- containers
- security
- queues send message
- list worker routes.
- pull messages from a queue.
- ddos protection
- workers delete script
- edge computing
- workers list secrets
- cloudflare
- durable objects list objects
- artificial intelligence
- pages create project
- list durable objects in a namespace.
- pages list deployments
- list worker scripts.
- ai gateway
- list pages deployments.
- create a pages project.
- queues create queue
- pages deployment management.
- cdn
- workers list routes
- queues delete queue
- worker deployment management.
- list all workers.
- pages project management.
- durable objects list namespaces
- api gateway
- list pages deployments
- list worker scripts
- pages get project
- web performance
- queues list queues
- durable object namespace management.
- list queues.
- platform
- workers list scripts
- rollback a pages deployment.
- workers create deployment
- real-time communication
- create a message queue.
- create a worker deployment.
- edge
- list worker secrets.
slug: serverless-compute
source_filename: serverless-compute.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cloudflare Serverless Compute\n  description: Deploy and manage serverless applications on Cloudflare's edge network combining Workers scripts, Pages deployments,\n    Durable Objects for state, and Queues for async messaging. Used by developers and platform engineers building edge-first\n    applications.\n  tags:\n  - Cloudflare\n  - Serverless\n  - Edge Computing\n  - Deployment\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cloudflare-workers\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Workers API for managing serverless scripts, deployments, and configuration.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: workers\n      path: /accounts/{account_id}/workers/workers\n      description: Manage\
  \ Worker resources.\n      operations:\n      - name: list-workers\n        method: GET\n        description: List all Workers for an account.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scripts\n      path: /accounts/{account_id}/workers/scripts\n      description: Manage Worker scripts.\n      operations:\n      - name: list-worker-scripts\n        method: GET\n        description: List all Worker scripts for an account.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ upload-worker-script\n        method: PUT\n        description: Upload a Worker script.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: script_name\n          in: path\n          type: string\n          required: true\n          description: Script name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-worker-script\n        method: DELETE\n        description: Delete a Worker script.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: script_name\n          in: path\n          type: string\n          required: true\n          description: Script name.\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /accounts/{account_id}/workers/scripts/{script_name}/deployments\n      description: Manage Worker deployments.\n      operations:\n      - name: list-deployments\n        method: GET\n        description: List deployments for a Worker script.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: script_name\n          in: path\n          type: string\n          required: true\n          description: Script name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Create a deployment for a Worker script.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n         \
  \ required: true\n          description: Account identifier.\n        - name: script_name\n          in: path\n          type: string\n          required: true\n          description: Script name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes\n      path: /zones/{zone_id}/workers/routes\n      description: Manage Worker routes.\n      operations:\n      - name: list-routes\n        method: GET\n        description: List Worker routes for a zone.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-route\n        method: POST\n        description: Create a Worker route.\n        inputParameters:\n        - name: zone_id\n          in:\
  \ path\n          type: string\n          required: true\n          description: Zone identifier.\n        body:\n          type: json\n          data:\n            pattern: '{{tools.pattern}}'\n            script: '{{tools.script}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets\n      path: /accounts/{account_id}/workers/scripts/{script_name}/secrets\n      description: Manage Worker secrets.\n      operations:\n      - name: list-secrets\n        method: GET\n        description: List secrets for a Worker script.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: script_name\n          in: path\n          type: string\n          required: true\n          description: Script name.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-pages\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Pages API for managing projects and deployments.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: projects\n      path: /accounts/{account_id}/pages/projects\n      description: Manage Pages projects.\n      operations:\n      - name: list-pages-projects\n        method: GET\n        description: List all Pages projects.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pages-project\n        method: POST\n        description: Create a new Pages project.\n        inputParameters:\n \
  \       - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            production_branch: '{{tools.production_branch}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project\n      path: /accounts/{account_id}/pages/projects/{project_name}\n      description: Manage a specific Pages project.\n      operations:\n      - name: get-pages-project\n        method: GET\n        description: Get Pages project details.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: project_name\n          in: path\n          type: string\n          required: true\n          description: Project name.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-pages-project\n        method: DELETE\n        description: Delete a Pages project.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: project_name\n          in: path\n          type: string\n          required: true\n          description: Project name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /accounts/{account_id}/pages/projects/{project_name}/deployments\n      description: Manage Pages deployments.\n      operations:\n      - name: list-pages-deployments\n        method: GET\n        description: List deployments for a project.\n        inputParameters:\n        - name: account_id\n          in: path\n \
  \         type: string\n          required: true\n          description: Account identifier.\n        - name: project_name\n          in: path\n          type: string\n          required: true\n          description: Project name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pages-deployment\n        method: POST\n        description: Create a new deployment.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: project_name\n          in: path\n          type: string\n          required: true\n          description: Project name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment\n      path: /accounts/{account_id}/pages/projects/{project_name}/deployments/{deployment_id}\n\
  \      description: Manage a specific deployment.\n      operations:\n      - name: get-pages-deployment\n        method: GET\n        description: Get deployment details.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: project_name\n          in: path\n          type: string\n          required: true\n          description: Project name.\n        - name: deployment_id\n          in: path\n          type: string\n          required: true\n          description: Deployment identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rollback-pages-deployment\n        method: POST\n        description: Rollback to a previous deployment.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n \
  \         description: Account identifier.\n        - name: project_name\n          in: path\n          type: string\n          required: true\n          description: Project name.\n        - name: deployment_id\n          in: path\n          type: string\n          required: true\n          description: Deployment identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-durable-objects\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Durable Objects API for managing stateful serverless objects.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: namespaces\n      path: /accounts/{account_id}/workers/durable_objects/namespaces\n      description: Manage Durable Object namespaces.\n      operations:\n      - name: list-durable-object-namespaces\n        method: GET\n        description:\
  \ List all Durable Object namespaces.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: objects\n      path: /accounts/{account_id}/workers/durable_objects/namespaces/{namespace_id}/objects\n      description: Manage objects within a namespace.\n      operations:\n      - name: list-durable-objects\n        method: GET\n        description: List Durable Objects in a namespace.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: namespace_id\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-queues\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Queues API for managing message queues.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: queues\n      path: /accounts/{account_id}/queues\n      description: Manage queues.\n      operations:\n      - name: list-queues\n        method: GET\n        description: List all queues.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-queue\n        method: POST\n        description: Create a new queue.\n        inputParameters:\n        - name: account_id\n          in: path\n\
  \          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            queue_name: '{{tools.queue_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queue\n      path: /accounts/{account_id}/queues/{queue_id}\n      description: Manage a specific queue.\n      operations:\n      - name: get-queue\n        method: GET\n        description: Get queue details.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: queue_id\n          in: path\n          type: string\n          required: true\n          description: Queue identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-queue\n\
  \        method: DELETE\n        description: Delete a queue.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: queue_id\n          in: path\n          type: string\n          required: true\n          description: Queue identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /accounts/{account_id}/queues/{queue_id}/messages\n      description: Send and receive messages.\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a message to a queue.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: queue_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Queue identifier.\n        body:\n          type: json\n          data:\n            body: '{{tools.body}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pull-messages\n        method: POST\n        description: Pull messages from a queue.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: queue_id\n          in: path\n          type: string\n          required: true\n          description: Queue identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consumers\n      path: /accounts/{account_id}/queues/{queue_id}/consumers\n      description: Manage queue consumers.\n      operations:\n      - name: list-queue-consumers\n        method:\
  \ GET\n        description: List consumers for a queue.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: queue_id\n          in: path\n          type: string\n          required: true\n          description: Queue identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-queue-consumer\n        method: POST\n        description: Create a consumer for a queue.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: queue_id\n          in: path\n          type: string\n          required: true\n          description: Queue identifier.\n        body:\n          type: json\n          data:\n            script_name: '{{tools.script_name}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: serverless-compute-api\n    description: Unified REST API for Cloudflare serverless compute management.\n    resources:\n    - path: /v1/workers\n      name: workers\n      description: Worker script management.\n      operations:\n      - method: GET\n        name: list-workers\n        description: List all Workers.\n        call: cloudflare-workers.list-workers\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scripts\n      name: scripts\n      description: Worker script management.\n      operations:\n      - method: GET\n        name: list-worker-scripts\n        description: List Worker scripts.\n        call: cloudflare-workers.list-worker-scripts\n        with:\n          account_id: rest.account_id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments\n      name: deployments\n      description: Worker deployment management.\n      operations:\n      - method: GET\n        name: list-deployments\n        description: List Worker deployments.\n        call: cloudflare-workers.list-deployments\n        with:\n          account_id: rest.account_id\n          script_name: rest.script_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages-projects\n      name: pages-projects\n      description: Pages project management.\n      operations:\n      - method: GET\n        name: list-pages-projects\n        description: List Pages projects.\n        call: cloudflare-pages.list-pages-projects\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages-deployments\n      name: pages-deployments\n      description:\
  \ Pages deployment management.\n      operations:\n      - method: GET\n        name: list-pages-deployments\n        description: List Pages deployments.\n        call: cloudflare-pages.list-pages-deployments\n        with:\n          account_id: rest.account_id\n          project_name: rest.project_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/durable-object-namespaces\n      name: durable-object-namespaces\n      description: Durable Object namespace management.\n      operations:\n      - method: GET\n        name: list-durable-object-namespaces\n        description: List Durable Object namespaces.\n        call: cloudflare-durable-objects.list-durable-object-namespaces\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queues\n      name: queues\n      description: Queue management.\n      operations:\n      - method: GET\n        name: list-queues\n\
  \        description: List queues.\n        call: cloudflare-queues.list-queues\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: serverless-compute-mcp\n    transport: http\n    description: MCP server for AI-assisted Cloudflare serverless compute management.\n    tools:\n    - name: workers-list-workers\n      description: List all Workers for an account.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-workers.list-workers\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: workers-list-scripts\n      description: List Worker scripts.\n      hints:\n        readOnly: true\n      call: cloudflare-workers.list-worker-scripts\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n  \
  \  - name: workers-upload-script\n      description: Upload a Worker script.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloudflare-workers.upload-worker-script\n      with:\n        account_id: tools.account_id\n        script_name: tools.script_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: workers-delete-script\n      description: Delete a Worker script.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-workers.delete-worker-script\n      with:\n        account_id: tools.account_id\n        script_name: tools.script_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: workers-list-deployments\n      description: List Worker deployments.\n      hints:\n        readOnly: true\n      call: cloudflare-workers.list-deployments\n      with:\n        account_id: tools.account_id\n        script_name: tools.script_name\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: workers-create-deployment\n      description: Create a Worker deployment.\n      hints:\n        readOnly: false\n      call: cloudflare-workers.create-deployment\n      with:\n        account_id: tools.account_id\n        script_name: tools.script_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: workers-list-routes\n      description: List Worker routes.\n      hints:\n        readOnly: true\n      call: cloudflare-workers.list-routes\n      with:\n        zone_id: tools.zone_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: workers-list-secrets\n      description: List Worker secrets.\n      hints:\n        readOnly: true\n      call: cloudflare-workers.list-secrets\n      with:\n        account_id: tools.account_id\n        script_name: tools.script_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pages-list-projects\n  \
  \    description: List Pages projects.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-pages.list-pages-projects\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pages-create-project\n      description: Create a Pages project.\n      hints:\n        readOnly: false\n      call: cloudflare-pages.create-pages-project\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pages-get-project\n      description: Get Pages project details.\n      hints:\n        readOnly: true\n      call: cloudflare-pages.get-pages-project\n      with:\n        account_id: tools.account_id\n        project_name: tools.project_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pages-list-deployments\n      description: List Pages deployments.\n      hints:\n        readOnly: true\n\
  \      call: cloudflare-pages.list-pages-deployments\n      with:\n        account_id: tools.account_id\n        project_name: tools.project_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pages-rollback-deployment\n      description: Rollback a Pages deployment.\n      hints:\n        readOnly: false\n      call: cloudflare-pages.rollback-pages-deployment\n      with:\n        account_id: tools.account_id\n        project_name: tools.project_name\n        deployment_id: tools.deployment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: durable-objects-list-namespaces\n      description: List Durable Object namespaces.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-durable-objects.list-durable-object-namespaces\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: durable-objects-list-objects\n    \
  \  description: List Durable Objects in a namespace.\n      hints:\n        readOnly: true\n      call: cloudflare-durable-objects.list-durable-objects\n      with:\n        account_id: tools.account_id\n        namespace_id: tools.namespace_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queues-list-queues\n      description: List message queues.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-queues.list-queues\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queues-create-queue\n      description: Create a message queue.\n      hints:\n        readOnly: false\n      call: cloudflare-queues.create-queue\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queues-send-message\n      description: Send a message to a queue.\n      hints:\n        readOnly:\
  \ false\n      call: cloudflare-queues.send-message\n      with:\n        account_id: tools.account_id\n        queue_id: tools.queue_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queues-pull-messages\n      description: Pull messages from a queue.\n      hints:\n        readOnly: true\n      call: cloudflare-queues.pull-messages\n      with:\n        account_id: tools.account_id\n        queue_id: tools.queue_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queues-delete-queue\n      description: Delete a queue.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-queues.delete-queue\n      with:\n        account_id: tools.account_id\n        queue_id: tools.queue_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
