---
categories: []
consumed_apis:
- wg-platform
- wg-endpoint
description: Unified threat response capability combining WatchGuard Cloud Platform account management with Endpoint Security device management, security event monitoring, and risk assessment. Designed for security operations teams responding to endpoint threats, managing device isolation, and reviewing security posture.
layout: capability
name: WatchGuard Endpoint Threat Response
operations:
- description: Get WatchGuard Cloud account details.
  method: GET
  name: get-account
  path: /v1/accounts/{accountId}
- description: List all managed sub-accounts.
  method: GET
  name: get-managed-accounts
  path: /v1/accounts/{accountId}/managed-accounts
- description: List all managed endpoint devices.
  method: GET
  name: list-devices
  path: /v1/devices
- description: Get protection status for all endpoint devices.
  method: GET
  name: get-devices-protection-status
  path: /v1/devices/protection-status
- description: Isolate devices from the network.
  method: POST
  name: isolate-devices
  path: /v1/devices/isolation
- description: Remove network isolation.
  method: POST
  name: remove-device-isolation
  path: /v1/devices/remove-isolation
- description: Start an immediate malware scan.
  method: POST
  name: start-immediate-scan
  path: /v1/devices/scan
- description: Get security overview summary.
  method: GET
  name: get-security-overview
  path: /v1/security/overview/{period}
- description: Get risk summary by severity level.
  method: GET
  name: get-company-risk-summary
  path: /v1/risk/summary
- description: Get detected risks by type.
  method: GET
  name: get-detected-risks
  path: /v1/risk/detected
- description: Activate hardware devices or software licenses.
  method: POST
  name: activate-device-or-license
  path: /v1/activations
- description: List operators for an account.
  method: GET
  name: get-operators
  path: /v1/operators
- description: Create new operator users.
  method: POST
  name: create-operators
  path: /v1/operators
