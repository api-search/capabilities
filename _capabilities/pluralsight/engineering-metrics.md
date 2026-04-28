---
categories:
- collaboration
consumed_apis:
- pluralsight-flow-coding-metrics
- pluralsight-flow-collaboration-metrics
- pluralsight-flow-dora-metrics
- pluralsight-flow-commits
- pluralsight-flow-pull-requests
- pluralsight-flow-tickets
description: Unified workflow for engineering managers to track developer productivity, code quality, collaboration, and delivery performance through Flow metrics. Combines coding metrics, collaboration metrics, DORA metrics, commits, pull requests, and tickets APIs.
layout: capability
name: Pluralsight Engineering Metrics
operations:
- description: Retrieve code-level engineering metrics
  method: GET
  name: get-coding-metrics
  path: /v1/coding-metrics
- description: Retrieve collaboration metrics for engineering teams
  method: GET
  name: get-collaboration-metrics
  path: /v1/collaboration-metrics
- description: Retrieve DORA engineering metrics
  method: GET
  name: get-dora-metrics
  path: /v1/dora-metrics
- description: Retrieve commit data and metrics
  method: GET
  name: get-commits
  path: /v1/commits
- description: Retrieve pull request data and events
  method: GET
  name: get-pull-requests
  path: /v1/pull-requests
- description: Retrieve ticket data and events
  method: GET
  name: get-tickets
  path: /v1/tickets
personas: []
provider_name: Pluralsight
provider_slug: pluralsight
search_terms:
- code-level engineering metrics and developer productivity data
- get dora metrics
- retrieve dora engineering metrics including deployment frequency, lead time for changes, change failure rate, and time to restore service.
- retrieve ticket data and events
- get tickets
- retrieve dora engineering metrics
- technology
- engineering metrics
- retrieve pull request and collaboration metrics for engineering teams with date range filtering.
- retrieve ticket data including comments, events, and project associations from connected project management tools.
- developer productivity
- courses
- retrieve collaboration metrics for engineering teams
- retrieve pull request data, comments, and events across repositories.
- learning
- flow
- ticket data from connected project management tools
- pull request data, comments, and events across repositories
- retrieve commit data and metrics
- get collaboration metrics
- commit data and aggregated metrics across repositories
- get coding metrics
- retrieve code-level engineering metrics and developer productivity data with date range filtering.
- collaboration
- video training
- retrieve pull request data and events
- skills assessment
- retrieve code-level engineering metrics
- dora
- dora engineering metrics including deployment frequency and lead time
- pluralsight
- get commits
- education
- pull request and collaboration metrics for engineering teams
- get pull requests
- retrieve commit data and aggregated commit metrics across repositories.
slug: engineering-metrics
tags:
- Pluralsight
- Flow
- Engineering Metrics
- Developer Productivity
- DORA
- Collaboration
tools:
- description: Retrieve code-level engineering metrics and developer productivity data with date range filtering.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-coding-metrics
- description: Retrieve pull request and collaboration metrics for engineering teams with date range filtering.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-collaboration-metrics
- description: Retrieve DORA engineering metrics including deployment frequency, lead time for changes, change failure rate, and time to restore service.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-dora-metrics
- description: Retrieve commit data and aggregated commit metrics across repositories.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-commits
- description: Retrieve pull request data, comments, and events across repositories.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-pull-requests
- description: Retrieve ticket data including comments, events, and project associations from connected project management tools.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-tickets
---
