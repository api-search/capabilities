---
categories: []
consumed_apis: []
description: The HashiCorp Nomad HTTP API provides programmatic access to all Nomad functionality including job scheduling, allocation management, node operations, deployments, services, evaluations, namespaces, ACL policies, and cluster status. All API routes are prefixed with /v1/ and the default port is 4646. The API is RESTful, responds to standard HTTP verbs, and supports ACL token authentication via the X-Nomad-Token header or Bearer scheme.
layout: capability
name: HashiCorp Nomad HTTP API
operations:
- description: List jobs
  method: GET
  name: listjobs
  path: /jobs
- description: Register a new job
  method: PUT
  name: registerjob
  path: /jobs
- description: Parse a job specification
  method: PUT
  name: parsejob
  path: /jobs/parse
- description: List job statuses
  method: GET
  name: listjobstatuses
  path: /jobs/statuses
- description: Read a job
  method: GET
  name: readjob
  path: /job/{jobID}
- description: Deregister a job
  method: DELETE
  name: deregisterjob
  path: /job/{jobID}
- description: Create a new evaluation for a job
  method: PUT
  name: evaluatejob
  path: /job/{jobID}/evaluate
- description: Plan a job update
  method: PUT
  name: planjob
  path: /job/{jobID}/plan
- description: List allocations for a job
  method: GET
  name: listjoballocations
  path: /job/{jobID}/allocations
- description: List evaluations for a job
  method: GET
  name: listjobevaluations
  path: /job/{jobID}/evaluations
- description: List deployments for a job
  method: GET
  name: listjobdeployments
  path: /job/{jobID}/deployments
- description: List versions of a job
  method: GET
  name: listjobversions
  path: /job/{jobID}/versions
- description: Revert job to an older version
  method: PUT
  name: revertjob
  path: /job/{jobID}/revert
- description: Set job stability
  method: PUT
  name: setjobstability
  path: /job/{jobID}/stable
- description: Read a job summary
  method: GET
  name: readjobsummary
  path: /job/{jobID}/summary
- description: Dispatch a parameterized job
  method: PUT
  name: dispatchjob
  path: /job/{jobID}/dispatch
- description: List allocations
  method: GET
  name: listallocations
  path: /allocations
- description: Read an allocation
  method: GET
  name: readallocation
  path: /allocation/{allocID}
- description: List allocation services
  method: GET
  name: listallocationservices
  path: /allocation/{allocID}/services
- description: List allocation health checks
  method: GET
  name: listallocationchecks
  path: /allocation/{allocID}/checks
- description: List evaluations
  method: GET
  name: listevaluations
  path: /evaluations
- description: Count evaluations
  method: GET
  name: countevaluations
  path: /evaluations/count
- description: Read an evaluation
  method: GET
  name: readevaluation
  path: /evaluation/{evalID}
- description: List allocations for an evaluation
  method: GET
  name: listevaluationallocations
  path: /evaluation/{evalID}/allocations
- description: List deployments
  method: GET
  name: listdeployments
  path: /deployments
- description: Read a deployment
  method: GET
  name: readdeployment
  path: /deployment/{deploymentID}
- description: List deployment allocations
  method: GET
  name: listdeploymentallocations
  path: /deployment/allocations/{deploymentID}
- description: Fail a deployment
  method: PUT
  name: faildeployment
  path: /deployment/fail/{deploymentID}
- description: Pause or resume a deployment
  method: PUT
  name: pausedeployment
  path: /deployment/pause/{deploymentID}
- description: Promote a deployment
  method: PUT
  name: promotedeployment
  path: /deployment/promote/{deploymentID}
- description: List nodes
  method: GET
  name: listnodes
  path: /nodes
- description: Read a node
  method: GET
  name: readnode
  path: /node/{nodeID}
- description: Create a new evaluation for a node
  method: PUT
  name: evaluatenode
  path: /node/{nodeID}/evaluate
- description: Set node drain mode
  method: POST
  name: drainnode
  path: /node/{nodeID}/drain
- description: Purge a node
  method: DELETE
  name: purgenode
  path: /node/{nodeID}/purge
- description: List node pools
  method: GET
  name: listnodepools
  path: /node/pools
