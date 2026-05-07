---
categories: []
consumed_apis: []
description: The Flink REST API is exposed by the JobManager Dispatcher and provides monitoring and management capabilities for a Flink cluster. It covers cluster configuration, JobManager environment and metrics, job lifecycle (submit, list, cancel, stop), checkpoint and savepoint management, JAR upload and execution, dataset operations, and TaskManager inspection.
layout: capability
name: Apache Flink REST API
operations:
- description: Shut down the cluster
  method: DELETE
  name: shutdowncluster
  path: /cluster
- description: Web UI configuration
  method: GET
  name: getwebuiconfig
  path: /config
- description: Cluster configuration
  method: GET
  name: getjobmanagerconfig
  path: /jobmanager/config
- description: JobManager environment
  method: GET
  name: getjobmanagerenvironment
  path: /jobmanager/environment
- description: List JobManager log files
  method: GET
  name: listjobmanagerlogs
  path: /jobmanager/logs
- description: JobManager metrics
  method: GET
  name: getjobmanagermetrics
  path: /jobmanager/metrics
- description: JobManager thread dump
  method: GET
  name: getjobmanagerthreaddump
  path: /jobmanager/thread-dump
- description: List jobs
  method: GET
  name: listjobs
  path: /jobs
- description: Jobs overview
  method: GET
  name: getjobsoverview
  path: /jobs/overview
- description: Aggregated job metrics
  method: GET
  name: getjobsmetrics
  path: /jobs/metrics
- description: Get job details
  method: GET
  name: getjob
  path: /jobs/{jobid}
- description: Cancel or stop a job
  method: PATCH
  name: terminatejob
  path: /jobs/{jobid}
- description: Job configuration
  method: GET
  name: getjobconfig
  path: /jobs/{jobid}/config
- description: Job exception history
  method: GET
  name: getjobexceptions
  path: /jobs/{jobid}/exceptions
- description: Job accumulators
  method: GET
  name: getjobaccumulators
  path: /jobs/{jobid}/accumulators
- description: Checkpoint statistics for a job
  method: GET
  name: getjobcheckpoints
  path: /jobs/{jobid}/checkpoints
- description: Trigger a checkpoint
  method: POST
  name: triggercheckpoint
  path: /jobs/{jobid}/checkpoints
- description: Checkpoint configuration for a job
  method: GET
  name: getcheckpointconfig
  path: /jobs/{jobid}/checkpoints/config
- description: Checkpoint details
  method: GET
  name: getcheckpointdetails
  path: /jobs/{jobid}/checkpoints/details/{checkpointid}
- description: List uploaded JARs
  method: GET
  name: listjars
  path: /jars
- description: Upload a JAR
  method: POST
  name: uploadjar
  path: /jars/upload
- description: Delete a JAR
  method: DELETE
  name: deletejar
  path: /jars/{jarid}
- description: Plan for a JAR
  method: GET
  name: getjarplan
  path: /jars/{jarid}/plan
- description: Run a job from a JAR
  method: POST
  name: runjar
  path: /jars/{jarid}/run
- description: List TaskManagers
  method: GET
  name: listtaskmanagers
  path: /taskmanagers
- description: TaskManager metrics
  method: GET
  name: gettaskmanagermetrics
  path: /taskmanagers/{taskmanagerid}/metrics
- description: List TaskManager logs
  method: GET
  name: listtaskmanagerlogs
  path: /taskmanagers/{taskmanagerid}/logs
- description: List cluster datasets
  method: GET
  name: listdatasets
  path: /datasets
- description: Delete a cluster dataset
  method: DELETE
  name: deletedataset
  path: /datasets/{datasetid}
