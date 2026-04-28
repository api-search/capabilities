---
categories:
- evidence
- api-governance
consumed_apis:
- jira-cloud-rest
description: Search Jira issues for API-impacting work — by label, JQL for endpoint or component mentions, and version planning — so a technical writer can surface tickets they need to know about before a release. One of the five enterprise systems where evidence of API change already lives, ahead of the docs catching up.
layout: capability
name: Jira API Change Evidence
operations:
- description: Search Jira issues using JQL for API-impacting work
  method: GET
  name: search-issues
  path: /rest/api/3/search
- description: List issues filtered by label such as api-change or breaking-change
  method: GET
  name: list-issues-by-label
  path: /rest/api/3/search
- description: Get a single issue including comments and change history
  method: GET
  name: get-issue
  path: /rest/api/3/issue/{issueIdOrKey}
- description: List remote and internal links from an issue to related API epics
  method: GET
  name: list-issue-links
  path: /rest/api/3/issue/{issueIdOrKey}/remotelink
- description: List planned versions and releases for a project
  method: GET
  name: list-versions
  path: /rest/api/3/project/{projectIdOrKey}/versions
- description: Get all comments on an issue to capture context written outside the ticket body
  method: GET
  name: get-issue-comments
  path: /rest/api/3/issue/{issueIdOrKey}/comment
personas:
- Technical Writer
- API Program Manager
provider_name: Jira
provider_slug: jira
search_terms:
- search jira issues with jql
- evidence of api change in jira
- list issues by label api-change
- get issue with comments
- list issue links to api epics
- list versions and releases
- breaking change ticket triage
- jql for endpoint mentions
- api program manager release prep
- five places api change evidence lives
- pre-release ticket inventory
- jira issue history
- get issue comments
- planned api releases
- api impacting work
- technical writer ticket review
- mine jira for api work
- api change tickets
- release version inventory
- component-scoped jql
slug: api-change-evidence
tags:
- Jira
- API Change
- Evidence
- JQL
- Release Planning
tools:
- description: Search Jira issues using JQL for API-impacting work tied to specific endpoints, components, or fix versions
  hints:
    openWorld: false
    readOnly: true
  name: search-issues
- description: List issues filtered by label such as api-change or breaking-change to surface tickets a writer needs before release
  hints:
    openWorld: false
    readOnly: true
  name: list-issues-by-label
- description: Get a single issue including comments and change history for full context on an API change
  hints:
    openWorld: false
    readOnly: true
  name: get-issue
- description: List remote and internal links from an issue to related API epics or upstream tickets
  hints:
    openWorld: false
    readOnly: true
  name: list-issue-links
- description: List planned versions and releases for a project to align docs with upcoming API ship dates
  hints:
    openWorld: false
    readOnly: true
  name: list-versions
- description: Retrieve all comments on an issue to capture context written outside the ticket body
  hints:
    openWorld: false
    readOnly: true
  name: get-issue-comments
---
