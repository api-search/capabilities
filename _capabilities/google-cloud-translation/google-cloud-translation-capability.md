---
categories: []
consumed_apis: []
description: Dynamically translates text between thousands of language pairs using Google's Neural Machine Translation technology.
layout: capability
name: Google Cloud Translation API
operations:
- description: Google Cloud Translation Translate text
  method: POST
  name: translatetext
  path: /projects/{projectId}/locations/{location}:translateText
- description: Google Cloud Translation Detect language
  method: POST
  name: detectlanguage
  path: /projects/{projectId}/locations/{location}:detectLanguage
- description: Google Cloud Translation Get supported languages
  method: GET
  name: getsupportedlanguages
  path: /projects/{projectId}/locations/{location}/supportedLanguages
- description: Google Cloud Translation List glossaries
  method: GET
  name: listglossaries
  path: /projects/{projectId}/locations/{location}/glossaries
- description: Google Cloud Translation Create a glossary
  method: POST
  name: createglossary
  path: /projects/{projectId}/locations/{location}/glossaries
personas: []
provider_name: Google Cloud Translation
provider_slug: google-cloud-translation
search_terms:
- translatetext
- translation
- google cloud translation translate text
- localization
- detectlanguage
- google cloud translation create a glossary
- machine learning
- createglossary
- google cloud translation list glossaries
- getsupportedlanguages
- google
- google cloud translation get supported languages
- google cloud translation detect language
- google cloud
- listglossaries
- language
- api
- cloud
slug: google-cloud-translation-capability
source_filename: google-cloud-translation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Translation API\n  description: Dynamically translates text between thousands of language pairs using Google's Neural Machine Translation technology.\n  tags:\n  - Google\n  - Cloud\n  - Translation\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-translation\n    baseUri: https://translation.googleapis.com/v3\n    description: Google Cloud Translation API HTTP API.\n    resources:\n    - name: projects-projectid-locations-location-translatet\n      path: /projects/{projectId}/locations/{location}:translateText\n      operations:\n      - name: translatetext\n        method: POST\n        description: Google Cloud Translation Translate text\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-detectlang\n      path: /projects/{projectId}/locations/{location}:detectLanguage\n      operations:\n      - name: detectlanguage\n        method: POST\n        description: Google Cloud Translation Detect language\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-supportedl\n      path: /projects/{projectId}/locations/{location}/supportedLanguages\n      operations:\n      - name: getsupportedlanguages\n        method: GET\n        description: Google Cloud Translation\
  \ Get supported languages\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: displayLanguageCode\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-glossaries\n      path: /projects/{projectId}/locations/{location}/glossaries\n      operations:\n      - name: listglossaries\n        method: GET\n        description: Google Cloud Translation List glossaries\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: createglossary\n        method: POST\n        description: Google Cloud Translation Create a glossary\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-translation-rest\n    description: REST adapter for Google Cloud Translation API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}:translateText\n      name: translatetext\n      operations:\n      - method: POST\n        name: translatetext\n        description: Google Cloud Translation Translate text\n        call: google-cloud-translation.translatetext\n        with:\n  \
  \        projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}:detectLanguage\n      name: detectlanguage\n      operations:\n      - method: POST\n        name: detectlanguage\n        description: Google Cloud Translation Detect language\n        call: google-cloud-translation.detectlanguage\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/supportedLanguages\n      name: getsupportedlanguages\n      operations:\n      - method: GET\n        name: getsupportedlanguages\n        description: Google Cloud Translation Get supported languages\n        call: google-cloud-translation.getsupportedlanguages\n        with:\n          projectId: rest.projectId\n          location: rest.location\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/glossaries\n      name: listglossaries\n      operations:\n      - method: GET\n        name: listglossaries\n        description: Google Cloud Translation List glossaries\n        call: google-cloud-translation.listglossaries\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/glossaries\n      name: createglossary\n      operations:\n      - method: POST\n        name: createglossary\n        description: Google Cloud Translation Create a glossary\n        call: google-cloud-translation.createglossary\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n  \
  \  namespace: google-cloud-translation-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Translation API for AI agent use.\n    tools:\n    - name: translatetext\n      description: Google Cloud Translation Translate text\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-translation.translatetext\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detectlanguage\n      description: Google Cloud Translation Detect language\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-translation.detectlanguage\n\
  \      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsupportedlanguages\n      description: Google Cloud Translation Get supported languages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-translation.getsupportedlanguages\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        displayLanguageCode: tools.displayLanguageCode\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n\
  \      - name: displayLanguageCode\n        type: string\n        description: displayLanguageCode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listglossaries\n      description: Google Cloud Translation List glossaries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-translation.listglossaries\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createglossary\n      description: Google Cloud Translation Create a glossary\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-translation.createglossary\n\
  \      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-translation/refs/heads/main/capabilities/google-cloud-translation-capability.yaml
tags:
- Google
- Cloud
- Translation
- API
tools:
- description: Google Cloud Translation Translate text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: translatetext
- description: Google Cloud Translation Detect language
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: detectlanguage
- description: Google Cloud Translation Get supported languages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsupportedlanguages
- description: Google Cloud Translation List glossaries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listglossaries
- description: Google Cloud Translation Create a glossary
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createglossary
---
