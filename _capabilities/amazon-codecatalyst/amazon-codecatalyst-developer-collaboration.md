---
categories:
- ci-cd
consumed_apis:
- codecatalyst
description: Unified workflow for development teams to collaborate on projects, manage spaces, workflows, and source repositories using Amazon CodeCatalyst.
layout: capability
name: Amazon CodeCatalyst Developer Collaboration
operations: []
personas: []
provider_name: Amazon CodeCatalyst
provider_slug: amazon-codecatalyst
search_terms:
- team collaboration on code and projects.
- project and workflow management for development teams.
- manage codecatalyst spaces
- source control
- create project
- create source repository
- list workflow runs
- manage projects
- developer tools
- devops
- start workflow run
- aws
- list projects
- continuous integration and deployment workflows.
- manage ci/cd workflows
- start a workflow run
- developer collaboration
- manages ci/cd workflows and project automation.
- list spaces
- Developer
- project management
- list codecatalyst spaces
- create a source repository
- list workflows
- create a cloud dev environment
- writes code and manages repos and dev environments.
- list projects in a space
- amazon
- list dev environments
- ci/cd
- create dev environment
- create a new project
- collaboration
- list source repositories
- list workflows for a project
- DevOps Engineer
slug: amazon-codecatalyst-developer-collaboration
source_filename: amazon-codecatalyst-developer-collaboration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon CodeCatalyst Developer Collaboration\n  description: Unified workflow for development teams to collaborate on projects, manage spaces, workflows, and source repositories using Amazon CodeCatalyst.\n  tags:\n  - Amazon\n  - AWS\n  - Developer Collaboration\n  - CI/CD\n  - Project Management\n  - DevOps\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    CODECATALYST_TOKEN: CODECATALYST_TOKEN\ncapability:\n  consumes:\n  - import: codecatalyst\n    location: ./shared/codecatalyst.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: codecatalyst-collab-api\n    description: Unified REST API for CodeCatalyst collaboration.\n    resources:\n    - path: /v1/spaces\n      name: spaces\n      description: Manage CodeCatalyst spaces\n    - path: /v1/projects\n      name: projects\n      description: Manage projects\n    - path: /v1/workflows\n      name: workflows\n      description: Manage\
  \ CI/CD workflows\n  - type: mcp\n    port: 9090\n    namespace: codecatalyst-collab-mcp\n    transport: http\n    description: MCP server for AI-assisted development collaboration.\n    tools:\n    - name: list-spaces\n      description: List CodeCatalyst spaces\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codecatalyst.listSpaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List projects in a space\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codecatalyst.listProjects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new project\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codecatalyst.createProject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workflows\n      description: List workflows for a project\n     \
  \ hints:\n        readOnly: true\n        openWorld: true\n      call: codecatalyst.listWorkflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-workflow-run\n      description: Start a workflow run\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codecatalyst.startWorkflowRun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workflow-runs\n      description: List workflow runs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codecatalyst.listWorkflowRuns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-source-repositories\n      description: List source repositories\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codecatalyst.listSourceRepositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-source-repository\n      description: Create a source repository\n\
  \      hints:\n        readOnly: false\n        openWorld: false\n      call: codecatalyst.createSourceRepository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dev-environments\n      description: List Dev Environments\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codecatalyst.listDevEnvironments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-dev-environment\n      description: Create a cloud Dev Environment\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codecatalyst.createDevEnvironment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-codecatalyst/refs/heads/main/capabilities/amazon-codecatalyst-developer-collaboration.yaml
tags:
- Amazon
- Developer Collaboration
- CI/CD
- Project Management
- DevOps
tools:
- description: List CodeCatalyst spaces
  hints:
    openWorld: true
    readOnly: true
  name: list-spaces
- description: List projects in a space
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Create a new project
  hints:
    openWorld: false
    readOnly: false
  name: create-project
- description: List workflows for a project
  hints:
    openWorld: true
    readOnly: true
  name: list-workflows
- description: Start a workflow run
  hints:
    openWorld: false
    readOnly: false
  name: start-workflow-run
- description: List workflow runs
  hints:
    openWorld: true
    readOnly: true
  name: list-workflow-runs
- description: List source repositories
  hints:
    openWorld: true
    readOnly: true
  name: list-source-repositories
- description: Create a source repository
  hints:
    openWorld: false
    readOnly: false
  name: create-source-repository
- description: List Dev Environments
  hints:
    openWorld: true
    readOnly: true
  name: list-dev-environments
- description: Create a cloud Dev Environment
  hints:
    openWorld: false
    readOnly: false
  name: create-dev-environment
---
