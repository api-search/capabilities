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
- database monitoring
- get loggly account information
- list papertrail system groups
- application monitoring
- log management
- list systems
- papertrail list systems
- itsm
- search loggly log events
- papertrail search events
- loggly get account info
- loggly search events
- it management
- loggly get events
- loggly search
- search papertrail log events
- papertrail
- ip address management
- papertrail list groups
- infrastructure
- papertrail search
- papertrail system management
- list papertrail log-sending systems
- papertrail list saved searches
- loggly log search
- network monitoring
- solarwinds
- list log-sending systems
- retrieve loggly search results by rsid
- observability
- list papertrail saved searches
- papertrail log search
- loggly
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
