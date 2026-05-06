---
categories: []
consumed_apis: []
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
- create new operator users.
- get recent watchguard device and license activation history.
- start an immediate malware scan on watchguard endpoint devices.
- managed endpoint devices.
- get operators
- get the protection status of all watchguard managed endpoint devices.
- sub-accounts managed by a service provider.
- detected risk details.
- risk assessment
- list all managed sub-accounts.
- security posture overview.
- threat response
- remove network isolation.
- device and license activation.
- firewall
- watchguard cloud account information.
- device management
- isolate devices
- watchguard cloud operator management.
- initiate immediate security scans.
- activate hardware devices or software licenses.
- isolate compromised watchguard endpoint devices from the network.
- get watchguard endpoint detected risks broken down by type and device.
- list devices
- get risk summary by severity level.
- mfa
- create new watchguard cloud operator users.
- get watchguard cloud account details.
- get security overview summary.
- start an immediate malware scan.
- protection status for all managed devices.
- cloud security
- network security
- get detected risks by type.
- get a watchguard endpoint security overview for 1, 7, or 30 days.
- get company-wide endpoint security risk summary by severity level.
- list all managed endpoint devices.
- remove network isolation from watchguard endpoint devices after remediation.
- zero trust
- watchguard
- endpoint security
- get detected risks
- list all watchguard managed endpoint devices with protection status.
- remove network isolation from devices.
- get security overview
- get company risk summary
- list all managed sub-accounts in watchguard cloud.
- get protection status for all endpoint devices.
- list operators for an account.
- get devices protection status
- company-wide risk summary.
- isolate or release endpoint devices.
- remove device isolation
- activate device or license
- get watchguard cloud account information and status.
- list watchguard cloud operator users for an account.
- start immediate scan
- get account
- activate watchguard hardware devices or software license keys.
- isolate devices from the network.
- get recent activations
- get managed accounts
- create operators
slug: endpoint-threat-response
source_filename: endpoint-threat-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WatchGuard Endpoint Threat Response\n  description: Unified threat response capability combining WatchGuard Cloud Platform account management with Endpoint Security\n    device management, security event monitoring, and risk assessment. Designed for security operations teams responding to\n    endpoint threats, managing device isolation, and reviewing security posture.\n  tags:\n  - WatchGuard\n  - Endpoint Security\n  - Threat Response\n  - Device Management\n  - Risk Assessment\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WATCHGUARD_ACCESS_TOKEN: WATCHGUARD_ACCESS_TOKEN\n    WATCHGUARD_API_KEY: WATCHGUARD_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: wg-platform\n    baseUri: https://api.usa.cloud.watchguard.com/rest\n    description: WatchGuard Cloud Platform API.\n    authentication:\n      type: bearer\n      token: '{{WATCHGUARD_ACCESS_TOKEN}}'\n    resources:\n  \
  \  - name: accounts\n      path: /platform/accounts/v1/accounts/{accountId}\n      description: WatchGuard Cloud account management.\n      operations:\n      - name: get-account\n        method: GET\n        description: Get account information.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new managed account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Parent account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            type: '{{tools.type}}'\n            name: '{{tools.name}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n      - name: delete-account\n        method: DELETE\n        description: Delete a managed account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        - name: force\n          in: query\n          type: boolean\n          required: false\n          description: Also delete all sub-accounts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: managed-accounts\n      path: /platform/accounts/v1/accounts/{accountId}/children\n      description: Managed sub-accounts.\n      operations:\n      - name: get-managed-accounts\n        method: GET\n        description: List managed\
  \ accounts under the specified account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        - name: type\n          in: query\n          type: integer\n          required: false\n          description: Filter by account type.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authorization\n      path: /platform/authorization/v1/audiences\n      description: Get audience tokens for managed account API access.\n      operations:\n      - name: get-audience\n        method: POST\n        description:\
  \ Get audience token to access a managed account's APIs.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.accountId}}'\n    - name: activations\n      path: /platform/activation/v1/activate\n      description: Activate hardware devices and software licenses.\n      operations:\n      - name: activate-device-or-license\n        method: POST\n        description: Activate one or more devices or license keys.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            activations: '{{tools.activations}}'\n    - name: recent-activations\n      path: /platform/activation/v1/recentactivations\n      description: Recent activation history.\n\
  \      operations:\n      - name: get-recent-activations\n        method: GET\n        description: Get recent activation batch history.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operators\n      path: /platform/operator-mgmt/v1/operators\n      description: WatchGuard Cloud operator management.\n      operations:\n      - name: create-operators\n        method: POST\n        description: Create new operator users.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n      \
  \    type: json\n          data:\n            username: '{{tools.username}}'\n            accountId: '{{tools.accountId}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n            role: '{{tools.role}}'\n      - name: get-operators-by-account\n        method: GET\n        description: List all operators for an account.\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: wg-endpoint\n    baseUri: https://api.usa.cloud.watchguard.com/rest/endpoint-security/management/api/v1\n    description: WatchGuard Endpoint Security Management API.\n    authentication:\n      type: bearer\n      token:\
  \ '{{WATCHGUARD_ACCESS_TOKEN}}'\n    resources:\n    - name: devices\n      path: /accounts/{accountId}/devices\n      description: Managed endpoint devices.\n      operations:\n      - name: list-devices\n        method: GET\n        description: List all managed endpoint devices.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Number of records to return.\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Records to skip.\n        - name: $search\n          in: query\n          type: string\n          required: false\n          description: Text search.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: device-protection-status\n      path: /accounts/{accountId}/devicesprotectionstatus\n      description: Protection status for all devices.\n      operations:\n      - name: get-devices-protection-status\n        method: GET\n        description: Get protection status for all managed devices.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-isolation\n      path: /accounts/{accountId}/devices/isolation\n      description: Isolate devices from network communication.\n      operations:\n      - name: isolate-devices\n        method: POST\n        description: Isolate specified devices from the network.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n  \
  \        required: true\n          description: WatchGuard Cloud account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            device_ids: '{{tools.device_ids}}'\n            customized_message: '{{tools.customized_message}}'\n    - name: device-no-isolation\n      path: /accounts/{accountId}/devices/noisolation\n      description: Remove device isolation.\n      operations:\n      - name: remove-device-isolation\n        method: POST\n        description: Remove network isolation from devices.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            device_ids: '{{tools.device_ids}}'\n    - name: security-overview\n      path: /accounts/{accountId}/securityoverview/{period}\n      description: Security overview summary.\n      operations:\n      - name: get-security-overview\n        method: GET\n        description: Get security overview for 1, 7, or 30 days.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        - name: period\n          in: path\n          type: integer\n          required: true\n          description: Period in days (1, 7, or 30).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: risk-summary\n      path: /accounts/{accountId}/riskassessment/companyrisksummary\n      description: Company-wide risk assessment summary.\n      operations:\n      - name: get-company-risk-summary\n    \
  \    method: GET\n        description: Get company risk summary by severity.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: detected-risks\n      path: /accounts/{accountId}/riskassessment/detectedrisks\n      description: Detected risk counts by type.\n      operations:\n      - name: get-detected-risks\n        method: GET\n        description: Get detected risks with optional OS and device type filters.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: immediate-scan\n      path: /accounts/{accountId}/immediatescan\n      description: Start an immediate security scan.\n      operations:\n      - name: start-immediate-scan\n        method: POST\n        description: Initiate an immediate malware scan on specified devices.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: WatchGuard Cloud account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            device_ids: '{{tools.device_ids}}'\n            task_name: '{{tools.task_name}}'\n            scan_scope: '{{tools.scan_scope}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wg-threat-response-api\n  \
  \  description: Unified REST API for WatchGuard endpoint threat response workflows.\n    resources:\n    - path: /v1/accounts/{accountId}\n      name: account\n      description: WatchGuard Cloud account information.\n      operations:\n      - method: GET\n        name: get-account\n        description: Get WatchGuard Cloud account details.\n        call: wg-platform.get-account\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/managed-accounts\n      name: managed-accounts\n      description: Sub-accounts managed by a service provider.\n      operations:\n      - method: GET\n        name: get-managed-accounts\n        description: List all managed sub-accounts.\n        call: wg-platform.get-managed-accounts\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices\n      name: devices\n\
  \      description: Managed endpoint devices.\n      operations:\n      - method: GET\n        name: list-devices\n        description: List all managed endpoint devices.\n        call: wg-endpoint.list-devices\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/protection-status\n      name: device-protection-status\n      description: Protection status for all managed devices.\n      operations:\n      - method: GET\n        name: get-devices-protection-status\n        description: Get protection status for all endpoint devices.\n        call: wg-endpoint.get-devices-protection-status\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/isolation\n      name: device-isolation\n      description: Isolate or release endpoint devices.\n      operations:\n      - method: POST\n        name: isolate-devices\n\
  \        description: Isolate devices from the network.\n        call: wg-endpoint.isolate-devices\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/remove-isolation\n      name: device-remove-isolation\n      description: Remove network isolation from devices.\n      operations:\n      - method: POST\n        name: remove-device-isolation\n        description: Remove network isolation.\n        call: wg-endpoint.remove-device-isolation\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/scan\n      name: device-scan\n      description: Initiate immediate security scans.\n      operations:\n      - method: POST\n        name: start-immediate-scan\n        description: Start an immediate malware scan.\n        call: wg-endpoint.start-immediate-scan\n        with:\n          accountId: rest.accountId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/security/overview/{period}\n      name: security-overview\n      description: Security posture overview.\n      operations:\n      - method: GET\n        name: get-security-overview\n        description: Get security overview summary.\n        call: wg-endpoint.get-security-overview\n        with:\n          accountId: rest.accountId\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/risk/summary\n      name: risk-summary\n      description: Company-wide risk summary.\n      operations:\n      - method: GET\n        name: get-company-risk-summary\n        description: Get risk summary by severity level.\n        call: wg-endpoint.get-company-risk-summary\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/risk/detected\n      name: detected-risks\n\
  \      description: Detected risk details.\n      operations:\n      - method: GET\n        name: get-detected-risks\n        description: Get detected risks by type.\n        call: wg-endpoint.get-detected-risks\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/activations\n      name: activations\n      description: Device and license activation.\n      operations:\n      - method: POST\n        name: activate-device-or-license\n        description: Activate hardware devices or software licenses.\n        call: wg-platform.activate-device-or-license\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/operators\n      name: operators\n      description: WatchGuard Cloud operator management.\n      operations:\n      - method: GET\n        name: get-operators\n        description: List operators for an account.\n        call: wg-platform.get-operators-by-account\n\
  \        with:\n          account_id: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-operators\n        description: Create new operator users.\n        call: wg-platform.create-operators\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wg-threat-response-mcp\n    transport: http\n    description: MCP server for AI-assisted WatchGuard endpoint threat response.\n    tools:\n    - name: get-account\n      description: Get WatchGuard Cloud account information and status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wg-platform.get-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-managed-accounts\n      description: List all managed sub-accounts in WatchGuard Cloud.\n      hints:\n        readOnly: true\n       \
  \ openWorld: true\n      call: wg-platform.get-managed-accounts\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-devices\n      description: List all WatchGuard managed endpoint devices with protection status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wg-endpoint.list-devices\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-devices-protection-status\n      description: Get the protection status of all WatchGuard managed endpoint devices.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wg-endpoint.get-devices-protection-status\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isolate-devices\n      description: Isolate compromised WatchGuard endpoint devices from the network.\n \
  \     hints:\n        readOnly: false\n        destructive: true\n      call: wg-endpoint.isolate-devices\n      with:\n        accountId: tools.accountId\n        device_ids: tools.device_ids\n        customized_message: tools.customized_message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-device-isolation\n      description: Remove network isolation from WatchGuard endpoint devices after remediation.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: wg-endpoint.remove-device-isolation\n      with:\n        accountId: tools.accountId\n        device_ids: tools.device_ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-immediate-scan\n      description: Start an immediate malware scan on WatchGuard endpoint devices.\n      hints:\n        readOnly: false\n      call: wg-endpoint.start-immediate-scan\n      with:\n        accountId: tools.accountId\n        device_ids: tools.device_ids\n\
  \        task_name: tools.task_name\n        scan_scope: tools.scan_scope\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-security-overview\n      description: Get a WatchGuard endpoint security overview for 1, 7, or 30 days.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wg-endpoint.get-security-overview\n      with:\n        accountId: tools.accountId\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-company-risk-summary\n      description: Get company-wide endpoint security risk summary by severity level.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wg-endpoint.get-company-risk-summary\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-detected-risks\n      description: Get WatchGuard endpoint detected risks broken down by type and device.\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: wg-endpoint.get-detected-risks\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-device-or-license\n      description: Activate WatchGuard hardware devices or software license keys.\n      hints:\n        readOnly: false\n      call: wg-platform.activate-device-or-license\n      with:\n        activations: tools.activations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recent-activations\n      description: Get recent WatchGuard device and license activation history.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wg-platform.get-recent-activations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-operators\n      description: List WatchGuard Cloud operator users for an account.\n      hints:\n        readOnly: true\n     \
  \   openWorld: true\n      call: wg-platform.get-operators-by-account\n      with:\n        account_id: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-operators\n      description: Create new WatchGuard Cloud operator users.\n      hints:\n        readOnly: false\n      call: wg-platform.create-operators\n      with:\n        username: tools.username\n        accountId: tools.accountId\n        firstName: tools.firstName\n        lastName: tools.lastName\n        email: tools.email\n        phone: tools.phone\n        role: tools.role\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
