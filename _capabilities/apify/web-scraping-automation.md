---
categories:
- automation
consumed_apis:
- apify
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
- run actor
- get run status.
- actors
- monitor actor runs.
- crawling
- retrieve scraped data.
- list actors
- list all available apify actors for web scraping and automation.
- abort actor run
- engineer building and running production web scrapers on apify.
- web automation
- retrieve structured scraped data from an apify dataset.
- browser automation
- apify
- web scraping
- get scraped data
- get run
- Data Engineer
- run an apify actor with custom input to scrape a website or automate a task.
- browse and run actors.
- Web Scraping Engineer
- developer using web scraping to collect training data or rag document sources.
- automation
- data extraction
- list actors.
- get dataset items
- check the status of an apify actor run.
- abort a running apify actor.
- get dataset items.
- engineer extracting structured data from websites for analytics pipelines.
- data aggregation
- AI Developer
- get run status
slug: web-scraping-automation
source_filename: web-scraping-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apify Web Scraping and Automation\"\n  description: \"Unified workflow for running web scraping actors, monitoring execution, and retrieving structured data from the Apify platform.\"\n  tags:\n    - Apify\n    - Web Scraping\n    - Automation\n    - Data Extraction\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APIFY_TOKEN: APIFY_TOKEN\n\ncapability:\n  consumes:\n    - import: apify\n      location: ./shared/apify.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: apify-scraping-api\n      description: \"Unified REST API for Apify web scraping and automation.\"\n      resources:\n        - path: /v1/actors\n          name: actors\n          description: \"Browse and run Actors.\"\n          operations:\n            - method: GET\n              name: list-actors\n              description: \"List Actors.\"\n              call: \"apify.list-actors\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runs/{runId}\n          name: runs\n          description: \"Monitor Actor runs.\"\n          operations:\n            - method: GET\n              name: get-run\n              description: \"Get run status.\"\n              call: \"apify.get-run\"\n              with:\n                runId: \"rest.runId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/datasets/{datasetId}/items\n          name: dataset-items\n          description: \"Retrieve scraped data.\"\n          operations:\n            - method: GET\n              name: get-dataset-items\n              description: \"Get dataset items.\"\n              call: \"apify.get-dataset-items\"\n              with:\n                datasetId: \"rest.datasetId\"\n              outputParameters:\n                - type: object\n                \
  \  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: apify-scraping-mcp\n      transport: http\n      description: \"MCP server for AI-assisted web scraping and data extraction.\"\n      tools:\n        - name: list-actors\n          description: \"List all available Apify Actors for web scraping and automation.\"\n          hints: {readOnly: true, destructive: false, idempotent: true}\n          call: \"apify.list-actors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-actor\n          description: \"Run an Apify Actor with custom input to scrape a website or automate a task.\"\n          hints: {readOnly: false, destructive: false, idempotent: false}\n          call: \"apify.run-actor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-run-status\n          description: \"Check the status of an Apify Actor run.\"\n          hints: {readOnly: true,\
  \ destructive: false, idempotent: true}\n          call: \"apify.get-run\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-scraped-data\n          description: \"Retrieve structured scraped data from an Apify dataset.\"\n          hints: {readOnly: true, destructive: false, idempotent: true}\n          call: \"apify.get-dataset-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: abort-actor-run\n          description: \"Abort a running Apify Actor.\"\n          hints: {readOnly: false, destructive: true, idempotent: true}\n          call: \"apify.abort-run\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
