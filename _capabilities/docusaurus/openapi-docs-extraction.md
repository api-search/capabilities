---
categories:
- documentation
- discovery
consumed_apis:
- docusaurus-build
description: Extract OpenAPI references and rendered API documentation pages from a Docusaurus site that uses the docusaurus-openapi-docs plugin. Lets a technical writer programmatically inspect what API surface the published docs currently describe — list rendered API pages, fetch the source OpenAPI specs the site builds from, and enumerate referenced operations to compare against upstream evidence of API change.
layout: capability
name: Docusaurus OpenAPI Docs Extraction
operations:
- description: List all rendered documentation pages from the Docusaurus sitemap
  method: GET
  name: list-docs-pages
  path: /sitemap.xml
- description: List the rendered API reference index built by docusaurus-openapi-docs
  method: GET
  name: list-api-reference
  path: /docs/api
- description: Get the source OpenAPI specification the Docusaurus site builds the API docs from
  method: GET
  name: get-openapi-spec
  path: /api/v1/openapi.json
- description: Get a specific rendered API operation page
  method: GET
  name: get-operation-page
  path: /docs/api/{operationId}
- description: Get the rendered docs page metadata for a given path
  method: GET
  name: get-docs-page
  path: /docs/{slug}
- description: List all tags surfaced by the docusaurus-openapi-docs plugin
  method: GET
  name: list-api-tags
  path: /docs/api/tags
personas:
- Technical Writer
- API Program Manager
provider_name: Docusaurus
provider_slug: docusaurus
search_terms:
- list rendered documentation pages
- docusaurus openapi docs plugin
- extract openapi reference from docusaurus
- get source openapi spec
- list api reference operations
- evidence of current published api docs
- list api tags
- get rendered api operation page
- compare published docs to upstream spec
- docusaurus sitemap crawl
- technical writer api inventory
- api documentation discovery
- openapi extraction
- docs site introspection
- list operations in docs
- get docs page metadata
- palo alto docs
- published api truth
- docs vs spec drift
- api documentation pipeline
slug: openapi-docs-extraction
tags:
- Docusaurus
- OpenAPI
- Documentation
- API Discovery
- Technical Writing
tools:
- description: List all rendered documentation pages from the Docusaurus sitemap so the writer can inventory what is currently published
  hints:
    openWorld: false
    readOnly: true
  name: list-docs-pages
- description: List the rendered API reference index built by the docusaurus-openapi-docs plugin
  hints:
    openWorld: false
    readOnly: true
  name: list-api-reference
- description: Fetch the source OpenAPI specification the Docusaurus site builds API docs from, for diffing against upstream evidence
  hints:
    openWorld: false
    readOnly: true
  name: get-openapi-spec
- description: Retrieve a specific rendered API operation page to inspect what is currently published for one endpoint
  hints:
    openWorld: false
    readOnly: true
  name: get-operation-page
- description: Get the rendered docs page metadata (title, description, last update) for a given doc slug
  hints:
    openWorld: false
    readOnly: true
  name: get-docs-page
- description: List all tags surfaced by docusaurus-openapi-docs to map docs sections to API areas
  hints:
    openWorld: false
    readOnly: true
  name: list-api-tags
---
