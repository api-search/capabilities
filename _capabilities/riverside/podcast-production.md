---
api_specs:
- filename: riverside-business-openapi.yml
  format: yaml
  label: riverside
  slug: riverside
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/riverside/refs/heads/main/openapi/riverside-business-openapi.yml
categories: []
consumed_apis:
- riverside
description: Unified workflow capability for enterprise podcast and video production using the Riverside Business API. Combines recording management, transcription retrieval, export handling, and webinar registration into workflows for content teams and production managers.
layout: capability
name: Riverside Podcast Production
operations:
- description: List all productions with associated studios and projects
  method: GET
  name: list-productions
  path: /v1/productions
- description: List all recordings with optional studio, project, or date filters
  method: GET
  name: list-recordings
  path: /v1/recordings
- description: Get a recording with tracks and metadata
  method: GET
  name: get-recording
  path: /v1/recordings/{recording-id}
- description: Permanently delete a recording
  method: DELETE
  name: delete-recording
  path: /v1/recordings/{recording-id}
- description: Download transcription file in SRT or TXT format
  method: GET
  name: download-transcription
  path: /v1/recordings/{recording-id}/transcription
- description: List all exports in the workspace
  method: GET
  name: list-exports
  path: /v1/exports
- description: Get details for a specific export
  method: GET
  name: get-export
  path: /v1/exports/{export-id}
- description: Delete an export
  method: DELETE
  name: delete-export
  path: /v1/exports/{export-id}
- description: Register a participant for a webinar
  method: POST
  name: register-participant
  path: /v1/webinars/{webinar-id}/registrants
- description: List all webinar registrants
  method: GET
  name: list-registrants
  path: /v1/webinars/{webinar-id}/registrants
