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
- get details about specific builds
- build automation
- list builds
- create a new codebuild build project
- list reports
- ci/cd
- access build and test reports
- continuous integration and delivery pipeline management.
- build
- stop build
- stop a running codebuild build
- create project
- start and monitor builds
- DevOps Engineer
- list codebuild report groups
- automated compilation, testing, and artifact production.
- start build
- continuous integration
- build project management and build execution workflows.
- start a new build for a codebuild project
- list builds for a specific codebuild project
- aws
- update project
- delete project
- runs and monitors builds for their projects.
- manage codebuild build projects
- devops
- list all codebuild projects
- get projects
- amazon
- list builds for project
- delete a codebuild project
- list report groups
- list projects
- manages build infrastructure and pipelines.
- list all builds or builds for a specific project
- Developer
- list codebuild test and coverage reports
- get details about specific codebuild projects
- testing
- update an existing codebuild project configuration
- get builds
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
