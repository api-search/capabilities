---
consumed_apis:
- apis-io-search
description: Workflow capability for searching, discovering, and submitting APIs using the APIs.io search engine. Enables developers and platform engineers to programmatically find APIs by keyword across the full APIs.io index and submit their own APIs for discovery by others. The primary personas are API developers building integrations and API producers wanting their APIs discovered.
layout: capability
name: APIs.io API Discovery and Search
operations:
- description: Search for APIs by keyword or phrase
  method: GET
  name: search-apis
  path: /v1/apis
- description: Submit a new API to the directory
  method: POST
  name: submit-api
  path: /v1/apis
personas: []
provider_name: APIs.io
provider_slug: apis-io
search_terms:
- apis.json
- search for apis by keyword or phrase
- a developer searching for apis to integrate into their applications
- finding apis in the directory by keyword or topic
- search and submit apis in the directory
- API Producer
- api directory
- apis.io
- an api owner or provider submitting their api for discovery in the index
- submit api
- submitting new apis to the directory for indexing and discovery
- api aggregation
- api rating
- api discovery
- submit a new api to the directory
- search for apis in the directory and submit new apis for indexing
- api search
- search engine
- API Developer
- api indexing
- search apis
- search across the apis.io directory for apis matching a keyword or phrase. returns api names, descriptions, tags, quality scores, and links.
- submit a new api to the apis.io index by providing a valid apis.json document. the api will be reviewed and added to the searchable directory.
slug: api-discovery-search
tags:
- API Discovery
- API Indexing
- API Search
- APIs.io
- APIs.json
- Search Engine
tools:
- description: Search across the APIs.io directory for APIs matching a keyword or phrase. Returns API names, descriptions, tags, quality scores, and links.
  hints:
    openWorld: true
    readOnly: true
  name: search-apis
- description: Submit a new API to the APIs.io index by providing a valid APIs.json document. The API will be reviewed and added to the searchable directory.
  hints:
    openWorld: false
    readOnly: false
  name: submit-api
---
