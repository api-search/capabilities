---
categories: []
consumed_apis: []
description: The Cloud Dataproc API manages Hadoop-based clusters and jobs on Google Cloud Platform. It provides programmatic access to create and manage clusters, submit and monitor Apache Spark, Apache Hadoop, Apache Hive, and Apache Pig jobs, and manage workflow templates for orchestrating multi-step data processing pipelines.
layout: capability
name: Google Cloud Dataproc API
operations:
- description: Google Cloud Dataproc List clusters
  method: GET
  name: listclusters
  path: /projects/{project}/regions/{region}/clusters
- description: Google Cloud Dataproc Create a cluster
  method: POST
  name: createcluster
  path: /projects/{project}/regions/{region}/clusters
- description: Google Cloud Dataproc Get a cluster
  method: GET
  name: getcluster
  path: /projects/{project}/regions/{region}/clusters/{cluster}
- description: Google Cloud Dataproc Update a cluster
  method: PATCH
  name: updatecluster
  path: /projects/{project}/regions/{region}/clusters/{cluster}
- description: Google Cloud Dataproc Delete a cluster
  method: DELETE
  name: deletecluster
  path: /projects/{project}/regions/{region}/clusters/{cluster}
- description: Google Cloud Dataproc List jobs
  method: GET
  name: listjobs
  path: /projects/{project}/regions/{region}/jobs
- description: Google Cloud Dataproc Submit a job
  method: POST
  name: submitjob
  path: /projects/{project}/regions/{region}/jobs:submit
- description: Google Cloud Dataproc Get a job
  method: GET
  name: getjob
  path: /projects/{project}/regions/{region}/jobs/{jobId}
- description: Google Cloud Dataproc Delete a job
  method: DELETE
  name: deletejob
  path: /projects/{project}/regions/{region}/jobs/{jobId}
- description: Google Cloud Dataproc Cancel a job
  method: POST
  name: canceljob
  path: /projects/{project}/regions/{region}/jobs/{jobId}:cancel
- description: Google Cloud Dataproc List workflow templates
  method: GET
  name: listworkflowtemplates
  path: /projects/{project}/regions/{region}/workflowTemplates
- description: Google Cloud Dataproc Create a workflow template
  method: POST
  name: createworkflowtemplate
  path: /projects/{project}/regions/{region}/workflowTemplates
