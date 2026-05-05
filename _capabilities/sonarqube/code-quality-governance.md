---
api_specs:
- filename: sonarqube-web-api-openapi.yml
  format: yaml
  label: sonarqube
  slug: sonarqube
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sonarqube/refs/heads/main/openapi/sonarqube-web-api-openapi.yml
categories: []
consumed_apis:
- sonarqube
description: Unified workflow capability for AI-assisted code quality governance using SonarQube. Combines issue tracking, quality gate monitoring, code metrics, and rule management into a single workflow for developers, security engineers, and engineering managers. Enables AI agents to audit code quality, detect security vulnerabilities, enforce quality gates in CI/CD, and track technical debt.
layout: capability
name: SonarQube Code Quality Governance
operations:
- description: Search projects by name or key
  method: GET
  name: search-projects
  path: /v1/projects
- description: Search for bugs, vulnerabilities, and code smells
  method: GET
  name: search-issues
  path: /v1/issues
- description: List all quality gates
  method: GET
  name: list-quality-gates
  path: /v1/quality-gates
- description: Get quality gate pass/fail status for a project
  method: GET
  name: get-quality-gate-status
  path: /v1/quality-gate-status
- description: Get code quality metrics for a project
  method: GET
  name: get-component-measures
  path: /v1/measures
- description: Search analysis rules
  method: GET
  name: search-rules
  path: /v1/rules
- description: Check SonarQube server status
  method: GET
  name: get-system-status
  path: /v1/system/status
personas: []
provider_name: SonarQube
provider_slug: sonarqube
search_terms:
- list all quality gates
- find code bugs in a project — reliability issues that cause incorrect runtime behavior
- security
- get code metrics
- search analysis rules
- find security analysis rules applicable to a language for policy review
- search security rules
- search projects by name or key
- get code quality metrics for a project
- quality gate definitions
- analysis rule catalog
- list all quality gate definitions with their metric conditions and thresholds
- get quality gate status
- search bugs
- search issues
- find security vulnerabilities in a project's code
- code metrics and measurements
- search rules
- technical debt
- static analysis
- project inventory and analysis status
- get component measures
- list quality gates
- code quality and security issues
- check if a project passes its quality gate — critical for ci/cd release decisions
- get quality gate pass/fail status for a project
- project quality gate results
- get system status
- devops
- 'get code quality metrics for a project: coverage, bugs, vulnerabilities, code smells, duplications'
- search for all types of code issues with full filtering (severity, type, status, rule)
- search projects
- search all analysis rules by language, type, severity, or keyword
- check sonarqube server status
- search vulnerabilities
- search for sonarqube projects to audit or monitor code quality
- sonarqube
- check sonarqube server version and operational status
- server operational status
- check quality gate
- search for bugs, vulnerabilities, and code smells
- code quality
slug: code-quality-governance
source_filename: code-quality-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SonarQube Code Quality Governance\"\n  description: >-\n    Unified workflow capability for AI-assisted code quality governance using\n    SonarQube. Combines issue tracking, quality gate monitoring, code metrics,\n    and rule management into a single workflow for developers, security engineers,\n    and engineering managers. Enables AI agents to audit code quality, detect\n    security vulnerabilities, enforce quality gates in CI/CD, and track technical debt.\n  tags:\n    - Code Quality\n    - DevOps\n    - Security\n    - SonarQube\n    - Static Analysis\n    - Technical Debt\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SONARQUBE_TOKEN: SONARQUBE_TOKEN\n\ncapability:\n  consumes:\n    - import: sonarqube\n      location: ./shared/sonarqube-web-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sonarqube-governance-api\n      description: \"\
  Unified REST API for SonarQube code quality governance workflows.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: \"Project inventory and analysis status\"\n          operations:\n            - method: GET\n              name: search-projects\n              description: \"Search projects by name or key\"\n              call: \"sonarqube.search-projects\"\n              with:\n                q: \"rest.q\"\n                p: \"rest.p\"\n                ps: \"rest.ps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/issues\n          name: issues\n          description: \"Code quality and security issues\"\n          operations:\n            - method: GET\n              name: search-issues\n              description: \"Search for bugs, vulnerabilities, and code smells\"\n              call: \"sonarqube.search-issues\"\n              with:\n                componentKeys:\
  \ \"rest.componentKeys\"\n                severities: \"rest.severities\"\n                types: \"rest.types\"\n                statuses: \"rest.statuses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/quality-gates\n          name: quality-gates\n          description: \"Quality gate definitions\"\n          operations:\n            - method: GET\n              name: list-quality-gates\n              description: \"List all quality gates\"\n              call: \"sonarqube.list-quality-gates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/quality-gate-status\n          name: quality-gate-status\n          description: \"Project quality gate results\"\n          operations:\n            - method: GET\n              name: get-quality-gate-status\n              description: \"Get quality gate pass/fail status for a project\"\n        \
  \      call: \"sonarqube.get-quality-gate-status\"\n              with:\n                projectKey: \"rest.projectKey\"\n                branch: \"rest.branch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/measures\n          name: measures\n          description: \"Code metrics and measurements\"\n          operations:\n            - method: GET\n              name: get-component-measures\n              description: \"Get code quality metrics for a project\"\n              call: \"sonarqube.get-component-measures\"\n              with:\n                component: \"rest.component\"\n                metricKeys: \"rest.metricKeys\"\n                branch: \"rest.branch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/rules\n          name: rules\n          description: \"Analysis rule catalog\"\n          operations:\n            - method:\
  \ GET\n              name: search-rules\n              description: \"Search analysis rules\"\n              call: \"sonarqube.search-rules\"\n              with:\n                q: \"rest.q\"\n                languages: \"rest.languages\"\n                types: \"rest.types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/system/status\n          name: system-status\n          description: \"Server operational status\"\n          operations:\n            - method: GET\n              name: get-system-status\n              description: \"Check SonarQube server status\"\n              call: \"sonarqube.get-system-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sonarqube-governance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SonarQube code quality governance and security\
  \ review.\"\n      tools:\n        - name: search-projects\n          description: \"Search for SonarQube projects to audit or monitor code quality\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarqube.search-projects\"\n          with:\n            q: \"tools.q\"\n            p: \"tools.p\"\n            ps: \"tools.ps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-bugs\n          description: \"Find code bugs in a project — reliability issues that cause incorrect runtime behavior\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarqube.search-issues\"\n          with:\n            componentKeys: \"tools.projectKey\"\n            types: \"CODE_SMELL,BUG\"\n            statuses: \"OPEN,CONFIRMED,REOPENED\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-vulnerabilities\n\
  \          description: \"Find security vulnerabilities in a project's code\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarqube.search-issues\"\n          with:\n            componentKeys: \"tools.projectKey\"\n            types: \"VULNERABILITY,SECURITY_HOTSPOT\"\n            statuses: \"OPEN,CONFIRMED,REOPENED\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-issues\n          description: \"Search for all types of code issues with full filtering (severity, type, status, rule)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarqube.search-issues\"\n          with:\n            componentKeys: \"tools.componentKeys\"\n            severities: \"tools.severities\"\n            types: \"tools.types\"\n            statuses: \"tools.statuses\"\n            rules: \"tools.rules\"\n            p: \"tools.p\"\n            ps:\
  \ \"tools.ps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-quality-gate\n          description: \"Check if a project passes its quality gate — critical for CI/CD release decisions\"\n          hints:\n            readOnly: true\n          call: \"sonarqube.get-quality-gate-status\"\n          with:\n            projectKey: \"tools.projectKey\"\n            branch: \"tools.branch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-quality-gates\n          description: \"List all quality gate definitions with their metric conditions and thresholds\"\n          hints:\n            readOnly: true\n          call: \"sonarqube.list-quality-gates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-code-metrics\n          description: \"Get code quality metrics for a project: coverage, bugs, vulnerabilities,\
  \ code smells, duplications\"\n          hints:\n            readOnly: true\n          call: \"sonarqube.get-component-measures\"\n          with:\n            component: \"tools.projectKey\"\n            metricKeys: \"tools.metricKeys\"\n            branch: \"tools.branch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-security-rules\n          description: \"Find security analysis rules applicable to a language for policy review\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sonarqube.search-rules\"\n          with:\n            languages: \"tools.languages\"\n            types: \"VULNERABILITY,SECURITY_HOTSPOT\"\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-rules\n          description: \"Search all analysis rules by language, type, severity, or keyword\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"sonarqube.search-rules\"\n          with:\n            q: \"tools.q\"\n            languages: \"tools.languages\"\n            types: \"tools.types\"\n            severities: \"tools.severities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-system-status\n          description: \"Check SonarQube server version and operational status\"\n          hints:\n            readOnly: true\n          call: \"sonarqube.get-system-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sonarqube/refs/heads/main/capabilities/code-quality-governance.yaml