- description: Create or update a node pool
  method: PUT
  name: createnodepool
  path: /node/pools
- description: Read a node pool
  method: GET
  name: readnodepool
  path: /node/pool/{poolName}
- description: Delete a node pool
  method: DELETE
  name: deletenodepool
  path: /node/pool/{poolName}
- description: List services
  method: GET
  name: listservices
  path: /services
- description: Read a service
  method: GET
  name: readservice
  path: /service/{serviceName}
- description: Delete a service registration
  method: DELETE
  name: deleteservice
  path: /service/{serviceName}
- description: List volumes
  method: GET
  name: listvolumes
  path: /volumes
- description: List namespaces
  method: GET
  name: listnamespaces
  path: /namespaces
- description: Create or update a namespace
  method: PUT
  name: createnamespace
  path: /namespace
- description: Read a namespace
  method: GET
  name: readnamespace
  path: /namespace/{namespaceName}
- description: Delete a namespace
  method: DELETE
  name: deletenamespace
  path: /namespace/{namespaceName}
- description: List ACL policies
  method: GET
  name: listaclpolicies
  path: /acl/policies
- description: Read an ACL policy
  method: GET
  name: readaclpolicy
  path: /acl/policy/{policyName}
- description: Create or update an ACL policy
  method: PUT
  name: upsertaclpolicy
  path: /acl/policy/{policyName}
- description: Delete an ACL policy
  method: DELETE
  name: deleteaclpolicy
  path: /acl/policy/{policyName}
- description: List ACL tokens
  method: GET
  name: listacltokens
  path: /acl/tokens
- description: Create an ACL token
  method: PUT
  name: createacltoken
  path: /acl/token
- description: Read own ACL token
  method: GET
  name: readselfacltoken
  path: /acl/token/self
- description: Read an ACL token
  method: GET
  name: readacltoken
  path: /acl/token/{tokenAccessorID}
- description: Delete an ACL token
  method: DELETE
  name: deleteacltoken
  path: /acl/token/{tokenAccessorID}
- description: List agent members
  method: GET
  name: listagentmembers
  path: /agent/members
- description: Read agent self
  method: GET
  name: readagentself
  path: /agent/self
- description: Join an agent
  method: PUT
  name: joinagent
  path: /agent/join
- description: Force leave an agent
  method: PUT
  name: forceleaveagent
  path: /agent/force-leave
