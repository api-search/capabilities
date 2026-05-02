---
api_specs:
- filename: apache-nutch-openapi.yaml
  format: yaml
  label: nutch
  slug: nutch
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/apache-nutch/refs/heads/main/openapi/apache-nutch-openapi.yaml
categories:
- data-engineering
consumed_apis:
- nutch
description: Workflow capability for managing end-to-end web crawl pipelines with Apache Nutch. Covers job lifecycle management, configuration control, seed list management, and CrawlDB querying for web crawl engineers and data engineers.
layout: capability
name: Apache Nutch Crawl Management
operations:
- description: Get Apache Nutch server status.
  method: GET
  name: get-status
  path: /v1/admin/status
- description: List all available configurations.
  method: GET
  name: list-configs
  path: /v1/configs
- description: Create a new crawl configuration.
  method: POST
  name: create-config
  path: /v1/configs
- description: Get all properties for a configuration.
  method: GET
  name: get-config
  path: /v1/configs/{configId}
- description: Delete a configuration.
  method: DELETE
  name: delete-config
  path: /v1/configs/{configId}
- description: List all crawl jobs.
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Create and start a crawl job.
  method: POST
  name: create-job
  path: /v1/jobs
- description: Get job status and info.
  method: GET
  name: get-job
  path: /v1/jobs/{id}
- description: Stop a running crawl job.
  method: POST
  name: stop-job
  path: /v1/jobs/{id}/stop
- description: List all seed URL lists.
  method: GET
  name: list-seeds
  path: /v1/seeds
- description: Create a new seed URL list.
  method: POST
  name: create-seed
  path: /v1/seeds
- description: Query the CrawlDB for stats or URL lookups.
  method: POST
  name: query-crawldb
  path: /v1/db/crawldb
- description: Query the FetchDB for node information.
  method: POST
  name: query-fetchdb
  path: /v1/db/fetchdb
