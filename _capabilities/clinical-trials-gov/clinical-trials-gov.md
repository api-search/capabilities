---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Clinical Trials Gov
operations: []
personas: []
provider_name: ClinicalTrials.gov
provider_slug: clinical-trials-gov
search_terms:
- clinical trials
- nih
- open data
- health
- research
- government
- public health
slug: clinical-trials-gov
source_filename: clinical-trials-gov.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko capabilities profile for ClinicalTrials.gov.\n# Capabilities map verbs against the high-value operations exposed\n# by the Data API v2 at https://clinicaltrials.gov/api/v2.\nprovider: clinical-trials-gov\nname: ClinicalTrials.gov\ndescription: >-\n  ClinicalTrials.gov is the U.S. NIH registry and results database of\n  clinical studies. These capabilities cover searching the registry,\n  retrieving studies by NCT ID, exploring metadata and search areas,\n  and reading version and statistics endpoints.\ncapabilities:\n  - id: clinical-trials-gov.studies.search\n    name: Search studies\n    description: >-\n      Search the registry by free-text query, condition, intervention,\n      location, and structured filters with paging and selectable fields.\n    api: clinical-trials-gov:data-api-v2\n    operationRef: openapi/clinical-trials-gov-data-api-v2-openapi.yml#/paths/~1studies/get\n    inputs:\n      - query.term\n      - query.cond\n      - query.intr\n      - query.locn\n\
  \      - filter.overallStatus\n      - filter.geo\n      - pageSize\n      - pageToken\n      - fields\n      - format\n    outputs:\n      - studies\n      - nextPageToken\n      - totalCount\n\n  - id: clinical-trials-gov.studies.get\n    name: Get a single study\n    description: Retrieve a single study record by its NCT identifier.\n    api: clinical-trials-gov:data-api-v2\n    operationRef: openapi/clinical-trials-gov-data-api-v2-openapi.yml#/paths/~1studies~1{nctId}/get\n    inputs:\n      - nctId\n      - fields\n      - format\n    outputs:\n      - study\n\n  - id: clinical-trials-gov.studies.metadata\n    name: Get study fields metadata\n    description: >-\n      Return field-level metadata describing the study record schema,\n      types, and allowed values used by /studies queries.\n    api: clinical-trials-gov:data-api-v2\n    operationRef: openapi/clinical-trials-gov-data-api-v2-openapi.yml#/paths/~1studies~1metadata/get\n    inputs:\n      - includeIndexedOnly\n    outputs:\n\
  \      - fields\n\n  - id: clinical-trials-gov.studies.search-areas\n    name: List search areas\n    description: List the named search areas usable in /studies queries.\n    api: clinical-trials-gov:data-api-v2\n    operationRef: openapi/clinical-trials-gov-data-api-v2-openapi.yml#/paths/~1studies~1search-areas/get\n    inputs: []\n    outputs:\n      - searchAreas\n\n  - id: clinical-trials-gov.studies.enums\n    name: List enumerations\n    description: List enumerated values used for filter and field parameters.\n    api: clinical-trials-gov:data-api-v2\n    operationRef: openapi/clinical-trials-gov-data-api-v2-openapi.yml#/paths/~1studies~1enums/get\n    inputs: []\n    outputs:\n      - enums\n\n  - id: clinical-trials-gov.version.get\n    name: Get API version\n    description: Return the data version and last-updated timestamp.\n    api: clinical-trials-gov:data-api-v2\n    operationRef: openapi/clinical-trials-gov-data-api-v2-openapi.yml#/paths/~1version/get\n    inputs: []\n\
  \    outputs:\n      - apiVersion\n      - dataTimestamp\n\n  - id: clinical-trials-gov.stats.size\n    name: Get study size statistics\n    description: Return aggregate counts and size statistics for the registry.\n    api: clinical-trials-gov:data-api-v2\n    operationRef: openapi/clinical-trials-gov-data-api-v2-openapi.yml#/paths/~1stats~1size/get\n    inputs: []\n    outputs:\n      - totalStudies\n      - sizes\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/clinical-trials-gov/refs/heads/main/capabilities/clinical-trials-gov.yaml
tags: []
tools: []
---