personas: []
provider_name: HashiCorp Nomad
provider_slug: nomad
search_terms:
- container orchestration
- readacltoken
- registerjob
- read an allocation
- read a service
- listjobdeployments
- read a job summary
- delete an acl policy
- promote a deployment
- list services
- upsertaclpolicy
- create a new evaluation for a node
- force leave an agent
- readnodepool
- createnamespace
- list allocation services
- listnamespaces
- list allocations for an evaluation
- listallocationservices
- read an evaluation
- faildeployment
- createnodepool
- read a namespace
- create or update an acl policy
- readevaluation
- forceleaveagent
- list evaluations for a job
- count evaluations
- list namespaces
- api
- listjoballocations
- drainnode
- read a deployment
- promotedeployment
- list evaluations
- create or update a namespace
- delete a node pool
- list allocations
- countevaluations
- createacltoken
- pause or resume a deployment
- purge a node
- list volumes
- listnodes
- listvolumes
- readaclpolicy
- infrastructure
- pausedeployment
- create a new evaluation for a job
- list job statuses
- listjobversions
- dispatch a parameterized job
- listallocationchecks
- deleteaclpolicy
- readjob
- listnodepools
- nomad
- register a new job
- listallocations
- readnamespace
- listdeployments
- read own acl token
- dispatchjob
- readservice
- parsejob
- listevaluations
- read an acl token
- revertjob
- list acl tokens
- readallocation
- join an agent
- listjobstatuses
- parse a job specification
- listjobs
- deregister a job
- fail a deployment
- devops
- read agent self
- delete an acl token
- set node drain mode
- list deployment allocations
- revert job to an older version
- list deployments
- deleteservice
- listjobevaluations
- read an acl policy
- workload orchestration
- joinagent
- read a node pool
- list acl policies
- list allocations for a job
- evaluatejob
- listaclpolicies
- list node pools
- create an acl token
- delete a namespace
- set job stability
- planjob
- read a node
- list jobs
- purgenode
- create or update a node pool
- list versions of a job
- deleteacltoken
- scheduling
- readjobsummary
- listagentmembers
- list agent members
- readnode
- list nodes
- list allocation health checks
- listevaluationallocations
- deletenodepool
- deregisterjob
- read a job
- deletenamespace
- readagentself
- listdeploymentallocations
- setjobstability
- plan a job update
- readdeployment
- delete a service registration
- readselfacltoken
- listservices
- listacltokens
- list deployments for a job
- evaluatenode
slug: nomad-capability
source_filename: nomad-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HashiCorp Nomad HTTP API\n  description: The HashiCorp Nomad HTTP API provides programmatic access to all Nomad functionality including job scheduling,\n    allocation management, node operations, deployments, services, evaluations, namespaces, ACL policies, and cluster status.\n    All API routes are prefixed with /v1/ and the default port is 4646. The API is RESTful, responds to standard HTTP verbs,\n    and supports ACL token authentication via the X-Nomad-Token header or Bearer scheme.\n  tags:\n  - Nomad\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nomad\n    baseUri: http://localhost:4646/v1\n    description: HashiCorp Nomad HTTP API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Nomad-Token\n      value: '{{NOMAD_TOKEN}}'\n    resources:\n    - name: jobs\n      path: /jobs\n      operations:\n      - name: listjobs\n  \
  \      method: GET\n        description: List jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registerjob\n        method: PUT\n        description: Register a new job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-parse\n      path: /jobs/parse\n      operations:\n      - name: parsejob\n        method: PUT\n        description: Parse a job specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-statuses\n      path: /jobs/statuses\n      operations:\n      - name: listjobstatuses\n        method: GET\n        description: List job statuses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid\n\
  \      path: /job/{jobID}\n      operations:\n      - name: readjob\n        method: GET\n        description: Read a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deregisterjob\n        method: DELETE\n        description: Deregister a job\n        inputParameters:\n        - name: purge\n          in: query\n          type: boolean\n          description: If true, the job is purged from the system and cannot be recovered. Defaults to false.\n        - name: global\n          in: query\n          type: boolean\n          description: If true, deregisters the job in all federated regions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid-evaluate\n      path: /job/{jobID}/evaluate\n      operations:\n      - name: evaluatejob\n        method: PUT\n        description: Create a new evaluation\
  \ for a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid-plan\n      path: /job/{jobID}/plan\n      operations:\n      - name: planjob\n        method: PUT\n        description: Plan a job update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid-allocations\n      path: /job/{jobID}/allocations\n      operations:\n      - name: listjoballocations\n        method: GET\n        description: List allocations for a job\n        inputParameters:\n        - name: all\n          in: query\n          type: boolean\n          description: If true, includes allocations from all namespaces.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid-evaluations\n      path: /job/{jobID}/evaluations\n      operations:\n\
  \      - name: listjobevaluations\n        method: GET\n        description: List evaluations for a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid-deployments\n      path: /job/{jobID}/deployments\n      operations:\n      - name: listjobdeployments\n        method: GET\n        description: List deployments for a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid-versions\n      path: /job/{jobID}/versions\n      operations:\n      - name: listjobversions\n        method: GET\n        description: List versions of a job\n        inputParameters:\n        - name: diffs\n          in: query\n          type: boolean\n          description: If true, includes the diff between consecutive job versions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: job-jobid-revert\n      path: /job/{jobID}/revert\n      operations:\n      - name: revertjob\n        method: PUT\n        description: Revert job to an older version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid-stable\n      path: /job/{jobID}/stable\n      operations:\n      - name: setjobstability\n        method: PUT\n        description: Set job stability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid-summary\n      path: /job/{jobID}/summary\n      operations:\n      - name: readjobsummary\n        method: GET\n        description: Read a job summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-jobid-dispatch\n      path:\
  \ /job/{jobID}/dispatch\n      operations:\n      - name: dispatchjob\n        method: PUT\n        description: Dispatch a parameterized job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocations\n      path: /allocations\n      operations:\n      - name: listallocations\n        method: GET\n        description: List allocations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocation-allocid\n      path: /allocation/{allocID}\n      operations:\n      - name: readallocation\n        method: GET\n        description: Read an allocation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocation-allocid-services\n      path: /allocation/{allocID}/services\n      operations:\n      - name: listallocationservices\n\
  \        method: GET\n        description: List allocation services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocation-allocid-checks\n      path: /allocation/{allocID}/checks\n      operations:\n      - name: listallocationchecks\n        method: GET\n        description: List allocation health checks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evaluations\n      path: /evaluations\n      operations:\n      - name: listevaluations\n        method: GET\n        description: List evaluations\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter evaluations by status.\n        - name: job\n          in: query\n          type: string\n          description: Filter evaluations by job ID.\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evaluations-count\n      path: /evaluations/count\n      operations:\n      - name: countevaluations\n        method: GET\n        description: Count evaluations\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter the count by evaluation status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evaluation-evalid\n      path: /evaluation/{evalID}\n      operations:\n      - name: readevaluation\n        method: GET\n        description: Read an evaluation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evaluation-evalid-allocations\n      path: /evaluation/{evalID}/allocations\n      operations:\n      - name: listevaluationallocations\n\
  \        method: GET\n        description: List allocations for an evaluation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /deployments\n      operations:\n      - name: listdeployments\n        method: GET\n        description: List deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-deploymentid\n      path: /deployment/{deploymentID}\n      operations:\n      - name: readdeployment\n        method: GET\n        description: Read a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-allocations-deploymentid\n      path: /deployment/allocations/{deploymentID}\n      operations:\n      - name: listdeploymentallocations\n        method: GET\n        description:\
  \ List deployment allocations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-fail-deploymentid\n      path: /deployment/fail/{deploymentID}\n      operations:\n      - name: faildeployment\n        method: PUT\n        description: Fail a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-pause-deploymentid\n      path: /deployment/pause/{deploymentID}\n      operations:\n      - name: pausedeployment\n        method: PUT\n        description: Pause or resume a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-promote-deploymentid\n      path: /deployment/promote/{deploymentID}\n      operations:\n      - name: promotedeployment\n        method: PUT\n        description:\
  \ Promote a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /nodes\n      operations:\n      - name: listnodes\n        method: GET\n        description: List nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-nodeid\n      path: /node/{nodeID}\n      operations:\n      - name: readnode\n        method: GET\n        description: Read a node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-nodeid-evaluate\n      path: /node/{nodeID}/evaluate\n      operations:\n      - name: evaluatenode\n        method: PUT\n        description: Create a new evaluation for a node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: node-nodeid-drain\n      path: /node/{nodeID}/drain\n      operations:\n      - name: drainnode\n        method: POST\n        description: Set node drain mode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-nodeid-purge\n      path: /node/{nodeID}/purge\n      operations:\n      - name: purgenode\n        method: DELETE\n        description: Purge a node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-pools\n      path: /node/pools\n      operations:\n      - name: listnodepools\n        method: GET\n        description: List node pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnodepool\n        method: PUT\n        description: Create or update a node pool\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-pool-poolname\n      path: /node/pool/{poolName}\n      operations:\n      - name: readnodepool\n        method: GET\n        description: Read a node pool\n        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: The name of the node pool.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenodepool\n        method: DELETE\n        description: Delete a node pool\n        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: The name of the node pool.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: services\n      path: /services\n      operations:\n      - name: listservices\n        method: GET\n        description: List services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-servicename\n      path: /service/{serviceName}\n      operations:\n      - name: readservice\n        method: GET\n        description: Read a service\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: The name of the service.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteservice\n        method: DELETE\n        description: Delete a service registration\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description:\
  \ The name of the service.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: volumes\n      path: /volumes\n      operations:\n      - name: listvolumes\n        method: GET\n        description: List volumes\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          description: Filter volumes by type (csi or host).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces\n      path: /namespaces\n      operations:\n      - name: listnamespaces\n        method: GET\n        description: List namespaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespace\n      path: /namespace\n      operations:\n      - name: createnamespace\n        method: PUT\n        description:\
  \ Create or update a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespace-namespacename\n      path: /namespace/{namespaceName}\n      operations:\n      - name: readnamespace\n        method: GET\n        description: Read a namespace\n        inputParameters:\n        - name: namespaceName\n          in: path\n          type: string\n          required: true\n          description: The name of the namespace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespace\n        method: DELETE\n        description: Delete a namespace\n        inputParameters:\n        - name: namespaceName\n          in: path\n          type: string\n          required: true\n          description: The name of the namespace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: acl-policies\n      path: /acl/policies\n      operations:\n      - name: listaclpolicies\n        method: GET\n        description: List ACL policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acl-policy-policyname\n      path: /acl/policy/{policyName}\n      operations:\n      - name: readaclpolicy\n        method: GET\n        description: Read an ACL policy\n        inputParameters:\n        - name: policyName\n          in: path\n          type: string\n          required: true\n          description: The name of the ACL policy.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upsertaclpolicy\n        method: PUT\n        description: Create or update an ACL policy\n        inputParameters:\n        - name: policyName\n          in: path\n\
  \          type: string\n          required: true\n          description: The name of the ACL policy.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaclpolicy\n        method: DELETE\n        description: Delete an ACL policy\n        inputParameters:\n        - name: policyName\n          in: path\n          type: string\n          required: true\n          description: The name of the ACL policy.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acl-tokens\n      path: /acl/tokens\n      operations:\n      - name: listacltokens\n        method: GET\n        description: List ACL tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acl-token\n      path: /acl/token\n      operations:\n      - name: createacltoken\n\
  \        method: PUT\n        description: Create an ACL token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acl-token-self\n      path: /acl/token/self\n      operations:\n      - name: readselfacltoken\n        method: GET\n        description: Read own ACL token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acl-token-tokenaccessorid\n      path: /acl/token/{tokenAccessorID}\n      operations:\n      - name: readacltoken\n        method: GET\n        description: Read an ACL token\n        inputParameters:\n        - name: tokenAccessorID\n          in: path\n          type: string\n          required: true\n          description: The accessor ID of the ACL token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ deleteacltoken\n        method: DELETE\n        description: Delete an ACL token\n        inputParameters:\n        - name: tokenAccessorID\n          in: path\n          type: string\n          required: true\n          description: The accessor ID of the ACL token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-members\n      path: /agent/members\n      operations:\n      - name: listagentmembers\n        method: GET\n        description: List agent members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-self\n      path: /agent/self\n      operations:\n      - name: readagentself\n        method: GET\n        description: Read agent self\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-join\n\
  \      path: /agent/join\n      operations:\n      - name: joinagent\n        method: PUT\n        description: Join an agent\n        inputParameters:\n        - name: address\n          in: query\n          type: string\n          required: true\n          description: The address of the server(s) to join.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-force-leave\n      path: /agent/force-leave\n      operations:\n      - name: forceleaveagent\n        method: PUT\n        description: Force leave an agent\n        inputParameters:\n        - name: node\n          in: query\n          type: string\n          required: true\n          description: The name of the node to force leave.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nomad-rest\n    description:\
  \ REST adapter for HashiCorp Nomad HTTP API.\n    resources:\n    - path: /jobs\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: List jobs\n        call: nomad.listjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs\n      name: registerjob\n      operations:\n      - method: PUT\n        name: registerjob\n        description: Register a new job\n        call: nomad.registerjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/parse\n      name: parsejob\n      operations:\n      - method: PUT\n        name: parsejob\n        description: Parse a job specification\n        call: nomad.parsejob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/statuses\n      name: listjobstatuses\n      operations:\n      - method: GET\n        name: listjobstatuses\n        description: List job statuses\n      \
  \  call: nomad.listjobstatuses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}\n      name: readjob\n      operations:\n      - method: GET\n        name: readjob\n        description: Read a job\n        call: nomad.readjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}\n      name: deregisterjob\n      operations:\n      - method: DELETE\n        name: deregisterjob\n        description: Deregister a job\n        call: nomad.deregisterjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/evaluate\n      name: evaluatejob\n      operations:\n      - method: PUT\n        name: evaluatejob\n        description: Create a new evaluation for a job\n        call: nomad.evaluatejob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/plan\n      name: planjob\n      operations:\n      - method:\
  \ PUT\n        name: planjob\n        description: Plan a job update\n        call: nomad.planjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/allocations\n      name: listjoballocations\n      operations:\n      - method: GET\n        name: listjoballocations\n        description: List allocations for a job\n        call: nomad.listjoballocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/evaluations\n      name: listjobevaluations\n      operations:\n      - method: GET\n        name: listjobevaluations\n        description: List evaluations for a job\n        call: nomad.listjobevaluations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/deployments\n      name: listjobdeployments\n      operations:\n      - method: GET\n        name: listjobdeployments\n        description: List deployments for a job\n        call: nomad.listjobdeployments\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/versions\n      name: listjobversions\n      operations:\n      - method: GET\n        name: listjobversions\n        description: List versions of a job\n        call: nomad.listjobversions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/revert\n      name: revertjob\n      operations:\n      - method: PUT\n        name: revertjob\n        description: Revert job to an older version\n        call: nomad.revertjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/stable\n      name: setjobstability\n      operations:\n      - method: PUT\n        name: setjobstability\n        description: Set job stability\n        call: nomad.setjobstability\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/summary\n      name: readjobsummary\n      operations:\n\
  \      - method: GET\n        name: readjobsummary\n        description: Read a job summary\n        call: nomad.readjobsummary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job/{jobID}/dispatch\n      name: dispatchjob\n      operations:\n      - method: PUT\n        name: dispatchjob\n        description: Dispatch a parameterized job\n        call: nomad.dispatchjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /allocations\n      name: listallocations\n      operations:\n      - method: GET\n        name: listallocations\n        description: List allocations\n        call: nomad.listallocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /allocation/{allocID}\n      name: readallocation\n      operations:\n      - method: GET\n        name: readallocation\n        description: Read an allocation\n        call: nomad.readallocation\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /allocation/{allocID}/services\n      name: listallocationservices\n      operations:\n      - method: GET\n        name: listallocationservices\n        description: List allocation services\n        call: nomad.listallocationservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /allocation/{allocID}/checks\n      name: listallocationchecks\n      operations:\n      - method: GET\n        name: listallocationchecks\n        description: List allocation health checks\n        call: nomad.listallocationchecks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /evaluations\n      name: listevaluations\n      operations:\n      - method: GET\n        name: listevaluations\n        description: List evaluations\n        call: nomad.listevaluations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /evaluations/count\n\
  \      name: countevaluations\n      operations:\n      - method: GET\n        name: countevaluations\n        description: Count evaluations\n        call: nomad.countevaluations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /evaluation/{evalID}\n      name: readevaluation\n      operations:\n      - method: GET\n        name: readevaluation\n        description: Read an evaluation\n        call: nomad.readevaluation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /evaluation/{evalID}/allocations\n      name: listevaluationallocations\n      operations:\n      - method: GET\n        name: listevaluationallocations\n        description: List allocations for an evaluation\n        call: nomad.listevaluationallocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments\n      name: listdeployments\n      operations:\n      - method: GET\n        name: listdeployments\n\
  \        description: List deployments\n        call: nomad.listdeployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployment/{deploymentID}\n      name: readdeployment\n      operations:\n      - method: GET\n        name: readdeployment\n        description: Read a deployment\n        call: nomad.readdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployment/allocations/{deploymentID}\n      name: listdeploymentallocations\n      operations:\n      - method: GET\n        name: listdeploymentallocations\n        description: List deployment allocations\n        call: nomad.listdeploymentallocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployment/fail/{deploymentID}\n      name: faildeployment\n      operations:\n      - method: PUT\n        name: faildeployment\n        description: Fail a deployment\n        call: nomad.faildeployment\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployment/pause/{deploymentID}\n      name: pausedeployment\n      operations:\n      - method: PUT\n        name: pausedeployment\n        description: Pause or resume a deployment\n        call: nomad.pausedeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployment/promote/{deploymentID}\n      name: promotedeployment\n      operations:\n      - method: PUT\n        name: promotedeployment\n        description: Promote a deployment\n        call: nomad.promotedeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes\n      name: listnodes\n      operations:\n      - method: GET\n        name: listnodes\n        description: List nodes\n        call: nomad.listnodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{nodeID}\n      name: readnode\n      operations:\n\
  \      - method: GET\n        name: readnode\n        description: Read a node\n        call: nomad.readnode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{nodeID}/evaluate\n      name: evaluatenode\n      operations:\n      - method: PUT\n        name: evaluatenode\n        description: Create a new evaluation for a node\n        call: nomad.evaluatenode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{nodeID}/drain\n      name: drainnode\n      operations:\n      - method: POST\n        name: drainnode\n        description: Set node drain mode\n        call: nomad.drainnode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{nodeID}/purge\n      name: purgenode\n      operations:\n      - method: DELETE\n        name: purgenode\n        description: Purge a node\n        call: nomad.purgenode\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /node/pools\n      name: listnodepools\n      operations:\n      - method: GET\n        name: listnodepools\n        description: List node pools\n        call: nomad.listnodepools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/pools\n      name: createnodepool\n      operations:\n      - method: PUT\n        name: createnodepool\n        description: Create or update a node pool\n        call: nomad.createnodepool\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/pool/{poolName}\n      name: readnodepool\n      operations:\n      - method: GET\n        name: readnodepool\n        description: Read a node pool\n        call: nomad.readnodepool\n        with:\n          poolName: rest.poolName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/pool/{poolName}\n      name: deletenodepool\n      operations:\n      - method: DELETE\n\
  \        name: deletenodepool\n        description: Delete a node pool\n        call: nomad.deletenodepool\n        with:\n          poolName: rest.poolName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: List services\n        call: nomad.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service/{serviceName}\n      name: readservice\n      operations:\n      - method: GET\n        name: readservice\n        description: Read a service\n        call: nomad.readservice\n        with:\n          serviceName: rest.serviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service/{serviceName}\n      name: deleteservice\n      operatio\n\n# --- truncated at 32 KB (56 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/nomad/refs/heads/main/capabilities/nomad-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nomad/refs/heads/main/capabilities/nomad-capability.yaml
