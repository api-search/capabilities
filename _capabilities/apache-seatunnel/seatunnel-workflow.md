---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Seatunnel Workflow
operations: []
personas: []
provider_name: Apache SeaTunnel
provider_slug: apache-seatunnel
search_terms:
- extract, transform, load pipeline processing
- batch
- elt
- data integration
- streaming
- open source
- end-to-end data synchronization from source to sink
- apache
- engineer managing seatunnel clusters
- moving and transforming data between systems
- engineer designing and operating data pipelines
- etl
slug: seatunnel-workflow
source_filename: seatunnel-workflow.yaml
source_heading: Capability Spec
source_yaml: "name: Apache SeaTunnel Data Integration Workflow\ndescription: Workflow capability for submitting and managing data integration jobs with Apache SeaTunnel.\nversion: 1.0.0-alpha1\napis:\n  - name: Apache SeaTunnel REST API\n    url: https://raw.githubusercontent.com/api-evangelist/apache-seatunnel/refs/heads/main/apis.yml\nshared:\n  - url: capabilities/shared/seatunnel-api.yaml\nworkflow:\n  name: seatunnel-workflow\n  description: Submit, monitor, and manage SeaTunnel data sync jobs across sources and sinks.\n  steps:\n    - name: get-overview\n      description: Check cluster status and capacity\n      api: Apache SeaTunnel REST API\n      operation: getOverview\n    - name: submit-job\n      description: Submit a data integration job\n      api: Apache SeaTunnel REST API\n      operation: submitJob\n    - name: get-job\n      description: Monitor job progress and metrics\n      api: Apache SeaTunnel REST API\n      operation: getJob\n    - name: stop-job\n      description:\
  \ Stop a running job\n      api: Apache SeaTunnel REST API\n      operation: stopJob\nexposes:\n  - type: rest\n    port: 5801\n    paths:\n      - /hazelcast/rest/maps/running-jobs\n      - /hazelcast/rest/maps/job/submit\n      - /hazelcast/rest/maps/job/{jobId}\n      - /hazelcast/rest/maps/job/stop\n      - /hazelcast/rest/maps/system-monitoring-information\n      - /hazelcast/rest/maps/overview\n  - type: mcp\n    port: 9090\n    tools:\n      - name: list-running-jobs\n        description: List running data sync jobs\n        operation: listRunningJobs\n      - name: submit-job\n        description: Submit a data integration job\n        operation: submitJob\n      - name: get-job\n        description: Get job status and metrics\n        operation: getJob\n      - name: stop-job\n        description: Stop a data sync job\n        operation: stopJob\n      - name: get-system-info\n        description: Get system resource information\n        operation: getSystemInfo\n      - name:\
  \ get-overview\n        description: Get cluster overview\n        operation: getOverview\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-seatunnel/refs/heads/main/capabilities/seatunnel-workflow.yaml
tags: []
tools: []
---
