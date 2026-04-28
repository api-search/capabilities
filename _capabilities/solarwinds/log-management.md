---
categories: []
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
- itsm
- papertrail system management
- papertrail search events
- papertrail log search
- list log-sending systems
- database monitoring
- search papertrail log events
- it management
- list papertrail system groups
- observability
- loggly search
- get loggly account information
- infrastructure
- list papertrail log-sending systems
- loggly log search
- log management
- solarwinds
- papertrail list systems
- list papertrail saved searches
- papertrail list saved searches
- search loggly log events
- loggly search events
- ip address management
- loggly get account info
- papertrail list groups
- papertrail search
- application monitoring
- papertrail
- loggly get events
- retrieve loggly search results by rsid
- loggly
- list systems
- network monitoring
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
