---
categories: []
consumed_apis:
- prisma-airs
- prisma-airs-red-teaming
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
- create a new red team scan target.
- list attack categories
- red team operator
- monitors and remediates cloud security misconfigurations and compliance violations.
- analyzes suspicious files and samples for malware characteristics.
- get results of a red team vulnerability scan.
- network security
- mssp operator
- identity and access management, tenant hierarchies, and subscription management.
- manages multi-tenant hierarchies and service group configurations for mssps.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- saas security admin
- submit an asynchronous ai security scan of model inputs/outputs for threats.
- manages multi-tenant security operations at scale for managed service providers.
- manages logging infrastructure, integrations, and platform automation.
- list ai profiles
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- malware researcher
- sre
- get the results of a previously submitted asynchronous scan.
- create red team target
- data protection analyst
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- manage enterprise browser policies, user sessions, and deployments.
- ai security engineer
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- threat intelligence
- get or delete a specific red team scan target.
- xdr
- firewall policy management, network objects, and cloud-native firewall configuration.
- firewall
- list all red team scan targets.
- investigates security incidents, triages alerts, and coordinates response actions.
- get red team scan status
- iam admin
- compliance officer
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- cybersecurity
- get results of a red team vulnerability scan with optional category and severity filters.
- submit a synchronous ai security scan of model inputs/outputs for threats like prompt injection, data leakage, and malicious content.
- secures ai applications with runtime scanning and vulnerability assessment.
- create a new red team scan target for ai application vulnerability testing.
- enterprise it
- manage ai red teaming scan targets.
- delete a specific red team scan target by id.
- cloud security
- cloud security posture management, compliance monitoring, and workload protection.
- soar
- get results of an asynchronous ai security scan.
- ai red teaming
- get red team scan results
- get async scan results
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- subscription manager
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- submit a synchronous scan of ai model inputs/outputs for threats.
- designs and implements network security architectures and policies.
- submit async scan
- list available attack categories for red teaming.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- sase
- get the status of a red team vulnerability scan.
- incident responder
- sd wan operator
- researches threat actors, malware campaigns, and vulnerability trends.
- start a new red team vulnerability scan against a target ai application.
- data loss prevention, saas security monitoring, and identity security posture.
- ai runtime security scanning and automated red teaming for ai applications.
- monitors network health, performance, and digital experience metrics.
- start red team scan
- list all ai security profiles with pagination.
- submit an asynchronous ai security scan.
- ai security
- get results of a red team vulnerability scan with optional filters.
- investigates dlp incidents and manages sensitive data protection policies.
- sase admin
- submit an asynchronous scan of ai model inputs/outputs for threats.
- threat intel analyst
- tenant operator
- network security engineer
- executes containment, eradication, and recovery actions during security incidents.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- manages enterprise browser policies and secure browsing configurations.
- cloud security engineer
- get results of a previously submitted asynchronous ai security scan.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- list all available attack categories for red team vulnerability scans.
- list ai security profiles.
- firewall admin
- get ai profile
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- network operations
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- get red team target
- enterprise browser policy management and secure browsing.
- prompt injection
- list red team targets
- proactively searches for threats and iocs across telemetry data.
- manages service accounts, roles, and access policies for platform api access.
- conducts automated adversarial testing against ai systems and llm applications.
- llm security
- browser security admin
- designs sase and sd-wan network architectures for secure remote access.
- list all red team scan targets with optional type filter.
- list all available attack categories for red team scans.
- get a specific ai security profile by name.
- platform engineer
- get a specific ai security profile.
- palo alto networks
- delete red team target
- submit sync scan
- start ai red team vulnerability scans.
- threat hunter
- digital experience monitoring, log management, and best practice assessment.
- compliance team
- get a specific red team scan target by id.
- soc analyst
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- submit a synchronous ai security scan.
- start a new red team vulnerability scan against a target.
- network architect
- vulnerability manager
slug: ai-security
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Palo Alto Networks AI Security\"\n  description: \"Unified AI security capability for scanning AI model inputs/outputs for threats and red-teaming AI applications for vulnerabilities across Prisma AIRS and AI Red Teaming APIs.\"\n  tags:\n    - Palo Alto Networks\n    - AI Security\n    - AI Red Teaming\n    - LLM Security\n    - Prompt Injection\n  created: \"2026-04-16\"\n  modified: \"2026-04-16\"\n\nbinds:\n  - namespace: env\n    keys:\n      PRISMA_AIRS_TOKEN: PRISMA_AIRS_TOKEN\n      PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: prisma-airs\n      location: ./shared/prisma-airs.yaml\n    - import: prisma-airs-red-teaming\n      location: ./shared/prisma-airs-red-teaming.yaml\n\n  exposes:\n    - type: rest\n      port: 8088\n      namespace: ai-security-api\n      description: \"Unified REST API for AI security scanning and red teaming.\"\n      resources:\n\n        # -- AI Security\
  \ Scanning (Prisma AIRS) --------------------------------\n        - path: /v1/ai-scans/sync\n          name: ai-scan-sync\n          description: \"Submit a synchronous AI security scan.\"\n          operations:\n            - method: POST\n              name: submit-sync-scan\n              description: \"Submit a synchronous scan of AI model inputs/outputs for threats.\"\n              inputParameters:\n                - name: ai_profile\n                  in: body\n                  type: string\n                  required: true\n                - name: contents\n                  in: body\n                  type: object\n                  required: true\n              call: \"prisma-airs.submit-scan-sync\"\n              with:\n                ai_profile: \"rest.ai_profile\"\n                contents: \"rest.contents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ai-scans/async\n          name: ai-scan-async\n\
  \          description: \"Submit an asynchronous AI security scan.\"\n          operations:\n            - method: POST\n              name: submit-async-scan\n              description: \"Submit an asynchronous scan of AI model inputs/outputs for threats.\"\n              inputParameters:\n                - name: ai_profile\n                  in: body\n                  type: string\n                  required: true\n                - name: contents\n                  in: body\n                  type: object\n                  required: true\n              call: \"prisma-airs.submit-scan-async\"\n              with:\n                ai_profile: \"rest.ai_profile\"\n                contents: \"rest.contents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ai-scans/async/{scan_id}/results\n          name: ai-scan-async-results\n          description: \"Get results of an asynchronous AI security scan.\"\n       \
  \   operations:\n            - method: GET\n              name: get-async-scan-results\n              description: \"Get the results of a previously submitted asynchronous scan.\"\n              inputParameters:\n                - name: scan_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-airs.get-async-scan-results\"\n              with:\n                scan_id: \"rest.scan_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -- AI Security Profiles (Prisma AIRS) --------------------------------\n        - path: /v1/ai-profiles\n          name: ai-profiles\n          description: \"List AI security profiles.\"\n          operations:\n            - method: GET\n              name: list-ai-profiles\n              description: \"List all AI security profiles with pagination.\"\n              inputParameters:\n                - name: offset\n   \
  \               in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"prisma-airs.list-ai-profiles\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ai-profiles/{profile_name}\n          name: ai-profile\n          description: \"Get a specific AI security profile.\"\n          operations:\n            - method: GET\n              name: get-ai-profile\n              description: \"Get a specific AI security profile by name.\"\n              inputParameters:\n                - name: profile_name\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-airs.get-ai-profile\"\n \
  \             with:\n                profile_name: \"rest.profile_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -- Red Team Targets (Prisma AIRS Red Teaming) ------------------------\n        - path: /v1/red-team-targets\n          name: red-team-targets\n          description: \"Manage AI red teaming scan targets.\"\n          operations:\n            - method: POST\n              name: create-red-team-target\n              description: \"Create a new red team scan target.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: type\n                  in: body\n                  type: string\n                  required: true\n                - name: endpoint_url\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n\
  \                  in: body\n                  type: string\n                  required: false\n                - name: model\n                  in: body\n                  type: string\n                  required: false\n                - name: auth_config\n                  in: body\n                  type: object\n                  required: false\n                - name: system_prompt\n                  in: body\n                  type: string\n                  required: false\n              call: \"prisma-airs-red-teaming.create-scan-target\"\n              with:\n                name: \"rest.name\"\n                type: \"rest.type\"\n                endpoint_url: \"rest.endpoint_url\"\n                description: \"rest.description\"\n                model: \"rest.model\"\n                auth_config: \"rest.auth_config\"\n                system_prompt: \"rest.system_prompt\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \            - method: GET\n              name: list-red-team-targets\n              description: \"List all red team scan targets.\"\n              inputParameters:\n                - name: type\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"prisma-airs-red-teaming.list-scan-targets\"\n              with:\n                type: \"rest.type\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/red-team-targets/{target_id}\n          name: red-team-target\n          description: \"Get or delete a specific red team scan\
  \ target.\"\n          operations:\n            - method: GET\n              name: get-red-team-target\n              description: \"Get a specific red team scan target by ID.\"\n              inputParameters:\n                - name: target_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-airs-red-teaming.get-scan-target\"\n              with:\n                target_id: \"rest.target_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-red-team-target\n              description: \"Delete a specific red team scan target by ID.\"\n              inputParameters:\n                - name: target_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-airs-red-teaming.delete-scan-target\"\n              with:\n                target_id:\
  \ \"rest.target_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -- Red Team Scans (Prisma AIRS Red Teaming) --------------------------\n        - path: /v1/red-team-scans\n          name: red-team-scans\n          description: \"Start AI red team vulnerability scans.\"\n          operations:\n            - method: POST\n              name: start-red-team-scan\n              description: \"Start a new red team vulnerability scan against a target.\"\n              inputParameters:\n                - name: target_id\n                  in: body\n                  type: string\n                  required: true\n                - name: attack_categories\n                  in: body\n                  type: object\n                  required: false\n                - name: custom_prompts\n                  in: body\n                  type: object\n                  required: false\n                - name: max_attacks_per_category\n\
  \                  in: body\n                  type: integer\n                  required: false\n              call: \"prisma-airs-red-teaming.start-vulnerability-scan\"\n              with:\n                target_id: \"rest.target_id\"\n                attack_categories: \"rest.attack_categories\"\n                custom_prompts: \"rest.custom_prompts\"\n                max_attacks_per_category: \"rest.max_attacks_per_category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/red-team-scans/{scan_id}\n          name: red-team-scan-status\n          description: \"Get the status of a red team vulnerability scan.\"\n          operations:\n            - method: GET\n              name: get-red-team-scan-status\n              description: \"Get the status of a red team vulnerability scan.\"\n              inputParameters:\n                - name: scan_id\n                  in: path\n                  type: string\n\
  \                  required: true\n              call: \"prisma-airs-red-teaming.get-scan-status\"\n              with:\n                scan_id: \"rest.scan_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/red-team-scans/{scan_id}/results\n          name: red-team-scan-results\n          description: \"Get results of a red team vulnerability scan.\"\n          operations:\n            - method: GET\n              name: get-red-team-scan-results\n              description: \"Get results of a red team vulnerability scan with optional filters.\"\n              inputParameters:\n                - name: scan_id\n                  in: path\n                  type: string\n                  required: true\n                - name: category\n                  in: query\n                  type: string\n                  required: false\n                - name: severity\n                  in: query\n                 \
  \ type: string\n                  required: false\n              call: \"prisma-airs-red-teaming.get-scan-results\"\n              with:\n                scan_id: \"rest.scan_id\"\n                category: \"rest.category\"\n                severity: \"rest.severity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -- Attack Categories (Prisma AIRS Red Teaming) -----------------------\n        - path: /v1/attack-categories\n          name: attack-categories\n          description: \"List available attack categories for red teaming.\"\n          operations:\n            - method: GET\n              name: list-attack-categories\n              description: \"List all available attack categories for red team scans.\"\n              call: \"prisma-airs-red-teaming.list-attack-categories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9098\n\
  \      namespace: ai-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AI security scanning and red teaming.\"\n      tools:\n\n        # -- AI Scanning Tools -------------------------------------------------\n        - name: submit-sync-scan\n          description: \"Submit a synchronous AI security scan of model inputs/outputs for threats like prompt injection, data leakage, and malicious content.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: ai_profile\n              type: string\n              required: true\n            - name: contents\n              type: object\n              required: true\n          call: \"prisma-airs.submit-scan-sync\"\n          with:\n            ai_profile: \"tools.ai_profile\"\n            contents: \"tools.contents\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n\n        - name: submit-async-scan\n          description: \"Submit an asynchronous AI security scan of model inputs/outputs for threats.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: ai_profile\n              type: string\n              required: true\n            - name: contents\n              type: object\n              required: true\n          call: \"prisma-airs.submit-scan-async\"\n          with:\n            ai_profile: \"tools.ai_profile\"\n            contents: \"tools.contents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-async-scan-results\n          description: \"Get results of a previously submitted asynchronous AI security scan.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent:\
  \ true\n            openWorld: true\n          inputParameters:\n            - name: scan_id\n              type: string\n              required: true\n          call: \"prisma-airs.get-async-scan-results\"\n          with:\n            scan_id: \"tools.scan_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ai-profiles\n          description: \"List all AI security profiles with pagination.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-airs.list-ai-profiles\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-ai-profile\n          description: \"Get a specific AI security profile by name.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: profile_name\n              type: string\n              required: true\n          call: \"prisma-airs.get-ai-profile\"\n          with:\n            profile_name: \"tools.profile_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # -- Red Teaming Tools -------------------------------------------------\n        - name: create-red-team-target\n          description: \"Create a new red team scan target for AI application vulnerability testing.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n      \
  \      - name: name\n              type: string\n              required: true\n            - name: type\n              type: string\n              required: true\n            - name: endpoint_url\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: model\n              type: string\n              required: false\n            - name: auth_config\n              type: object\n              required: false\n            - name: system_prompt\n              type: string\n              required: false\n          call: \"prisma-airs-red-teaming.create-scan-target\"\n          with:\n            name: \"tools.name\"\n            type: \"tools.type\"\n            endpoint_url: \"tools.endpoint_url\"\n            description: \"tools.description\"\n            model: \"tools.model\"\n            auth_config: \"tools.auth_config\"\n            system_prompt: \"tools.system_prompt\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-red-team-targets\n          description: \"List all red team scan targets with optional type filter.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: type\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-airs-red-teaming.list-scan-targets\"\n          with:\n            type: \"tools.type\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-red-team-target\n          description: \"Get a specific red\
  \ team scan target by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: target_id\n              type: string\n              required: true\n          call: \"prisma-airs-red-teaming.get-scan-target\"\n          with:\n            target_id: \"tools.target_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-red-team-target\n          description: \"Delete a specific red team scan target by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: target_id\n              type: string\n              required: true\n          call: \"prisma-airs-red-teaming.delete-scan-target\"\n          with:\n            target_id: \"tools.target_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: start-red-team-scan\n          description: \"Start a new red team vulnerability scan against a target AI application.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: target_id\n              type: string\n              required: true\n            - name: attack_categories\n              type: object\n              required: false\n            - name: custom_prompts\n              type: object\n              required: false\n            - name: max_attacks_per_category\n              type: integer\n              required: false\n          call: \"prisma-airs-red-teaming.start-vulnerability-scan\"\n          with:\n            target_id: \"tools.target_id\"\n            attack_categories: \"tools.attack_categories\"\n            custom_prompts: \"tools.custom_prompts\"\n\
  \            max_attacks_per_category: \"tools.max_attacks_per_category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-red-team-scan-status\n          description: \"Get the status of a red team vulnerability scan.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: scan_id\n              type: string\n              required: true\n          call: \"prisma-airs-red-teaming.get-scan-status\"\n          with:\n            scan_id: \"tools.scan_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-red-team-scan-results\n          description: \"Get results of a red team vulnerability scan with optional category and severity filters.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent:\
  \ true\n            openWorld: true\n          inputParameters:\n            - name: scan_id\n              type: string\n              required: true\n            - name: category\n              type: string\n              required: false\n            - name: severity\n              type: string\n              required: false\n          call: \"prisma-airs-red-teaming.get-scan-results\"\n          with:\n            scan_id: \"tools.scan_id\"\n            category: \"tools.category\"\n            severity: \"tools.severity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-attack-categories\n          description: \"List all available attack categories for red team vulnerability scans.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"prisma-airs-red-teaming.list-attack-categories\"\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n"
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
