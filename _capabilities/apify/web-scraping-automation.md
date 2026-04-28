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
- list actors
- run actor
- browser automation
- retrieve scraped data.
- Data Engineer
- actors
- get run
- check the status of an apify actor run.
- list actors.
- browse and run actors.
- abort actor run
- developer using web scraping to collect training data or rag document sources.
- Web Scraping Engineer
- get scraped data
- crawling
- abort a running apify actor.
- apify
- get run status
- data aggregation
- AI Developer
- web scraping
- engineer building and running production web scrapers on apify.
- web automation
- monitor actor runs.
- run an apify actor with custom input to scrape a website or automate a task.
- list all available apify actors for web scraping and automation.
- engineer extracting structured data from websites for analytics pipelines.
- data extraction
- get dataset items
- get run status.
- automation
- get dataset items.
- retrieve structured scraped data from an apify dataset.
slug: web-scraping-automation
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
