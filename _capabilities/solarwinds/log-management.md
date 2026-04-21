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
- list systems
- itsm
- papertrail list systems
- application monitoring
- list papertrail log-sending systems
- loggly
- search loggly log events
- it management
- papertrail system management
- database monitoring
- loggly log search
- network monitoring
- get loggly account information
- list papertrail system groups
- ip address management
- papertrail list groups
- solarwinds
- loggly search events
- loggly get account info
- list papertrail saved searches
- log management
- papertrail
- papertrail list saved searches
- papertrail log search
- infrastructure
- retrieve loggly search results by rsid
- loggly get events
- observability
- papertrail search events
- loggly search
- search papertrail log events
- list log-sending systems
- papertrail search
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