personas: []
provider_name: Apache Nutch
provider_slug: apache-nutch
search_terms:
- list all known nutch configuration identifiers.
- delete a configuration.
- create a new crawl configuration.
- list all crawl jobs.
- single job management.
- data engineering
- list all seed url lists.
- get the current status of the apache nutch server including running jobs and known configurations.
- engineers responsible for configuring and running web crawl pipelines using nutch.
- data engineers who consume crawl outputs for search indexing or data analysis pipelines.
- abort a nutch crawl job immediately without waiting for graceful shutdown.
- fetchdb node information.
- get job
- structured collection and storage of web data for downstream processing.
- indexing
- get config
- create a new nutch crawl configuration with custom properties.
- create and start a new nutch crawl job. job types include inject, generate, fetch, parse, updatedb, index, dedup, invertlinks.
- stop a running nutch crawl job gracefully.
- create config
- list seed lists
- single configuration management.
- create seed
- Crawl Engineer
- java
- stop a running job.
- open source
- create job
- list seeds
- apache nutch
- get all properties for a configuration.
- list all nutch crawl jobs, optionally filtered by crawl id.
- crawldb query interface.
- get status
- create a new seed url list for initializing a crawl.
- seed url list management.
- stop job
- query the crawldb for stats or url lookups.
- abort job
- end-to-end crawl pipeline management workflow covering job lifecycle, configuration, seeds, and database queries.
- web crawler
- manage crawl configurations.
- get server status
- Data Engineer
- crawl job management.
- hadoop
- create seed list
- list all available configurations.
- get job info
- delete config
- get all configuration properties for a specific nutch configuration.
- search
- create and start a crawl job.
- query crawldb
- query fetchdb
- apache
- query the fetchdb for node information.
- get job status and info.
- get apache nutch server status.
- get the current state and details for a specific nutch crawl job.
- systematic automated retrieval of web content at scale.
- stop a running crawl job.
- list configs
- list jobs
- create a new seed url list.
- list all available seed url lists in the nutch server.
- query the apache nutch crawldb for statistics, data dumps, or specific url status.
- query the apache nutch fetchdb for node fetch history and statistics.
- server status and administration.
- crawl management
slug: apache-nutch-crawl-management
source_filename: apache-nutch-crawl-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Apache Nutch Crawl Management\n  description: Workflow capability for managing end-to-end web crawl pipelines with Apache Nutch. Covers job lifecycle management, configuration control, seed list management, and CrawlDB querying for web crawl engineers and data engineers.\n  tags:\n    - Apache Nutch\n    - Web Crawler\n    - Crawl Management\n    - Data Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      NUTCH_USERNAME: NUTCH_USERNAME\n      NUTCH_PASSWORD: NUTCH_PASSWORD\n\ncapability:\n  consumes:\n    - import: nutch\n      location: ./shared/apache-nutch.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: nutch-crawl-api\n      description: Unified REST API for managing Apache Nutch web crawl pipelines.\n      resources:\n        - path: /v1/admin/status\n          name: admin-status\n          description: Server status and administration.\n\
  \          operations:\n            - method: GET\n              name: get-status\n              description: Get Apache Nutch server status.\n              call: \"nutch.get-server-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/configs\n          name: configs\n          description: Manage crawl configurations.\n          operations:\n            - method: GET\n              name: list-configs\n              description: List all available configurations.\n              call: \"nutch.get-configs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-config\n              description: Create a new crawl configuration.\n              call: \"nutch.create-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/configs/{configId}\n\
  \          name: config-detail\n          description: Single configuration management.\n          operations:\n            - method: GET\n              name: get-config\n              description: Get all properties for a configuration.\n              call: \"nutch.get-config\"\n              with:\n                configId: \"rest.configId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-config\n              description: Delete a configuration.\n              call: \"nutch.delete-config\"\n              with:\n                configId: \"rest.configId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs\n          name: jobs\n          description: Crawl job management.\n          operations:\n            - method: GET\n              name: list-jobs\n              description: List all crawl jobs.\n\
  \              call: \"nutch.get-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-job\n              description: Create and start a crawl job.\n              call: \"nutch.create-job\"\n              with:\n                crawlId: \"rest.crawlId\"\n                jobType: \"rest.type\"\n                confId: \"rest.confId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{id}\n          name: job-detail\n          description: Single job management.\n          operations:\n            - method: GET\n              name: get-job\n              description: Get job status and info.\n              call: \"nutch.get-job-info\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path:\
  \ /v1/jobs/{id}/stop\n          name: job-stop\n          description: Stop a running job.\n          operations:\n            - method: POST\n              name: stop-job\n              description: Stop a running crawl job.\n              call: \"nutch.stop-job\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/seeds\n          name: seeds\n          description: Seed URL list management.\n          operations:\n            - method: GET\n              name: list-seeds\n              description: List all seed URL lists.\n              call: \"nutch.get-seed-lists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-seed\n              description: Create a new seed URL list.\n              call: \"nutch.create-seed-file\"\n              with:\n         \
  \       crawlId: \"rest.crawlId\"\n                confId: \"rest.confId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/db/crawldb\n          name: crawldb\n          description: CrawlDB query interface.\n          operations:\n            - method: POST\n              name: query-crawldb\n              description: Query the CrawlDB for stats or URL lookups.\n              call: \"nutch.read-crawl-db\"\n              with:\n                crawlId: \"rest.crawlId\"\n                queryType: \"rest.type\"\n                confId: \"rest.confId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/db/fetchdb\n          name: fetchdb\n          description: FetchDB node information.\n          operations:\n            - method: POST\n              name: query-fetchdb\n              description: Query the FetchDB for node information.\n  \
  \            call: \"nutch.fetch-db\"\n              with:\n                crawlId: \"rest.crawlId\"\n                confId: \"rest.confId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: nutch-crawl-mcp\n      transport: http\n      description: MCP server for AI-assisted Apache Nutch crawl pipeline management.\n      tools:\n        - name: get-server-status\n          description: Get the current status of the Apache Nutch server including running jobs and known configurations.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nutch.get-server-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-configs\n          description: List all known Nutch configuration identifiers.\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"nutch.get-configs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-config\n          description: Create a new Nutch crawl configuration with custom properties.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"nutch.create-config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-config\n          description: Get all configuration properties for a specific Nutch configuration.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nutch.get-config\"\n          with:\n            configId: \"tools.configId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-jobs\n          description: List all Nutch crawl jobs, optionally filtered by crawl ID.\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"nutch.get-jobs\"\n          with:\n            crawlId: \"tools.crawlId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-job\n          description: Create and start a new Nutch crawl job. Job types include INJECT, GENERATE, FETCH, PARSE, UPDATEDB, INDEX, DEDUP, INVERTLINKS.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"nutch.create-job\"\n          with:\n            crawlId: \"tools.crawlId\"\n            jobType: \"tools.type\"\n            confId: \"tools.confId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-job-info\n          description: Get the current state and details for a specific Nutch crawl job.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nutch.get-job-info\"\n          with:\n            id: \"tools.id\"\n        \
  \  outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stop-job\n          description: Stop a running Nutch crawl job gracefully.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"nutch.stop-job\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: abort-job\n          description: Abort a Nutch crawl job immediately without waiting for graceful shutdown.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"nutch.abort-job\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-seed-lists\n          description: List all available seed URL lists in the Nutch server.\n          hints:\n \
  \           readOnly: true\n            openWorld: false\n          call: \"nutch.get-seed-lists\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-seed-list\n          description: Create a new seed URL list for initializing a crawl.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"nutch.create-seed-file\"\n          with:\n            crawlId: \"tools.crawlId\"\n            confId: \"tools.confId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-crawldb\n          description: Query the Apache Nutch CrawlDB for statistics, data dumps, or specific URL status.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nutch.read-crawl-db\"\n          with:\n            crawlId: \"tools.crawlId\"\n            queryType: \"tools.type\"\n            confId: \"tools.confId\"\n   \
  \       outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-fetchdb\n          description: Query the Apache Nutch FetchDB for node fetch history and statistics.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nutch.fetch-db\"\n          with:\n            crawlId: \"tools.crawlId\"\n            confId: \"tools.confId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-nutch/refs/heads/main/capabilities/apache-nutch-crawl-management.yaml
