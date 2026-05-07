---
categories: []
consumed_apis: []
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
- amazon monitron get project
- amazon monitron get project admin user
- developer building media processing applications
- engineer managing broadcast media workflows
- amazon monitron update project
- amazon monitron associate project admin user
- Media Developer
- list projects
- delete project
- create project
- amazon monitron media processing workflow
- workflow
- amazon monitron create project
- amazon monitron list project admin users
- associate project admin user
- get project admin user
- aws media processing and delivery
- list jobs
- manage media processing jobs
- media
- get project
- media processing
- aws
- broadcasting
- amazon monitron delete project
- amazon monitron list projects
- Broadcast Engineer
- update project
- list project admin users
slug: amazon-monitron-media-workflow
source_filename: amazon-monitron-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Monitron Workflow\n  description: Workflow capability for Amazon Monitron media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: monitron\n    baseUri: https://monitron.us-east-1.amazonaws.com\n    description: Amazon Monitron REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: default\n      path: /\n      description: Amazon Monitron resources\n      operations:\n      - name: list-projects\n        method: GET\n        description: Amazon Monitron List Projects\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of results to return.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: A pagination token.\n      - name: create-project\n        method: POST\n        description: Amazon Monitron Create Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-project\n        method: GET\n        description: Amazon Monitron Get Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: projectName\n\
  \          in: path\n          type: string\n          required: true\n          description: The name of the project.\n      - name: update-project\n        method: PATCH\n        description: Amazon Monitron Update Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: projectName\n          in: path\n          type: string\n          required: true\n          description: The name of the project.\n        body:\n          type: json\n          data: {}\n      - name: delete-project\n        method: DELETE\n        description: Amazon Monitron Delete Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: projectName\n          in: path\n          type: string\n          required: true\n          description: The name of the project.\n      -\
  \ name: list-project-admin-users\n        method: GET\n        description: Amazon Monitron List Project Admin Users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: projectName\n          in: path\n          type: string\n          required: true\n          description: The name of the project.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: Max results.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token.\n      - name: associate-project-admin-user\n        method: POST\n        description: Amazon Monitron Associate Project Admin User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name:\
  \ projectName\n          in: path\n          type: string\n          required: true\n          description: The name of the project.\n        body:\n          type: json\n          data: {}\n      - name: get-project-admin-user\n        method: GET\n        description: Amazon Monitron Get Project Admin User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: projectName\n          in: path\n          type: string\n          required: true\n          description: The name of the project.\n        - name: userArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the user.\n      - name: disassociate-project-admin-user\n        method: DELETE\n        description: Amazon Monitron Disassociate Project Admin User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        inputParameters:\n        - name: projectName\n          in: path\n          type: string\n          required: true\n          description: The name of the project.\n        - name: userArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the user.\n      - name: list-tags-for-resource\n        method: GET\n        description: Amazon Monitron List Tags for Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the resource.\n      - name: tag-resource\n        method: POST\n        description: Amazon Monitron Tag Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n\
  \        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the resource.\n        body:\n          type: json\n          data: {}\n      - name: untag-resource\n        method: DELETE\n        description: Amazon Monitron Untag Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the resource.\n        - name: tagKeys\n          in: query\n          type: array\n          required: true\n          description: Tag keys to remove.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: monitron-workflow-api\n    description: Unified REST API for Amazon Monitron workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing\
  \ jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: monitron.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: monitron-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Monitron workflow management.\n    tools:\n    - name: list-projects\n      description: Amazon Monitron List Projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: monitron.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Amazon Monitron Create Project\n      hints:\n        readOnly: false\n        openWorld: true\n      call: monitron.create-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Amazon Monitron Get Project\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: monitron.get-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-project\n      description: Amazon Monitron Update Project\n      hints:\n        readOnly: false\n        openWorld: true\n      call: monitron.update-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-project\n      description: Amazon Monitron Delete Project\n      hints:\n        readOnly: false\n        openWorld: true\n      call: monitron.delete-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-project-admin-users\n      description: Amazon Monitron List Project Admin Users\n      hints:\n        readOnly: true\n        openWorld: true\n      call: monitron.list-project-admin-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associate-project-admin-user\n      description: Amazon Monitron Associate Project Admin\
  \ User\n      hints:\n        readOnly: false\n        openWorld: true\n      call: monitron.associate-project-admin-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project-admin-user\n      description: Amazon Monitron Get Project Admin User\n      hints:\n        readOnly: true\n        openWorld: true\n      call: monitron.get-project-admin-user\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
