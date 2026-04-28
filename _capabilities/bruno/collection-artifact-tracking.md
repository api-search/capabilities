---
categories:
- api-testing
- discovery
consumed_apis:
- bruno-collections-api
description: Workflow capability for platform engineers tracking Bruno Collections as first-class artifacts inside the software catalog — discovering collections in repos, linking them to the components and APIs they exercise, and surfacing them alongside OpenAPI specs as testable contracts. Implements the Cvent pattern Mark Avery described where Bruno Collections sit next to package.json and deployment metadata as a native source of truth.
layout: capability
name: Bruno Collection Artifact Tracking
operations:
- description: List Bruno Collections discovered across registered repositories
  method: GET
  name: list-collections
  path: /v1/collections
- description: Get a single Bruno Collection with its requests and environment variables
  method: GET
  name: get-collection
  path: /v1/collections/{collectionId}
- description: Link a Bruno Collection to the component or API it exercises in the catalog
  method: POST
  name: link-collection
  path: /v1/collections/{collectionId}/links
- description: Run a Bruno Collection against an environment for contract validation
  method: POST
  name: run-collection
  path: /v1/collections/{collectionId}/runs
- description: Get the result of a collection run with per-request status
  method: GET
  name: get-run-result
  path: /v1/collections/{collectionId}/runs/{runId}
- description: List the components and OpenAPI specs related to a Bruno Collection
  method: GET
  name: list-collection-related
  path: /v1/collections/{collectionId}/related
personas:
- Platform Engineer
- API Developer
provider_name: Bruno
provider_slug: bruno
search_terms:
- discover bruno collections in repos
- track api test collections as catalog artifacts
- link bruno collection to component
- contract validation with bruno
- bruno collections alongside openapi
- list bruno collections
- get bruno collection contents
- run bruno collection for contract test
- bruno run result
- bruno catalog integration
- api artifact tracking
- bruno collections in backstage catalog
- bruno collection metadata
- find bruno collections by repo
- bruno
- api testing
- api collection
- collection artifact
- contract testing
- developer experience
- platform engineering
slug: collection-artifact-tracking
tags:
- Bruno
- API Testing
- Collections
- Contract Testing
- Catalog
tools:
- description: List Bruno Collections discovered across registered repositories so they can be tracked as first-class artifacts
  hints:
    openWorld: false
    readOnly: true
  name: list-collections
- description: Get a Bruno Collection's contents — requests, environments, variables — for review or generation
  hints:
    openWorld: false
    readOnly: true
  name: get-collection
- description: Link a Bruno Collection to the component or API it exercises in the platform catalog
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: link-collection-to-component
- description: Run a Bruno Collection against an environment to validate the contract end to end
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: run-collection
- description: Get the result of a Bruno Collection run including per-request pass/fail status
  hints:
    openWorld: false
    readOnly: true
  name: get-run-result
- description: List the components and OpenAPI specs already related to a Bruno Collection in the catalog
  hints:
    openWorld: false
    readOnly: true
  name: list-collection-related
---
