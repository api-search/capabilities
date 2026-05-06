---
categories:
- security
consumed_apis: []
description: Unified workflow for security operations combining code scanning, Dependabot, and secret scanning. Used by security engineers for vulnerability management, dependency auditing, and secret leak remediation.
layout: capability
name: GitHub Security Operations
operations:
- description: List code scanning alerts
  method: GET
  name: listCodeScanningAlertsForRepository
  path: /v1/repositories/{owner}/{repo}/code-scanning/alerts
- description: Get a code scanning alert
  method: GET
  name: getCodeScanningAlert
  path: /v1/repositories/{owner}/{repo}/code-scanning/alerts/{alert_number}
- description: Update a code scanning alert
  method: PATCH
  name: updateCodeScanningAlert
  path: /v1/repositories/{owner}/{repo}/code-scanning/alerts/{alert_number}
- description: List analyses
  method: GET
  name: listCodeScanningAnalysesForRepository
  path: /v1/repositories/{owner}/{repo}/code-scanning/analyses
- description: List Dependabot alerts
  method: GET
  name: listDependabotAlertsForRepository
  path: /v1/repositories/{owner}/{repo}/dependabot/alerts
- description: Get a Dependabot alert
  method: GET
  name: getDependabotAlert
  path: /v1/repositories/{owner}/{repo}/dependabot/alerts/{alert_number}
- description: Update a Dependabot alert
  method: PATCH
  name: updateDependabotAlert
  path: /v1/repositories/{owner}/{repo}/dependabot/alerts/{alert_number}
- description: List secret scanning alerts
  method: GET
  name: listSecretScanningAlertsForRepository
  path: /v1/repositories/{owner}/{repo}/secret-scanning/alerts
- description: Get a secret scanning alert
  method: GET
  name: getSecretScanningAlert
  path: /v1/repositories/{owner}/{repo}/secret-scanning/alerts/{alert_number}
- description: Update a secret scanning alert
  method: PATCH
  name: updateSecretScanningAlert
  path: /v1/repositories/{owner}/{repo}/secret-scanning/alerts/{alert_number}
- description: Check vulnerability alert status
  method: GET
  name: checkIfVulnerabilityAlertsAreEnabledForRepository
  path: /v1/repositories/{owner}/{repo}/vulnerability-alerts
- description: Enable vulnerability alerts
  method: PUT
  name: enableVulnerabilityAlerts
  path: /v1/repositories/{owner}/{repo}/vulnerability-alerts
