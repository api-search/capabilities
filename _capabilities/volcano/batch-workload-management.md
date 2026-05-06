---
categories: []
consumed_apis: []
description: Unified capability for managing Volcano batch workloads on Kubernetes. Combines Job, Queue, and PodGroup APIs to orchestrate distributed ML training, HPC simulation, big data processing, and scientific computing workflows. Designed for ML platform engineers, data engineers, and HPC cluster operators.
layout: capability
name: Volcano Batch Workload Management
operations:
- description: List all Volcano Jobs in a namespace.
  method: GET
  name: list-namespaced-jobs
  path: /v1/jobs/{namespace}
- description: Submit a new batch workload (ML training, HPC, Spark).
  method: POST
  name: create-namespaced-job
  path: /v1/jobs/{namespace}
- description: Get job status and configuration.
  method: GET
  name: get-namespaced-job
  path: /v1/jobs/{namespace}/{name}
- description: Cancel and remove a batch job.
  method: DELETE
  name: delete-namespaced-job
  path: /v1/jobs/{namespace}/{name}
- description: List all scheduling queues.
  method: GET
  name: list-queues
  path: /v1/queues
- description: Create a new scheduling queue.
  method: POST
  name: create-queue
  path: /v1/queues
- description: Get queue configuration and status.
  method: GET
  name: get-queue
  path: /v1/queues/{name}
- description: Delete a scheduling queue.
  method: DELETE
  name: delete-queue
  path: /v1/queues/{name}
- description: List PodGroups in a namespace.
  method: GET
  name: list-namespaced-podgroups
  path: /v1/podgroups/{namespace}
- description: Create a PodGroup for gang-scheduled workloads.
  method: POST
  name: create-namespaced-podgroup
  path: /v1/podgroups/{namespace}
- description: Get PodGroup status.
  method: GET
  name: get-namespaced-podgroup
  path: /v1/podgroups/{namespace}/{name}
