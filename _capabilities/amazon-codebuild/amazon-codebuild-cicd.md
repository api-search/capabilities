---
categories:
- ci-cd
consumed_apis:
- codebuild
description: Unified workflow for DevOps teams to manage build projects, run builds, monitor build status, and integrate with CI/CD pipelines using Amazon CodeBuild.
layout: capability
name: Amazon CodeBuild CI/CD
operations: []
personas: []
provider_name: Amazon CodeBuild
provider_slug: amazon-codebuild
search_terms:
- ci/cd
- list all builds or builds for a specific project
- list all codebuild projects
- continuous integration
- list report groups
- list projects
- get details about specific builds
- start build
- create a new codebuild build project
- list builds for project
- get builds
- continuous integration and delivery pipeline management.
- testing
- stop a running codebuild build
- delete a codebuild project
- list codebuild test and coverage reports
- amazon
- manage codebuild build projects
- build
- aws
- automated compilation, testing, and artifact production.
- start a new build for a codebuild project
- Developer
- list codebuild report groups
- runs and monitors builds for their projects.
- manages build infrastructure and pipelines.
- devops
- stop build
- access build and test reports
- build automation
- list builds
- delete project
- list builds for a specific codebuild project
- build project management and build execution workflows.
- update project
- create project
- update an existing codebuild project configuration
- get projects
- start and monitor builds
- get details about specific codebuild projects
- list reports
- DevOps Engineer
slug: amazon-codebuild-cicd
source_filename: amazon-codebuild-cicd.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon CodeBuild CI/CD\n  description: Unified workflow for DevOps teams to manage build projects, run builds, monitor build status, and integrate with CI/CD pipelines using Amazon CodeBuild.\n  tags:\n  - Amazon\n  - AWS\n  - CI/CD\n  - Build Automation\n  - DevOps\n  - Continuous Integration\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: codebuild\n    location: ./shared/codebuild.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: codebuild-cicd-api\n    description: Unified REST API for CodeBuild CI/CD operations.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Manage CodeBuild build projects\n    - path: /v1/builds\n      name: builds\n      description: Start and monitor builds\n    - path:\
  \ /v1/reports\n      name: reports\n      description: Access build and test reports\n  - type: mcp\n    port: 9090\n    namespace: codebuild-cicd-mcp\n    transport: http\n    description: MCP server for AI-assisted build management.\n    tools:\n    - name: list-projects\n      description: List all CodeBuild projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codebuild.listProjects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-projects\n      description: Get details about specific CodeBuild projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codebuild.batchGetProjects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new CodeBuild build project\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codebuild.createProject\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: update-project\n      description: Update an existing CodeBuild project configuration\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codebuild.updateProject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-project\n      description: Delete a CodeBuild project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: codebuild.deleteProject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-build\n      description: Start a new build for a CodeBuild project\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codebuild.startBuild\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-build\n      description: Stop a running CodeBuild build\n      hints:\n        readOnly: false\n        destructive: false\n        openWorld: false\n      call: codebuild.stopBuild\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-builds\n      description: Get details about specific builds\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codebuild.batchGetBuilds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-builds\n      description: List all builds or builds for a specific project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codebuild.listBuilds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-builds-for-project\n      description: List builds for a specific CodeBuild project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codebuild.listBuildsForProject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-report-groups\n      description: List CodeBuild report groups\n      hints:\n        readOnly: true\n        openWorld: true\n   \
  \   call: codebuild.listReportGroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List CodeBuild test and coverage reports\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codebuild.listReports\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-codebuild/refs/heads/main/capabilities/amazon-codebuild-cicd.yaml
tags:
- Amazon
- AWS
- CI/CD
- Build Automation
- DevOps
- Continuous Integration
tools:
- description: List all CodeBuild projects
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Get details about specific CodeBuild projects
  hints:
    openWorld: true
    readOnly: true
  name: get-projects
- description: Create a new CodeBuild build project
  hints:
    openWorld: false
    readOnly: false
  name: create-project
- description: Update an existing CodeBuild project configuration
  hints:
    openWorld: false
    readOnly: false
  name: update-project
- description: Delete a CodeBuild project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
- description: Start a new build for a CodeBuild project
  hints:
    openWorld: false
    readOnly: false
  name: start-build
- description: Stop a running CodeBuild build
  hints:
    destructive: false
    openWorld: false
    readOnly: false
  name: stop-build
- description: Get details about specific builds
  hints:
    openWorld: true
    readOnly: true
  name: get-builds
- description: List all builds or builds for a specific project
  hints:
    openWorld: true
    readOnly: true
  name: list-builds
- description: List builds for a specific CodeBuild project
  hints:
    openWorld: true
    readOnly: true
  name: list-builds-for-project
- description: List CodeBuild report groups
  hints:
    openWorld: true
    readOnly: true
  name: list-report-groups
- description: List CodeBuild test and coverage reports
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
---
