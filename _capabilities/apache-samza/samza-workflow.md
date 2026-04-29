---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Samza Workflow
operations: []
personas: []
provider_name: Apache Samza
provider_slug: apache-samza
search_terms:
- stream processing
- lifecycle management of samza stream processing jobs
- engineer building and operating stream processing pipelines
- apache
- real-time stream processing on distributed infrastructure
- engineer managing yarn/samza infrastructure
- open source
- hadoop
- streaming
- big data
- kafka
slug: samza-workflow
source_yaml: "name: Apache Samza Stream Processing Workflow\ndescription: Workflow capability for managing and monitoring Samza stream processing jobs.\nversion: 1.0.0-alpha1\napis:\n  - name: Apache Samza REST API\n    url: https://raw.githubusercontent.com/api-evangelist/apache-samza/refs/heads/main/apis.yml\nshared:\n  - url: capabilities/shared/samza-api.yaml\nworkflow:\n  name: samza-workflow\n  description: Manage Samza stream processing jobs and monitor task health.\n  steps:\n    - name: list-jobs\n      description: List stream processing jobs\n      api: Apache Samza REST API\n      operation: listJobs\n    - name: start-job\n      description: Start a stream processing job\n      api: Apache Samza REST API\n      operation: startJob\n    - name: list-tasks\n      description: Monitor job tasks\n      api: Apache Samza REST API\n      operation: listTasks\n    - name: get-checkpoints\n      description: Review job checkpoints\n      api: Apache Samza REST API\n      operation:\
  \ getCheckpoints\n    - name: stop-job\n      description: Stop a stream processing job\n      api: Apache Samza REST API\n      operation: stopJob\nexposes:\n  - type: rest\n    port: 8080\n    paths:\n      - /jobs\n      - /jobs/{jobName}/{jobId}\n      - /jobs/{jobName}/{jobId}/start\n      - /jobs/{jobName}/{jobId}/stop\n      - /jobs/{jobName}/{jobId}/tasks\n      - /jobs/{jobName}/{jobId}/checkpoints\n  - type: mcp\n    port: 9090\n    tools:\n      - name: list-jobs\n        description: List Samza jobs\n        operation: listJobs\n      - name: get-job\n        description: Get job details\n        operation: getJob\n      - name: start-job\n        description: Start a job\n        operation: startJob\n      - name: stop-job\n        description: Stop a job\n        operation: stopJob\n      - name: list-tasks\n        description: List job tasks\n        operation: listTasks\n      - name: get-checkpoints\n        description: Get job checkpoints\n        operation: getCheckpoints\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-samza/refs/heads/main/capabilities/samza-workflow.yaml
tags: []
tools: []
---