tags:
- Code Quality
- DevOps
- Security
- SonarQube
- Static Analysis
- Technical Debt
tools:
- description: Search for SonarQube projects to audit or monitor code quality
  hints:
    openWorld: true
    readOnly: true
  name: search-projects
- description: Find code bugs in a project — reliability issues that cause incorrect runtime behavior
  hints:
    openWorld: true
    readOnly: true
  name: search-bugs
- description: Find security vulnerabilities in a project's code
  hints:
    openWorld: true
    readOnly: true
  name: search-vulnerabilities
- description: Search for all types of code issues with full filtering (severity, type, status, rule)
  hints:
    openWorld: true
    readOnly: true
  name: search-issues
- description: Check if a project passes its quality gate — critical for CI/CD release decisions
  hints:
    readOnly: true
  name: check-quality-gate
- description: List all quality gate definitions with their metric conditions and thresholds
  hints:
    readOnly: true
  name: list-quality-gates
- description: 'Get code quality metrics for a project: coverage, bugs, vulnerabilities, code smells, duplications'
  hints:
    readOnly: true
  name: get-code-metrics
- description: Find security analysis rules applicable to a language for policy review
  hints:
    openWorld: true
    readOnly: true
  name: search-security-rules
- description: Search all analysis rules by language, type, severity, or keyword
  hints:
    openWorld: true
    readOnly: true
  name: search-rules
- description: Check SonarQube server version and operational status
  hints:
    readOnly: true
  name: get-system-status
---
