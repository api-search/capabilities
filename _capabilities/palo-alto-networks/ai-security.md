---
categories: []
consumed_apis: []
description: Unified AI security capability for scanning AI model inputs/outputs for threats and red-teaming AI applications for vulnerabilities across Prisma AIRS and AI Red Teaming APIs.
layout: capability
name: Palo Alto Networks AI Security
operations:
- description: Submit a synchronous scan of AI model inputs/outputs for threats.
  method: POST
  name: submit-sync-scan
  path: /v1/ai-scans/sync
- description: Submit an asynchronous scan of AI model inputs/outputs for threats.
  method: POST
  name: submit-async-scan
  path: /v1/ai-scans/async
- description: Get the results of a previously submitted asynchronous scan.
  method: GET
  name: get-async-scan-results
  path: /v1/ai-scans/async/{scan_id}/results
- description: List all AI security profiles with pagination.
  method: GET
  name: list-ai-profiles
  path: /v1/ai-profiles
- description: Get a specific AI security profile by name.
  method: GET
  name: get-ai-profile
  path: /v1/ai-profiles/{profile_name}
- description: Create a new red team scan target.
  method: POST
  name: create-red-team-target
  path: /v1/red-team-targets
- description: List all red team scan targets.
  method: GET
  name: list-red-team-targets
  path: /v1/red-team-targets
- description: Get a specific red team scan target by ID.
  method: GET
  name: get-red-team-target
  path: /v1/red-team-targets/{target_id}
- description: Delete a specific red team scan target by ID.
  method: DELETE
  name: delete-red-team-target
  path: /v1/red-team-targets/{target_id}
- description: Start a new red team vulnerability scan against a target.
  method: POST
  name: start-red-team-scan
  path: /v1/red-team-scans
- description: Get the status of a red team vulnerability scan.
  method: GET
  name: get-red-team-scan-status
  path: /v1/red-team-scans/{scan_id}
- description: Get results of a red team vulnerability scan with optional filters.
  method: GET
  name: get-red-team-scan-results
  path: /v1/red-team-scans/{scan_id}/results
- description: List all available attack categories for red team scans.
  method: GET
  name: list-attack-categories
  path: /v1/attack-categories
personas:
- description: Secures AI applications with runtime scanning and vulnerability assessment.
  id: ai-security-engineer
  name: AI Security Engineer
