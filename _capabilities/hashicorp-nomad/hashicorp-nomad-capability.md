---
categories: []
consumed_apis: []
description: The Nomad HTTP API provides full programmatic access to a Nomad cluster. All routes use the /v1/ prefix. Endpoints support managing jobs, nodes, allocations, deployments, and evaluations across on-premises and cloud environments. Authentication uses an ACL token via the X-Nomad-Token header or Bearer authorization.
layout: capability
name: HashiCorp Nomad HTTP API
operations:
- description: List jobs
  method: GET
  name: get-jobs
  path: /jobs
- description: Create or register job
  method: POST
  name: post-jobs
  path: /jobs
- description: Parse HCL jobspec
  method: POST
  name: post-jobs-parse
  path: /jobs/parse
- description: Read job
  method: GET
  name: get-job-job-id
  path: /job/{job_id}
- description: Update job
  method: POST
  name: post-job-job-id
  path: /job/{job_id}
- description: Deregister job
  method: DELETE
  name: delete-job-job-id
  path: /job/{job_id}
- description: List job versions
  method: GET
  name: get-job-job-id-versions
  path: /job/{job_id}/versions
- description: Read job summary
  method: GET
  name: get-job-job-id-summary
  path: /job/{job_id}/summary
- description: Force evaluation
  method: POST
  name: post-job-job-id-evaluate
  path: /job/{job_id}/evaluate
- description: Plan job
  method: POST
  name: post-job-job-id-plan
  path: /job/{job_id}/plan
- description: List job allocations
  method: GET
  name: get-job-job-id-allocations
  path: /job/{job_id}/allocations
- description: List job deployments
  method: GET
  name: get-job-job-id-deployments
  path: /job/{job_id}/deployments
- description: Read most recent deployment
  method: GET
  name: get-job-job-id-deployment
  path: /job/{job_id}/deployment
- description: Read scale status
  method: GET
  name: get-job-job-id-scale
  path: /job/{job_id}/scale
- description: Scale task group
  method: POST
  name: post-job-job-id-scale
  path: /job/{job_id}/scale
- description: List task actions
  method: GET
  name: get-job-job-id-actions
  path: /job/{job_id}/actions
- description: List nodes
  method: GET
  name: get-nodes
  path: /nodes
- description: Read node
  method: GET
  name: get-node-node-id
  path: /node/{node_id}
- description: List node allocations
  method: GET
  name: get-node-node-id-allocations
  path: /node/{node_id}/allocations
- description: Create node evaluation
  method: POST
  name: post-node-node-id-evaluate
  path: /node/{node_id}/evaluate
- description: Toggle node drain
  method: POST
  name: post-node-node-id-drain
  path: /node/{node_id}/drain
- description: Purge node
  method: POST
  name: post-node-node-id-purge
  path: /node/{node_id}/purge
- description: Toggle node eligibility
  method: POST
  name: post-node-node-id-eligibility
  path: /node/{node_id}/eligibility
- description: List allocations
  method: GET
  name: get-allocations
  path: /allocations
- description: Read allocation
  method: GET
  name: get-allocation-alloc-id
  path: /allocation/{alloc_id}
- description: List deployments
  method: GET
  name: get-deployments
  path: /deployments
- description: Read deployment
  method: GET
  name: get-deployment-deployment-id
  path: /deployment/{deployment_id}
- description: List evaluations
  method: GET
  name: get-evaluations
  path: /evaluations
- description: Read evaluation
  method: GET
  name: get-evaluation-eval-id
  path: /evaluation/{eval_id}
- description: List namespaces
  method: GET
  name: get-namespaces
  path: /namespaces
- description: Read namespace
  method: GET
  name: get-namespace-name
  path: /namespace/{name}
- description: Create or update namespace
  method: POST
  name: post-namespace-name
  path: /namespace/{name}
- description: Delete namespace
  method: DELETE
  name: delete-namespace-name
  path: /namespace/{name}
- description: List ACL tokens
  method: GET
  name: get-acl-tokens
  path: /acl/tokens
- description: List ACL policies
  method: GET
  name: get-acl-policies
  path: /acl/policies