personas: []
provider_name: WatchGuard
provider_slug: watchguard
search_terms:
- sub-accounts managed by a service provider.
- activate device or license
- get company risk summary
- list operators for an account.
- isolate or release endpoint devices.
- remove network isolation.
- get devices protection status
- get detected risks
- watchguard
- create new operator users.
- list all watchguard managed endpoint devices with protection status.
- create new watchguard cloud operator users.
- get detected risks by type.
- security posture overview.
- get watchguard endpoint detected risks broken down by type and device.
- get recent activations
- initiate immediate security scans.
- get watchguard cloud account information and status.
- start an immediate malware scan on watchguard endpoint devices.
- isolate compromised watchguard endpoint devices from the network.
- zero trust
- remove network isolation from devices.
- list watchguard cloud operator users for an account.
- get managed accounts
- get protection status for all endpoint devices.
- get risk summary by severity level.
- network security
- get account
- remove network isolation from watchguard endpoint devices after remediation.
- get a watchguard endpoint security overview for 1, 7, or 30 days.
- watchguard cloud operator management.
- endpoint security
- get security overview
- list devices
- isolate devices from the network.
- list all managed sub-accounts in watchguard cloud.
- mfa
- managed endpoint devices.
- list all managed sub-accounts.
- start immediate scan
- get operators
- get recent watchguard device and license activation history.
- protection status for all managed devices.
- device management
- company-wide risk summary.
- device and license activation.
- cloud security
- remove device isolation
- list all managed endpoint devices.
- firewall
- create operators
- threat response
- activate hardware devices or software licenses.
- get company-wide endpoint security risk summary by severity level.
- isolate devices
- activate watchguard hardware devices or software license keys.
- detected risk details.
- watchguard cloud account information.
- start an immediate malware scan.
- get the protection status of all watchguard managed endpoint devices.
- risk assessment
- get watchguard cloud account details.
- get security overview summary.
slug: endpoint-threat-response
source_filename: endpoint-threat-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WatchGuard Endpoint Threat Response\"\n  description: >-\n    Unified threat response capability combining WatchGuard Cloud Platform account\n    management with Endpoint Security device management, security event monitoring,\n    and risk assessment. Designed for security operations teams responding to\n    endpoint threats, managing device isolation, and reviewing security posture.\n  tags:\n    - WatchGuard\n    - Endpoint Security\n    - Threat Response\n    - Device Management\n    - Risk Assessment\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WATCHGUARD_ACCESS_TOKEN: WATCHGUARD_ACCESS_TOKEN\n      WATCHGUARD_API_KEY: WATCHGUARD_API_KEY\n\ncapability:\n  consumes:\n    - import: wg-platform\n      location: ./shared/cloud-platform.yaml\n    - import: wg-endpoint\n      location: ./shared/endpoint-security.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n    \
  \  namespace: wg-threat-response-api\n      description: \"Unified REST API for WatchGuard endpoint threat response workflows.\"\n      resources:\n        - path: /v1/accounts/{accountId}\n          name: account\n          description: \"WatchGuard Cloud account information.\"\n          operations:\n            - method: GET\n              name: get-account\n              description: \"Get WatchGuard Cloud account details.\"\n              call: \"wg-platform.get-account\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}/managed-accounts\n          name: managed-accounts\n          description: \"Sub-accounts managed by a service provider.\"\n          operations:\n            - method: GET\n              name: get-managed-accounts\n              description: \"List all managed sub-accounts.\"\n              call: \"wg-platform.get-managed-accounts\"\
  \n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices\n          name: devices\n          description: \"Managed endpoint devices.\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List all managed endpoint devices.\"\n              call: \"wg-endpoint.list-devices\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/protection-status\n          name: device-protection-status\n          description: \"Protection status for all managed devices.\"\n          operations:\n            - method: GET\n              name: get-devices-protection-status\n              description: \"Get protection status for all endpoint devices.\"\n       \
  \       call: \"wg-endpoint.get-devices-protection-status\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/isolation\n          name: device-isolation\n          description: \"Isolate or release endpoint devices.\"\n          operations:\n            - method: POST\n              name: isolate-devices\n              description: \"Isolate devices from the network.\"\n              call: \"wg-endpoint.isolate-devices\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/remove-isolation\n          name: device-remove-isolation\n          description: \"Remove network isolation from devices.\"\n          operations:\n            - method: POST\n              name: remove-device-isolation\n   \
  \           description: \"Remove network isolation.\"\n              call: \"wg-endpoint.remove-device-isolation\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/scan\n          name: device-scan\n          description: \"Initiate immediate security scans.\"\n          operations:\n            - method: POST\n              name: start-immediate-scan\n              description: \"Start an immediate malware scan.\"\n              call: \"wg-endpoint.start-immediate-scan\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/security/overview/{period}\n          name: security-overview\n          description: \"Security posture overview.\"\n          operations:\n            - method: GET\n            \
  \  name: get-security-overview\n              description: \"Get security overview summary.\"\n              call: \"wg-endpoint.get-security-overview\"\n              with:\n                accountId: \"rest.accountId\"\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/risk/summary\n          name: risk-summary\n          description: \"Company-wide risk summary.\"\n          operations:\n            - method: GET\n              name: get-company-risk-summary\n              description: \"Get risk summary by severity level.\"\n              call: \"wg-endpoint.get-company-risk-summary\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/risk/detected\n          name: detected-risks\n          description: \"Detected risk details.\"\n \
  \         operations:\n            - method: GET\n              name: get-detected-risks\n              description: \"Get detected risks by type.\"\n              call: \"wg-endpoint.get-detected-risks\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/activations\n          name: activations\n          description: \"Device and license activation.\"\n          operations:\n            - method: POST\n              name: activate-device-or-license\n              description: \"Activate hardware devices or software licenses.\"\n              call: \"wg-platform.activate-device-or-license\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/operators\n          name: operators\n          description: \"WatchGuard Cloud operator management.\"\n          operations:\n          \
  \  - method: GET\n              name: get-operators\n              description: \"List operators for an account.\"\n              call: \"wg-platform.get-operators-by-account\"\n              with:\n                account_id: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-operators\n              description: \"Create new operator users.\"\n              call: \"wg-platform.create-operators\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wg-threat-response-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WatchGuard endpoint threat response.\"\n      tools:\n        - name: get-account\n          description: \"Get WatchGuard Cloud account information and status.\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"wg-platform.get-account\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-managed-accounts\n          description: \"List all managed sub-accounts in WatchGuard Cloud.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wg-platform.get-managed-accounts\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-devices\n          description: \"List all WatchGuard managed endpoint devices with protection status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wg-endpoint.list-devices\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n\
  \        - name: get-devices-protection-status\n          description: \"Get the protection status of all WatchGuard managed endpoint devices.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wg-endpoint.get-devices-protection-status\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: isolate-devices\n          description: \"Isolate compromised WatchGuard endpoint devices from the network.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"wg-endpoint.isolate-devices\"\n          with:\n            accountId: \"tools.accountId\"\n            device_ids: \"tools.device_ids\"\n            customized_message: \"tools.customized_message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: remove-device-isolation\n          description:\
  \ \"Remove network isolation from WatchGuard endpoint devices after remediation.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"wg-endpoint.remove-device-isolation\"\n          with:\n            accountId: \"tools.accountId\"\n            device_ids: \"tools.device_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-immediate-scan\n          description: \"Start an immediate malware scan on WatchGuard endpoint devices.\"\n          hints:\n            readOnly: false\n          call: \"wg-endpoint.start-immediate-scan\"\n          with:\n            accountId: \"tools.accountId\"\n            device_ids: \"tools.device_ids\"\n            task_name: \"tools.task_name\"\n            scan_scope: \"tools.scan_scope\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-security-overview\n          description: \"Get\
  \ a WatchGuard endpoint security overview for 1, 7, or 30 days.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wg-endpoint.get-security-overview\"\n          with:\n            accountId: \"tools.accountId\"\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-company-risk-summary\n          description: \"Get company-wide endpoint security risk summary by severity level.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wg-endpoint.get-company-risk-summary\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-detected-risks\n          description: \"Get WatchGuard endpoint detected risks broken down by type and device.\"\n          hints:\n            readOnly: true\n           \
  \ openWorld: true\n          call: \"wg-endpoint.get-detected-risks\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: activate-device-or-license\n          description: \"Activate WatchGuard hardware devices or software license keys.\"\n          hints:\n            readOnly: false\n          call: \"wg-platform.activate-device-or-license\"\n          with:\n            activations: \"tools.activations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-recent-activations\n          description: \"Get recent WatchGuard device and license activation history.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wg-platform.get-recent-activations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-operators\n\
  \          description: \"List WatchGuard Cloud operator users for an account.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wg-platform.get-operators-by-account\"\n          with:\n            account_id: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-operators\n          description: \"Create new WatchGuard Cloud operator users.\"\n          hints:\n            readOnly: false\n          call: \"wg-platform.create-operators\"\n          with:\n            username: \"tools.username\"\n            accountId: \"tools.accountId\"\n            firstName: \"tools.firstName\"\n            lastName: \"tools.lastName\"\n            email: \"tools.email\"\n            phone: \"tools.phone\"\n            role: \"tools.role\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/watchguard/refs/heads/main/capabilities/endpoint-threat-response.yaml
