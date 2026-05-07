---
categories: []
consumed_apis: []
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
- project inventory and analysis status
- check quality gate
- search analysis rules
- devops
- list all quality gate definitions with their metric conditions and thresholds
- search rules
- project quality gate results
- search for all types of code issues with full filtering (severity, type, status, rule)
- quality gate definitions
- code quality
- find code bugs in a project — reliability issues that cause incorrect runtime behavior
- find security vulnerabilities in a project's code
- get code quality metrics for a project
- check if a project passes its quality gate — critical for ci/cd release decisions
- analysis rule catalog
- get system status
- get quality gate pass/fail status for a project
- get code metrics
- search bugs
- list quality gates
- 'get code quality metrics for a project: coverage, bugs, vulnerabilities, code smells, duplications'
- search all analysis rules by language, type, severity, or keyword
- search issues
- server operational status
- get quality gate status
- search for sonarqube projects to audit or monitor code quality
- list all quality gates
- check sonarqube server status
- search projects
- technical debt
- search security rules
- static analysis
- code metrics and measurements
- search vulnerabilities
- find security analysis rules applicable to a language for policy review
- code quality and security issues
- sonarqube
- get component measures
- check sonarqube server version and operational status
- search projects by name or key
- security
- search for bugs, vulnerabilities, and code smells
slug: code-quality-governance
source_filename: code-quality-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SonarQube Code Quality Governance\n  description: Unified workflow capability for AI-assisted code quality governance using SonarQube. Combines issue tracking,\n    quality gate monitoring, code metrics, and rule management into a single workflow for developers, security engineers,\n    and engineering managers. Enables AI agents to audit code quality, detect security vulnerabilities, enforce quality gates\n    in CI/CD, and track technical debt.\n  tags:\n  - Code Quality\n  - DevOps\n  - Security\n  - SonarQube\n  - Static Analysis\n  - Technical Debt\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SONARQUBE_TOKEN: SONARQUBE_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sonarqube\n    baseUri: https://sonarqube.example.com/api\n    description: SonarQube Web API for code quality and security management\n    authentication:\n      type: basic\n      username: '{{SONARQUBE_TOKEN}}'\n\
  \      password: ''\n    resources:\n    - name: projects\n      path: /projects\n      description: Project creation, search, and management\n      operations:\n      - name: search-projects\n        method: GET\n        description: Search for projects on the SonarQube instance\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: p\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: ps\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues\n      path: /issues\n      description: Code issue search and management\n      operations:\n      - name: search-issues\n        method: GET\n        description:\
  \ Search for code issues across projects\n        inputParameters:\n        - name: componentKeys\n          in: query\n          type: string\n          required: false\n          description: Component keys to scope search\n        - name: severities\n          in: query\n          type: string\n          required: false\n          description: Severity filter (INFO, MINOR, MAJOR, CRITICAL, BLOCKER)\n        - name: types\n          in: query\n          type: string\n          required: false\n          description: Issue types (CODE_SMELL, BUG, VULNERABILITY)\n        - name: statuses\n          in: query\n          type: string\n          required: false\n          description: Status filter\n        - name: p\n          in: query\n          type: integer\n          required: false\n        - name: ps\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: quality-gates\n      path: /qualitygates\n      description: Quality gate configuration and status\n      operations:\n      - name: list-quality-gates\n        method: GET\n        description: List all quality gates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-quality-gate-status\n        method: GET\n        description: Get quality gate status for a project\n        inputParameters:\n        - name: projectKey\n          in: query\n          type: string\n          required: false\n        - name: branch\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: measures\n      path: /measures\n      description: Component metrics and measurement data\n      operations:\n      - name: get-component-measures\n\
  \        method: GET\n        description: Get metrics for a specific component\n        inputParameters:\n        - name: component\n          in: query\n          type: string\n          required: true\n        - name: metricKeys\n          in: query\n          type: string\n          required: true\n        - name: branch\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rules\n      path: /rules\n      description: Analysis rule search and configuration\n      operations:\n      - name: search-rules\n        method: GET\n        description: Search for analysis rules\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n        - name: languages\n          in: query\n          type: string\n          required: false\n        - name: types\n          in: query\n\
  \          type: string\n          required: false\n        - name: severities\n          in: query\n          type: string\n          required: false\n        - name: p\n          in: query\n          type: integer\n          required: false\n        - name: ps\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User account management\n      operations:\n      - name: search-users\n        method: GET\n        description: Search for users in the SonarQube instance\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n        - name: p\n          in: query\n          type: integer\n          required: false\n        - name: ps\n          in: query\n          type: integer\n          required: false\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system\n      path: /system\n      description: Server status and health monitoring\n      operations:\n      - name: get-system-status\n        method: GET\n        description: Get SonarQube server status and version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-system-health\n        method: GET\n        description: Get cluster health and node status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sonarqube-governance-api\n    description: Unified REST API for SonarQube code quality governance workflows.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Project inventory and analysis status\n      operations:\n\
  \      - method: GET\n        name: search-projects\n        description: Search projects by name or key\n        call: sonarqube.search-projects\n        with:\n          q: rest.q\n          p: rest.p\n          ps: rest.ps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/issues\n      name: issues\n      description: Code quality and security issues\n      operations:\n      - method: GET\n        name: search-issues\n        description: Search for bugs, vulnerabilities, and code smells\n        call: sonarqube.search-issues\n        with:\n          componentKeys: rest.componentKeys\n          severities: rest.severities\n          types: rest.types\n          statuses: rest.statuses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quality-gates\n      name: quality-gates\n      description: Quality gate definitions\n      operations:\n      - method: GET\n        name: list-quality-gates\n       \
  \ description: List all quality gates\n        call: sonarqube.list-quality-gates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quality-gate-status\n      name: quality-gate-status\n      description: Project quality gate results\n      operations:\n      - method: GET\n        name: get-quality-gate-status\n        description: Get quality gate pass/fail status for a project\n        call: sonarqube.get-quality-gate-status\n        with:\n          projectKey: rest.projectKey\n          branch: rest.branch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/measures\n      name: measures\n      description: Code metrics and measurements\n      operations:\n      - method: GET\n        name: get-component-measures\n        description: Get code quality metrics for a project\n        call: sonarqube.get-component-measures\n        with:\n          component: rest.component\n          metricKeys: rest.metricKeys\n\
  \          branch: rest.branch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rules\n      name: rules\n      description: Analysis rule catalog\n      operations:\n      - method: GET\n        name: search-rules\n        description: Search analysis rules\n        call: sonarqube.search-rules\n        with:\n          q: rest.q\n          languages: rest.languages\n          types: rest.types\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/system/status\n      name: system-status\n      description: Server operational status\n      operations:\n      - method: GET\n        name: get-system-status\n        description: Check SonarQube server status\n        call: sonarqube.get-system-status\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sonarqube-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted SonarQube\
  \ code quality governance and security review.\n    tools:\n    - name: search-projects\n      description: Search for SonarQube projects to audit or monitor code quality\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sonarqube.search-projects\n      with:\n        q: tools.q\n        p: tools.p\n        ps: tools.ps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-bugs\n      description: Find code bugs in a project — reliability issues that cause incorrect runtime behavior\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sonarqube.search-issues\n      with:\n        componentKeys: tools.projectKey\n        types: CODE_SMELL,BUG\n        statuses: OPEN,CONFIRMED,REOPENED\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-vulnerabilities\n      description: Find security vulnerabilities in a project's code\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: sonarqube.search-issues\n      with:\n        componentKeys: tools.projectKey\n        types: VULNERABILITY,SECURITY_HOTSPOT\n        statuses: OPEN,CONFIRMED,REOPENED\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-issues\n      description: Search for all types of code issues with full filtering (severity, type, status, rule)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sonarqube.search-issues\n      with:\n        componentKeys: tools.componentKeys\n        severities: tools.severities\n        types: tools.types\n        statuses: tools.statuses\n        rules: tools.rules\n        p: tools.p\n        ps: tools.ps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-quality-gate\n      description: Check if a project passes its quality gate — critical for CI/CD release decisions\n      hints:\n        readOnly: true\n      call: sonarqube.get-quality-gate-status\n\
  \      with:\n        projectKey: tools.projectKey\n        branch: tools.branch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-quality-gates\n      description: List all quality gate definitions with their metric conditions and thresholds\n      hints:\n        readOnly: true\n      call: sonarqube.list-quality-gates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-code-metrics\n      description: 'Get code quality metrics for a project: coverage, bugs, vulnerabilities, code smells, duplications'\n      hints:\n        readOnly: true\n      call: sonarqube.get-component-measures\n      with:\n        component: tools.projectKey\n        metricKeys: tools.metricKeys\n        branch: tools.branch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-security-rules\n      description: Find security analysis rules applicable to a language for policy review\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: sonarqube.search-rules\n      with:\n        languages: tools.languages\n        types: VULNERABILITY,SECURITY_HOTSPOT\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-rules\n      description: Search all analysis rules by language, type, severity, or keyword\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sonarqube.search-rules\n      with:\n        q: tools.q\n        languages: tools.languages\n        types: tools.types\n        severities: tools.severities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-system-status\n      description: Check SonarQube server version and operational status\n      hints:\n        readOnly: true\n      call: sonarqube.get-system-status\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