- description: Read leader address
  method: GET
  name: get-status-leader
  path: /status/leader
- description: List server peers
  method: GET
  name: get-status-peers
  path: /status/peers
- description: Agent health
  method: GET
  name: get-agent-health
  path: /agent/health
personas: []
provider_name: HashiCorp Nomad
provider_slug: hashicorp-nomad
search_terms:
- get job job id
- list task actions
- delete namespace name
- post job job id evaluate
- create node evaluation
- list node allocations
- get node node id
- read namespace
- list namespaces
- api
- post jobs
- get namespaces
- scale task group
- read node
- list evaluations
- delete namespace
- list allocations
- get status peers
- read scale status
- toggle node drain
- get evaluation eval id
- get evaluations
- post node node id evaluate
- read allocation
- read evaluation
- post node node id eligibility
- get job job id summary
- get job job id actions
- post job job id plan
- get acl policies
- list server peers
- read job summary
- get job job id scale
- get jobs
- post namespace name
- nomad
- force evaluation
- parse hcl jobspec
- get nodes
- purge node
- get deployments
- list job allocations
- post job job id scale
- get job job id allocations
- agent health
- update job
- list acl tokens
- plan job
- get namespace name
- read leader address
- list deployments
- hashicorp
- toggle node eligibility
- create or register job
- multi-cloud
- list acl policies
- post node node id purge
- get job job id deployment
- post jobs parse
- list job deployments
- get job job id versions
- create or update namespace
- post node node id drain
- get acl tokens
- list job versions
- get job job id deployments
- get allocation alloc id
- read deployment
- list jobs
- get allocations
- read job
- scheduling
- get node node id allocations
- list nodes
- containers
- get agent health
- get deployment deployment id
- orchestration
- delete job job id
- workloads
- deregister job
- read most recent deployment
- get status leader
- post job job id
slug: hashicorp-nomad-capability
source_filename: hashicorp-nomad-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HashiCorp Nomad HTTP API\n  description: The Nomad HTTP API provides full programmatic access to a Nomad cluster. All routes use the /v1/ prefix. Endpoints\n    support managing jobs, nodes, allocations, deployments, and evaluations across on-premises and cloud environments. Authentication\n    uses an ACL token via the X-Nomad-Token header or Bearer authorization.\n  tags:\n  - Hashicorp\n  - Nomad\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hashicorp-nomad\n    baseUri: http://127.0.0.1:4646/v1\n    description: HashiCorp Nomad HTTP API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Nomad-Token\n      value: '{{HASHICORP_NOMAD_TOKEN}}'\n    resources:\n    - name: jobs\n      path: /jobs\n      operations:\n      - name: get-jobs\n        method: GET\n        description: List jobs\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: post-jobs\n        method: POST\n        description: Create or register job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-parse\n      path: /jobs/parse\n      operations:\n      - name: post-jobs-parse\n        method: POST\n        description: Parse HCL jobspec\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-job-id\n      path: /job/{job_id}\n      operations:\n      - name: get-job-job-id\n        method: GET\n        description: Read job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-job-job-id\n        method: POST\n        description: Update job\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-job-job-id\n        method: DELETE\n        description: Deregister job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-job-id-versions\n      path: /job/{job_id}/versions\n      operations:\n      - name: get-job-job-id-versions\n        method: GET\n        description: List job versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-job-id-summary\n      path: /job/{job_id}/summary\n      operations:\n      - name: get-job-job-id-summary\n        method: GET\n        description: Read job summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-job-id-evaluate\n      path: /job/{job_id}/evaluate\n      operations:\n\
  \      - name: post-job-job-id-evaluate\n        method: POST\n        description: Force evaluation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-job-id-plan\n      path: /job/{job_id}/plan\n      operations:\n      - name: post-job-job-id-plan\n        method: POST\n        description: Plan job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-job-id-allocations\n      path: /job/{job_id}/allocations\n      operations:\n      - name: get-job-job-id-allocations\n        method: GET\n        description: List job allocations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-job-id-deployments\n      path: /job/{job_id}/deployments\n      operations:\n      - name: get-job-job-id-deployments\n        method:\
  \ GET\n        description: List job deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-job-id-deployment\n      path: /job/{job_id}/deployment\n      operations:\n      - name: get-job-job-id-deployment\n        method: GET\n        description: Read most recent deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-job-id-scale\n      path: /job/{job_id}/scale\n      operations:\n      - name: get-job-job-id-scale\n        method: GET\n        description: Read scale status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-job-job-id-scale\n        method: POST\n        description: Scale task group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: job-job-id-actions\n      path: /job/{job_id}/actions\n      operations:\n      - name: get-job-job-id-actions\n        method: GET\n        description: List task actions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /nodes\n      operations:\n      - name: get-nodes\n        method: GET\n        description: List nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-node-id\n      path: /node/{node_id}\n      operations:\n      - name: get-node-node-id\n        method: GET\n        description: Read node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-node-id-allocations\n      path: /node/{node_id}/allocations\n      operations:\n\
  \      - name: get-node-node-id-allocations\n        method: GET\n        description: List node allocations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-node-id-evaluate\n      path: /node/{node_id}/evaluate\n      operations:\n      - name: post-node-node-id-evaluate\n        method: POST\n        description: Create node evaluation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-node-id-drain\n      path: /node/{node_id}/drain\n      operations:\n      - name: post-node-node-id-drain\n        method: POST\n        description: Toggle node drain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-node-id-purge\n      path: /node/{node_id}/purge\n      operations:\n      - name: post-node-node-id-purge\n\
  \        method: POST\n        description: Purge node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-node-id-eligibility\n      path: /node/{node_id}/eligibility\n      operations:\n      - name: post-node-node-id-eligibility\n        method: POST\n        description: Toggle node eligibility\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocations\n      path: /allocations\n      operations:\n      - name: get-allocations\n        method: GET\n        description: List allocations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocation-alloc-id\n      path: /allocation/{alloc_id}\n      operations:\n      - name: get-allocation-alloc-id\n        method: GET\n        description: Read allocation\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /deployments\n      operations:\n      - name: get-deployments\n        method: GET\n        description: List deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-deployment-id\n      path: /deployment/{deployment_id}\n      operations:\n      - name: get-deployment-deployment-id\n        method: GET\n        description: Read deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evaluations\n      path: /evaluations\n      operations:\n      - name: get-evaluations\n        method: GET\n        description: List evaluations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: evaluation-eval-id\n      path: /evaluation/{eval_id}\n      operations:\n      - name: get-evaluation-eval-id\n        method: GET\n        description: Read evaluation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces\n      path: /namespaces\n      operations:\n      - name: get-namespaces\n        method: GET\n        description: List namespaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespace-name\n      path: /namespace/{name}\n      operations:\n      - name: get-namespace-name\n        method: GET\n        description: Read namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-namespace-name\n        method: POST\n        description: Create or\
  \ update namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-namespace-name\n        method: DELETE\n        description: Delete namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acl-tokens\n      path: /acl/tokens\n      operations:\n      - name: get-acl-tokens\n        method: GET\n        description: List ACL tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acl-policies\n      path: /acl/policies\n      operations:\n      - name: get-acl-policies\n        method: GET\n        description: List ACL policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status-leader\n      path: /status/leader\n\
  \      operations:\n      - name: get-status-leader\n        method: GET\n        description: Read leader address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status-peers\n      path: /status/peers\n      operations:\n      - name: get-status-peers\n        method: GET\n        description: List server peers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-health\n      path: /agent/health\n      operations:\n      - name: get-agent-health\n        method: GET\n        description: Agent health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hashicorp-nomad-rest\n    description: REST adapter for HashiCorp Nomad HTTP API.\n    resources:\n    - path: /jobs\n\
  \      name: get-jobs\n      operations:\n      - method: GET\n        name: get-jobs\n        description: List jobs\n        call: hashicorp-nomad.get-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs\n      name: post-jobs\n      operations:\n      - method: POST\n        name: post-jobs\n        description: Create or register job\n        call: hashicorp-nomad.post-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/parse\n      name: post-jobs-parse\n      operations:\n      - method: POST\n        name: post-jobs-parse\n        description: Parse HCL jobspec\n        call: hashicorp-nomad.post-jobs-parse\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}\n      name: get-job-job-id\n      operations:\n      - method: GET\n        name: get-job-job-id\n        description: Read job\n        call: hashicorp-nomad.get-job-job-id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /job/{job_id}\n      name: post-job-job-id\n      operations:\n      - method: POST\n        name: post-job-job-id\n        description: Update job\n        call: hashicorp-nomad.post-job-job-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}\n      name: delete-job-job-id\n      operations:\n      - method: DELETE\n        name: delete-job-job-id\n        description: Deregister job\n        call: hashicorp-nomad.delete-job-job-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/versions\n      name: get-job-job-id-versions\n      operations:\n      - method: GET\n        name: get-job-job-id-versions\n        description: List job versions\n        call: hashicorp-nomad.get-job-job-id-versions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/summary\n      name: get-job-job-id-summary\n\
  \      operations:\n      - method: GET\n        name: get-job-job-id-summary\n        description: Read job summary\n        call: hashicorp-nomad.get-job-job-id-summary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/evaluate\n      name: post-job-job-id-evaluate\n      operations:\n      - method: POST\n        name: post-job-job-id-evaluate\n        description: Force evaluation\n        call: hashicorp-nomad.post-job-job-id-evaluate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/plan\n      name: post-job-job-id-plan\n      operations:\n      - method: POST\n        name: post-job-job-id-plan\n        description: Plan job\n        call: hashicorp-nomad.post-job-job-id-plan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/allocations\n      name: get-job-job-id-allocations\n      operations:\n      - method: GET\n        name:\
  \ get-job-job-id-allocations\n        description: List job allocations\n        call: hashicorp-nomad.get-job-job-id-allocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/deployments\n      name: get-job-job-id-deployments\n      operations:\n      - method: GET\n        name: get-job-job-id-deployments\n        description: List job deployments\n        call: hashicorp-nomad.get-job-job-id-deployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/deployment\n      name: get-job-job-id-deployment\n      operations:\n      - method: GET\n        name: get-job-job-id-deployment\n        description: Read most recent deployment\n        call: hashicorp-nomad.get-job-job-id-deployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/scale\n      name: get-job-job-id-scale\n      operations:\n      - method: GET\n        name:\
  \ get-job-job-id-scale\n        description: Read scale status\n        call: hashicorp-nomad.get-job-job-id-scale\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/scale\n      name: post-job-job-id-scale\n      operations:\n      - method: POST\n        name: post-job-job-id-scale\n        description: Scale task group\n        call: hashicorp-nomad.post-job-job-id-scale\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{job_id}/actions\n      name: get-job-job-id-actions\n      operations:\n      - method: GET\n        name: get-job-job-id-actions\n        description: List task actions\n        call: hashicorp-nomad.get-job-job-id-actions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes\n      name: get-nodes\n      operations:\n      - method: GET\n        name: get-nodes\n        description: List nodes\n        call: hashicorp-nomad.get-nodes\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{node_id}\n      name: get-node-node-id\n      operations:\n      - method: GET\n        name: get-node-node-id\n        description: Read node\n        call: hashicorp-nomad.get-node-node-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{node_id}/allocations\n      name: get-node-node-id-allocations\n      operations:\n      - method: GET\n        name: get-node-node-id-allocations\n        description: List node allocations\n        call: hashicorp-nomad.get-node-node-id-allocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{node_id}/evaluate\n      name: post-node-node-id-evaluate\n      operations:\n      - method: POST\n        name: post-node-node-id-evaluate\n        description: Create node evaluation\n        call: hashicorp-nomad.post-node-node-id-evaluate\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /node/{node_id}/drain\n      name: post-node-node-id-drain\n      operations:\n      - method: POST\n        name: post-node-node-id-drain\n        description: Toggle node drain\n        call: hashicorp-nomad.post-node-node-id-drain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{node_id}/purge\n      name: post-node-node-id-purge\n      operations:\n      - method: POST\n        name: post-node-node-id-purge\n        description: Purge node\n        call: hashicorp-nomad.post-node-node-id-purge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{node_id}/eligibility\n      name: post-node-node-id-eligibility\n      operations:\n      - method: POST\n        name: post-node-node-id-eligibility\n        description: Toggle node eligibility\n        call: hashicorp-nomad.post-node-node-id-eligibility\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /allocations\n      name: get-allocations\n      operations:\n      - method: GET\n        name: get-allocations\n        description: List allocations\n        call: hashicorp-nomad.get-allocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /allocation/{alloc_id}\n      name: get-allocation-alloc-id\n      operations:\n      - method: GET\n        name: get-allocation-alloc-id\n        description: Read allocation\n        call: hashicorp-nomad.get-allocation-alloc-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments\n      name: get-deployments\n      operations:\n      - method: GET\n        name: get-deployments\n        description: List deployments\n        call: hashicorp-nomad.get-deployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployment/{deployment_id}\n      name: get-deployment-deployment-id\n\
  \      operations:\n      - method: GET\n        name: get-deployment-deployment-id\n        description: Read deployment\n        call: hashicorp-nomad.get-deployment-deployment-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /evaluations\n      name: get-evaluations\n      operations:\n      - method: GET\n        name: get-evaluations\n        description: List evaluations\n        call: hashicorp-nomad.get-evaluations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /evaluation/{eval_id}\n      name: get-evaluation-eval-id\n      operations:\n      - method: GET\n        name: get-evaluation-eval-id\n        description: Read evaluation\n        call: hashicorp-nomad.get-evaluation-eval-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces\n      name: get-namespaces\n      operations:\n      - method: GET\n        name: get-namespaces\n        description:\
  \ List namespaces\n        call: hashicorp-nomad.get-namespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespace/{name}\n      name: get-namespace-name\n      operations:\n      - method: GET\n        name: get-namespace-name\n        description: Read namespace\n        call: hashicorp-nomad.get-namespace-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespace/{name}\n      name: post-namespace-name\n      operations:\n      - method: POST\n        name: post-namespace-name\n        description: Create or update namespace\n        call: hashicorp-nomad.post-namespace-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespace/{name}\n      name: delete-namespace-name\n      operations:\n      - method: DELETE\n        name: delete-namespace-name\n        description: Delete namespace\n        call: hashicorp-nomad.delete-namespace-name\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /acl/tokens\n      name: get-acl-tokens\n      operations:\n      - method: GET\n        name: get-acl-tokens\n        description: List ACL tokens\n        call: hashicorp-nomad.get-acl-tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /acl/policies\n      name: get-acl-policies\n      operations:\n      - method: GET\n        name: get-acl-policies\n        description: List ACL policies\n        call: hashicorp-nomad.get-acl-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /status/leader\n      name: get-status-leader\n      operations:\n      - method: GET\n        name: get-status-leader\n        description: Read leader address\n        call: hashicorp-nomad.get-status-leader\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /status/peers\n      name: get-status-peers\n      operations:\n      -\
  \ method: GET\n        name: get-status-peers\n        description: List server peers\n        call: hashicorp-nomad.get-status-peers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agent/health\n      name: get-agent-health\n      operations:\n      - method: GET\n        name: get-agent-health\n        description: Agent health\n        call: hashicorp-nomad.get-agent-health\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hashicorp-nomad-mcp\n    transport: http\n    description: MCP adapter for HashiCorp Nomad HTTP API for AI agent use.\n    tools:\n    - name: get-jobs\n      description: List jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-jobs\n      description: Create or register job\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hashicorp-nomad.post-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-jobs-parse\n      description: Parse HCL jobspec\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hashicorp-nomad.post-jobs-parse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-job-id\n      description: Read job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-job-job-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-job-job-id\n      description: Update job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hashicorp-nomad.post-job-job-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ delete-job-job-id\n      description: Deregister job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hashicorp-nomad.delete-job-job-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-job-id-versions\n      description: List job versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-job-job-id-versions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-job-id-summary\n      description: Read job summary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-job-job-id-summary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-job-job-id-evaluate\n      description: Force evaluation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: hashicorp-nomad.post-job-job-id-evaluate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-job-job-id-plan\n      description: Plan job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hashicorp-nomad.post-job-job-id-plan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-job-id-allocations\n      description: List job allocations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-job-job-id-allocations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-job-id-deployments\n      description: List job deployments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-job-job-id-deployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-job-job-id-deployment\n      description: Read most recent deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-job-job-id-deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-job-id-scale\n      description: Read scale status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-job-job-id-scale\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-job-job-id-scale\n      description: Scale task group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hashicorp-nomad.post-job-job-id-scale\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-job-id-actions\n      description: List task actions\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: hashicorp-nomad.get-job-job-id-actions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-nodes\n      description: List nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-nodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-node-node-id\n      description: Read node\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-node-node-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-node-node-id-allocations\n      description: List node allocations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-node-node-id-allocations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-node-node-id-evaluate\n\
  \      description: Create node evaluation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hashicorp-nomad.post-node-node-id-evaluate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-node-node-id-drain\n      description: Toggle node drain\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hashicorp-nomad.post-node-node-id-drain\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-node-node-id-purge\n      description: Purge node\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hashicorp-nomad.post-node-node-id-purge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-node-node-id-eligibility\n      description: Toggle node eligibility\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: hashicorp-nomad.post-node-node-id-eligibility\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-allocations\n      description: List allocations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-allocations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-allocation-alloc-id\n      description: Read allocation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-allocation-alloc-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployments\n      description: List deployments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-deployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment-deployment-id\n\
  \      description: Read deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-deployment-deployment-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-evaluations\n      description: List evaluations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-evaluations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-evaluation-eval-id\n      description: Read evaluation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-evaluation-eval-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-namespaces\n      description: List namespaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-namespaces\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-namespace-name\n      description: Read namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-namespace-name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-namespace-name\n      description: Create or update namespace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hashicorp-nomad.post-namespace-name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-namespace-name\n      description: Delete namespace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hashicorp-nomad.delete-namespace-name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-acl-tokens\n      description: List ACL tokens\n      hints:\n   \
  \     readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-acl-tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-acl-policies\n      description: List ACL policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-acl-policies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-status-leader\n      description: Read leader address\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hashicorp-nomad.get-status-leader\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-status-peers\n      description: List server peers\n      hints:\n        readOnly: true\n        de\n\n# --- truncated at 32 KB (32 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/hashicorp-nomad/refs/heads/main/capabilities/hashicorp-nomad-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hashicorp-nomad/refs/heads/main/capabilities/hashicorp-nomad-capability.yaml
