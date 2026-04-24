---
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
- get the current status of the apache nutch server including running jobs and known configurations.
- create seed list
- list all available configurations.
- single configuration management.
- Crawl Engineer
- hadoop
- abort job
- create and start a crawl job.
- search
- stop job
- fetchdb node information.
- create a new crawl configuration.
- create and start a new nutch crawl job. job types include inject, generate, fetch, parse, updatedb, index, dedup, invertlinks.
- crawl job management.
- list all seed url lists.
- query the apache nutch crawldb for statistics, data dumps, or specific url status.
- get job info
- list seed lists
- list all nutch crawl jobs, optionally filtered by crawl id.
- stop a running nutch crawl job gracefully.
- java
- create config
- stop a running crawl job.
- get job
- get all configuration properties for a specific nutch configuration.
- indexing
- get the current state and details for a specific nutch crawl job.
- list all crawl jobs.
- apache nutch
- create a new seed url list.
- query the apache nutch fetchdb for node fetch history and statistics.
- create a new nutch crawl configuration with custom properties.
- create job
- get apache nutch server status.
- apache
- stop a running job.
- list all known nutch configuration identifiers.
- query the fetchdb for node information.
- query crawldb
- get status
- seed url list management.
- end-to-end crawl pipeline management workflow covering job lifecycle, configuration, seeds, and database queries.
- list jobs
- crawl management
- list seeds
- engineers responsible for configuring and running web crawl pipelines using nutch.
- abort a nutch crawl job immediately without waiting for graceful shutdown.
- open source
- get server status
- get all properties for a configuration.
- web crawler
- data engineers who consume crawl outputs for search indexing or data analysis pipelines.
- data engineering
- get config
- Data Engineer
- query the crawldb for stats or url lookups.
- get job status and info.
- delete config
- systematic automated retrieval of web content at scale.
- delete a configuration.
- list configs
- manage crawl configurations.
- structured collection and storage of web data for downstream processing.
- crawldb query interface.
- list all available seed url lists in the nutch server.
- single job management.
- create seed
- query fetchdb
- create a new seed url list for initializing a crawl.
- server status and administration.
slug: apache-nutch-crawl-management
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
