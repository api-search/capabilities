---
categories: []
consumed_apis:
- sonarcloud
description: Unified workflow capability for AI-assisted code quality analysis using SonarCloud. Enables AI agents to audit projects across an organization, detect security vulnerabilities and bugs, check quality gate status for CI/CD decisions, and retrieve code metrics for engineering reporting. Serves developers, security engineers, and engineering managers using SonarCloud with GitHub, GitLab, Bitbucket, or Azure DevOps.
layout: capability
name: Sonar Cloud Code Quality
operations:
- description: Search for SonarCloud organizations
  method: GET
  name: search-organizations
  path: /v1/organizations
- description: Search projects in an organization
  method: GET
  name: search-projects
  path: /v1/projects
- description: Search code issues
  method: GET
  name: search-issues
  path: /v1/issues
- description: Check if a project passes its quality gate
  method: GET
  name: get-quality-gate-status
  path: /v1/quality-gate-status
- description: Get project code quality metrics
  method: GET
  name: get-component-measures
  path: /v1/measures
personas: []
provider_name: Sonar
provider_slug: sonar
search_terms:
- code quality metrics
- find reliability bugs in a sonarcloud project
- search code issues
- discover sonarcloud organizations connected to devops platforms
- find security issues
- check if a project passes its quality gate — required for ci/cd release decisions
- 'get code quality metrics for a project: coverage, bugs, vulnerabilities, code smells'
- security
- get code metrics
- cloud
- get quality gate status
- search issues
- find bugs
- search all code issues with full filtering (severity, type, status, rule)
- check if a project passes its quality gate
- static analysis
- get component measures
- list quality gates
- organization discovery
- search for sonarcloud organizations
- sonarcloud
- sonar
- search organizations
- list quality gate definitions for a sonarcloud organization
- devops
- get project code quality metrics
- search projects
- ci/cd
- find security vulnerabilities and hotspots in a sonarcloud project
- code issues
- sonarqube
- quality gate results for ci/cd
- search for projects in a sonarcloud organization to audit or monitor
- project discovery
- check quality gate
- search projects in an organization
- code quality
slug: cloud-code-quality
source_filename: cloud-code-quality.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sonar Cloud Code Quality\"\n  description: >-\n    Unified workflow capability for AI-assisted code quality analysis using\n    SonarCloud. Enables AI agents to audit projects across an organization,\n    detect security vulnerabilities and bugs, check quality gate status for\n    CI/CD decisions, and retrieve code metrics for engineering reporting.\n    Serves developers, security engineers, and engineering managers using\n    SonarCloud with GitHub, GitLab, Bitbucket, or Azure DevOps.\n  tags:\n    - CI/CD\n    - Cloud\n    - Code Quality\n    - DevOps\n    - Security\n    - Sonar\n    - SonarCloud\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SONARCLOUD_TOKEN: SONARCLOUD_TOKEN\n\ncapability:\n  consumes:\n    - import: sonarcloud\n      location: ./shared/sonarcloud-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sonar-cloud-quality-api\n \
  \     description: \"Unified REST API for Sonar cloud-based code quality workflows.\"\n      resources:\n        - path: /v1/organizations\n          name: organizations\n          description: \"Organization discovery\"\n          operations:\n            - method: GET\n              name: search-organizations\n              description: \"Search for SonarCloud organizations\"\n              call: \"sonarcloud.search-organizations\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects\n          name: projects\n          description: \"Project discovery\"\n          operations:\n            - method: GET\n              name: search-projects\n              description: \"Search projects in an organization\"\n              call: \"sonarcloud.search-projects\"\n              with:\n                organization: \"rest.organization\"\n                q: \"rest.q\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/issues\n          name: issues\n          description: \"Code issues\"\n          operations:\n            - method: GET\n              name: search-issues\n              description: \"Search code issues\"\n              call: \"sonarcloud.search-issues\"\n              with:\n                organization: \"rest.organization\"\n                componentKeys: \"rest.componentKeys\"\n                severities: \"rest.severities\"\n                types: \"rest.types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/quality-gate-status\n          name: quality-gate-status\n          description: \"Quality gate results for CI/CD\"\n          operations:\n            - method: GET\n              name: get-quality-gate-status\n              description: \"Check if a project passes its quality\
  \ gate\"\n              call: \"sonarcloud.get-quality-gate-status\"\n              with:\n                projectKey: \"rest.projectKey\"\n                branch: \"rest.branch\"\n                pullRequest: \"rest.pullRequest\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/measures\n          name: measures\n          description: \"Code quality metrics\"\n          operations:\n            - method: GET\n              name: get-component-measures\n              description: \"Get project code quality metrics\"\n              call: \"sonarcloud.get-component-measures\"\n              with:\n                component: \"rest.component\"\n                metricKeys: \"rest.metricKeys\"\n                branch: \"rest.branch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sonar-cloud-quality-mcp\n     \
  \ transport: http\n      description: \"MCP server for AI-assisted Sonar cloud code quality analysis and CI/CD governance.\"\n      tools:\n        - name: search-organizations\n          description: \"Discover SonarCloud organizations connected to DevOps platforms\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarcloud.search-organizations\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-projects\n          description: \"Search for projects in a SonarCloud organization to audit or monitor\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarcloud.search-projects\"\n          with:\n            organization: \"tools.organization\"\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-security-issues\n\
  \          description: \"Find security vulnerabilities and hotspots in a SonarCloud project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarcloud.search-issues\"\n          with:\n            organization: \"tools.organization\"\n            componentKeys: \"tools.projectKey\"\n            types: \"VULNERABILITY,SECURITY_HOTSPOT\"\n            statuses: \"OPEN,CONFIRMED,REOPENED\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-bugs\n          description: \"Find reliability bugs in a SonarCloud project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarcloud.search-issues\"\n          with:\n            organization: \"tools.organization\"\n            componentKeys: \"tools.projectKey\"\n            types: \"BUG\"\n            statuses: \"OPEN,CONFIRMED,REOPENED\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: search-issues\n          description: \"Search all code issues with full filtering (severity, type, status, rule)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarcloud.search-issues\"\n          with:\n            organization: \"tools.organization\"\n            componentKeys: \"tools.componentKeys\"\n            severities: \"tools.severities\"\n            types: \"tools.types\"\n            statuses: \"tools.statuses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-quality-gate\n          description: \"Check if a project passes its quality gate — required for CI/CD release decisions\"\n          hints:\n            readOnly: true\n          call: \"sonarcloud.get-quality-gate-status\"\n          with:\n            projectKey: \"tools.projectKey\"\n            branch: \"tools.branch\"\n            pullRequest: \"tools.pullRequest\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-quality-gates\n          description: \"List quality gate definitions for a SonarCloud organization\"\n          hints:\n            readOnly: true\n          call: \"sonarcloud.list-quality-gates\"\n          with:\n            organization: \"tools.organization\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-code-metrics\n          description: \"Get code quality metrics for a project: coverage, bugs, vulnerabilities, code smells\"\n          hints:\n            readOnly: true\n          call: \"sonarcloud.get-component-measures\"\n          with:\n            component: \"tools.projectKey\"\n            metricKeys: \"tools.metricKeys\"\n            branch: \"tools.branch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sonar/refs/heads/main/capabilities/cloud-code-quality.yaml
tags:
- CI/CD
- Cloud
- Code Quality
- DevOps
- Security
- Sonar
- SonarCloud
tools:
- description: Discover SonarCloud organizations connected to DevOps platforms
  hints:
    openWorld: true
    readOnly: true
  name: search-organizations
- description: Search for projects in a SonarCloud organization to audit or monitor
  hints:
    openWorld: true
    readOnly: true
  name: search-projects
- description: Find security vulnerabilities and hotspots in a SonarCloud project
  hints:
    openWorld: true
    readOnly: true
  name: find-security-issues
- description: Find reliability bugs in a SonarCloud project
  hints:
    openWorld: true
    readOnly: true
  name: find-bugs
- description: Search all code issues with full filtering (severity, type, status, rule)
  hints:
    openWorld: true
    readOnly: true
  name: search-issues
- description: Check if a project passes its quality gate — required for CI/CD release decisions
  hints:
    readOnly: true
  name: check-quality-gate
- description: List quality gate definitions for a SonarCloud organization
  hints:
    readOnly: true
  name: list-quality-gates
- description: 'Get code quality metrics for a project: coverage, bugs, vulnerabilities, code smells'
  hints:
    readOnly: true
  name: get-code-metrics
---
