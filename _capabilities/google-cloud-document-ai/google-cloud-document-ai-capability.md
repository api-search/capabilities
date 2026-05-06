---
categories: []
consumed_apis: []
description: Processes documents to extract structured data from unstructured and semi-structured content using machine learning.
layout: capability
name: Google Cloud Document AI API
operations:
- description: Google Cloud Document AI List processors
  method: GET
  name: listprocessors
  path: /projects/{projectId}/locations/{location}/processors
- description: Google Cloud Document AI Create a processor
  method: POST
  name: createprocessor
  path: /projects/{projectId}/locations/{location}/processors
- description: Google Cloud Document AI Process a document
  method: POST
  name: processdocument
  path: /projects/{projectId}/locations/{location}/processors/{processorId}:process
- description: Google Cloud Document AI Batch process documents
  method: POST
  name: batchprocessdocuments
  path: /projects/{projectId}/locations/{location}/processors/{processorId}:batchProcess
- description: Google Cloud Document AI List processor types
  method: GET
  name: listprocessortypes
  path: /projects/{projectId}/locations/{location}/processorTypes
personas: []
provider_name: Google Cloud Document AI
provider_slug: google-cloud-document-ai
search_terms:
- google cloud document ai batch process documents
- google cloud document ai create a processor
- document processing
- processdocument
- cloud
- data extraction
- google
- ai
- document
- google cloud document ai process a document
- batchprocessdocuments
- machine learning
- api
- listprocessors
- forms
- google cloud document ai list processors
- createprocessor
- google cloud document ai list processor types
- ocr
- google cloud
- listprocessortypes
slug: google-cloud-document-ai-capability
source_filename: google-cloud-document-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Document AI API\n  description: Processes documents to extract structured data from unstructured and semi-structured content using machine\n    learning.\n  tags:\n  - Google\n  - Cloud\n  - Document\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-document-ai\n    baseUri: https://documentai.googleapis.com/v1\n    description: Google Cloud Document AI API HTTP API.\n    resources:\n    - name: projects-projectid-locations-location-processors\n      path: /projects/{projectId}/locations/{location}/processors\n      operations:\n      - name: listprocessors\n        method: GET\n        description: Google Cloud Document AI List processors\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n    \
  \      required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprocessor\n        method: POST\n        description: Google Cloud Document AI Create a processor\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-processors\n      path: /projects/{projectId}/locations/{location}/processors/{processorId}:process\n      operations:\n      - name: processdocument\n        method: POST\n        description: Google Cloud Document AI Process a document\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n\
  \          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: processorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-processors\n      path: /projects/{projectId}/locations/{location}/processors/{processorId}:batchProcess\n      operations:\n      - name: batchprocessdocuments\n        method: POST\n        description: Google Cloud Document AI Batch process documents\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: processorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-processort\n      path: /projects/{projectId}/locations/{location}/processorTypes\n      operations:\n      - name: listprocessortypes\n        method: GET\n        description: Google Cloud Document AI List processor types\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-document-ai-rest\n    description: REST adapter for Google Cloud Document AI API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/processors\n      name: listprocessors\n      operations:\n\
  \      - method: GET\n        name: listprocessors\n        description: Google Cloud Document AI List processors\n        call: google-cloud-document-ai.listprocessors\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/processors\n      name: createprocessor\n      operations:\n      - method: POST\n        name: createprocessor\n        description: Google Cloud Document AI Create a processor\n        call: google-cloud-document-ai.createprocessor\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/processors/{processorId}:process\n      name: processdocument\n      operations:\n      - method: POST\n        name: processdocument\n        description: Google\
  \ Cloud Document AI Process a document\n        call: google-cloud-document-ai.processdocument\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          processorId: rest.processorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/processors/{processorId}:batchProcess\n      name: batchprocessdocuments\n      operations:\n      - method: POST\n        name: batchprocessdocuments\n        description: Google Cloud Document AI Batch process documents\n        call: google-cloud-document-ai.batchprocessdocuments\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          processorId: rest.processorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/processorTypes\n      name: listprocessortypes\n      operations:\n      - method: GET\n        name: listprocessortypes\n\
  \        description: Google Cloud Document AI List processor types\n        call: google-cloud-document-ai.listprocessortypes\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-document-ai-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Document AI API for AI agent use.\n    tools:\n    - name: listprocessors\n      description: Google Cloud Document AI List processors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-document-ai.listprocessors\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createprocessor\n      description: Google Cloud Document AI Create a processor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-document-ai.createprocessor\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: processdocument\n      description: Google Cloud Document AI Process a document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-document-ai.processdocument\n      with:\n        projectId: tools.projectId\n\
  \        location: tools.location\n        processorId: tools.processorId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: processorId\n        type: string\n        description: processorId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batchprocessdocuments\n      description: Google Cloud Document AI Batch process documents\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-document-ai.batchprocessdocuments\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        processorId: tools.processorId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name:\
  \ location\n        type: string\n        description: location\n        required: true\n      - name: processorId\n        type: string\n        description: processorId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprocessortypes\n      description: Google Cloud Document AI List processor types\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-document-ai.listprocessortypes\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-document-ai/refs/heads/main/capabilities/google-cloud-document-ai-capability.yaml
tags:
- Google
- Cloud
- Document
- Ai
- API
tools:
- description: Google Cloud Document AI List processors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprocessors
- description: Google Cloud Document AI Create a processor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprocessor
- description: Google Cloud Document AI Process a document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: processdocument
- description: Google Cloud Document AI Batch process documents
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchprocessdocuments
- description: Google Cloud Document AI List processor types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprocessortypes
---