tags:
- Hashicorp
- Nomad
- API
tools:
- description: List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-jobs
- description: Create or register job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-jobs
- description: Parse HCL jobspec
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-jobs-parse
- description: Read job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-job-id
- description: Update job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-job-job-id
- description: Deregister job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-job-job-id
- description: List job versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-job-id-versions
- description: Read job summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-job-id-summary
- description: Force evaluation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-job-job-id-evaluate
- description: Plan job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-job-job-id-plan
- description: List job allocations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-job-id-allocations
- description: List job deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-job-id-deployments
- description: Read most recent deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-job-id-deployment
- description: Read scale status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-job-id-scale
- description: Scale task group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-job-job-id-scale
- description: List task actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-job-id-actions
- description: List nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-nodes
- description: Read node
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-node-node-id
- description: List node allocations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-node-node-id-allocations
- description: Create node evaluation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-node-node-id-evaluate
- description: Toggle node drain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-node-node-id-drain
- description: Purge node
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-node-node-id-purge
- description: Toggle node eligibility
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-node-node-id-eligibility
- description: List allocations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-allocations
- description: Read allocation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-allocation-alloc-id
- description: List deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-deployments
- description: Read deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-deployment-deployment-id
- description: List evaluations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-evaluations
- description: Read evaluation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-evaluation-eval-id
- description: List namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-namespaces
- description: Read namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-namespace-name
- description: Create or update namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-namespace-name
- description: Delete namespace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-namespace-name
- description: List ACL tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-acl-tokens
- description: List ACL policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-acl-policies
- description: Read leader address
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-status-leader
- description: List server peers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-status-peers
- description: Agent health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-health
---
