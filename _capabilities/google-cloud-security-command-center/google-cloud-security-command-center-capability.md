---
categories: []
consumed_apis: []
description: The Security Command Center API provides programmatic access to manage security findings, assets, sources, and notification configurations across an organization's Google Cloud resources. It enables security teams to detect threats, identify vulnerabilities, and manage compliance posture.
layout: capability
name: Google Cloud Security Command Center API
operations:
- description: Google Cloud Security Command Center List sources
  method: GET
  name: listsources
  path: /organizations/{organizationId}/sources
- description: Google Cloud Security Command Center Create a source
  method: POST
  name: createsource
  path: /organizations/{organizationId}/sources
- description: Google Cloud Security Command Center List findings
  method: GET
  name: listfindings
  path: /organizations/{organizationId}/sources/{sourceId}/findings
- description: Google Cloud Security Command Center Create a finding
  method: POST
  name: createfinding
  path: /organizations/{organizationId}/sources/{sourceId}/findings
- description: Google Cloud Security Command Center List assets
  method: GET
  name: listassets
  path: /organizations/{organizationId}/assets
- description: Google Cloud Security Command Center List notification configs
  method: GET
  name: listnotificationconfigs
  path: /organizations/{organizationId}/notificationConfigs
- description: Google Cloud Security Command Center Create a notification config
  method: POST
  name: createnotificationconfig
  path: /organizations/{organizationId}/notificationConfigs
