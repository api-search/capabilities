---
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
- automated compilation, testing, and artifact production.
- access build and test reports
- delete project
- get details about specific builds
- DevOps Engineer
- list report groups
- stop build
- list builds for a specific codebuild project
- build project management and build execution workflows.
- list builds for project
- manages build infrastructure and pipelines.
- update project
- list codebuild test and coverage reports
- build
- manage codebuild build projects
- aws
- devops
- list all builds or builds for a specific project
- list projects
- list all codebuild projects
- list builds
- start build
- get details about specific codebuild projects
- continuous integration and delivery pipeline management.
- amazon
- update an existing codebuild project configuration
- list codebuild report groups
- list reports
- build automation
- get projects
- get builds
- ci/cd
- create a new codebuild build project
- testing
- start a new build for a codebuild project
- stop a running codebuild build
- Developer
- continuous integration
- runs and monitors builds for their projects.
- create project
- start and monitor builds
- delete a codebuild project
slug: amazon-codebuild-cicd
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