tags:
- Nomad
- API
tools:
- description: List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Register a new job
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: registerjob
- description: Parse a job specification
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: parsejob
- description: List job statuses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobstatuses
- description: Read a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readjob
- description: Deregister a job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deregisterjob
- description: Create a new evaluation for a job
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: evaluatejob
- description: Plan a job update
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: planjob
- description: List allocations for a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjoballocations
- description: List evaluations for a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobevaluations
- description: List deployments for a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobdeployments
- description: List versions of a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobversions
- description: Revert job to an older version
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: revertjob
- description: Set job stability
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setjobstability
- description: Read a job summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readjobsummary
- description: Dispatch a parameterized job
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: dispatchjob
- description: List allocations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listallocations
- description: Read an allocation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readallocation
- description: List allocation services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listallocationservices
- description: List allocation health checks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listallocationchecks
- description: List evaluations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevaluations
- description: Count evaluations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: countevaluations
- description: Read an evaluation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readevaluation
- description: List allocations for an evaluation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevaluationallocations
- description: List deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeployments
- description: Read a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readdeployment
- description: List deployment allocations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeploymentallocations
- description: Fail a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: faildeployment
- description: Pause or resume a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: pausedeployment
- description: Promote a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: promotedeployment
- description: List nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodes
- description: Read a node
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readnode
- description: Create a new evaluation for a node
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: evaluatenode
- description: Set node drain mode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: drainnode
- description: Purge a node
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: purgenode
- description: List node pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodepools
- description: Create or update a node pool
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createnodepool
- description: Read a node pool
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readnodepool
- description: Delete a node pool
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenodepool
- description: List services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Read a service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readservice
- description: Delete a service registration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: List volumes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvolumes
- description: List namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaces
- description: Create or update a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createnamespace
- description: Read a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readnamespace
- description: Delete a namespace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespace
- description: List ACL policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaclpolicies
- description: Read an ACL policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readaclpolicy
- description: Create or update an ACL policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: upsertaclpolicy
- description: Delete an ACL policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaclpolicy
- description: List ACL tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listacltokens
- description: Create an ACL token
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createacltoken
- description: Read own ACL token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readselfacltoken
- description: Read an ACL token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readacltoken
- description: Delete an ACL token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteacltoken
- description: List agent members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagentmembers
- description: Read agent self
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readagentself
- description: Join an agent
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: joinagent
- description: Force leave an agent
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: forceleaveagent
---