- description: Conducts automated adversarial testing against AI systems and LLM applications.
  id: red-team-operator
  name: Red Team Operator
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- analyzes suspicious files and samples for malware characteristics.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- malware researcher
- threat intelligence
- delete red team target
- get red team scan results
- identity and access management, tenant hierarchies, and subscription management.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- enterprise browser policy management and secure browsing.
- manage enterprise browser policies, user sessions, and deployments.
- cloud security
- submit a synchronous scan of ai model inputs/outputs for threats.
- delete a specific red team scan target by id.
- list all ai security profiles with pagination.
- proactively searches for threats and iocs across telemetry data.
- sre
- data loss prevention, saas security monitoring, and identity security posture.
- palo alto networks
- create red team target
- get the status of a red team vulnerability scan.
- submit a synchronous ai security scan of model inputs/outputs for threats like prompt injection, data leakage, and malicious content.
- designs and implements network security architectures and policies.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- list red team targets
- compliance team
- enterprise it
- threat hunter
- network operations
- data protection analyst
- start red team scan
- tenant operator
- ai runtime security scanning and automated red teaming for ai applications.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- submit an asynchronous ai security scan.
- mssp operator
- secures ai applications with runtime scanning and vulnerability assessment.
- digital experience monitoring, log management, and best practice assessment.
- submit async scan
- iam admin
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- submit an asynchronous ai security scan of model inputs/outputs for threats.
- conducts automated adversarial testing against ai systems and llm applications.
- firewall
- manages service accounts, roles, and access policies for platform api access.
- researches threat actors, malware campaigns, and vulnerability trends.
- network security engineer
- browser security admin
- get results of a red team vulnerability scan with optional category and severity filters.
- submit sync scan
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- get a specific ai security profile.
- compliance officer
- manages logging infrastructure, integrations, and platform automation.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- start a new red team vulnerability scan against a target.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- investigates security incidents, triages alerts, and coordinates response actions.
- manage ai red teaming scan targets.
- network architect
- list ai security profiles.
- subscription manager
- cloud security posture management, compliance monitoring, and workload protection.
- saas security admin
- firewall admin
- prompt injection
- get ai profile
- get or delete a specific red team scan target.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages multi-tenant hierarchies and service group configurations for mssps.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- red team operator
- soc analyst
- sase
- ai security engineer
- get a specific ai security profile by name.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- manages multi-tenant security operations at scale for managed service providers.
- create a new red team scan target for ai application vulnerability testing.
- ai security
- monitors and remediates cloud security misconfigurations and compliance violations.
- cybersecurity
- list all available attack categories for red team vulnerability scans.
- start a new red team vulnerability scan against a target ai application.
- get results of a red team vulnerability scan.
- submit a synchronous ai security scan.
- sase admin
- list available attack categories for red teaming.
- platform engineer
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- cloud security engineer
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- get results of an asynchronous ai security scan.
- get the results of a previously submitted asynchronous scan.
- get async scan results
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- firewall policy management, network objects, and cloud-native firewall configuration.
- list ai profiles
- submit an asynchronous scan of ai model inputs/outputs for threats.
- get red team scan status
- ai red teaming
- sd wan operator
- threat intel analyst
- vulnerability manager
- list all red team scan targets with optional type filter.
- incident responder
- network security
- xdr
- get results of a previously submitted asynchronous ai security scan.
- get a specific red team scan target by id.
- llm security
- executes containment, eradication, and recovery actions during security incidents.
- soar
- create a new red team scan target.
- manages enterprise browser policies and secure browsing configurations.
- designs sase and sd-wan network architectures for secure remote access.
- get results of a red team vulnerability scan with optional filters.
- list attack categories
- investigates dlp incidents and manages sensitive data protection policies.
- monitors network health, performance, and digital experience metrics.
- start ai red team vulnerability scans.
- list all available attack categories for red team scans.
- list all red team scan targets.
- get red team target
slug: ai-security
source_filename: ai-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Palo Alto Networks AI Security\n  description: Unified AI security capability for scanning AI model inputs/outputs for threats and red-teaming AI applications\n    for vulnerabilities across Prisma AIRS and AI Red Teaming APIs.\n  tags:\n  - Palo Alto Networks\n  - AI Security\n  - AI Red Teaming\n  - LLM Security\n  - Prompt Injection\n  created: '2026-04-16'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PRISMA_AIRS_TOKEN: PRISMA_AIRS_TOKEN\n    PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: prisma-airs\n    baseUri: https://security.api.aisecurity.paloaltonetworks.com\n    description: Prisma AIRS API for submitting AI security scans and managing AI profiles.\n    authentication:\n      type: apikey\n      name: x-pan-token\n      in: header\n      value: '{{env.PRISMA_AIRS_TOKEN}}'\n    resources:\n    - name: scan-sync\n      path: /v1/scan/sync/request\n \
  \     operations:\n      - name: submit-scan-sync\n        method: POST\n        description: Submit a synchronous scan request.\n        inputParameters:\n        - name: ai_profile\n          in: body\n          type: string\n          required: true\n        - name: contents\n          in: body\n          type: object\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ai_profile: '{{tools.ai_profile}}'\n            contents: '{{tools.contents}}'\n    - name: scan-async\n      path: /v1/scan/async/request\n      operations:\n      - name: submit-scan-async\n        method: POST\n        description: Submit an asynchronous scan request.\n        inputParameters:\n        - name: ai_profile\n          in: body\n          type: string\n          required: true\n        - name: contents\n          in: body\n          type:\
  \ object\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ai_profile: '{{tools.ai_profile}}'\n            contents: '{{tools.contents}}'\n    - name: async-scan-results\n      path: /v1/scan/async/results/{scan_id}\n      operations:\n      - name: get-async-scan-results\n        method: GET\n        description: Get results of an asynchronous scan.\n        inputParameters:\n        - name: scan_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ai-profiles\n      path: /v1/profile\n      operations:\n      - name: list-ai-profiles\n        method: GET\n        description: List all AI profiles with pagination.\n        inputParameters:\n        - name: offset\n\
  \          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ai-profile\n      path: /v1/profile/{profile_name}\n      operations:\n      - name: get-ai-profile\n        method: GET\n        description: Get a specific AI profile by name.\n        inputParameters:\n        - name: profile_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: prisma-airs-red-teaming\n    baseUri: https://api.sase.paloaltonetworks.com/ai-red-teaming\n    description: Prisma AIRS AI Red Teaming API for managing scan targets, running vulnerability scans, and reviewing results.\n    authentication:\n\
  \      type: bearer\n      token: '{{env.PALO_ALTO_OAUTH_TOKEN}}'\n    resources:\n    - name: scan-targets\n      path: /v1/targets\n      operations:\n      - name: create-scan-target\n        method: POST\n        description: Create a new scan target.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: type\n          in: body\n          type: string\n          required: true\n        - name: endpoint_url\n          in: body\n          type: string\n          required: true\n        - name: description\n          in: body\n          type: string\n          required: false\n        - name: model\n          in: body\n          type: string\n          required: false\n        - name: auth_config\n          in: body\n          type: object\n          required: false\n        - name: system_prompt\n          in: body\n          type: string\n          required: false\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            endpoint_url: '{{tools.endpoint_url}}'\n            description: '{{tools.description}}'\n            model: '{{tools.model}}'\n            auth_config: '{{tools.auth_config}}'\n            system_prompt: '{{tools.system_prompt}}'\n      - name: list-scan-targets\n        method: GET\n        description: List all scan targets with optional type filter.\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: scan-target\n      path: /v1/targets/{target_id}\n      operations:\n      - name: get-scan-target\n        method: GET\n        description: Get a specific scan target by ID.\n        inputParameters:\n        - name: target_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-scan-target\n        method: DELETE\n        description: Delete a specific scan target by ID.\n        inputParameters:\n        - name: target_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans\n      path: /v1/scans\n      operations:\n      - name: start-vulnerability-scan\n        method: POST\n        description: Start a new vulnerability scan\
  \ against a target.\n        inputParameters:\n        - name: target_id\n          in: body\n          type: string\n          required: true\n        - name: attack_categories\n          in: body\n          type: object\n          required: false\n        - name: custom_prompts\n          in: body\n          type: object\n          required: false\n        - name: max_attacks_per_category\n          in: body\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            target_id: '{{tools.target_id}}'\n            attack_categories: '{{tools.attack_categories}}'\n            custom_prompts: '{{tools.custom_prompts}}'\n            max_attacks_per_category: '{{tools.max_attacks_per_category}}'\n    - name: scan-status\n      path: /v1/scans/{scan_id}\n      operations:\n      - name: get-scan-status\n   \
  \     method: GET\n        description: Get the status of a vulnerability scan.\n        inputParameters:\n        - name: scan_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scan-results\n      path: /v1/scans/{scan_id}/results\n      operations:\n      - name: get-scan-results\n        method: GET\n        description: Get results of a vulnerability scan with optional filters.\n        inputParameters:\n        - name: scan_id\n          in: path\n          type: string\n          required: true\n        - name: category\n          in: query\n          type: string\n          required: false\n        - name: severity\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ attack-categories\n      path: /v1/attack-categories\n      operations:\n      - name: list-attack-categories\n        method: GET\n        description: List all available attack categories.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8088\n    namespace: ai-security-api\n    description: Unified REST API for AI security scanning and red teaming.\n    resources:\n    - path: /v1/ai-scans/sync\n      name: ai-scan-sync\n      description: Submit a synchronous AI security scan.\n      operations:\n      - method: POST\n        name: submit-sync-scan\n        description: Submit a synchronous scan of AI model inputs/outputs for threats.\n        inputParameters:\n        - name: ai_profile\n          in: body\n          type: string\n          required: true\n        - name: contents\n          in: body\n          type: object\n          required: true\n        call:\
  \ prisma-airs.submit-scan-sync\n        with:\n          ai_profile: rest.ai_profile\n          contents: rest.contents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai-scans/async\n      name: ai-scan-async\n      description: Submit an asynchronous AI security scan.\n      operations:\n      - method: POST\n        name: submit-async-scan\n        description: Submit an asynchronous scan of AI model inputs/outputs for threats.\n        inputParameters:\n        - name: ai_profile\n          in: body\n          type: string\n          required: true\n        - name: contents\n          in: body\n          type: object\n          required: true\n        call: prisma-airs.submit-scan-async\n        with:\n          ai_profile: rest.ai_profile\n          contents: rest.contents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai-scans/async/{scan_id}/results\n      name: ai-scan-async-results\n      description:\
  \ Get results of an asynchronous AI security scan.\n      operations:\n      - method: GET\n        name: get-async-scan-results\n        description: Get the results of a previously submitted asynchronous scan.\n        inputParameters:\n        - name: scan_id\n          in: path\n          type: string\n          required: true\n        call: prisma-airs.get-async-scan-results\n        with:\n          scan_id: rest.scan_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai-profiles\n      name: ai-profiles\n      description: List AI security profiles.\n      operations:\n      - method: GET\n        name: list-ai-profiles\n        description: List all AI security profiles with pagination.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        call: prisma-airs.list-ai-profiles\n\
  \        with:\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai-profiles/{profile_name}\n      name: ai-profile\n      description: Get a specific AI security profile.\n      operations:\n      - method: GET\n        name: get-ai-profile\n        description: Get a specific AI security profile by name.\n        inputParameters:\n        - name: profile_name\n          in: path\n          type: string\n          required: true\n        call: prisma-airs.get-ai-profile\n        with:\n          profile_name: rest.profile_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/red-team-targets\n      name: red-team-targets\n      description: Manage AI red teaming scan targets.\n      operations:\n      - method: POST\n        name: create-red-team-target\n        description: Create a new red team scan target.\n        inputParameters:\n       \
  \ - name: name\n          in: body\n          type: string\n          required: true\n        - name: type\n          in: body\n          type: string\n          required: true\n        - name: endpoint_url\n          in: body\n          type: string\n          required: true\n        - name: description\n          in: body\n          type: string\n          required: false\n        - name: model\n          in: body\n          type: string\n          required: false\n        - name: auth_config\n          in: body\n          type: object\n          required: false\n        - name: system_prompt\n          in: body\n          type: string\n          required: false\n        call: prisma-airs-red-teaming.create-scan-target\n        with:\n          name: rest.name\n          type: rest.type\n          endpoint_url: rest.endpoint_url\n          description: rest.description\n          model: rest.model\n          auth_config: rest.auth_config\n          system_prompt: rest.system_prompt\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-red-team-targets\n        description: List all red team scan targets.\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        call: prisma-airs-red-teaming.list-scan-targets\n        with:\n          type: rest.type\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/red-team-targets/{target_id}\n      name: red-team-target\n      description: Get or delete a specific red team scan target.\n      operations:\n      - method: GET\n        name: get-red-team-target\n        description: Get a specific red team scan\
  \ target by ID.\n        inputParameters:\n        - name: target_id\n          in: path\n          type: string\n          required: true\n        call: prisma-airs-red-teaming.get-scan-target\n        with:\n          target_id: rest.target_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-red-team-target\n        description: Delete a specific red team scan target by ID.\n        inputParameters:\n        - name: target_id\n          in: path\n          type: string\n          required: true\n        call: prisma-airs-red-teaming.delete-scan-target\n        with:\n          target_id: rest.target_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/red-team-scans\n      name: red-team-scans\n      description: Start AI red team vulnerability scans.\n      operations:\n      - method: POST\n        name: start-red-team-scan\n        description: Start a new red team vulnerability\
  \ scan against a target.\n        inputParameters:\n        - name: target_id\n          in: body\n          type: string\n          required: true\n        - name: attack_categories\n          in: body\n          type: object\n          required: false\n        - name: custom_prompts\n          in: body\n          type: object\n          required: false\n        - name: max_attacks_per_category\n          in: body\n          type: integer\n          required: false\n        call: prisma-airs-red-teaming.start-vulnerability-scan\n        with:\n          target_id: rest.target_id\n          attack_categories: rest.attack_categories\n          custom_prompts: rest.custom_prompts\n          max_attacks_per_category: rest.max_attacks_per_category\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/red-team-scans/{scan_id}\n      name: red-team-scan-status\n      description: Get the status of a red team vulnerability scan.\n      operations:\n      -\
  \ method: GET\n        name: get-red-team-scan-status\n        description: Get the status of a red team vulnerability scan.\n        inputParameters:\n        - name: scan_id\n          in: path\n          type: string\n          required: true\n        call: prisma-airs-red-teaming.get-scan-status\n        with:\n          scan_id: rest.scan_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/red-team-scans/{scan_id}/results\n      name: red-team-scan-results\n      description: Get results of a red team vulnerability scan.\n      operations:\n      - method: GET\n        name: get-red-team-scan-results\n        description: Get results of a red team vulnerability scan with optional filters.\n        inputParameters:\n        - name: scan_id\n          in: path\n          type: string\n          required: true\n        - name: category\n          in: query\n          type: string\n          required: false\n        - name: severity\n        \
  \  in: query\n          type: string\n          required: false\n        call: prisma-airs-red-teaming.get-scan-results\n        with:\n          scan_id: rest.scan_id\n          category: rest.category\n          severity: rest.severity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/attack-categories\n      name: attack-categories\n      description: List available attack categories for red teaming.\n      operations:\n      - method: GET\n        name: list-attack-categories\n        description: List all available attack categories for red team scans.\n        call: prisma-airs-red-teaming.list-attack-categories\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9098\n    namespace: ai-security-mcp\n    transport: http\n    description: MCP server for AI-assisted AI security scanning and red teaming.\n    tools:\n    - name: submit-sync-scan\n      description: Submit a synchronous AI security\
  \ scan of model inputs/outputs for threats like prompt injection, data leakage,\n        and malicious content.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n        openWorld: true\n      inputParameters:\n      - name: ai_profile\n        type: string\n        required: true\n      - name: contents\n        type: object\n        required: true\n      call: prisma-airs.submit-scan-sync\n      with:\n        ai_profile: tools.ai_profile\n        contents: tools.contents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-async-scan\n      description: Submit an asynchronous AI security scan of model inputs/outputs for threats.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n        openWorld: true\n      inputParameters:\n      - name: ai_profile\n        type: string\n        required: true\n      - name: contents\n        type: object\n        required:\
  \ true\n      call: prisma-airs.submit-scan-async\n      with:\n        ai_profile: tools.ai_profile\n        contents: tools.contents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-async-scan-results\n      description: Get results of a previously submitted asynchronous AI security scan.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      inputParameters:\n      - name: scan_id\n        type: string\n        required: true\n      call: prisma-airs.get-async-scan-results\n      with:\n        scan_id: tools.scan_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ai-profiles\n      description: List all AI security profiles with pagination.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      inputParameters:\n      - name: offset\n        type: integer\n        required:\
  \ false\n      - name: limit\n        type: integer\n        required: false\n      call: prisma-airs.list-ai-profiles\n      with:\n        offset: tools.offset\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ai-profile\n      description: Get a specific AI security profile by name.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      inputParameters:\n      - name: profile_name\n        type: string\n        required: true\n      call: prisma-airs.get-ai-profile\n      with:\n        profile_name: tools.profile_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-red-team-target\n      description: Create a new red team scan target for AI application vulnerability testing.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n        openWorld: true\n      inputParameters:\n\
  \      - name: name\n        type: string\n        required: true\n      - name: type\n        type: string\n        required: true\n      - name: endpoint_url\n        type: string\n        required: true\n      - name: description\n        type: string\n        required: false\n      - name: model\n        type: string\n        required: false\n      - name: auth_config\n        type: object\n        required: false\n      - name: system_prompt\n        type: string\n        required: false\n      call: prisma-airs-red-teaming.create-scan-target\n      with:\n        name: tools.name\n        type: tools.type\n        endpoint_url: tools.endpoint_url\n        description: tools.description\n        model: tools.model\n        auth_config: tools.auth_config\n        system_prompt: tools.system_prompt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-red-team-targets\n      description: List all red team scan targets with optional type filter.\n    \
  \  hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      inputParameters:\n      - name: type\n        type: string\n        required: false\n      - name: offset\n        type: integer\n        required: false\n      - name: limit\n        type: integer\n        required: false\n      call: prisma-airs-red-teaming.list-scan-targets\n      with:\n        type: tools.type\n        offset: tools.offset\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-red-team-target\n      description: Get a specific red team scan target by ID.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      inputParameters:\n      - name: target_id\n        type: string\n        required: true\n      call: prisma-airs-red-teaming.get-scan-target\n      with:\n        target_id: tools.target_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: delete-red-team-target\n      description: Delete a specific red team scan target by ID.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n        openWorld: true\n      inputParameters:\n      - name: target_id\n        type: string\n        required: true\n      call: prisma-airs-red-teaming.delete-scan-target\n      with:\n        target_id: tools.target_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-red-team-scan\n      description: Start a new red team vulnerability scan against a target AI application.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n        openWorld: true\n      inputParameters:\n      - name: target_id\n        type: string\n        required: true\n      - name: attack_categories\n        type: object\n        required: false\n      - name: custom_prompts\n        type: object\n\
  \        required: false\n      - name: max_attacks_per_category\n        type: integer\n        required: false\n      call: prisma-airs-red-teaming.start-vulnerability-scan\n      with:\n        target_id: tools.target_id\n        attack_categories: tools.attack_categories\n        custom_prompts: tools.custom_prompts\n        max_attacks_per_category: tools.max_attacks_per_category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-red-team-scan-status\n      description: Get the status of a red team vulnerability scan.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      inputParameters:\n      - name: scan_id\n        type: string\n        required: true\n      call: prisma-airs-red-teaming.get-scan-status\n      with:\n        scan_id: tools.scan_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-red-team-scan-results\n      description: Get\
  \ results of a red team vulnerability scan with optional category and severity filters.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      inputParameters:\n      - name: scan_id\n        type: string\n        required: true\n      - name: category\n        type: string\n        required: false\n      - name: severity\n        type: string\n        required: false\n      call: prisma-airs-red-teaming.get-scan-results\n      with:\n        scan_id: tools.scan_id\n        category: tools.category\n        severity: tools.severity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-attack-categories\n      description: List all available attack categories for red team vulnerability scans.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: prisma-airs-red-teaming.list-attack-categories\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/ai-security.yaml
tags:
- Palo Alto Networks
- AI Security
- AI Red Teaming
- LLM Security
- Prompt Injection
tools:
- description: Submit a synchronous AI security scan of model inputs/outputs for threats like prompt injection, data leakage, and malicious content.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: submit-sync-scan
- description: Submit an asynchronous AI security scan of model inputs/outputs for threats.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: submit-async-scan
- description: Get results of a previously submitted asynchronous AI security scan.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-async-scan-results
- description: List all AI security profiles with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-ai-profiles
- description: Get a specific AI security profile by name.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-ai-profile
- description: Create a new red team scan target for AI application vulnerability testing.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-red-team-target
- description: List all red team scan targets with optional type filter.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-red-team-targets
- description: Get a specific red team scan target by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-red-team-target
- description: Delete a specific red team scan target by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-red-team-target
- description: Start a new red team vulnerability scan against a target AI application.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: start-red-team-scan
- description: Get the status of a red team vulnerability scan.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-red-team-scan-status
- description: Get results of a red team vulnerability scan with optional category and severity filters.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-red-team-scan-results
- description: List all available attack categories for red team vulnerability scans.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-attack-categories
---
