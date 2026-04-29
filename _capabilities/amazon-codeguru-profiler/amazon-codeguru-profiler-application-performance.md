---
categories: []
consumed_apis:
- codeguruprofiler
description: Unified workflow for DevOps teams to manage profiling groups, retrieve CPU and heap profile data, and act on performance recommendations for production applications.
layout: capability
name: Amazon CodeGuru Profiler Application Performance Profiling
operations: []
personas: []
provider_name: Amazon CodeGuru Profiler
provider_slug: amazon-codeguru-profiler
search_terms:
- aws
- amazon
- get profile
- DevOps Engineer
- get details about a profiling group
- create profiling group
- list findings reports for a profiling group
- application performance
- describe profiling group
- get recommendations
- Platform Engineer
- developer persona.
- get aggregated profile data
- post agent profile
- list profile collection times for a profiling group
- create a new profiling group
- devops
- profiling
- devops engineer persona.
- platform engineer persona.
- machine learning
- list findings reports
- list profiling groups
- submit profiling agent data
- Developer
- get optimization recommendations for a profiling group
- unified workflow for devops teams to manage profiling groups, retrieve cpu and heap profile data, and act on performance recommendations for productio
- list profile times
- list profiling groups in the account
- unified workflow for devops teams to manage profiling groups, retrieve cpu and heap profile data, an
slug: amazon-codeguru-profiler-application-performance
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon CodeGuru Profiler Application Performance Profiling\n  description: Unified workflow for DevOps teams to manage profiling groups, retrieve CPU and heap profile data, and act on performance recommendations for production applications.\n  tags:\n  - Amazon\n  - AWS\n  - Application Performance\n  - Profiling\n  - DevOps\n  - Machine Learning\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: codeguruprofiler\n    location: ./shared/codeguruprofiler.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: codeguruprofiler-application-performance-api\n    description: Unified REST API for Application Performance Profiling.\n    resources:\n    - path: /v1/listProfilingGroups\n      name: list-profiling-groups\n      description: List\
  \ profiling groups in the account\n    - path: /v1/createProfilingGroup\n      name: create-profiling-group\n      description: Create a new profiling group\n    - path: /v1/describeProfilingGroup\n      name: describe-profiling-group\n      description: Get details about a profiling group\n    - path: /v1/getRecommendations\n      name: get-recommendations\n      description: Get optimization recommendations for a profiling group\n  - type: mcp\n    port: 9090\n    namespace: codeguruprofiler-application-performance-mcp\n    transport: http\n    description: MCP server for AI-assisted Application Performance Profiling.\n    tools:\n    - name: list-profiling-groups\n      description: List profiling groups in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeguruprofiler.listProfilingGroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-profiling-group\n      description: Create a new profiling group\n\
  \      hints:\n        readOnly: false\n        openWorld: true\n      call: codeguruprofiler.createProfilingGroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-profiling-group\n      description: Get details about a profiling group\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeguruprofiler.describeProfilingGroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recommendations\n      description: Get optimization recommendations for a profiling group\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeguruprofiler.getRecommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-profile-times\n      description: List profile collection times for a profiling group\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeguruprofiler.listProfileTimes\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-profile\n      description: Get aggregated profile data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeguruprofiler.getProfile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-agent-profile\n      description: Submit profiling agent data\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codeguruprofiler.postAgentProfile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-findings-reports\n      description: List findings reports for a profiling group\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeguruprofiler.listFindingsReports\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-codeguru-profiler/refs/heads/main/capabilities/amazon-codeguru-profiler-application-performance.yaml
tags:
- Amazon
- AWS
- Application Performance
- Profiling
- DevOps
- Machine Learning
tools:
- description: List profiling groups in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-profiling-groups
- description: Create a new profiling group
  hints:
    openWorld: true
    readOnly: false
  name: create-profiling-group
- description: Get details about a profiling group
  hints:
    openWorld: true
    readOnly: true
  name: describe-profiling-group
- description: Get optimization recommendations for a profiling group
  hints:
    openWorld: true
    readOnly: true
  name: get-recommendations
- description: List profile collection times for a profiling group
  hints:
    openWorld: true
    readOnly: true
  name: list-profile-times
- description: Get aggregated profile data
  hints:
    openWorld: true
    readOnly: true
  name: get-profile
- description: Submit profiling agent data
  hints:
    openWorld: true
    readOnly: false
  name: post-agent-profile
- description: List findings reports for a profiling group
  hints:
    openWorld: true
    readOnly: true
  name: list-findings-reports
---
