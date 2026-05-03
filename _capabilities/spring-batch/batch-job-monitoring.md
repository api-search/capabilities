---
categories: []
consumed_apis:
- spring-batch-actuator
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
provider_name: Spring Batch
provider_slug: spring-batch
search_terms:
- batch processing
- java
- job management
- list job instances by job name
- monitoring
- list all registered batch jobs
- get current measurements for a spring batch metric such as job duration, step duration, or item counts
- get configuration and last execution details for a named spring batch job
- list all registered spring batch jobs with their last execution status
- list job executions
- list job instances for a spring batch job (each instance represents a unique set of parameters)
- list metrics
- list execution history for a batch job
- data processing
- list batch metrics
- application and batch component health status
- list jobs
- single metric measurements with tag filtering
- list all available batch metrics
- registered spring batch jobs
- etl
- get overall application health including batch components
- spring batch
- get measurements for a named batch metric
- enterprise
- list all available spring batch micrometer metrics names
- job scheduling
- get metric
- check the health of the spring batch application and its database connection
- micrometer metrics for batch performance tracking
- list executions
- list job instances
- get job details
- spring framework
- get batch metric
- observability
- check batch health
- job execution history
- job instances for a specific job
- list instances
- get job
- individual job details
- list execution history for a spring batch job including status, timing, and step statistics
- get details for a specific batch job
- get health
slug: batch-job-monitoring
source_filename: batch-job-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spring Batch 5.1 Job Monitoring\"\n  description: >-\n    Workflow capability for monitoring and observing Spring Batch 5.1 job\n    executions. Combines Actuator health, Micrometer metrics, and job execution\n    history into a unified monitoring interface for platform operators and\n    batch administrators.\n  tags:\n    - Spring Batch\n    - Batch Processing\n    - Monitoring\n    - Observability\n    - Job Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPRING_BATCH_ACTUATOR_BASE_URL: SPRING_BATCH_ACTUATOR_BASE_URL\n\ncapability:\n  consumes:\n    - import: spring-batch-actuator\n      location: ./shared/spring-batch-51-actuator.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: batch-monitoring-api\n      description: \"Unified REST API for Spring Batch 5.1 job monitoring and observability.\"\n      resources:\n        - path: /v1/health\n\
  \          name: health\n          description: \"Application and batch component health status\"\n          operations:\n            - method: GET\n              name: get-health\n              description: \"Get overall application health including batch components\"\n              call: \"spring-batch-actuator.get-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metrics\n          name: metrics\n          description: \"Micrometer metrics for batch performance tracking\"\n          operations:\n            - method: GET\n              name: list-metrics\n              description: \"List all available batch metrics\"\n              call: \"spring-batch-actuator.list-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metrics/{metricName}\n          name: metric-detail\n          description: \"Single metric measurements with\
  \ tag filtering\"\n          operations:\n            - method: GET\n              name: get-metric\n              description: \"Get measurements for a named batch metric\"\n              call: \"spring-batch-actuator.get-metric\"\n              with:\n                metricName: \"rest.metricName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs\n          name: jobs\n          description: \"Registered Spring Batch jobs\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List all registered batch jobs\"\n              call: \"spring-batch-actuator.list-batch-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{jobName}\n          name: job-detail\n          description: \"Individual job details\"\n          operations:\n            - method: GET\n              name:\
  \ get-job\n              description: \"Get details for a specific batch job\"\n              call: \"spring-batch-actuator.get-batch-job\"\n              with:\n                jobName: \"rest.jobName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{jobName}/executions\n          name: job-executions\n          description: \"Job execution history\"\n          operations:\n            - method: GET\n              name: list-executions\n              description: \"List execution history for a batch job\"\n              call: \"spring-batch-actuator.list-job-executions\"\n              with:\n                jobName: \"rest.jobName\"\n                page: \"rest.page\"\n                size: \"rest.size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{jobName}/instances\n          name: job-instances\n          description:\
  \ \"Job instances for a specific job\"\n          operations:\n            - method: GET\n              name: list-instances\n              description: \"List job instances by job name\"\n              call: \"spring-batch-actuator.list-job-instances\"\n              with:\n                jobName: \"rest.jobName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: batch-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Spring Batch 5.1 job monitoring and diagnosis.\"\n      tools:\n        - name: check-batch-health\n          description: \"Check the health of the Spring Batch application and its database connection\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-batch-actuator.get-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        -\
  \ name: list-batch-metrics\n          description: \"List all available Spring Batch Micrometer metrics names\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-batch-actuator.list-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-batch-metric\n          description: \"Get current measurements for a Spring Batch metric such as job duration, step duration, or item counts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-batch-actuator.get-metric\"\n          with:\n            metricName: \"tools.metricName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-jobs\n          description: \"List all registered Spring Batch jobs with their last execution status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"\
  spring-batch-actuator.list-batch-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-job-details\n          description: \"Get configuration and last execution details for a named Spring Batch job\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-batch-actuator.get-batch-job\"\n          with:\n            jobName: \"tools.jobName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-job-executions\n          description: \"List execution history for a Spring Batch job including status, timing, and step statistics\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-batch-actuator.list-job-executions\"\n          with:\n            jobName: \"tools.jobName\"\n            page: \"tools.page\"\n            size: \"tools.size\"\n          outputParameters:\n     \
  \       - type: object\n              mapping: \"$.\"\n\n        - name: list-job-instances\n          description: \"List job instances for a Spring Batch job (each instance represents a unique set of parameters)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-batch-actuator.list-job-instances\"\n          with:\n            jobName: \"tools.jobName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-batch/refs/heads/main/capabilities/batch-job-monitoring.yaml
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