tags:
- WatchGuard
- Endpoint Security
- Threat Response
- Device Management
- Risk Assessment
tools:
- description: Get WatchGuard Cloud account information and status.
  hints:
    openWorld: true
    readOnly: true
  name: get-account
- description: List all managed sub-accounts in WatchGuard Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: get-managed-accounts
- description: List all WatchGuard managed endpoint devices with protection status.
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: Get the protection status of all WatchGuard managed endpoint devices.
  hints:
    openWorld: true
    readOnly: true
  name: get-devices-protection-status
- description: Isolate compromised WatchGuard endpoint devices from the network.
  hints:
    destructive: true
    readOnly: false
  name: isolate-devices
- description: Remove network isolation from WatchGuard endpoint devices after remediation.
  hints:
    idempotent: true
    readOnly: false
  name: remove-device-isolation
- description: Start an immediate malware scan on WatchGuard endpoint devices.
  hints:
    readOnly: false
  name: start-immediate-scan
- description: Get a WatchGuard endpoint security overview for 1, 7, or 30 days.
  hints:
    openWorld: true
    readOnly: true
  name: get-security-overview
- description: Get company-wide endpoint security risk summary by severity level.
  hints:
    openWorld: true
    readOnly: true
  name: get-company-risk-summary
- description: Get WatchGuard endpoint detected risks broken down by type and device.
  hints:
    openWorld: true
    readOnly: true
  name: get-detected-risks
- description: Activate WatchGuard hardware devices or software license keys.
  hints:
    readOnly: false
  name: activate-device-or-license
- description: Get recent WatchGuard device and license activation history.
  hints:
    openWorld: true
    readOnly: true
  name: get-recent-activations
- description: List WatchGuard Cloud operator users for an account.
  hints:
    openWorld: true
    readOnly: true
  name: get-operators
- description: Create new WatchGuard Cloud operator users.
  hints:
    readOnly: false
  name: create-operators
---