personas: []
provider_name: Riverside
provider_slug: riverside
search_terms:
- get a recording with tracks and metadata
- video
- list all registrants for a webinar session
- register participant
- list recordings, optionally filtered by studio, project, or date range
- retrieve a single recording with tracks and transcription status
- list all workspace productions with their studios and projects
- permanently delete a recording and all its files
- register webinar participant
- get recording
- recording
- individual export
- list all exports in the workspace
- get export
- media
- register a participant for a webinar
- list webinar registrants
- delete recording
- production workspace management
- content creation
- recording management
- download transcription
- transcription file access
- list recordings
- export management
- download transcription file in srt or txt format
- list all recordings with optional studio, project, or date filters
- riverside
- webinar registration
- video recording
- download a recording transcription in srt or txt format
- list all webinar registrants
- delete an export
- permanently delete a recording
- delete export
- get details for a specific export
- list exports
- individual recording
- register a participant for a scheduled webinar
- list registrants
- podcast
- audio
- list productions
- list all productions with associated studios and projects
slug: podcast-production
source_filename: podcast-production.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Riverside Podcast Production\"\n  description: >-\n    Unified workflow capability for enterprise podcast and video production\n    using the Riverside Business API. Combines recording management,\n    transcription retrieval, export handling, and webinar registration into\n    workflows for content teams and production managers.\n  tags:\n    - Podcast\n    - Recording\n    - Media\n    - Content Creation\n    - Riverside\n    - Video\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RIVERSIDE_API_KEY: RIVERSIDE_API_KEY\n\ncapability:\n  consumes:\n    - import: riverside\n      location: ./shared/riverside-business.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: riverside-production-api\n      description: \"Unified REST API for Riverside podcast and video production workflows.\"\n      resources:\n        - path: /v1/productions\n          name: productions\n\
  \          description: \"Production workspace management\"\n          operations:\n            - method: GET\n              name: list-productions\n              description: \"List all productions with associated studios and projects\"\n              call: \"riverside.list-workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recordings\n          name: recordings\n          description: \"Recording management\"\n          operations:\n            - method: GET\n              name: list-recordings\n              description: \"List all recordings with optional studio, project, or date filters\"\n              call: \"riverside.list-all-recordings\"\n              with:\n                studioId: \"rest.studioId\"\n                projectId: \"rest.projectId\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n                page: \"rest.page\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recordings/{recording-id}\n          name: recording-detail\n          description: \"Individual recording\"\n          operations:\n            - method: GET\n              name: get-recording\n              description: \"Get a recording with tracks and metadata\"\n              call: \"riverside.get-recording\"\n              with:\n                recording_id: \"rest.recording-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-recording\n              description: \"Permanently delete a recording\"\n              call: \"riverside.delete-recording\"\n              with:\n                recording_id: \"rest.recording-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recordings/{recording-id}/transcription\n\
  \          name: transcription\n          description: \"Transcription file access\"\n          operations:\n            - method: GET\n              name: download-transcription\n              description: \"Download transcription file in SRT or TXT format\"\n              call: \"riverside.download-transcription-file\"\n              with:\n                recording_id: \"rest.recording-id\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/exports\n          name: exports\n          description: \"Export management\"\n          operations:\n            - method: GET\n              name: list-exports\n              description: \"List all exports in the workspace\"\n              call: \"riverside.list-all-exports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/exports/{export-id}\n          name:\
  \ export-detail\n          description: \"Individual export\"\n          operations:\n            - method: GET\n              name: get-export\n              description: \"Get details for a specific export\"\n              call: \"riverside.get-export\"\n              with:\n                export_id: \"rest.export-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-export\n              description: \"Delete an export\"\n              call: \"riverside.delete-export\"\n              with:\n                export_id: \"rest.export-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/webinars/{webinar-id}/registrants\n          name: webinar-registrants\n          description: \"Webinar registration\"\n          operations:\n            - method: POST\n              name: register-participant\n       \
  \       description: \"Register a participant for a webinar\"\n              call: \"riverside.create-webinar-registrant\"\n              with:\n                webinar_id: \"rest.webinar-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-registrants\n              description: \"List all webinar registrants\"\n              call: \"riverside.get-registrants\"\n              with:\n                webinar_id: \"rest.webinar-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: riverside-production-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Riverside podcast production workflows.\"\n      tools:\n        - name: list-productions\n          description: \"List all workspace productions with their studios and projects\"\n          hints:\n       \
  \     readOnly: true\n            openWorld: false\n          call: \"riverside.list-workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-recordings\n          description: \"List recordings, optionally filtered by studio, project, or date range\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"riverside.list-all-recordings\"\n          with:\n            studioId: \"tools.studioId\"\n            projectId: \"tools.projectId\"\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-recording\n          description: \"Retrieve a single recording with tracks and transcription status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"riverside.get-recording\"\
  \n          with:\n            recording_id: \"tools.recording_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-recording\n          description: \"Permanently delete a recording and all its files\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"riverside.delete-recording\"\n          with:\n            recording_id: \"tools.recording_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: download-transcription\n          description: \"Download a recording transcription in SRT or TXT format\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"riverside.download-transcription-file\"\n          with:\n            recording_id: \"tools.recording_id\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: list-exports\n          description: \"List all exports in the workspace\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"riverside.list-all-exports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-export\n          description: \"Get details for a specific export\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"riverside.get-export\"\n          with:\n            export_id: \"tools.export_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-export\n          description: \"Delete an export\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"riverside.delete-export\"\n          with:\n            export_id: \"tools.export_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: register-webinar-participant\n          description: \"Register a participant for a scheduled webinar\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"riverside.create-webinar-registrant\"\n          with:\n            webinar_id: \"tools.webinar_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-webinar-registrants\n          description: \"List all registrants for a webinar session\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"riverside.get-registrants\"\n          with:\n            webinar_id: \"tools.webinar_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/riverside/refs/heads/main/capabilities/podcast-production.yaml
tags:
- Podcast
- Recording
- Media
- Content Creation
- Riverside
- Video
tools:
- description: List all workspace productions with their studios and projects
  hints:
    openWorld: false
    readOnly: true
  name: list-productions
- description: List recordings, optionally filtered by studio, project, or date range
  hints:
    openWorld: false
    readOnly: true
  name: list-recordings
- description: Retrieve a single recording with tracks and transcription status
  hints:
    openWorld: false
    readOnly: true
  name: get-recording
- description: Permanently delete a recording and all its files
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-recording
- description: Download a recording transcription in SRT or TXT format
  hints:
    openWorld: false
    readOnly: true
  name: download-transcription
- description: List all exports in the workspace
  hints:
    openWorld: false
    readOnly: true
  name: list-exports
- description: Get details for a specific export
  hints:
    openWorld: false
    readOnly: true
  name: get-export
- description: Delete an export
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-export
- description: Register a participant for a scheduled webinar
  hints:
    destructive: false
    readOnly: false
  name: register-webinar-participant
- description: List all registrants for a webinar session
  hints:
    openWorld: false
    readOnly: true
  name: list-webinar-registrants
---