personas: []
provider_name: Apache Flink
provider_slug: flink
search_terms:
- getjobsoverview
- listdatasets
- getjobcheckpoints
- shutdowncluster
- plan for a jar
- getjobconfig
- trigger a checkpoint
- listjobmanagerlogs
- web ui configuration
- getwebuiconfig
- jobmanager environment
- get job details
- delete a cluster dataset
- api
- gettaskmanagermetrics
- list jobmanager log files
- getjobaccumulators
- deletejar
- listtaskmanagerlogs
- stream processing
- listjobs
- listtaskmanagers
- aggregated job metrics
- getjobexceptions
- run a job from a jar
- getjobmanagerconfig
- triggercheckpoint
- jobs overview
- big data
- checkpoint configuration for a job
- jobmanager thread dump
- cancel or stop a job
- real-time analytics
- jobmanager metrics
- checkpoint statistics for a job
- checkpoint details
- getjobmanagermetrics
- getcheckpointdetails
- list taskmanager logs
- getjobmanagerthreaddump
- getjobmanagerenvironment
- job accumulators
- listjars
- list cluster datasets
- list jobs
- uploadjar
- getjob
- terminatejob
- shut down the cluster
- job configuration
- getcheckpointconfig
- getjarplan
- cluster configuration
- flink
- list taskmanagers
- workflows
- runjar
- upload a jar
- taskmanager metrics
- list uploaded jars
- deletedataset
- getjobsmetrics
- delete a jar
- distributed computing
- job exception history
slug: flink-capability
source_filename: flink-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Flink REST API\n  description: The Flink REST API is exposed by the JobManager Dispatcher and provides monitoring and management capabilities\n    for a Flink cluster. It covers cluster configuration, JobManager environment and metrics, job lifecycle (submit, list,\n    cancel, stop), checkpoint and savepoint management, JAR upload and execution, dataset operations, and TaskManager inspection.\n  tags:\n  - Flink\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: flink\n    baseUri: http://localhost:8081\n    description: Apache Flink REST API HTTP API.\n    resources:\n    - name: cluster\n      path: /cluster\n      operations:\n      - name: shutdowncluster\n        method: DELETE\n        description: Shut down the cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ config\n      path: /config\n      operations:\n      - name: getwebuiconfig\n        method: GET\n        description: Web UI configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobmanager-config\n      path: /jobmanager/config\n      operations:\n      - name: getjobmanagerconfig\n        method: GET\n        description: Cluster configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobmanager-environment\n      path: /jobmanager/environment\n      operations:\n      - name: getjobmanagerenvironment\n        method: GET\n        description: JobManager environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobmanager-logs\n      path: /jobmanager/logs\n      operations:\n      - name: listjobmanagerlogs\n\
  \        method: GET\n        description: List JobManager log files\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobmanager-metrics\n      path: /jobmanager/metrics\n      operations:\n      - name: getjobmanagermetrics\n        method: GET\n        description: JobManager metrics\n        inputParameters:\n        - name: get\n          in: query\n          type: string\n          description: Comma-separated metric names.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobmanager-thread-dump\n      path: /jobmanager/thread-dump\n      operations:\n      - name: getjobmanagerthreaddump\n        method: GET\n        description: JobManager thread dump\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n     \
  \ path: /jobs\n      operations:\n      - name: listjobs\n        method: GET\n        description: List jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-overview\n      path: /jobs/overview\n      operations:\n      - name: getjobsoverview\n        method: GET\n        description: Jobs overview\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-metrics\n      path: /jobs/metrics\n      operations:\n      - name: getjobsmetrics\n        method: GET\n        description: Aggregated job metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobid\n      path: /jobs/{jobid}\n      operations:\n      - name: getjob\n        method: GET\n        description: Get job details\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminatejob\n        method: PATCH\n        description: Cancel or stop a job\n        inputParameters:\n        - name: mode\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobid-config\n      path: /jobs/{jobid}/config\n      operations:\n      - name: getjobconfig\n        method: GET\n        description: Job configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobid-exceptions\n      path: /jobs/{jobid}/exceptions\n      operations:\n      - name: getjobexceptions\n        method: GET\n        description: Job exception history\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: jobs-jobid-accumulators\n      path: /jobs/{jobid}/accumulators\n      operations:\n      - name: getjobaccumulators\n        method: GET\n        description: Job accumulators\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobid-checkpoints\n      path: /jobs/{jobid}/checkpoints\n      operations:\n      - name: getjobcheckpoints\n        method: GET\n        description: Checkpoint statistics for a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: triggercheckpoint\n        method: POST\n        description: Trigger a checkpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobid-checkpoints-config\n      path: /jobs/{jobid}/checkpoints/config\n      operations:\n\
  \      - name: getcheckpointconfig\n        method: GET\n        description: Checkpoint configuration for a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobid-checkpoints-details-checkpointid\n      path: /jobs/{jobid}/checkpoints/details/{checkpointid}\n      operations:\n      - name: getcheckpointdetails\n        method: GET\n        description: Checkpoint details\n        inputParameters:\n        - name: checkpointid\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jars\n      path: /jars\n      operations:\n      - name: listjars\n        method: GET\n        description: List uploaded JARs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: jars-upload\n      path: /jars/upload\n      operations:\n      - name: uploadjar\n        method: POST\n        description: Upload a JAR\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jars-jarid\n      path: /jars/{jarid}\n      operations:\n      - name: deletejar\n        method: DELETE\n        description: Delete a JAR\n        inputParameters:\n        - name: jarid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jars-jarid-plan\n      path: /jars/{jarid}/plan\n      operations:\n      - name: getjarplan\n        method: GET\n        description: Plan for a JAR\n        inputParameters:\n        - name: jarid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jars-jarid-run\n      path: /jars/{jarid}/run\n      operations:\n      - name: runjar\n        method: POST\n        description: Run a job from a JAR\n        inputParameters:\n        - name: jarid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: taskmanagers\n      path: /taskmanagers\n      operations:\n      - name: listtaskmanagers\n        method: GET\n        description: List TaskManagers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: taskmanagers-taskmanagerid-metrics\n      path: /taskmanagers/{taskmanagerid}/metrics\n      operations:\n      - name: gettaskmanagermetrics\n        method: GET\n        description: TaskManager\
  \ metrics\n        inputParameters:\n        - name: taskmanagerid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: taskmanagers-taskmanagerid-logs\n      path: /taskmanagers/{taskmanagerid}/logs\n      operations:\n      - name: listtaskmanagerlogs\n        method: GET\n        description: List TaskManager logs\n        inputParameters:\n        - name: taskmanagerid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets\n      path: /datasets\n      operations:\n      - name: listdatasets\n        method: GET\n        description: List cluster datasets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: datasets-datasetid\n      path: /datasets/{datasetid}\n      operations:\n      - name: deletedataset\n        method: DELETE\n        description: Delete a cluster dataset\n        inputParameters:\n        - name: datasetid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: flink-rest\n    description: REST adapter for Apache Flink REST API.\n    resources:\n    - path: /cluster\n      name: shutdowncluster\n      operations:\n      - method: DELETE\n        name: shutdowncluster\n        description: Shut down the cluster\n        call: flink.shutdowncluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /config\n      name: getwebuiconfig\n      operations:\n      - method: GET\n        name: getwebuiconfig\n  \
  \      description: Web UI configuration\n        call: flink.getwebuiconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobmanager/config\n      name: getjobmanagerconfig\n      operations:\n      - method: GET\n        name: getjobmanagerconfig\n        description: Cluster configuration\n        call: flink.getjobmanagerconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobmanager/environment\n      name: getjobmanagerenvironment\n      operations:\n      - method: GET\n        name: getjobmanagerenvironment\n        description: JobManager environment\n        call: flink.getjobmanagerenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobmanager/logs\n      name: listjobmanagerlogs\n      operations:\n      - method: GET\n        name: listjobmanagerlogs\n        description: List JobManager log files\n        call: flink.listjobmanagerlogs\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobmanager/metrics\n      name: getjobmanagermetrics\n      operations:\n      - method: GET\n        name: getjobmanagermetrics\n        description: JobManager metrics\n        call: flink.getjobmanagermetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobmanager/thread-dump\n      name: getjobmanagerthreaddump\n      operations:\n      - method: GET\n        name: getjobmanagerthreaddump\n        description: JobManager thread dump\n        call: flink.getjobmanagerthreaddump\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: List jobs\n        call: flink.listjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/overview\n      name: getjobsoverview\n      operations:\n\
  \      - method: GET\n        name: getjobsoverview\n        description: Jobs overview\n        call: flink.getjobsoverview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/metrics\n      name: getjobsmetrics\n      operations:\n      - method: GET\n        name: getjobsmetrics\n        description: Aggregated job metrics\n        call: flink.getjobsmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobid}\n      name: getjob\n      operations:\n      - method: GET\n        name: getjob\n        description: Get job details\n        call: flink.getjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobid}\n      name: terminatejob\n      operations:\n      - method: PATCH\n        name: terminatejob\n        description: Cancel or stop a job\n        call: flink.terminatejob\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /jobs/{jobid}/config\n      name: getjobconfig\n      operations:\n      - method: GET\n        name: getjobconfig\n        description: Job configuration\n        call: flink.getjobconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobid}/exceptions\n      name: getjobexceptions\n      operations:\n      - method: GET\n        name: getjobexceptions\n        description: Job exception history\n        call: flink.getjobexceptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobid}/accumulators\n      name: getjobaccumulators\n      operations:\n      - method: GET\n        name: getjobaccumulators\n        description: Job accumulators\n        call: flink.getjobaccumulators\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobid}/checkpoints\n      name: getjobcheckpoints\n      operations:\n      - method: GET\n        name: getjobcheckpoints\n\
  \        description: Checkpoint statistics for a job\n        call: flink.getjobcheckpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobid}/checkpoints\n      name: triggercheckpoint\n      operations:\n      - method: POST\n        name: triggercheckpoint\n        description: Trigger a checkpoint\n        call: flink.triggercheckpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobid}/checkpoints/config\n      name: getcheckpointconfig\n      operations:\n      - method: GET\n        name: getcheckpointconfig\n        description: Checkpoint configuration for a job\n        call: flink.getcheckpointconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobid}/checkpoints/details/{checkpointid}\n      name: getcheckpointdetails\n      operations:\n      - method: GET\n        name: getcheckpointdetails\n        description: Checkpoint details\n\
  \        call: flink.getcheckpointdetails\n        with:\n          checkpointid: rest.checkpointid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jars\n      name: listjars\n      operations:\n      - method: GET\n        name: listjars\n        description: List uploaded JARs\n        call: flink.listjars\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jars/upload\n      name: uploadjar\n      operations:\n      - method: POST\n        name: uploadjar\n        description: Upload a JAR\n        call: flink.uploadjar\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jars/{jarid}\n      name: deletejar\n      operations:\n      - method: DELETE\n        name: deletejar\n        description: Delete a JAR\n        call: flink.deletejar\n        with:\n          jarid: rest.jarid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jars/{jarid}/plan\n\
  \      name: getjarplan\n      operations:\n      - method: GET\n        name: getjarplan\n        description: Plan for a JAR\n        call: flink.getjarplan\n        with:\n          jarid: rest.jarid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jars/{jarid}/run\n      name: runjar\n      operations:\n      - method: POST\n        name: runjar\n        description: Run a job from a JAR\n        call: flink.runjar\n        with:\n          jarid: rest.jarid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /taskmanagers\n      name: listtaskmanagers\n      operations:\n      - method: GET\n        name: listtaskmanagers\n        description: List TaskManagers\n        call: flink.listtaskmanagers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /taskmanagers/{taskmanagerid}/metrics\n      name: gettaskmanagermetrics\n      operations:\n      - method: GET\n        name:\
  \ gettaskmanagermetrics\n        description: TaskManager metrics\n        call: flink.gettaskmanagermetrics\n        with:\n          taskmanagerid: rest.taskmanagerid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /taskmanagers/{taskmanagerid}/logs\n      name: listtaskmanagerlogs\n      operations:\n      - method: GET\n        name: listtaskmanagerlogs\n        description: List TaskManager logs\n        call: flink.listtaskmanagerlogs\n        with:\n          taskmanagerid: rest.taskmanagerid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasets\n      name: listdatasets\n      operations:\n      - method: GET\n        name: listdatasets\n        description: List cluster datasets\n        call: flink.listdatasets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasets/{datasetid}\n      name: deletedataset\n      operations:\n      - method: DELETE\n      \
  \  name: deletedataset\n        description: Delete a cluster dataset\n        call: flink.deletedataset\n        with:\n          datasetid: rest.datasetid\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: flink-mcp\n    transport: http\n    description: MCP adapter for Apache Flink REST API for AI agent use.\n    tools:\n    - name: shutdowncluster\n      description: Shut down the cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: flink.shutdowncluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwebuiconfig\n      description: Web UI configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getwebuiconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobmanagerconfig\n      description: Cluster configuration\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjobmanagerconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobmanagerenvironment\n      description: JobManager environment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjobmanagerenvironment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobmanagerlogs\n      description: List JobManager log files\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.listjobmanagerlogs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobmanagermetrics\n      description: JobManager metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjobmanagermetrics\n      with:\n        get: tools.get\n\
  \      inputParameters:\n      - name: get\n        type: string\n        description: Comma-separated metric names.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobmanagerthreaddump\n      description: JobManager thread dump\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjobmanagerthreaddump\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobs\n      description: List jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.listjobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobsoverview\n      description: Jobs overview\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjobsoverview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobsmetrics\n    \
  \  description: Aggregated job metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjobsmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjob\n      description: Get job details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminatejob\n      description: Cancel or stop a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flink.terminatejob\n      with:\n        mode: tools.mode\n      inputParameters:\n      - name: mode\n        type: string\n        description: mode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobconfig\n      description: Job configuration\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: flink.getjobconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobexceptions\n      description: Job exception history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjobexceptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobaccumulators\n      description: Job accumulators\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjobaccumulators\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobcheckpoints\n      description: Checkpoint statistics for a job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getjobcheckpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: triggercheckpoint\n      description: Trigger\
  \ a checkpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flink.triggercheckpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcheckpointconfig\n      description: Checkpoint configuration for a job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getcheckpointconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcheckpointdetails\n      description: Checkpoint details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.getcheckpointdetails\n      with:\n        checkpointid: tools.checkpointid\n      inputParameters:\n      - name: checkpointid\n        type: integer\n        description: checkpointid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjars\n      description:\
  \ List uploaded JARs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.listjars\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadjar\n      description: Upload a JAR\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flink.uploadjar\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletejar\n      description: Delete a JAR\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: flink.deletejar\n      with:\n        jarid: tools.jarid\n      inputParameters:\n      - name: jarid\n        type: string\n        description: jarid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjarplan\n      description: Plan for a JAR\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: flink.getjarplan\n      with:\n        jarid: tools.jarid\n      inputParameters:\n      - name: jarid\n        type: string\n        description: jarid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runjar\n      description: Run a job from a JAR\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flink.runjar\n      with:\n        jarid: tools.jarid\n      inputParameters:\n      - name: jarid\n        type: string\n        description: jarid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtaskmanagers\n      description: List TaskManagers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.listtaskmanagers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettaskmanagermetrics\n      description: TaskManager\
  \ metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.gettaskmanagermetrics\n      with:\n        taskmanagerid: tools.taskmanagerid\n      inputParameters:\n      - name: taskmanagerid\n        type: string\n        description: taskmanagerid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtaskmanagerlogs\n      description: List TaskManager logs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flink.listtaskmanagerlogs\n      with:\n        taskmanagerid: tools.taskmanagerid\n      inputParameters:\n      - name: taskmanagerid\n        type: string\n        description: taskmanagerid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatasets\n      description: List cluster datasets\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: flink.listdatasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedataset\n      description: Delete a cluster dataset\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: flink.deletedataset\n      with:\n        datasetid: tools.datasetid\n      inputParameters:\n      - name: datasetid\n        type: string\n        description: datasetid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/flink/refs/heads/main/capabilities/flink-capability.yaml
