---
categories: []
consumed_apis: []
description: Delivers personalized product recommendations at scale using machine learning for retail and e-commerce use cases.
layout: capability
name: Google Cloud Recommendations AI API
operations:
- description: Google Cloud Recommendations AI List catalog items
  method: GET
  name: listcatalogitems
  path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/catalogItems
- description: Google Cloud Recommendations AI Create a catalog item
  method: POST
  name: createcatalogitem
  path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/catalogItems
- description: Google Cloud Recommendations AI Write a user event
  method: POST
  name: writeuserevent
  path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/eventStores/{eventStoreId}/userEvents
- description: Google Cloud Recommendations AI Get recommendations
  method: POST
  name: predict
  path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/eventStores/{eventStoreId}/placements/{placementId}:predict
personas: []
provider_name: Google Cloud Recommendations AI
provider_slug: google-cloud-recommendations-ai
search_terms:
- writeuserevent
- google cloud recommendations ai write a user event
- predict
- machine learning
- retail
- cloud
- google cloud recommendations ai create a catalog item
- personalization
- google
- api
- listcatalogitems
- createcatalogitem
- e-commerce
- google cloud recommendations ai get recommendations
- ai
- google cloud
- recommendations
- google cloud recommendations ai list catalog items
slug: google-cloud-recommendations-ai-capability
source_filename: google-cloud-recommendations-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Recommendations AI API\n  description: Delivers personalized product recommendations at scale using machine learning for retail and e-commerce use\n    cases.\n  tags:\n  - Google\n  - Cloud\n  - Recommendations\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-recommendations-ai\n    baseUri: https://recommendationengine.googleapis.com/v1beta1\n    description: Google Cloud Recommendations AI API HTTP API.\n    resources:\n    - name: projects-projectid-locations-location-catalogs-c\n      path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/catalogItems\n      operations:\n      - name: listcatalogitems\n        method: GET\n        description: Google Cloud Recommendations AI List catalog items\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n\
  \        - name: location\n          in: path\n          type: string\n          required: true\n        - name: catalogId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcatalogitem\n        method: POST\n        description: Google Cloud Recommendations AI Create a catalog item\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: catalogId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: projects-projectid-locations-location-catalogs-c\n      path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/eventStores/{eventStoreId}/userEvents\n      operations:\n      - name: writeuserevent\n        method: POST\n        description: Google Cloud Recommendations AI Write a user event\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: catalogId\n          in: path\n          type: string\n          required: true\n        - name: eventStoreId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-catalogs-c\n      path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/eventStores/{eventStoreId}/placements/{placementId}:predict\n\
  \      operations:\n      - name: predict\n        method: POST\n        description: Google Cloud Recommendations AI Get recommendations\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: catalogId\n          in: path\n          type: string\n          required: true\n        - name: eventStoreId\n          in: path\n          type: string\n          required: true\n        - name: placementId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-recommendations-ai-rest\n    description: REST adapter for Google Cloud Recommendations AI API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/catalogItems\n\
  \      name: listcatalogitems\n      operations:\n      - method: GET\n        name: listcatalogitems\n        description: Google Cloud Recommendations AI List catalog items\n        call: google-cloud-recommendations-ai.listcatalogitems\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          catalogId: rest.catalogId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/catalogItems\n      name: createcatalogitem\n      operations:\n      - method: POST\n        name: createcatalogitem\n        description: Google Cloud Recommendations AI Create a catalog item\n        call: google-cloud-recommendations-ai.createcatalogitem\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          catalogId: rest.catalogId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/eventStores/{eventStoreId}/userEvents\n\
  \      name: writeuserevent\n      operations:\n      - method: POST\n        name: writeuserevent\n        description: Google Cloud Recommendations AI Write a user event\n        call: google-cloud-recommendations-ai.writeuserevent\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          catalogId: rest.catalogId\n          eventStoreId: rest.eventStoreId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/catalogs/{catalogId}/eventStores/{eventStoreId}/placements/{placementId}:predict\n      name: predict\n      operations:\n      - method: POST\n        name: predict\n        description: Google Cloud Recommendations AI Get recommendations\n        call: google-cloud-recommendations-ai.predict\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          catalogId: rest.catalogId\n          eventStoreId: rest.eventStoreId\n     \
  \     placementId: rest.placementId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-recommendations-ai-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Recommendations AI API for AI agent use.\n    tools:\n    - name: listcatalogitems\n      description: Google Cloud Recommendations AI List catalog items\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-recommendations-ai.listcatalogitems\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        catalogId: tools.catalogId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name:\
  \ catalogId\n        type: string\n        description: catalogId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcatalogitem\n      description: Google Cloud Recommendations AI Create a catalog item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-recommendations-ai.createcatalogitem\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        catalogId: tools.catalogId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: catalogId\n        type: string\n        description: catalogId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: writeuserevent\n      description: Google Cloud Recommendations AI Write a user event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-recommendations-ai.writeuserevent\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        catalogId: tools.catalogId\n        eventStoreId: tools.eventStoreId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: catalogId\n        type: string\n        description: catalogId\n        required: true\n      - name: eventStoreId\n        type: string\n        description: eventStoreId\n        required: true\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: predict\n      description: Google Cloud Recommendations AI Get recommendations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-recommendations-ai.predict\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        catalogId: tools.catalogId\n        eventStoreId: tools.eventStoreId\n        placementId: tools.placementId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: catalogId\n        type: string\n        description: catalogId\n        required: true\n      - name: eventStoreId\n        type: string\n        description: eventStoreId\n        required: true\n      - name: placementId\n        type: string\n        description: placementId\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-recommendations-ai/refs/heads/main/capabilities/google-cloud-recommendations-ai-capability.yaml
tags:
- Google
- Cloud
- Recommendations
- Ai
- API
tools:
- description: Google Cloud Recommendations AI List catalog items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcatalogitems
- description: Google Cloud Recommendations AI Create a catalog item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcatalogitem
- description: Google Cloud Recommendations AI Write a user event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: writeuserevent
- description: Google Cloud Recommendations AI Get recommendations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: predict
---
