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
- list papertrail saved searches
- papertrail system management
- papertrail log search
- solarwinds
- network monitoring
- database monitoring
- loggly
- it management
- log management
- observability
- application monitoring
- loggly search
- papertrail
- loggly log search
- get loggly account information
- papertrail list systems
- list systems
- loggly get account info
- papertrail list groups
- retrieve loggly search results by rsid
- infrastructure
- papertrail search events
- list papertrail system groups
- itsm
- papertrail list saved searches
- search papertrail log events
- ip address management
- list log-sending systems
- search loggly log events
- loggly get events
- loggly search events
- papertrail search
- list papertrail log-sending systems
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