personas: []
provider_name: GitHub
provider_slug: github
search_terms:
- code scanning
- get a code scanning analysis
- get a code scanning alert
- update a code scanning alert
- list dependabot alerts
- individual dependabot alert
- enable vulnerability alerts
- upload sarif analysis data
- get code scanning default setup configuration
- update default setup
- get dependabot alert
- listCodeScanningAlertsForRepository
- list secret scanning locations
- check vulnerability alerts
- listDependabotAlertsForRepository
- vulnerability management
- list code scanning alerts
- update code scanning alert
- upload sarif
- list code scanning analyses
- listSecretScanningAlertsForRepository
- updateDependabotAlert
- update dependabot alert
- list secret scanning alerts
- get default setup
- list code scanning alerts for a repository
- update secret scanning alert
- get code scanning analysis
- update a dependabot alert
- pipelines
- checkIfVulnerabilityAlertsAreEnabledForRepository
- secret scanning
- getSecretScanningAlert
- security
- software development
- updateCodeScanningAlert
- check vulnerability alert status
- source control
- code scanning alert management
- enableVulnerabilityAlerts
- dependabot alert management
- dependabot
- vulnerability alert settings
- update a dependabot alert (dismiss, reopen)
- secret scanning alert management
- list locations for a secret scanning alert
- disable vulnerability alerts
- t1
- code
- getCodeScanningAlert
- code scanning analyses
- list analyses
- update a code scanning alert (dismiss, reopen)
- get a dependabot alert
- update a secret scanning alert
- get a secret scanning alert
- platform
- individual code scanning alert
- individual secret scanning alert
- update code scanning default setup
- getDependabotAlert
- updateSecretScanningAlert
- update a secret scanning alert (resolve, reopen)
- get secret scanning alert
- check if vulnerability alerts are enabled
- listCodeScanningAnalysesForRepository
- list dependabot secrets
- github
- get code scanning alert
slug: security-operations
source_filename: security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GitHub Security Operations\n  description: Unified workflow for security operations combining code scanning, Dependabot, and secret scanning. Used by\n    security engineers for vulnerability management, dependency auditing, and secret leak remediation.\n  tags:\n  - GitHub\n  - Security\n  - Code Scanning\n  - Dependabot\n  - Secret Scanning\n  - Vulnerability Management\n  personas:\n  - security engineers\n  - application security specialists\n  - compliance officers\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GITHUB_TOKEN: GITHUB_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: github-security\n    baseUri: https://api.github.com\n    description: GitHub REST API for code scanning, Dependabot, and secret scanning.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: code-scanning\n      path: /repos/{owner}/{repo}/code-scanning\n\
  \      description: Code scanning alert and analysis management.\n      operations:\n      - name: listCodeScanningAlertsForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/code-scanning/alerts\n        description: List code scanning alerts for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getCodeScanningAlert\n        method: GET\n        path: /repos/{owner}/{repo}/code-scanning/alerts/{alert_number}\n        description: Get a code scanning alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateCodeScanningAlert\n        method: PATCH\n        path: /repos/{owner}/{repo}/code-scanning/alerts/{alert_number}\n        description: Update a code scanning alert.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n      - name: listInstancesOfCodeScanningAlert\n        method: GET\n        path: /repos/{owner}/{repo}/code-scanning/alerts/{alert_number}/instances\n        description: List instances of a code scanning alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listCodeScanningAnalysesForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/code-scanning/analyses\n        description: List code scanning analyses for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getCodeScanningAnalysisForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/code-scanning/analyses/{analysis_id}\n        description: Get a code scanning analysis.\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n      - name: deleteCodeScanningAnalysisFromRepository\n        method: DELETE\n        path: /repos/{owner}/{repo}/code-scanning/analyses/{analysis_id}\n        description: Delete a code scanning analysis.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getCodeScanningDefaultSetupConfiguration\n        method: GET\n        path: /repos/{owner}/{repo}/code-scanning/default-setup\n        description: Get code scanning default setup configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateCodeScanningDefaultSetupConfiguration\n        method: PATCH\n        path: /repos/{owner}/{repo}/code-scanning/default-setup\n        description: Update code scanning default setup configuration.\n        body:\n          type: json\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadAnAnalysisAsSarifData\n        method: POST\n        path: /repos/{owner}/{repo}/code-scanning/sarifs\n        description: Upload an analysis as SARIF data.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getInformationAboutSarifUpload\n        method: GET\n        path: /repos/{owner}/{repo}/code-scanning/sarifs/{sarif_id}\n        description: Get information about a SARIF upload.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dependabot\n      path: /repos/{owner}/{repo}/dependabot\n      description: Dependabot alert and secret management.\n      operations:\n      - name: listDependabotAlertsForRepository\n        method:\
  \ GET\n        path: /repos/{owner}/{repo}/dependabot/alerts\n        description: List Dependabot alerts for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getDependabotAlert\n        method: GET\n        path: /repos/{owner}/{repo}/dependabot/alerts/{alert_number}\n        description: Get a Dependabot alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateDependabotAlert\n        method: PATCH\n        path: /repos/{owner}/{repo}/dependabot/alerts/{alert_number}\n        description: Update a Dependabot alert.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoryDependabotSecrets\n        method: GET\n        path: /repos/{owner}/{repo}/dependabot/secrets\n\
  \        description: List repository Dependabot secrets.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getRepositoryDependabotSecretsPublicKey\n        method: GET\n        path: /repos/{owner}/{repo}/dependabot/secrets/public-key\n        description: Get a repository Dependabot secrets public key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getRepositoryDependabotSecret\n        method: GET\n        path: /repos/{owner}/{repo}/dependabot/secrets/{secret_name}\n        description: Get a repository Dependabot secret.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createOrUpdateRepositoryDependabotSecret\n        method: PUT\n        path: /repos/{owner}/{repo}/dependabot/secrets/{secret_name}\n     \
  \   description: Create or update a repository Dependabot secret.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteRepositoryDependabotSecret\n        method: DELETE\n        path: /repos/{owner}/{repo}/dependabot/secrets/{secret_name}\n        description: Delete a repository Dependabot secret.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secret-scanning\n      path: /repos/{owner}/{repo}/secret-scanning\n      description: Secret scanning alert management.\n      operations:\n      - name: listSecretScanningAlertsForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/secret-scanning/alerts\n        description: List secret scanning alerts for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n      - name: getSecretScanningAlert\n        method: GET\n        path: /repos/{owner}/{repo}/secret-scanning/alerts/{alert_number}\n        description: Get a secret scanning alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateSecretScanningAlert\n        method: PATCH\n        path: /repos/{owner}/{repo}/secret-scanning/alerts/{alert_number}\n        description: Update a secret scanning alert.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listLocationsForSecretScanningAlert\n        method: GET\n        path: /repos/{owner}/{repo}/secret-scanning/alerts/{alert_number}/locations\n        description: List locations for a secret scanning alert.\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: vulnerability-alerts\n      path: /repos/{owner}/{repo}\n      description: Repository vulnerability alert settings.\n      operations:\n      - name: checkIfVulnerabilityAlertsAreEnabledForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/vulnerability-alerts\n        description: Check if vulnerability alerts are enabled.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enableVulnerabilityAlerts\n        method: PUT\n        path: /repos/{owner}/{repo}/vulnerability-alerts\n        description: Enable vulnerability alerts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disableVulnerabilityAlerts\n        method: DELETE\n        path: /repos/{owner}/{repo}/vulnerability-alerts\n        description: Disable\
  \ vulnerability alerts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: github-security-ops-api\n    description: Unified REST API for security operations combining code scanning, Dependabot, and secret scanning.\n    resources:\n    - path: /v1/repositories/{owner}/{repo}/code-scanning/alerts\n      name: code-scanning-alerts\n      description: Code scanning alert management\n      operations:\n      - method: GET\n        name: listCodeScanningAlertsForRepository\n        description: List code scanning alerts\n        call: github-security.listCodeScanningAlertsForRepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{owner}/{repo}/code-scanning/alerts/{alert_number}\n      name: code-scanning-alert\n      description: Individual code scanning alert\n      operations:\n      - method:\
  \ GET\n        name: getCodeScanningAlert\n        description: Get a code scanning alert\n        call: github-security.getCodeScanningAlert\n        with:\n          alert_number: rest.alert_number\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: updateCodeScanningAlert\n        description: Update a code scanning alert\n        call: github-security.updateCodeScanningAlert\n        with:\n          alert_number: rest.alert_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{owner}/{repo}/code-scanning/analyses\n      name: code-scanning-analyses\n      description: Code scanning analyses\n      operations:\n      - method: GET\n        name: listCodeScanningAnalysesForRepository\n        description: List analyses\n        call: github-security.listCodeScanningAnalysesForRepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/repositories/{owner}/{repo}/dependabot/alerts\n      name: dependabot-alerts\n      description: Dependabot alert management\n      operations:\n      - method: GET\n        name: listDependabotAlertsForRepository\n        description: List Dependabot alerts\n        call: github-security.listDependabotAlertsForRepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{owner}/{repo}/dependabot/alerts/{alert_number}\n      name: dependabot-alert\n      description: Individual Dependabot alert\n      operations:\n      - method: GET\n        name: getDependabotAlert\n        description: Get a Dependabot alert\n        call: github-security.getDependabotAlert\n        with:\n          alert_number: rest.alert_number\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: updateDependabotAlert\n        description: Update a Dependabot alert\n        call: github-security.updateDependabotAlert\n\
  \        with:\n          alert_number: rest.alert_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{owner}/{repo}/secret-scanning/alerts\n      name: secret-scanning-alerts\n      description: Secret scanning alert management\n      operations:\n      - method: GET\n        name: listSecretScanningAlertsForRepository\n        description: List secret scanning alerts\n        call: github-security.listSecretScanningAlertsForRepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{owner}/{repo}/secret-scanning/alerts/{alert_number}\n      name: secret-scanning-alert\n      description: Individual secret scanning alert\n      operations:\n      - method: GET\n        name: getSecretScanningAlert\n        description: Get a secret scanning alert\n        call: github-security.getSecretScanningAlert\n        with:\n          alert_number: rest.alert_number\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: PATCH\n        name: updateSecretScanningAlert\n        description: Update a secret scanning alert\n        call: github-security.updateSecretScanningAlert\n        with:\n          alert_number: rest.alert_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{owner}/{repo}/vulnerability-alerts\n      name: vulnerability-alerts\n      description: Vulnerability alert settings\n      operations:\n      - method: GET\n        name: checkIfVulnerabilityAlertsAreEnabledForRepository\n        description: Check vulnerability alert status\n        call: github-security.checkIfVulnerabilityAlertsAreEnabledForRepository\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: enableVulnerabilityAlerts\n        description: Enable vulnerability alerts\n        call: github-security.enableVulnerabilityAlerts\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9083\n    namespace: github-security-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted security operations.\n    tools:\n    - name: list-code-scanning-alerts\n      description: List code scanning alerts for a repository\n      call: github-security.listCodeScanningAlertsForRepository\n      hints:\n        readOnly: true\n    - name: get-code-scanning-alert\n      description: Get a code scanning alert\n      call: github-security.getCodeScanningAlert\n      hints:\n        readOnly: true\n    - name: update-code-scanning-alert\n      description: Update a code scanning alert (dismiss, reopen)\n      call: github-security.updateCodeScanningAlert\n      hints:\n        idempotent: true\n    - name: list-code-scanning-analyses\n      description: List code scanning analyses\n      call: github-security.listCodeScanningAnalysesForRepository\n      hints:\n        readOnly: true\n    - name:\
  \ get-code-scanning-analysis\n      description: Get a code scanning analysis\n      call: github-security.getCodeScanningAnalysisForRepository\n      hints:\n        readOnly: true\n    - name: upload-sarif\n      description: Upload SARIF analysis data\n      call: github-security.uploadAnAnalysisAsSarifData\n    - name: get-default-setup\n      description: Get code scanning default setup configuration\n      call: github-security.getCodeScanningDefaultSetupConfiguration\n      hints:\n        readOnly: true\n    - name: update-default-setup\n      description: Update code scanning default setup\n      call: github-security.updateCodeScanningDefaultSetupConfiguration\n      hints:\n        idempotent: true\n    - name: list-dependabot-alerts\n      description: List Dependabot alerts\n      call: github-security.listDependabotAlertsForRepository\n      hints:\n        readOnly: true\n    - name: get-dependabot-alert\n      description: Get a Dependabot alert\n      call: github-security.getDependabotAlert\n\
  \      hints:\n        readOnly: true\n    - name: update-dependabot-alert\n      description: Update a Dependabot alert (dismiss, reopen)\n      call: github-security.updateDependabotAlert\n      hints:\n        idempotent: true\n    - name: list-dependabot-secrets\n      description: List Dependabot secrets\n      call: github-security.listRepositoryDependabotSecrets\n      hints:\n        readOnly: true\n    - name: list-secret-scanning-alerts\n      description: List secret scanning alerts\n      call: github-security.listSecretScanningAlertsForRepository\n      hints:\n        readOnly: true\n    - name: get-secret-scanning-alert\n      description: Get a secret scanning alert\n      call: github-security.getSecretScanningAlert\n      hints:\n        readOnly: true\n    - name: update-secret-scanning-alert\n      description: Update a secret scanning alert (resolve, reopen)\n      call: github-security.updateSecretScanningAlert\n      hints:\n        idempotent: true\n    - name:\
  \ list-secret-scanning-locations\n      description: List locations for a secret scanning alert\n      call: github-security.listLocationsForSecretScanningAlert\n      hints:\n        readOnly: true\n    - name: check-vulnerability-alerts\n      description: Check if vulnerability alerts are enabled\n      call: github-security.checkIfVulnerabilityAlertsAreEnabledForRepository\n      hints:\n        readOnly: true\n    - name: enable-vulnerability-alerts\n      description: Enable vulnerability alerts\n      call: github-security.enableVulnerabilityAlerts\n    - name: disable-vulnerability-alerts\n      description: Disable vulnerability alerts\n      call: github-security.disableVulnerabilityAlerts\n      hints:\n        destructive: true\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/security-operations.yaml
