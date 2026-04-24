---
consumed_apis:
- loggly
- papertrail
description: Workflow for centralized log management combining Loggly cloud log aggregation with Papertrail log search and system management for DevOps and operations teams.
layout: capability
name: SolarWinds Log Management
operations:
- description: Search Loggly log events
  method: GET
  name: loggly-search-events
  path: /v1/loggly-search
- description: Search Papertrail log events
  method: GET
  name: papertrail-search-events
  path: /v1/papertrail-search
- description: List log-sending systems
  method: GET
  name: list-systems
  path: /v1/systems
personas: []
provider_name: SolarWinds
provider_slug: solarwinds
search_terms:
- observability
- papertrail log search
- papertrail list groups
- ip address management
- log management
- loggly get account info
- list papertrail saved searches
- loggly search
- papertrail search
- list systems
- papertrail system management
- list log-sending systems
- get loggly account information
- search loggly log events
- list papertrail system groups
- loggly log search
- list papertrail log-sending systems
- papertrail
- loggly
- retrieve loggly search results by rsid
- application monitoring
- itsm
- it management
- database monitoring
- loggly search events
- network monitoring
- solarwinds
- papertrail list systems
- papertrail list saved searches
- loggly get events
- papertrail search events
- search papertrail log events
- infrastructure
slug: log-management
tags:
- SolarWinds
- Log Management
- Loggly
- Papertrail
tools:
- description: Search Loggly log events
  hints:
    readOnly: true
  name: loggly-search
- description: Retrieve Loggly search results by RSID
  hints:
    readOnly: true
  name: loggly-get-events
- description: Get Loggly account information
  hints:
    readOnly: true
  name: loggly-get-account-info
- description: Search Papertrail log events
  hints:
    readOnly: true
  name: papertrail-search
- description: List Papertrail log-sending systems
  hints:
    readOnly: true
  name: papertrail-list-systems
- description: List Papertrail system groups
  hints:
    readOnly: true
  name: papertrail-list-groups
- description: List Papertrail saved searches
  hints:
    readOnly: true
  name: papertrail-list-saved-searches
---