personas: []
provider_name: Google Cloud Dataproc
provider_slug: google-cloud-dataproc
search_terms:
- google cloud dataproc create a workflow template
- deletecluster
- google cloud dataproc list workflow templates
- hadoop
- getcluster
- api
- createcluster
- google cloud dataproc update a cluster
- listjobs
- canceljob
- google
- google cloud dataproc delete a cluster
- createworkflowtemplate
- listclusters
- google cloud dataproc get a cluster
- dataproc
- updatecluster
- google cloud dataproc submit a job
- submitjob
- google cloud dataproc list clusters
- big data
- google cloud dataproc list jobs
- google cloud dataproc get a job
- google cloud dataproc delete a job
- data processing
- google cloud dataproc cancel a job
- google cloud dataproc create a cluster
- spark
- cloud
- deletejob
- getjob
- listworkflowtemplates
- google cloud
slug: google-cloud-dataproc-capability
source_filename: google-cloud-dataproc-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Dataproc API\n  description: The Cloud Dataproc API manages Hadoop-based clusters and jobs on Google Cloud Platform. It provides programmatic\n    access to create and manage clusters, submit and monitor Apache Spark, Apache Hadoop, Apache Hive, and Apache Pig jobs,\n    and manage workflow templates for orchestrating multi-step data processing pipelines.\n  tags:\n  - Google\n  - Cloud\n  - Dataproc\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-dataproc\n    baseUri: https://dataproc.googleapis.com/v1\n    description: Google Cloud Dataproc API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_DATAPROC_TOKEN}}'\n    resources:\n    - name: projects-project-regions-region-clusters\n      path: /projects/{project}/regions/{region}/clusters\n      operations:\n      - name: listclusters\n        method: GET\n \
  \       description: Google Cloud Dataproc List clusters\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcluster\n        method: POST\n        description: Google Cloud Dataproc Create a cluster\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: projects-project-regions-region-clusters-cluster\n      path: /projects/{project}/regions/{region}/clusters/{cluster}\n      operations:\n      - name: getcluster\n        method: GET\n        description: Google Cloud Dataproc Get a cluster\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: cluster\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecluster\n        method: PATCH\n        description: Google Cloud Dataproc Update a cluster\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n    \
  \    - name: region\n          in: path\n          type: string\n          required: true\n        - name: cluster\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecluster\n        method: DELETE\n        description: Google Cloud Dataproc Delete a cluster\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: cluster\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-regions-region-jobs\n\
  \      path: /projects/{project}/regions/{region}/jobs\n      operations:\n      - name: listjobs\n        method: GET\n        description: Google Cloud Dataproc List jobs\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: clusterName\n          in: query\n          type: string\n        - name: jobStateMatcher\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-regions-region-jobs-submit\n      path: /projects/{project}/regions/{region}/jobs:submit\n      operations:\n      - name: submitjob\n        method: POST\n  \
  \      description: Google Cloud Dataproc Submit a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-regions-region-jobs-jobid\n      path: /projects/{project}/regions/{region}/jobs/{jobId}\n      operations:\n      - name: getjob\n        method: GET\n        description: Google Cloud Dataproc Get a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletejob\n        method: DELETE\n        description: Google Cloud Dataproc Delete a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-regions-region-jobs-jobid-cance\n      path: /projects/{project}/regions/{region}/jobs/{jobId}:cancel\n      operations:\n      - name: canceljob\n        method: POST\n        description: Google Cloud Dataproc Cancel a job\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name:\
  \ region\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-regions-region-workflowtemplate\n      path: /projects/{project}/regions/{region}/workflowTemplates\n      operations:\n      - name: listworkflowtemplates\n        method: GET\n        description: Google Cloud Dataproc List workflow templates\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: createworkflowtemplate\n        method: POST\n        description: Google Cloud Dataproc Create a workflow template\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-dataproc-rest\n    description: REST adapter for Google Cloud Dataproc API.\n    resources:\n    - path: /projects/{project}/regions/{region}/clusters\n      name: listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: Google Cloud Dataproc List clusters\n        call: google-cloud-dataproc.listclusters\n        with:\n          project: rest.project\n\
  \          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/clusters\n      name: createcluster\n      operations:\n      - method: POST\n        name: createcluster\n        description: Google Cloud Dataproc Create a cluster\n        call: google-cloud-dataproc.createcluster\n        with:\n          project: rest.project\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/clusters/{cluster}\n      name: getcluster\n      operations:\n      - method: GET\n        name: getcluster\n        description: Google Cloud Dataproc Get a cluster\n        call: google-cloud-dataproc.getcluster\n        with:\n          project: rest.project\n          region: rest.region\n          cluster: rest.cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/clusters/{cluster}\n\
  \      name: updatecluster\n      operations:\n      - method: PATCH\n        name: updatecluster\n        description: Google Cloud Dataproc Update a cluster\n        call: google-cloud-dataproc.updatecluster\n        with:\n          project: rest.project\n          region: rest.region\n          cluster: rest.cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/clusters/{cluster}\n      name: deletecluster\n      operations:\n      - method: DELETE\n        name: deletecluster\n        description: Google Cloud Dataproc Delete a cluster\n        call: google-cloud-dataproc.deletecluster\n        with:\n          project: rest.project\n          region: rest.region\n          cluster: rest.cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/jobs\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n\
  \        description: Google Cloud Dataproc List jobs\n        call: google-cloud-dataproc.listjobs\n        with:\n          project: rest.project\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/jobs:submit\n      name: submitjob\n      operations:\n      - method: POST\n        name: submitjob\n        description: Google Cloud Dataproc Submit a job\n        call: google-cloud-dataproc.submitjob\n        with:\n          project: rest.project\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/jobs/{jobId}\n      name: getjob\n      operations:\n      - method: GET\n        name: getjob\n        description: Google Cloud Dataproc Get a job\n        call: google-cloud-dataproc.getjob\n        with:\n          project: rest.project\n          region: rest.region\n          jobId:\
  \ rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/jobs/{jobId}\n      name: deletejob\n      operations:\n      - method: DELETE\n        name: deletejob\n        description: Google Cloud Dataproc Delete a job\n        call: google-cloud-dataproc.deletejob\n        with:\n          project: rest.project\n          region: rest.region\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/jobs/{jobId}:cancel\n      name: canceljob\n      operations:\n      - method: POST\n        name: canceljob\n        description: Google Cloud Dataproc Cancel a job\n        call: google-cloud-dataproc.canceljob\n        with:\n          project: rest.project\n          region: rest.region\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/workflowTemplates\n\
  \      name: listworkflowtemplates\n      operations:\n      - method: GET\n        name: listworkflowtemplates\n        description: Google Cloud Dataproc List workflow templates\n        call: google-cloud-dataproc.listworkflowtemplates\n        with:\n          project: rest.project\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/workflowTemplates\n      name: createworkflowtemplate\n      operations:\n      - method: POST\n        name: createworkflowtemplate\n        description: Google Cloud Dataproc Create a workflow template\n        call: google-cloud-dataproc.createworkflowtemplate\n        with:\n          project: rest.project\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-dataproc-mcp\n    transport: http\n    description: MCP adapter for Google Cloud\
  \ Dataproc API for AI agent use.\n    tools:\n    - name: listclusters\n      description: Google Cloud Dataproc List clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dataproc.listclusters\n      with:\n        project: tools.project\n        region: tools.region\n        filter: tools.filter\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      - name: filter\n        type: string\n        description: filter\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcluster\n      description:\
  \ Google Cloud Dataproc Create a cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dataproc.createcluster\n      with:\n        project: tools.project\n        region: tools.region\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcluster\n      description: Google Cloud Dataproc Get a cluster\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dataproc.getcluster\n      with:\n        project: tools.project\n        region: tools.region\n        cluster: tools.cluster\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n   \
  \   - name: region\n        type: string\n        description: region\n        required: true\n      - name: cluster\n        type: string\n        description: cluster\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecluster\n      description: Google Cloud Dataproc Update a cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dataproc.updatecluster\n      with:\n        project: tools.project\n        region: tools.region\n        cluster: tools.cluster\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      - name: cluster\n        type: string\n        description: cluster\n        required: true\n      - name: updateMask\n        type: string\n\
  \        description: updateMask\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecluster\n      description: Google Cloud Dataproc Delete a cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-dataproc.deletecluster\n      with:\n        project: tools.project\n        region: tools.region\n        cluster: tools.cluster\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      - name: cluster\n        type: string\n        description: cluster\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobs\n      description: Google Cloud Dataproc List jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: google-cloud-dataproc.listjobs\n      with:\n        project: tools.project\n        region: tools.region\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        clusterName: tools.clusterName\n        jobStateMatcher: tools.jobStateMatcher\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: clusterName\n        type: string\n        description: clusterName\n      - name: jobStateMatcher\n        type: string\n        description: jobStateMatcher\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitjob\n      description: Google Cloud Dataproc Submit a job\n      hints:\n   \
  \     readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dataproc.submitjob\n      with:\n        project: tools.project\n        region: tools.region\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjob\n      description: Google Cloud Dataproc Get a job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dataproc.getjob\n      with:\n        project: tools.project\n        region: tools.region\n        jobId: tools.jobId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required:\
  \ true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletejob\n      description: Google Cloud Dataproc Delete a job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-dataproc.deletejob\n      with:\n        project: tools.project\n        region: tools.region\n        jobId: tools.jobId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: canceljob\n      description: Google Cloud Dataproc Cancel a job\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: google-cloud-dataproc.canceljob\n      with:\n        project: tools.project\n        region: tools.region\n        jobId: tools.jobId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkflowtemplates\n      description: Google Cloud Dataproc List workflow templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dataproc.listworkflowtemplates\n      with:\n        project: tools.project\n        region: tools.region\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name:\
  \ project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkflowtemplate\n      description: Google Cloud Dataproc Create a workflow template\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dataproc.createworkflowtemplate\n      with:\n        project: tools.project\n        region: tools.region\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_DATAPROC_TOKEN: GOOGLE_CLOUD_DATAPROC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-dataproc/refs/heads/main/capabilities/google-cloud-dataproc-capability.yaml
tags:
- Google
- Cloud
- Dataproc
- API
tools:
- description: Google Cloud Dataproc List clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
- description: Google Cloud Dataproc Create a cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcluster
- description: Google Cloud Dataproc Get a cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcluster
- description: Google Cloud Dataproc Update a cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecluster
- description: Google Cloud Dataproc Delete a cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecluster
- description: Google Cloud Dataproc List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Google Cloud Dataproc Submit a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitjob
- description: Google Cloud Dataproc Get a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: Google Cloud Dataproc Delete a job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejob
- description: Google Cloud Dataproc Cancel a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: canceljob
- description: Google Cloud Dataproc List workflow templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowtemplates
- description: Google Cloud Dataproc Create a workflow template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkflowtemplate
---