tags:
- GitHub
- Security
- Code Scanning
- Dependabot
- Secret Scanning
- Vulnerability Management
tools:
- description: List code scanning alerts for a repository
  hints:
    readOnly: true
  name: list-code-scanning-alerts
- description: Get a code scanning alert
  hints:
    readOnly: true
  name: get-code-scanning-alert
- description: Update a code scanning alert (dismiss, reopen)
  hints:
    idempotent: true
  name: update-code-scanning-alert
- description: List code scanning analyses
  hints:
    readOnly: true
  name: list-code-scanning-analyses
- description: Get a code scanning analysis
  hints:
    readOnly: true
  name: get-code-scanning-analysis
- description: Upload SARIF analysis data
  hints: {}
  name: upload-sarif
- description: Get code scanning default setup configuration
  hints:
    readOnly: true
  name: get-default-setup
- description: Update code scanning default setup
  hints:
    idempotent: true
  name: update-default-setup
- description: List Dependabot alerts
  hints:
    readOnly: true
  name: list-dependabot-alerts
- description: Get a Dependabot alert
  hints:
    readOnly: true
  name: get-dependabot-alert
- description: Update a Dependabot alert (dismiss, reopen)
  hints:
    idempotent: true
  name: update-dependabot-alert
- description: List Dependabot secrets
  hints:
    readOnly: true
  name: list-dependabot-secrets
- description: List secret scanning alerts
  hints:
    readOnly: true
  name: list-secret-scanning-alerts
- description: Get a secret scanning alert
  hints:
    readOnly: true
  name: get-secret-scanning-alert
- description: Update a secret scanning alert (resolve, reopen)
  hints:
    idempotent: true
  name: update-secret-scanning-alert
- description: List locations for a secret scanning alert
  hints:
    readOnly: true
  name: list-secret-scanning-locations
- description: Check if vulnerability alerts are enabled
  hints:
    readOnly: true
  name: check-vulnerability-alerts
- description: Enable vulnerability alerts
  hints: {}
  name: enable-vulnerability-alerts
- description: Disable vulnerability alerts
  hints:
    destructive: true
  name: disable-vulnerability-alerts
---
