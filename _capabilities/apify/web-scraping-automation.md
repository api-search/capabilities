---
categories:
- automation
consumed_apis: []
description: Unified workflow for running web scraping actors, monitoring execution, and retrieving structured data from the Apify platform.
layout: capability
name: Apify Web Scraping and Automation
operations:
- description: List Actors.
  method: GET
  name: list-actors
  path: /v1/actors
- description: Get run status.
  method: GET
  name: get-run
  path: /v1/runs/{runId}
- description: Get dataset items.
  method: GET
  name: get-dataset-items
  path: /v1/datasets/{datasetId}/items
personas: []
provider_name: Apify
provider_slug: apify
search_terms:
- list actors.
- web automation
- engineer extracting structured data from websites for analytics pipelines.
- AI Developer
- run actor
- monitor actor runs.
- engineer building and running production web scrapers on apify.
- actors
- check the status of an apify actor run.
- data extraction
- Data Engineer
- abort a running apify actor.
- abort actor run
- retrieve scraped data.
- web scraping
- apify
- list actors
- developer using web scraping to collect training data or rag document sources.
- data aggregation
- get run status.
- run an apify actor with custom input to scrape a website or automate a task.
- get run
- get run status
- browser automation
- list all available apify actors for web scraping and automation.
- get scraped data
- crawling
- browse and run actors.
- retrieve structured scraped data from an apify dataset.
- get dataset items.
- get dataset items
- Web Scraping Engineer
- automation
slug: web-scraping-automation
source_filename: web-scraping-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apify Web Scraping and Automation\n  description: Unified workflow for running web scraping actors, monitoring execution, and retrieving structured data from\n    the Apify platform.\n  tags:\n  - Apify\n  - Web Scraping\n  - Automation\n  - Data Extraction\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APIFY_TOKEN: APIFY_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: apify\n    baseUri: https://api.apify.com/v2\n    description: Apify REST API for managing web scraping actors and data.\n    authentication:\n      type: bearer\n      token: '{{APIFY_TOKEN}}'\n    resources:\n    - name: actors\n      path: /acts\n      description: Manage and run Apify Actors.\n      operations:\n      - name: list-actors\n        method: GET\n        description: List all Actors.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n      - name: get-actor\n        method: GET\n        description: Get a specific Actor.\n        inputParameters:\n        - name: actorId\n          in: path\n          type: string\n          required: true\n          description: Actor ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: run-actor\n        method: POST\n        description: Run an Actor.\n        inputParameters:\n        - name: actorId\n          in: path\n          type: string\n          required: true\n          description: Actor ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: actor-runs\n      path: /actor-runs\n      description: Monitor Actor runs.\n      operations:\n      - name: get-run\n        method: GET\n        description: Get run details.\n        inputParameters:\n        - name: runId\n     \
  \     in: path\n          type: string\n          required: true\n          description: Run ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: abort-run\n        method: POST\n        description: Abort a running Actor.\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n          description: Run ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets\n      path: /datasets\n      description: Manage datasets.\n      operations:\n      - name: list-datasets\n        method: GET\n        description: List all datasets.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-dataset-items\n        method: GET\n        description: Get dataset\
  \ items.\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset ID.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Output format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apify-scraping-api\n    description: Unified REST API for Apify web scraping and automation.\n    resources:\n    - path: /v1/actors\n      name: actors\n      description: Browse and run Actors.\n      operations:\n      - method: GET\n        name: list-actors\n        description: List Actors.\n        call: apify.list-actors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}\n      name: runs\n      description: Monitor Actor runs.\n      operations:\n\
  \      - method: GET\n        name: get-run\n        description: Get run status.\n        call: apify.get-run\n        with:\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasets/{datasetId}/items\n      name: dataset-items\n      description: Retrieve scraped data.\n      operations:\n      - method: GET\n        name: get-dataset-items\n        description: Get dataset items.\n        call: apify.get-dataset-items\n        with:\n          datasetId: rest.datasetId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apify-scraping-mcp\n    transport: http\n    description: MCP server for AI-assisted web scraping and data extraction.\n    tools:\n    - name: list-actors\n      description: List all available Apify Actors for web scraping and automation.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: apify.list-actors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-actor\n      description: Run an Apify Actor with custom input to scrape a website or automate a task.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apify.run-actor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-run-status\n      description: Check the status of an Apify Actor run.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apify.get-run\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-scraped-data\n      description: Retrieve structured scraped data from an Apify dataset.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apify.get-dataset-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ abort-actor-run\n      description: Abort a running Apify Actor.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: apify.abort-run\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apify/refs/heads/main/capabilities/web-scraping-automation.yaml
tags:
- Apify
- Web Scraping
- Automation
- Data Extraction
tools:
- description: List all available Apify Actors for web scraping and automation.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-actors
- description: Run an Apify Actor with custom input to scrape a website or automate a task.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: run-actor
- description: Check the status of an Apify Actor run.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-run-status
- description: Retrieve structured scraped data from an Apify dataset.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-scraped-data
- description: Abort a running Apify Actor.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: abort-actor-run
---
