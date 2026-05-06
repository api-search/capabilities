---
categories: []
consumed_apis: []
description: The Contact Center AI API enables building AI-powered contact center solutions with conversation profiles, participants, conversation analysis, and insights for virtual and human agent interactions.
layout: capability
name: Google Cloud Contact Center AI API
operations:
- description: Google Cloud Contact Center AI List conversations
  method: GET
  name: listconversations
  path: /projects/{projectId}/locations/{location}/conversations
- description: Google Cloud Contact Center AI Create a conversation
  method: POST
  name: createconversation
  path: /projects/{projectId}/locations/{location}/conversations
- description: Google Cloud Contact Center AI Get a conversation
  method: GET
  name: getconversation
  path: /projects/{projectId}/locations/{location}/conversations/{conversationId}
- description: Google Cloud Contact Center AI Update a conversation
  method: PATCH
  name: updateconversation
  path: /projects/{projectId}/locations/{location}/conversations/{conversationId}
- description: Google Cloud Contact Center AI Delete a conversation
  method: DELETE
  name: deleteconversation
  path: /projects/{projectId}/locations/{location}/conversations/{conversationId}
- description: Google Cloud Contact Center AI List analyses
  method: GET
  name: listanalyses
  path: /projects/{projectId}/locations/{location}/conversations/{conversationId}/analyses
- description: Google Cloud Contact Center AI Create an analysis
  method: POST
  name: createanalysis
  path: /projects/{projectId}/locations/{location}/conversations/{conversationId}/analyses
- description: Google Cloud Contact Center AI Export insights data
  method: POST
  name: exportinsightsdata
  path: /projects/{projectId}/locations/{location}/insightsdata:export