personas: []
provider_name: Volcano
provider_slug: volcano
search_terms:
- get configuration, capacity, and status of a volcano scheduling queue.
- incubating
- create a new volcano queue for multi-tenant resource partitioning.
- submit batch job
- batch scheduling
- get detailed status and phase of a volcano batch job.
- scheduling
- volcano
- manage scheduling queues for resource partitioning.
- get job status and configuration.
- cancel batch job
- list podgroups
- list podgroups in a namespace.
- list scheduling queues
- submit a new batch workload (ml training, hpc, spark).
- get namespaced podgroup
- delete a scheduling queue.
- create queue
- list queues
- cancel and delete a volcano batch job and its associated pods.
- create namespaced podgroup
- cloud native
- get namespaced job
- kubernetes
- list all scheduling queues.
- submit a new distributed batch workload to volcano (pytorch, tensorflow, spark, mpi).
- create scheduling queue
- hpc
- list all volcano jobs in a namespace.
- machine learning
- get queue
- get queue configuration and status.
- get podgroup status.
- get the status of a podgroup to check gang-scheduling progress.
- inspect scheduling queue
- list volcano batch jobs in a kubernetes namespace (ml training, spark, hpc).
- cancel and remove a batch job.
- create a new scheduling queue.
- list namespaced podgroups
- delete queue
- list podgroups used for gang-scheduling coordination in a namespace.
- cncf
- list batch jobs
- list all volcano batch jobs across all namespaces in the cluster.
- manage volcano batch jobs.
- inspect or manage a specific queue.
- list all volcano scheduling queues and their resource allocations.
- batch processing
- inspect podgroup
- create a podgroup for gang-scheduled workloads.
- manage podgroups for gang scheduling.
- inspect a specific podgroup.
- delete namespaced job
- list cluster jobs
- create namespaced job
- inspect and manage a specific batch job.
- list namespaced jobs
- inspect batch job
slug: batch-workload-management
source_filename: batch-workload-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Volcano Batch Workload Management\n  description: Unified capability for managing Volcano batch workloads on Kubernetes. Combines Job, Queue, and PodGroup APIs\n    to orchestrate distributed ML training, HPC simulation, big data processing, and scientific computing workflows. Designed\n    for ML platform engineers, data engineers, and HPC cluster operators.\n  tags:\n  - Volcano\n  - Kubernetes\n  - Batch Scheduling\n  - Machine Learning\n  - HPC\n  - Cloud Native\n  - CNCF\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    KUBERNETES_API_SERVER: KUBERNETES_API_SERVER\n    KUBERNETES_TOKEN: KUBERNETES_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: volcano-jobs\n    baseUri: https://{{KUBERNETES_API_SERVER}}\n    description: Volcano Job CRD API via Kubernetes API server.\n    authentication:\n      type: bearer\n      token: '{{KUBERNETES_TOKEN}}'\n    resources:\n    - name: namespaced-jobs\n\
  \      path: /apis/batch.volcano.sh/v1alpha1/namespaces/{namespace}/jobs\n      description: Volcano Jobs in a namespace.\n      operations:\n      - name: list-namespaced-jobs\n        method: GET\n        description: List all Volcano Jobs in a namespace.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Kubernetes namespace.\n        - name: labelSelector\n          in: query\n          type: string\n          required: false\n          description: Label selector filter.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-namespaced-job\n        method: POST\n        description: Create a new Volcano Job.\n        inputParameters:\n        - name: namespace\n\
  \          in: path\n          type: string\n          required: true\n          description: Kubernetes namespace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiVersion: batch.volcano.sh/v1alpha1\n            kind: Job\n    - name: namespaced-job-detail\n      path: /apis/batch.volcano.sh/v1alpha1/namespaces/{namespace}/jobs/{name}\n      description: Operate on a specific Volcano Job.\n      operations:\n      - name: get-namespaced-job\n        method: GET\n        description: Get a specific Volcano Job.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: delete-namespaced-job\n        method: DELETE\n        description: Delete a Volcano Job.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-jobs\n      path: /apis/batch.volcano.sh/v1alpha1/jobs\n      description: List Volcano Jobs across all namespaces.\n      operations:\n      - name: list-jobs-all-namespaces\n        method: GET\n        description: List all Volcano Jobs cluster-wide.\n        inputParameters:\n        - name: labelSelector\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n\
  \    namespace: volcano-queues\n    baseUri: https://{{KUBERNETES_API_SERVER}}\n    description: Volcano Queue CRD API via Kubernetes API server.\n    authentication:\n      type: bearer\n      token: '{{KUBERNETES_TOKEN}}'\n    resources:\n    - name: queues\n      path: /apis/scheduling.volcano.sh/v1beta1/queues\n      description: Cluster-scoped Volcano Queue resources.\n      operations:\n      - name: list-queues\n        method: GET\n        description: List all Volcano Queues in the cluster.\n        inputParameters:\n        - name: labelSelector\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-queue\n        method: POST\n        description: Create a new Volcano Queue.\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiVersion: scheduling.volcano.sh/v1beta1\n            kind: Queue\n    - name: queue-detail\n      path: /apis/scheduling.volcano.sh/v1beta1/queues/{name}\n      description: Operate on a specific Volcano Queue.\n      operations:\n      - name: get-queue\n        method: GET\n        description: Get a specific Volcano Queue.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-queue\n        method: PUT\n        description: Replace a Volcano Queue specification.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiVersion: scheduling.volcano.sh/v1beta1\n            kind: Queue\n      - name: delete-queue\n        method: DELETE\n        description: Delete a Volcano Queue.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: volcano-podgroups\n    baseUri: https://{{KUBERNETES_API_SERVER}}\n    description: Volcano PodGroup CRD API via Kubernetes API server.\n    authentication:\n      type: bearer\n      token: '{{KUBERNETES_TOKEN}}'\n    resources:\n    - name: namespaced-podgroups\n      path: /apis/scheduling.volcano.sh/v1beta1/namespaces/{namespace}/podgroups\n      description: PodGroups in a namespace.\n \
  \     operations:\n      - name: list-namespaced-podgroups\n        method: GET\n        description: List PodGroups in a namespace.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n        - name: labelSelector\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-namespaced-podgroup\n        method: POST\n        description: Create a PodGroup for gang scheduling.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiVersion: scheduling.volcano.sh/v1beta1\n            kind: PodGroup\n\
  \    - name: namespaced-podgroup-detail\n      path: /apis/scheduling.volcano.sh/v1beta1/namespaces/{namespace}/podgroups/{name}\n      description: Operate on a specific PodGroup.\n      operations:\n      - name: get-namespaced-podgroup\n        method: GET\n        description: Get a specific PodGroup.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-namespaced-podgroup\n        method: DELETE\n        description: Delete a PodGroup.\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: volcano-batch-api\n    description: Unified REST API for Volcano batch workload management.\n    resources:\n    - path: /v1/jobs/{namespace}\n      name: jobs\n      description: Manage Volcano batch jobs.\n      operations:\n      - method: GET\n        name: list-namespaced-jobs\n        description: List all Volcano Jobs in a namespace.\n        call: volcano-jobs.list-namespaced-jobs\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-namespaced-job\n        description: Submit a new batch workload (ML training, HPC, Spark).\n        call: volcano-jobs.create-namespaced-job\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{namespace}/{name}\n\
  \      name: job-detail\n      description: Inspect and manage a specific batch job.\n      operations:\n      - method: GET\n        name: get-namespaced-job\n        description: Get job status and configuration.\n        call: volcano-jobs.get-namespaced-job\n        with:\n          namespace: rest.namespace\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-namespaced-job\n        description: Cancel and remove a batch job.\n        call: volcano-jobs.delete-namespaced-job\n        with:\n          namespace: rest.namespace\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queues\n      name: queues\n      description: Manage scheduling queues for resource partitioning.\n      operations:\n      - method: GET\n        name: list-queues\n        description: List all scheduling queues.\n        call: volcano-queues.list-queues\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-queue\n        description: Create a new scheduling queue.\n        call: volcano-queues.create-queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queues/{name}\n      name: queue-detail\n      description: Inspect or manage a specific queue.\n      operations:\n      - method: GET\n        name: get-queue\n        description: Get queue configuration and status.\n        call: volcano-queues.get-queue\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-queue\n        description: Delete a scheduling queue.\n        call: volcano-queues.delete-queue\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/podgroups/{namespace}\n      name: podgroups\n\
  \      description: Manage PodGroups for gang scheduling.\n      operations:\n      - method: GET\n        name: list-namespaced-podgroups\n        description: List PodGroups in a namespace.\n        call: volcano-podgroups.list-namespaced-podgroups\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-namespaced-podgroup\n        description: Create a PodGroup for gang-scheduled workloads.\n        call: volcano-podgroups.create-namespaced-podgroup\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/podgroups/{namespace}/{name}\n      name: podgroup-detail\n      description: Inspect a specific PodGroup.\n      operations:\n      - method: GET\n        name: get-namespaced-podgroup\n        description: Get PodGroup status.\n        call: volcano-podgroups.get-namespaced-podgroup\n\
  \        with:\n          namespace: rest.namespace\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: volcano-batch-mcp\n    transport: http\n    description: MCP server for AI-assisted Volcano batch workload management.\n    tools:\n    - name: list-batch-jobs\n      description: List Volcano batch jobs in a Kubernetes namespace (ML training, Spark, HPC).\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: volcano-jobs.list-namespaced-jobs\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-batch-job\n      description: Submit a new distributed batch workload to Volcano (PyTorch, TensorFlow, Spark, MPI).\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: volcano-jobs.create-namespaced-job\n      with:\n\
  \        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inspect-batch-job\n      description: Get detailed status and phase of a Volcano batch job.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: volcano-jobs.get-namespaced-job\n      with:\n        namespace: tools.namespace\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-batch-job\n      description: Cancel and delete a Volcano batch job and its associated pods.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: volcano-jobs.delete-namespaced-job\n      with:\n        namespace: tools.namespace\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cluster-jobs\n      description: List all Volcano batch jobs across all namespaces in the cluster.\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: volcano-jobs.list-jobs-all-namespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-scheduling-queues\n      description: List all Volcano scheduling queues and their resource allocations.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: volcano-queues.list-queues\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inspect-scheduling-queue\n      description: Get configuration, capacity, and status of a Volcano scheduling queue.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: volcano-queues.get-queue\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-scheduling-queue\n      description: Create a new Volcano queue for multi-tenant\
  \ resource partitioning.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: volcano-queues.create-queue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-podgroups\n      description: List PodGroups used for gang-scheduling coordination in a namespace.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: volcano-podgroups.list-namespaced-podgroups\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inspect-podgroup\n      description: Get the status of a PodGroup to check gang-scheduling progress.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: volcano-podgroups.get-namespaced-podgroup\n      with:\n        namespace: tools.namespace\n        name: tools.name\n      outputParameters:\n      - type: object\n    \
  \    mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/volcano/refs/heads/main/capabilities/batch-workload-management.yaml
tags:
- Volcano
- Kubernetes
- Batch Scheduling
- Machine Learning
- HPC
- Cloud Native
- CNCF
tools:
- description: List Volcano batch jobs in a Kubernetes namespace (ML training, Spark, HPC).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-batch-jobs
- description: Submit a new distributed batch workload to Volcano (PyTorch, TensorFlow, Spark, MPI).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-batch-job
- description: Get detailed status and phase of a Volcano batch job.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: inspect-batch-job
- description: Cancel and delete a Volcano batch job and its associated pods.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-batch-job
- description: List all Volcano batch jobs across all namespaces in the cluster.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-cluster-jobs
- description: List all Volcano scheduling queues and their resource allocations.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-scheduling-queues
- description: Get configuration, capacity, and status of a Volcano scheduling queue.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: inspect-scheduling-queue
- description: Create a new Volcano queue for multi-tenant resource partitioning.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-scheduling-queue
- description: List PodGroups used for gang-scheduling coordination in a namespace.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-podgroups
- description: Get the status of a PodGroup to check gang-scheduling progress.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: inspect-podgroup
---
