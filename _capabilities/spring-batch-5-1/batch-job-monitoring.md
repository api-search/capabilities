---
categories: []
consumed_apis: []
description: Workflow capability for monitoring and observing Spring Batch 5.1 job executions. Combines Actuator health, Micrometer metrics, and job execution history into a unified monitoring interface for platform operators and batch administrators.
layout: capability
name: Spring Batch 5.1 Job Monitoring
operations:
- description: Get overall application health including batch components
  method: GET
  name: get-health
  path: /v1/health
- description: List all available batch metrics
  method: GET
  name: list-metrics
  path: /v1/metrics
- description: Get measurements for a named batch metric
  method: GET
  name: get-metric
  path: /v1/metrics/{metricName}
- description: List all registered batch jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Get details for a specific batch job
  method: GET
  name: get-job
  path: /v1/jobs/{jobName}
- description: List execution history for a batch job
  method: GET
  name: list-executions
  path: /v1/jobs/{jobName}/executions
- description: List job instances by job name
  method: GET
  name: list-instances
  path: /v1/jobs/{jobName}/instances
personas: []
provider_name: Spring Batch 5.1
provider_slug: spring-batch-5-1
search_terms:
- check batch health
- get job
- list jobs
- get current measurements for a spring batch metric such as job duration, step duration, or item counts
- java
- registered spring batch jobs
- application and batch component health status
- job execution history
- list all available spring batch micrometer metrics names
- job scheduling
- get details for a specific batch job
- spring batch
- etl
- list all available batch metrics
- monitoring
- get batch metric
- enterprise
- job instances for a specific job
- single metric measurements with tag filtering
- get overall application health including batch components
- list executions
- list instances
- list execution history for a batch job
- get job details
- list job instances for a spring batch job (each instance represents a unique set of parameters)
- micrometer metrics for batch performance tracking
- list job executions
- individual job details
- observability
- data processing
- list all registered batch jobs
- list metrics
- list batch metrics
- spring framework
- batch processing
- get measurements for a named batch metric
- list job instances
- check the health of the spring batch application and its database connection
- get configuration and last execution details for a named spring batch job
- list all registered spring batch jobs with their last execution status
- get metric
- list job instances by job name
- job management
- get health
- list execution history for a spring batch job including status, timing, and step statistics
slug: batch-job-monitoring
source_filename: batch-job-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Batch 5.1 Job Monitoring\n  description: Workflow capability for monitoring and observing Spring Batch 5.1 job executions. Combines Actuator health,\n    Micrometer metrics, and job execution history into a unified monitoring interface for platform operators and batch administrators.\n  tags:\n  - Spring Batch\n  - Batch Processing\n  - Monitoring\n  - Observability\n  - Job Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPRING_BATCH_ACTUATOR_BASE_URL: SPRING_BATCH_ACTUATOR_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: spring-batch-actuator\n    baseUri: '{{env.SPRING_BATCH_ACTUATOR_BASE_URL}}/actuator'\n    description: Spring Boot Actuator endpoints for Spring Batch 5.1 monitoring\n    resources:\n    - name: health\n      path: /health\n      description: Application and batch subsystem health checks\n      operations:\n      - name: get-health\n    \
  \    method: GET\n        description: Get overall application health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-batch-health\n        method: GET\n        description: Get Spring Batch specific health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      description: Micrometer metrics including Spring Batch job and step metrics\n      operations:\n      - name: list-metrics\n        method: GET\n        description: List all available metric names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-metric\n        method: GET\n        description: Get measurements for a specific metric by name\n        inputParameters:\n        - name: metricName\n       \
  \   in: path\n          type: string\n          required: true\n          description: Metric name (e.g., spring.batch.job.duration)\n        - name: tag\n          in: query\n          type: string\n          required: false\n          description: Tag filter in name:value format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-jobs\n      path: /batch/jobs\n      description: Batch job management and execution history\n      operations:\n      - name: list-batch-jobs\n        method: GET\n        description: List all registered Spring Batch jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-batch-job\n        method: GET\n        description: Get details for a specific batch job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required:\
  \ true\n          description: Name of the batch job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-job-executions\n        method: GET\n        description: List execution history for a specific batch job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Name of the batch job\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number (zero-based)\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Number of executions per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-job-instances\n        method: GET\n        description: List job instances for a specific\
  \ batch job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Name of the batch job\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number (zero-based)\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: batch-monitoring-api\n    description: Unified REST API for Spring Batch 5.1 job monitoring and observability.\n    resources:\n    - path: /v1/health\n      name: health\n      description: Application and batch component health status\n      operations:\n      - method: GET\n        name: get-health\n        description: Get overall application health including\
  \ batch components\n        call: spring-batch-actuator.get-health\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Micrometer metrics for batch performance tracking\n      operations:\n      - method: GET\n        name: list-metrics\n        description: List all available batch metrics\n        call: spring-batch-actuator.list-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/{metricName}\n      name: metric-detail\n      description: Single metric measurements with tag filtering\n      operations:\n      - method: GET\n        name: get-metric\n        description: Get measurements for a named batch metric\n        call: spring-batch-actuator.get-metric\n        with:\n          metricName: rest.metricName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description:\
  \ Registered Spring Batch jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List all registered batch jobs\n        call: spring-batch-actuator.list-batch-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobName}\n      name: job-detail\n      description: Individual job details\n      operations:\n      - method: GET\n        name: get-job\n        description: Get details for a specific batch job\n        call: spring-batch-actuator.get-batch-job\n        with:\n          jobName: rest.jobName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobName}/executions\n      name: job-executions\n      description: Job execution history\n      operations:\n      - method: GET\n        name: list-executions\n        description: List execution history for a batch job\n        call: spring-batch-actuator.list-job-executions\n        with:\n          jobName:\
  \ rest.jobName\n          page: rest.page\n          size: rest.size\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobName}/instances\n      name: job-instances\n      description: Job instances for a specific job\n      operations:\n      - method: GET\n        name: list-instances\n        description: List job instances by job name\n        call: spring-batch-actuator.list-job-instances\n        with:\n          jobName: rest.jobName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: batch-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted Spring Batch 5.1 job monitoring and diagnosis.\n    tools:\n    - name: check-batch-health\n      description: Check the health of the Spring Batch application and its database connection\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-batch-actuator.get-health\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-batch-metrics\n      description: List all available Spring Batch Micrometer metrics names\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-batch-actuator.list-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-batch-metric\n      description: Get current measurements for a Spring Batch metric such as job duration, step duration, or item counts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-batch-actuator.get-metric\n      with:\n        metricName: tools.metricName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List all registered Spring Batch jobs with their last execution status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-batch-actuator.list-batch-jobs\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-job-details\n      description: Get configuration and last execution details for a named Spring Batch job\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-batch-actuator.get-batch-job\n      with:\n        jobName: tools.jobName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-job-executions\n      description: List execution history for a Spring Batch job including status, timing, and step statistics\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-batch-actuator.list-job-executions\n      with:\n        jobName: tools.jobName\n        page: tools.page\n        size: tools.size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-job-instances\n      description: List job instances for a Spring Batch job (each instance represents a unique set of parameters)\n      hints:\n        readOnly: true\n      \
  \  openWorld: true\n      call: spring-batch-actuator.list-job-instances\n      with:\n        jobName: tools.jobName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-batch-5-1/refs/heads/main/capabilities/batch-job-monitoring.yaml
tags:
- Spring Batch
- Batch Processing
- Monitoring
- Observability
- Job Management
tools:
- description: Check the health of the Spring Batch application and its database connection
  hints:
    openWorld: true
    readOnly: true
  name: check-batch-health
- description: List all available Spring Batch Micrometer metrics names
  hints:
    openWorld: true
    readOnly: true
  name: list-batch-metrics
- description: Get current measurements for a Spring Batch metric such as job duration, step duration, or item counts
  hints:
    openWorld: true
    readOnly: true
  name: get-batch-metric
- description: List all registered Spring Batch jobs with their last execution status
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Get configuration and last execution details for a named Spring Batch job
  hints:
    openWorld: true
    readOnly: true
  name: get-job-details
- description: List execution history for a Spring Batch job including status, timing, and step statistics
  hints:
    openWorld: true
    readOnly: true
  name: list-job-executions
- description: List job instances for a Spring Batch job (each instance represents a unique set of parameters)
  hints:
    openWorld: true
    readOnly: true
  name: list-job-instances
---