tags:
- Apache Nutch
- Web Crawler
- Crawl Management
- Data Engineering
tools:
- description: Get the current status of the Apache Nutch server including running jobs and known configurations.
  hints:
    openWorld: false
    readOnly: true
  name: get-server-status
- description: List all known Nutch configuration identifiers.
  hints:
    openWorld: false
    readOnly: true
  name: list-configs
- description: Create a new Nutch crawl configuration with custom properties.
  hints:
    openWorld: false
    readOnly: false
  name: create-config
- description: Get all configuration properties for a specific Nutch configuration.
  hints:
    openWorld: false
    readOnly: true
  name: get-config
- description: List all Nutch crawl jobs, optionally filtered by crawl ID.
  hints:
    openWorld: false
    readOnly: true
  name: list-jobs
- description: Create and start a new Nutch crawl job. Job types include INJECT, GENERATE, FETCH, PARSE, UPDATEDB, INDEX, DEDUP, INVERTLINKS.
  hints:
    openWorld: false
    readOnly: false
  name: create-job
- description: Get the current state and details for a specific Nutch crawl job.
  hints:
    openWorld: false
    readOnly: true
  name: get-job-info
- description: Stop a running Nutch crawl job gracefully.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stop-job
- description: Abort a Nutch crawl job immediately without waiting for graceful shutdown.
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: abort-job
- description: List all available seed URL lists in the Nutch server.
  hints:
    openWorld: false
    readOnly: true
  name: list-seed-lists
- description: Create a new seed URL list for initializing a crawl.
  hints:
    openWorld: false
    readOnly: false
  name: create-seed-list
- description: Query the Apache Nutch CrawlDB for statistics, data dumps, or specific URL status.
  hints:
    openWorld: false
    readOnly: true
  name: query-crawldb
- description: Query the Apache Nutch FetchDB for node fetch history and statistics.
  hints:
    openWorld: false
    readOnly: true
  name: query-fetchdb
---
