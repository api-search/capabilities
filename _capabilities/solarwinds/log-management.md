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
- papertrail system management
- papertrail list groups
- list log-sending systems
- log management
- loggly search
- loggly search events
- papertrail
- ip address management
- loggly get events
- network monitoring
- observability
- papertrail log search
- papertrail search
- solarwinds
- get loggly account information
- retrieve loggly search results by rsid
- itsm
- list papertrail saved searches
- loggly log search
- application monitoring
- search loggly log events
- papertrail list systems
- search papertrail log events
- loggly
- list systems
- loggly get account info
- list papertrail system groups
- infrastructure
- papertrail search events
- database monitoring
- list papertrail log-sending systems
- papertrail list saved searches
- it management
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
