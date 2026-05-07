---
categories: []
consumed_apis: []
description: Spring Boot Actuator endpoints exposed by Spring Batch 5.1 applications for monitoring and managing batch jobs. Provides health checks, metrics, job execution status, and step execution details via the Spring Boot Actuator infrastructure. These endpoints are available when spring-boot-actuator is on the classpath alongside spring-batch-core.
layout: capability
name: Spring Batch 5.1 Actuator API
operations:
- description: Get Application Health
  method: GET
  name: gethealth
  path: /health
- description: Get Batch Health
  method: GET
  name: getbatchhealth
  path: /health/batch
- description: List Available Metrics
  method: GET
  name: listmetrics
  path: /metrics
- description: Get Metric Value
  method: GET
  name: getmetric
  path: /metrics/{metricName}
- description: List Batch Jobs
  method: GET
  name: listbatchjobs
  path: /batch/jobs
- description: Get Batch Job Details
  method: GET
  name: getbatchjob
  path: /batch/jobs/{jobName}
- description: List Job Executions
  method: GET
  name: listjobexecutions
  path: /batch/jobs/{jobName}/executions
- description: List Job Instances
  method: GET
  name: listjobinstances
  path: /batch/jobs/{jobName}/instances
personas: []
provider_name: Spring Batch
provider_slug: spring-batch
search_terms:
- list batch jobs
- getbatchjob
- api
- batch
- java
- list available metrics
- job scheduling
- list job instances
- data processing
- listjobexecutions
- listjobinstances
- spring
- enterprise
- gethealth
- getmetric
- get metric value
- get application health
- listmetrics
- list job executions
- listbatchjobs
- etl
- getbatchhealth
- get batch job details
- spring framework
- get batch health
- batch processing
slug: spring-batch-capability
source_filename: spring-batch-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Batch 5.1 Actuator API\n  description: Spring Boot Actuator endpoints exposed by Spring Batch 5.1 applications for monitoring and managing batch jobs.\n    Provides health checks, metrics, job execution status, and step execution details via the Spring Boot Actuator infrastructure.\n    These endpoints are available when spring-boot-actuator is on the classpath alongside spring-batch-core.\n  tags:\n  - Spring\n  - Batch\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: spring-batch\n    baseUri: http://localhost:8080/actuator\n    description: Spring Batch 5.1 Actuator API HTTP API.\n    resources:\n    - name: health\n      path: /health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Get Application Health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: health-batch\n      path: /health/batch\n      operations:\n      - name: getbatchhealth\n        method: GET\n        description: Get Batch Health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      operations:\n      - name: listmetrics\n        method: GET\n        description: List Available Metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-metricname\n      path: /metrics/{metricName}\n      operations:\n      - name: getmetric\n        method: GET\n        description: Get Metric Value\n        inputParameters:\n        - name: metricName\n          in: path\n          type: string\n          required: true\n          description: Name of the metric (e.g., spring.batch.job.duration, spring.batch.step.duration, spring.batch.chunk.size)\n\
  \        - name: tag\n          in: query\n          type: string\n          description: Tag filter in the form name:value (can be repeated)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-jobs\n      path: /batch/jobs\n      operations:\n      - name: listbatchjobs\n        method: GET\n        description: List Batch Jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-jobs-jobname\n      path: /batch/jobs/{jobName}\n      operations:\n      - name: getbatchjob\n        method: GET\n        description: Get Batch Job Details\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Name of the batch job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: batch-jobs-jobname-executions\n      path: /batch/jobs/{jobName}/executions\n      operations:\n      - name: listjobexecutions\n        method: GET\n        description: List Job Executions\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Name of the batch job\n        - name: page\n          in: query\n          type: integer\n          description: Page number (zero-based)\n        - name: size\n          in: query\n          type: integer\n          description: Number of executions per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-jobs-jobname-instances\n      path: /batch/jobs/{jobName}/instances\n      operations:\n      - name: listjobinstances\n        method: GET\n        description: List Job Instances\n        inputParameters:\n        - name:\
  \ jobName\n          in: path\n          type: string\n          required: true\n          description: Name of the batch job\n        - name: page\n          in: query\n          type: integer\n        - name: size\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: spring-batch-rest\n    description: REST adapter for Spring Batch 5.1 Actuator API.\n    resources:\n    - path: /health\n      name: gethealth\n      operations:\n      - method: GET\n        name: gethealth\n        description: Get Application Health\n        call: spring-batch.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health/batch\n      name: getbatchhealth\n      operations:\n      - method: GET\n        name: getbatchhealth\n        description: Get Batch Health\n        call: spring-batch.getbatchhealth\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics\n      name: listmetrics\n      operations:\n      - method: GET\n        name: listmetrics\n        description: List Available Metrics\n        call: spring-batch.listmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/{metricName}\n      name: getmetric\n      operations:\n      - method: GET\n        name: getmetric\n        description: Get Metric Value\n        call: spring-batch.getmetric\n        with:\n          metricName: rest.metricName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch/jobs\n      name: listbatchjobs\n      operations:\n      - method: GET\n        name: listbatchjobs\n        description: List Batch Jobs\n        call: spring-batch.listbatchjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch/jobs/{jobName}\n      name: getbatchjob\n\
  \      operations:\n      - method: GET\n        name: getbatchjob\n        description: Get Batch Job Details\n        call: spring-batch.getbatchjob\n        with:\n          jobName: rest.jobName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch/jobs/{jobName}/executions\n      name: listjobexecutions\n      operations:\n      - method: GET\n        name: listjobexecutions\n        description: List Job Executions\n        call: spring-batch.listjobexecutions\n        with:\n          jobName: rest.jobName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch/jobs/{jobName}/instances\n      name: listjobinstances\n      operations:\n      - method: GET\n        name: listjobinstances\n        description: List Job Instances\n        call: spring-batch.listjobinstances\n        with:\n          jobName: rest.jobName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9090\n    namespace: spring-batch-mcp\n    transport: http\n    description: MCP adapter for Spring Batch 5.1 Actuator API for AI agent use.\n    tools:\n    - name: gethealth\n      description: Get Application Health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring-batch.gethealth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbatchhealth\n      description: Get Batch Health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring-batch.getbatchhealth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmetrics\n      description: List Available Metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring-batch.listmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetric\n      description:\
  \ Get Metric Value\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring-batch.getmetric\n      with:\n        metricName: tools.metricName\n        tag: tools.tag\n      inputParameters:\n      - name: metricName\n        type: string\n        description: Name of the metric (e.g., spring.batch.job.duration, spring.batch.step.duration, spring.batch.chunk.size)\n        required: true\n      - name: tag\n        type: string\n        description: Tag filter in the form name:value (can be repeated)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbatchjobs\n      description: List Batch Jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring-batch.listbatchjobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbatchjob\n      description: Get Batch Job Details\n      hints:\n        readOnly: true\n \
  \       destructive: false\n        idempotent: true\n      call: spring-batch.getbatchjob\n      with:\n        jobName: tools.jobName\n      inputParameters:\n      - name: jobName\n        type: string\n        description: Name of the batch job\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobexecutions\n      description: List Job Executions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring-batch.listjobexecutions\n      with:\n        jobName: tools.jobName\n        page: tools.page\n        size: tools.size\n      inputParameters:\n      - name: jobName\n        type: string\n        description: Name of the batch job\n        required: true\n      - name: page\n        type: integer\n        description: Page number (zero-based)\n      - name: size\n        type: integer\n        description: Number of executions per page\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: listjobinstances\n      description: List Job Instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring-batch.listjobinstances\n      with:\n        jobName: tools.jobName\n        page: tools.page\n        size: tools.size\n      inputParameters:\n      - name: jobName\n        type: string\n        description: Name of the batch job\n        required: true\n      - name: page\n        type: integer\n        description: page\n      - name: size\n        type: integer\n        description: size\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-batch/refs/heads/main/capabilities/spring-batch-capability.yaml
tags:
- Spring
- Batch
- API
tools:
- description: Get Application Health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
- description: Get Batch Health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbatchhealth
- description: List Available Metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmetrics
- description: Get Metric Value
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetric
- description: List Batch Jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbatchjobs
- description: Get Batch Job Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbatchjob
- description: List Job Executions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobexecutions
- description: List Job Instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobinstances
---
