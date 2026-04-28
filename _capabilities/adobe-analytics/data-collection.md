---
categories:
- analytics
consumed_apis:
- adobe-bulk-data-insertion
- adobe-analytics
description: Unified workflow for server-side data collection and ingestion combining Bulk Data Insertion for high-volume event uploads with the Analytics API for report suite discovery and validation. Used by data engineers and implementation teams.
layout: capability
name: Adobe Analytics Data Collection
operations:
- description: Upload a batch events file.
  method: POST
  name: upload-events
  path: /v1/events
- description: Validate a batch events file without ingesting.
  method: POST
  name: validate-events
  path: /v1/events/validate
- description: List report suites to identify collection targets.
  method: GET
  name: list-report-suites
  path: /v1/report-suites
- description: Get report suite details.
  method: GET
  name: get-report-suite
  path: /v1/report-suites/{rsid}
- description: List metrics to validate event data mapping.
  method: GET
  name: list-metrics
  path: /v1/metrics
- description: List dimensions to validate event data mapping.
  method: GET
  name: list-dimensions
  path: /v1/dimensions
personas: []
provider_name: Adobe Analytics
provider_slug: adobe-analytics
search_terms:
- data collection
- get report suite
- events
- list report suites to identify collection targets.
- validate a batch events file without ingesting data.
- list available metrics to validate event data mapping.
- validate events
- report suite details.
- list metrics to validate event data mapping.
- web analytics
- dimension discovery for event mapping.
- upload a gzip-compressed csv file of batched analytics event data.
- upload events
- list report suites
- upload a batch events file.
- list available dimensions to validate event data mapping.
- adobe analytics
- validate event files.
- bulk data insertion
- report suite discovery for data collection targeting.
- business intelligence
- list metrics
- marketing
- server side
- list dimensions to validate event data mapping.
- list report suites to identify data collection targets.
- get report suite details.
- validate a batch events file without ingesting.
- analytics
- batch event upload.
- digital marketing
- get details for a report suite to verify collection configuration.
- customer intelligence
- metric discovery for event mapping.
- adobe
- list dimensions
slug: data-collection
tags:
- Adobe Analytics
- Data Collection
- Bulk Data Insertion
- Events
- Server Side
tools:
- description: Upload a gzip-compressed CSV file of batched Analytics event data.
  hints:
    idempotent: false
    readOnly: false
  name: upload-events
- description: Validate a batch events file without ingesting data.
  hints:
    idempotent: true
    readOnly: true
  name: validate-events
- description: List report suites to identify data collection targets.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-report-suites
- description: Get details for a report suite to verify collection configuration.
  hints:
    idempotent: true
    readOnly: true
  name: get-report-suite
- description: List available metrics to validate event data mapping.
  hints:
    idempotent: true
    readOnly: true
  name: list-metrics
- description: List available dimensions to validate event data mapping.
  hints:
    idempotent: true
    readOnly: true
  name: list-dimensions
---