personas: []
provider_name: Google Cloud Contact Center AI
provider_slug: google-cloud-contact-center-ai
search_terms:
- google cloud contact center ai export insights data
- contact
- createanalysis
- contact center
- listconversations
- deleteconversation
- listanalyses
- cloud
- getconversation
- google
- center
- ai
- createconversation
- google cloud contact center ai list analyses
- virtual agents
- conversations
- exportinsightsdata
- api
- google cloud contact center ai list conversations
- google cloud contact center ai get a conversation
- google cloud contact center ai create an analysis
- google cloud contact center ai update a conversation
- customer service
- google cloud contact center ai create a conversation
- updateconversation
- google cloud
- google cloud contact center ai delete a conversation
slug: google-cloud-contact-center-ai-capability
source_filename: google-cloud-contact-center-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Contact Center AI API\n  description: The Contact Center AI API enables building AI-powered contact center solutions with conversation profiles,\n    participants, conversation analysis, and insights for virtual and human agent interactions.\n  tags:\n  - Google\n  - Cloud\n  - Contact\n  - Center\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-contact-center-ai\n    baseUri: https://contactcenterinsights.googleapis.com/v1\n    description: Google Cloud Contact Center AI API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_CONTACT_CENTER_AI_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-conversati\n      path: /projects/{projectId}/locations/{location}/conversations\n      operations:\n      - name: listconversations\n        method: GET\n        description: Google Cloud Contact\
  \ Center AI List conversations\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconversation\n        method: POST\n        description: Google Cloud Contact Center AI Create a conversation\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: projects-projectid-locations-location-conversati\n      path: /projects/{projectId}/locations/{location}/conversations/{conversationId}\n      operations:\n      - name: getconversation\n        method: GET\n        description: Google Cloud Contact Center AI Get a conversation\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: conversationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateconversation\n        method: PATCH\n        description: Google Cloud Contact Center AI Update a conversation\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n   \
  \     - name: location\n          in: path\n          type: string\n          required: true\n        - name: conversationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteconversation\n        method: DELETE\n        description: Google Cloud Contact Center AI Delete a conversation\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: conversationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-conversati\n      path: /projects/{projectId}/locations/{location}/conversations/{conversationId}/analyses\n\
  \      operations:\n      - name: listanalyses\n        method: GET\n        description: Google Cloud Contact Center AI List analyses\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: conversationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createanalysis\n        method: POST\n        description: Google Cloud Contact Center AI Create an analysis\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: conversationId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-insightsda\n      path: /projects/{projectId}/locations/{location}/insightsdata:export\n      operations:\n      - name: exportinsightsdata\n        method: POST\n        description: Google Cloud Contact Center AI Export insights data\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-contact-center-ai-rest\n    description: REST adapter for Google Cloud Contact Center AI API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/conversations\n\
  \      name: listconversations\n      operations:\n      - method: GET\n        name: listconversations\n        description: Google Cloud Contact Center AI List conversations\n        call: google-cloud-contact-center-ai.listconversations\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/conversations\n      name: createconversation\n      operations:\n      - method: POST\n        name: createconversation\n        description: Google Cloud Contact Center AI Create a conversation\n        call: google-cloud-contact-center-ai.createconversation\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/conversations/{conversationId}\n      name: getconversation\n   \
  \   operations:\n      - method: GET\n        name: getconversation\n        description: Google Cloud Contact Center AI Get a conversation\n        call: google-cloud-contact-center-ai.getconversation\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          conversationId: rest.conversationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/conversations/{conversationId}\n      name: updateconversation\n      operations:\n      - method: PATCH\n        name: updateconversation\n        description: Google Cloud Contact Center AI Update a conversation\n        call: google-cloud-contact-center-ai.updateconversation\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          conversationId: rest.conversationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/conversations/{conversationId}\n\
  \      name: deleteconversation\n      operations:\n      - method: DELETE\n        name: deleteconversation\n        description: Google Cloud Contact Center AI Delete a conversation\n        call: google-cloud-contact-center-ai.deleteconversation\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          conversationId: rest.conversationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/conversations/{conversationId}/analyses\n      name: listanalyses\n      operations:\n      - method: GET\n        name: listanalyses\n        description: Google Cloud Contact Center AI List analyses\n        call: google-cloud-contact-center-ai.listanalyses\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          conversationId: rest.conversationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/conversations/{conversationId}/analyses\n\
  \      name: createanalysis\n      operations:\n      - method: POST\n        name: createanalysis\n        description: Google Cloud Contact Center AI Create an analysis\n        call: google-cloud-contact-center-ai.createanalysis\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          conversationId: rest.conversationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/insightsdata:export\n      name: exportinsightsdata\n      operations:\n      - method: POST\n        name: exportinsightsdata\n        description: Google Cloud Contact Center AI Export insights data\n        call: google-cloud-contact-center-ai.exportinsightsdata\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-contact-center-ai-mcp\n\
  \    transport: http\n    description: MCP adapter for Google Cloud Contact Center AI API for AI agent use.\n    tools:\n    - name: listconversations\n      description: Google Cloud Contact Center AI List conversations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-contact-center-ai.listconversations\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createconversation\n\
  \      description: Google Cloud Contact Center AI Create a conversation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-contact-center-ai.createconversation\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconversation\n      description: Google Cloud Contact Center AI Get a conversation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-contact-center-ai.getconversation\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        conversationId: tools.conversationId\n      inputParameters:\n\
  \      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: conversationId\n        type: string\n        description: conversationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateconversation\n      description: Google Cloud Contact Center AI Update a conversation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-contact-center-ai.updateconversation\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        conversationId: tools.conversationId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n\
  \      - name: conversationId\n        type: string\n        description: conversationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteconversation\n      description: Google Cloud Contact Center AI Delete a conversation\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-contact-center-ai.deleteconversation\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        conversationId: tools.conversationId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: conversationId\n        type: string\n        description: conversationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listanalyses\n\
  \      description: Google Cloud Contact Center AI List analyses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-contact-center-ai.listanalyses\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        conversationId: tools.conversationId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: conversationId\n        type: string\n        description: conversationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createanalysis\n      description: Google Cloud Contact Center AI Create an analysis\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-contact-center-ai.createanalysis\n\
  \      with:\n        projectId: tools.projectId\n        location: tools.location\n        conversationId: tools.conversationId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: conversationId\n        type: string\n        description: conversationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exportinsightsdata\n      description: Google Cloud Contact Center AI Export insights data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-contact-center-ai.exportinsightsdata\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required:\
  \ true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_CONTACT_CENTER_AI_TOKEN: GOOGLE_CLOUD_CONTACT_CENTER_AI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-contact-center-ai/refs/heads/main/capabilities/google-cloud-contact-center-ai-capability.yaml
tags:
- Google
- Cloud
- Contact
- Center
- Ai
- API
tools:
- description: Google Cloud Contact Center AI List conversations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconversations
- description: Google Cloud Contact Center AI Create a conversation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconversation
- description: Google Cloud Contact Center AI Get a conversation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconversation
- description: Google Cloud Contact Center AI Update a conversation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateconversation
- description: Google Cloud Contact Center AI Delete a conversation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconversation
- description: Google Cloud Contact Center AI List analyses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listanalyses
- description: Google Cloud Contact Center AI Create an analysis
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createanalysis
- description: Google Cloud Contact Center AI Export insights data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exportinsightsdata
---
