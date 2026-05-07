---
categories: []
consumed_apis: []
description: The Cloud Profiler API enables creating, listing, and managing profiling profiles for applications. It supports creating profiles for CPU, heap, wall time, contention, and thread profiling types, and provides access to collected profiling data for performance analysis.
layout: capability
name: Google Cloud Profiler API
operations:
- description: Google Cloud Profiler Create Profile
  method: POST
  name: createprofile
  path: /v2/projects/{projectId}/profiles
- description: Google Cloud Profiler Create Offline Profile
  method: POST
  name: createofflineprofile
  path: /v2/projects/{projectId}/profiles:createOffline
- description: Google Cloud Profiler Update Profile
  method: PATCH
  name: updateprofile
  path: /v2/projects/{projectId}/profiles/{profileId}
- description: Google Cloud Profiler List Profiles
  method: GET
  name: listprofiles
  path: /v2/projects/{projectId}/profiles:list
personas: []
provider_name: Google Cloud Profiler
provider_slug: google-cloud-profiler
search_terms:
- cpu
- google cloud profiler update profile
- api
- google cloud profiler create profile
- createprofile
- profiler
- google cloud profiler list profiles
- flame graphs
- memory
- google cloud profiler create offline profile
- google
- createofflineprofile
- listprofiles
- observability
- cloud
- performance
- profiling
- updateprofile
- google cloud
slug: google-cloud-profiler-capability
source_filename: google-cloud-profiler-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Profiler API\n  description: The Cloud Profiler API enables creating, listing, and managing profiling profiles for applications. It supports\n    creating profiles for CPU, heap, wall time, contention, and thread profiling types, and provides access to collected profiling\n    data for performance analysis.\n  tags:\n  - Google\n  - Cloud\n  - Profiler\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-profiler\n    baseUri: https://cloudprofiler.googleapis.com\n    description: Google Cloud Profiler API HTTP API.\n    resources:\n    - name: v2-projects-projectid-profiles\n      path: /v2/projects/{projectId}/profiles\n      operations:\n      - name: createprofile\n        method: POST\n        description: Google Cloud Profiler Create Profile\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n \
  \         required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-projects-projectid-profiles-createoffline\n      path: /v2/projects/{projectId}/profiles:createOffline\n      operations:\n      - name: createofflineprofile\n        method: POST\n        description: Google Cloud Profiler Create Offline Profile\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-projects-projectid-profiles-profileid\n      path: /v2/projects/{projectId}/profiles/{profileId}\n      operations:\n      - name: updateprofile\n        method: PATCH\n        description: Google Cloud Profiler Update Profile\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n\
  \          required: true\n        - name: profileId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-projects-projectid-profiles-list\n      path: /v2/projects/{projectId}/profiles:list\n      operations:\n      - name: listprofiles\n        method: GET\n        description: Google Cloud Profiler List Profiles\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-profiler-rest\n    description: REST adapter for Google\
  \ Cloud Profiler API.\n    resources:\n    - path: /v2/projects/{projectId}/profiles\n      name: createprofile\n      operations:\n      - method: POST\n        name: createprofile\n        description: Google Cloud Profiler Create Profile\n        call: google-cloud-profiler.createprofile\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{projectId}/profiles:createOffline\n      name: createofflineprofile\n      operations:\n      - method: POST\n        name: createofflineprofile\n        description: Google Cloud Profiler Create Offline Profile\n        call: google-cloud-profiler.createofflineprofile\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{projectId}/profiles/{profileId}\n      name: updateprofile\n      operations:\n      - method: PATCH\n        name: updateprofile\n\
  \        description: Google Cloud Profiler Update Profile\n        call: google-cloud-profiler.updateprofile\n        with:\n          projectId: rest.projectId\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{projectId}/profiles:list\n      name: listprofiles\n      operations:\n      - method: GET\n        name: listprofiles\n        description: Google Cloud Profiler List Profiles\n        call: google-cloud-profiler.listprofiles\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-profiler-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Profiler API for AI agent use.\n    tools:\n    - name: createprofile\n      description: Google Cloud Profiler Create Profile\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: google-cloud-profiler.createprofile\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createofflineprofile\n      description: Google Cloud Profiler Create Offline Profile\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-profiler.createofflineprofile\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateprofile\n      description: Google Cloud Profiler Update Profile\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-profiler.updateprofile\n\
  \      with:\n        projectId: tools.projectId\n        profileId: tools.profileId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: profileId\n        type: string\n        description: profileId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprofiles\n      description: Google Cloud Profiler List Profiles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-profiler.listprofiles\n      with:\n        projectId: tools.projectId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-profiler/refs/heads/main/capabilities/google-cloud-profiler-capability.yaml
tags:
- Google
- Cloud
- Profiler
- API
tools:
- description: Google Cloud Profiler Create Profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprofile
- description: Google Cloud Profiler Create Offline Profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createofflineprofile
- description: Google Cloud Profiler Update Profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateprofile
- description: Google Cloud Profiler List Profiles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprofiles
---
