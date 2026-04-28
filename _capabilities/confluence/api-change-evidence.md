---
categories:
- evidence
- wiki
consumed_apis:
- confluence-cloud-rest
description: Mine the Confluence wiki for API documentation pages, spec URLs, and endpoint mentions so a technical writer can locate what backend teams already wrote down — and find pages updated since the last release. One of the five enterprise systems where evidence of API change already lives, often as design notes before any spec lands.
layout: capability
name: Confluence API Change Evidence
operations:
- description: Search wiki content using CQL for API-related pages
  method: GET
  name: search-content
  path: /wiki/rest/api/content/search
- description: Get a Confluence page by title within a space
  method: GET
  name: get-page-by-title
  path: /wiki/rest/api/content
- description: List pages updated since a given timestamp using CQL lastmodified clause
  method: GET
  name: list-recently-updated
  path: /wiki/rest/api/content/search
- description: Get the version history of a page to see who edited what when
  method: GET
  name: get-page-version-history
  path: /wiki/rest/api/content/{id}/version
- description: List spaces likely to contain API documentation
  method: GET
  name: list-api-spaces
  path: /wiki/rest/api/space
- description: Get a page body in storage format to scan for spec URLs and endpoints
  method: GET
  name: get-page-body
  path: /wiki/rest/api/content/{id}
personas:
- Technical Writer
- API Program Manager
provider_name: Confluence
provider_slug: confluence
search_terms:
- search wiki content with cql
- evidence of api change in confluence
- get page by title
- list pages updated since last release
- page version history
- list spaces with api content
- get page body for endpoint mentions
- mine confluence for design docs
- five places api change evidence lives
- technical writer wiki review
- cql lastmodified clause
- spec url discovery in wiki
- pre-release page inventory
- wiki edit history
- api design page search
- backend team notes
- api program manager research
- api documentation drift
- endpoint mention scan
- confluence api truth
slug: api-change-evidence
tags:
- Confluence
- API Change
- Evidence
- Wiki
- CQL
tools:
- description: Search wiki content using CQL to surface API-related pages across all spaces
  hints:
    openWorld: false
    readOnly: true
  name: search-content
- description: Get a Confluence page by title within a space for direct access to a known doc
  hints:
    openWorld: false
    readOnly: true
  name: get-page-by-title
- description: List pages updated since a given timestamp using CQL lastmodified clause for release-window triage
  hints:
    openWorld: false
    readOnly: true
  name: list-recently-updated
- description: Get the version history of a page to see who edited what and when an API design changed
  hints:
    openWorld: false
    readOnly: true
  name: get-page-version-history
- description: List spaces likely to contain API documentation so a writer can scope their search
  hints:
    openWorld: false
    readOnly: true
  name: list-api-spaces
- description: Get a page body in storage format to scan for spec URLs and endpoint mentions
  hints:
    openWorld: false
    readOnly: true
  name: get-page-body
---