personas: []
provider_name: Google Cloud Security Command Center
provider_slug: google-cloud-security-command-center
search_terms:
- listfindings
- threat detection
- api
- google cloud security command center create a source
- compliance
- listsources
- google cloud security command center create a finding
- google
- command
- google cloud security command center list assets
- createnotificationconfig
- cloud security
- google cloud security command center list notification configs
- createfinding
- center
- google cloud security command center list sources
- google cloud security command center create a notification config
- listassets
- cloud
- google cloud security command center list findings
- createsource
- vulnerability management
- security
- listnotificationconfigs
- risk management
slug: google-cloud-security-command-center-capability
source_filename: google-cloud-security-command-center-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Security Command Center API\n  description: The Security Command Center API provides programmatic access to manage security findings, assets, sources,\n    and notification configurations across an organization's Google Cloud resources. It enables security teams to detect threats,\n    identify vulnerabilities, and manage compliance posture.\n  tags:\n  - Google\n  - Cloud\n  - Security\n  - Command\n  - Center\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-security-command-center\n    baseUri: https://securitycenter.googleapis.com/v1\n    description: Google Cloud Security Command Center API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_SECURITY_COMMAND_CENTER_TOKEN}}'\n    resources:\n    - name: organizations-organizationid-sources\n      path: /organizations/{organizationId}/sources\n      operations:\n\
  \      - name: listsources\n        method: GET\n        description: Google Cloud Security Command Center List sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsource\n        method: POST\n        description: Google Cloud Security Command Center Create a source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organizationid-sources-sourceid-fi\n      path: /organizations/{organizationId}/sources/{sourceId}/findings\n      operations:\n      - name: listfindings\n        method: GET\n        description: Google Cloud Security Command Center List findings\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Expression that defines the filter to apply across findings\n        - name: orderBy\n          in: query\n\
  \          type: string\n          description: Expression that defines what fields and order to use for sorting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfinding\n        method: POST\n        description: Google Cloud Security Command Center Create a finding\n        inputParameters:\n        - name: findingId\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the finding\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organizationid-assets\n      path: /organizations/{organizationId}/assets\n      operations:\n      - name: listassets\n        method: GET\n        description: Google Cloud Security Command Center List assets\n        inputParameters:\n        - name: filter\n          in: query\n          type:\
  \ string\n          description: Expression that defines the filter to apply across assets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organizationid-notificationconfigs\n      path: /organizations/{organizationId}/notificationConfigs\n      operations:\n      - name: listnotificationconfigs\n        method: GET\n        description: Google Cloud Security Command Center List notification configs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnotificationconfig\n        method: POST\n        description: Google Cloud Security Command Center Create a notification config\n        inputParameters:\n        - name: configId\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the notification config\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-security-command-center-rest\n    description: REST adapter for Google Cloud Security Command Center API.\n    resources:\n    - path: /organizations/{organizationId}/sources\n      name: listsources\n      operations:\n      - method: GET\n        name: listsources\n        description: Google Cloud Security Command Center List sources\n        call: google-cloud-security-command-center.listsources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/sources\n      name: createsource\n      operations:\n      - method: POST\n        name: createsource\n        description: Google Cloud Security Command Center Create a source\n        call: google-cloud-security-command-center.createsource\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /organizations/{organizationId}/sources/{sourceId}/findings\n      name: listfindings\n      operations:\n      - method: GET\n        name: listfindings\n        description: Google Cloud Security Command Center List findings\n        call: google-cloud-security-command-center.listfindings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/sources/{sourceId}/findings\n      name: createfinding\n      operations:\n      - method: POST\n        name: createfinding\n        description: Google Cloud Security Command Center Create a finding\n        call: google-cloud-security-command-center.createfinding\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/assets\n      name: listassets\n      operations:\n      - method: GET\n        name: listassets\n        description: Google Cloud Security Command Center List assets\n   \
  \     call: google-cloud-security-command-center.listassets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/notificationConfigs\n      name: listnotificationconfigs\n      operations:\n      - method: GET\n        name: listnotificationconfigs\n        description: Google Cloud Security Command Center List notification configs\n        call: google-cloud-security-command-center.listnotificationconfigs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/notificationConfigs\n      name: createnotificationconfig\n      operations:\n      - method: POST\n        name: createnotificationconfig\n        description: Google Cloud Security Command Center Create a notification config\n        call: google-cloud-security-command-center.createnotificationconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: google-cloud-security-command-center-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Security Command Center API for AI agent use.\n    tools:\n    - name: listsources\n      description: Google Cloud Security Command Center List sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-security-command-center.listsources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsource\n      description: Google Cloud Security Command Center Create a source\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-security-command-center.createsource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfindings\n      description: Google Cloud Security Command Center List findings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: google-cloud-security-command-center.listfindings\n      with:\n        filter: tools.filter\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: filter\n        type: string\n        description: Expression that defines the filter to apply across findings\n      - name: orderBy\n        type: string\n        description: Expression that defines what fields and order to use for sorting\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfinding\n      description: Google Cloud Security Command Center Create a finding\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-security-command-center.createfinding\n      with:\n        findingId: tools.findingId\n      inputParameters:\n      - name: findingId\n        type: string\n        description: Unique identifier for the finding\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: listassets\n      description: Google Cloud Security Command Center List assets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-security-command-center.listassets\n      with:\n        filter: tools.filter\n      inputParameters:\n      - name: filter\n        type: string\n        description: Expression that defines the filter to apply across assets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnotificationconfigs\n      description: Google Cloud Security Command Center List notification configs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-security-command-center.listnotificationconfigs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnotificationconfig\n      description: Google Cloud Security Command Center Create a notification config\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-security-command-center.createnotificationconfig\n      with:\n        configId: tools.configId\n      inputParameters:\n      - name: configId\n        type: string\n        description: Unique identifier for the notification config\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_SECURITY_COMMAND_CENTER_TOKEN: GOOGLE_CLOUD_SECURITY_COMMAND_CENTER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-security-command-center/refs/heads/main/capabilities/google-cloud-security-command-center-capability.yaml
tags:
- Google
- Cloud
- Security
- Command
- Center
- API
tools:
- description: Google Cloud Security Command Center List sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsources
- description: Google Cloud Security Command Center Create a source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsource
- description: Google Cloud Security Command Center List findings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfindings
- description: Google Cloud Security Command Center Create a finding
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfinding
- description: Google Cloud Security Command Center List assets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassets
- description: Google Cloud Security Command Center List notification configs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnotificationconfigs
- description: Google Cloud Security Command Center Create a notification config
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnotificationconfig
---