tags:
- Flink
- API
tools:
- description: Shut down the cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: shutdowncluster
- description: Web UI configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebuiconfig
- description: Cluster configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobmanagerconfig
- description: JobManager environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobmanagerenvironment
- description: List JobManager log files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobmanagerlogs
- description: JobManager metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobmanagermetrics
- description: JobManager thread dump
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobmanagerthreaddump
- description: List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Jobs overview
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobsoverview
- description: Aggregated job metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobsmetrics
- description: Get job details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: Cancel or stop a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: terminatejob
- description: Job configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobconfig
- description: Job exception history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobexceptions
- description: Job accumulators
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobaccumulators
- description: Checkpoint statistics for a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobcheckpoints
- description: Trigger a checkpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: triggercheckpoint
- description: Checkpoint configuration for a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcheckpointconfig
- description: Checkpoint details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcheckpointdetails
- description: List uploaded JARs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjars
- description: Upload a JAR
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadjar
- description: Delete a JAR
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejar
- description: Plan for a JAR
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjarplan
- description: Run a job from a JAR
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runjar
- description: List TaskManagers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtaskmanagers
- description: TaskManager metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettaskmanagermetrics
- description: List TaskManager logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtaskmanagerlogs
- description: List cluster datasets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatasets
- description: Delete a cluster dataset
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedataset
---
