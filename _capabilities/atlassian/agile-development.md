---
consumed_apis:
- atlassian-admin
description: Agile software development workflow combining Jira Issue, Project, Filter, Search, Field, Workflow, and Dashboard APIs for software developers and scrum masters to plan, track, and deliver software.
layout: capability
name: Atlassian Agile Development
operations:
- description: Search issues using JQL
  method: GET
  name: search-issues
  path: /v1/issues
- description: List all projects
  method: GET
  name: list-projects
  path: /v1/projects
personas: []
provider_name: Atlassian
provider_slug: atlassian
search_terms:
- code
- list projects
- list saved jira filters
- list workflow statuses
- list all projects
- search issues using jql
- software development
- productivity
- list filters
- list dashboards
- list jira dashboards
- list workflows
- platform
- list jira workflows
- agile
- atlassian
- search issues
- list statuses
- jira
- list all jira projects
- jira project management
- collaboration
- search jira issues using jql queries
- jira issue management
slug: agile-development
tags:
- Agile
- Atlassian
- Jira
- Software Development
tools:
- description: Search Jira issues using JQL queries
  hints:
    openWorld: true
    readOnly: true
  name: search-issues
- description: List all Jira projects
  hints:
    readOnly: true
  name: list-projects
- description: List Jira dashboards
  hints:
    readOnly: true
  name: list-dashboards
- description: List saved Jira filters
  hints:
    readOnly: true
  name: list-filters
- description: List Jira workflows
  hints:
    readOnly: true
  name: list-workflows
- description: List workflow statuses
  hints:
    readOnly: true
  name: list-statuses
---
