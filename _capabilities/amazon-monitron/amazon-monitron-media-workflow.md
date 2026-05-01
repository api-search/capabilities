---
categories: []
consumed_apis:
- monitron
description: Workflow capability for Amazon Monitron media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon Monitron Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon Monitron
provider_slug: amazon-monitron
search_terms:
- Broadcast Engineer
- create project
- get project
- broadcasting
- amazon monitron list project admin users
- media
- media processing
- workflow
- amazon monitron get project admin user
- associate project admin user
- aws media processing and delivery
- amazon monitron create project
- list projects
- delete project
- amazon monitron delete project
- amazon monitron media processing workflow
- get project admin user
- amazon monitron associate project admin user
- update project
- list jobs
- Media Developer
- engineer managing broadcast media workflows
- developer building media processing applications
- manage media processing jobs
- amazon monitron list projects
- aws
- amazon monitron get project
- amazon monitron update project
- list project admin users
slug: amazon-monitron-media-workflow
source_filename: amazon-monitron-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Monitron Workflow\n  description: Workflow capability for Amazon Monitron media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: monitron\n    location: ./shared/monitron.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: monitron-workflow-api\n    description: Unified REST API for Amazon Monitron workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: monitron.list-jobs\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: monitron-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Monitron workflow management.\n    tools:\n    - name: list-projects\n      description: Amazon Monitron List Projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: monitron.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Amazon Monitron Create Project\n      hints:\n        readOnly: false\n        openWorld: true\n      call: monitron.create-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Amazon Monitron Get Project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: monitron.get-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-project\n      description: Amazon Monitron\
  \ Update Project\n      hints:\n        readOnly: false\n        openWorld: true\n      call: monitron.update-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-project\n      description: Amazon Monitron Delete Project\n      hints:\n        readOnly: false\n        openWorld: true\n      call: monitron.delete-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-project-admin-users\n      description: Amazon Monitron List Project Admin Users\n      hints:\n        readOnly: true\n        openWorld: true\n      call: monitron.list-project-admin-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associate-project-admin-user\n      description: Amazon Monitron Associate Project Admin User\n      hints:\n        readOnly: false\n        openWorld: true\n      call: monitron.associate-project-admin-user\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-project-admin-user\n      description: Amazon Monitron Get Project Admin User\n      hints:\n        readOnly: true\n        openWorld: true\n      call: monitron.get-project-admin-user\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-monitron/refs/heads/main/capabilities/amazon-monitron-media-workflow.yaml
tags:
- Media
- Broadcasting
- Workflow
tools:
- description: Amazon Monitron List Projects
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Amazon Monitron Create Project
  hints:
    openWorld: true
    readOnly: false
  name: create-project
- description: Amazon Monitron Get Project
  hints:
    openWorld: true
    readOnly: true
  name: get-project
- description: Amazon Monitron Update Project
  hints:
    openWorld: true
    readOnly: false
  name: update-project
- description: Amazon Monitron Delete Project
  hints:
    openWorld: true
    readOnly: false
  name: delete-project
- description: Amazon Monitron List Project Admin Users
  hints:
    openWorld: true
    readOnly: true
  name: list-project-admin-users
- description: Amazon Monitron Associate Project Admin User
  hints:
    openWorld: true
    readOnly: false
  name: associate-project-admin-user
- description: Amazon Monitron Get Project Admin User
  hints:
    openWorld: true
    readOnly: true
  name: get-project-admin-user
---
