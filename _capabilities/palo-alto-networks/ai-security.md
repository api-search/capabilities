---
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
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- investigates dlp incidents and manages sensitive data protection policies.
- list all red team scan targets.
- xdr
- submit a synchronous ai security scan of model inputs/outputs for threats like prompt injection, data leakage, and malicious content.
- get the results of a previously submitted asynchronous scan.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- secures ai applications with runtime scanning and vulnerability assessment.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- monitors network health, performance, and digital experience metrics.
- submit a synchronous scan of ai model inputs/outputs for threats.
- analyzes suspicious files and samples for malware characteristics.
- manages enterprise browser policies and secure browsing configurations.
- firewall policy management, network objects, and cloud-native firewall configuration.
- get red team target
- sre
- list ai security profiles.
- get red team scan results
- list all red team scan targets with optional type filter.
- start ai red team vulnerability scans.
- submit an asynchronous ai security scan of model inputs/outputs for threats.
- get ai profile
- designs sase and sd-wan network architectures for secure remote access.
- vulnerability manager
- soar
- firewall admin
- monitors and remediates cloud security misconfigurations and compliance violations.
- tenant operator
- start red team scan
- create a new red team scan target.
- soc analyst
- get the status of a red team vulnerability scan.
- manages service accounts, roles, and access policies for platform api access.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- create red team target
- data loss prevention, saas security monitoring, and identity security posture.
- cloud security posture management, compliance monitoring, and workload protection.
- get results of a red team vulnerability scan with optional filters.
- threat intelligence
- list all available attack categories for red team scans.
- ai security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- compliance team
- enterprise it
- incident responder
- subscription manager
- malware researcher
- manage ai red teaming scan targets.
- list attack categories
- network operations
- manage enterprise browser policies, user sessions, and deployments.
- get results of a red team vulnerability scan.
- conducts automated adversarial testing against ai systems and llm applications.
- get results of an asynchronous ai security scan.
- threat intel analyst
- firewall
- browser security admin
- get or delete a specific red team scan target.
- start a new red team vulnerability scan against a target.
- submit an asynchronous ai security scan.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- threat hunter
- get red team scan status
- llm security
- secure access service edge with remote networking, sd-wan, and zero trust access.
- get results of a previously submitted asynchronous ai security scan.
- compliance officer
- get results of a red team vulnerability scan with optional category and severity filters.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- get a specific red team scan target by id.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- ai runtime security scanning and automated red teaming for ai applications.
- saas security admin
- manages multi-tenant security operations at scale for managed service providers.
- list available attack categories for red teaming.
- prompt injection
- digital experience monitoring, log management, and best practice assessment.
- submit sync scan
- data protection analyst
- cloud security
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- platform engineer
- proactively searches for threats and iocs across telemetry data.
- network architect
- submit a synchronous ai security scan.
- red team operator
- ai red teaming
- submit async scan
- executes containment, eradication, and recovery actions during security incidents.
- researches threat actors, malware campaigns, and vulnerability trends.
- get a specific ai security profile.
- sase
- delete a specific red team scan target by id.
- cybersecurity
- list all ai security profiles with pagination.
- manages multi-tenant hierarchies and service group configurations for mssps.
- get a specific ai security profile by name.
- palo alto networks
- identity and access management, tenant hierarchies, and subscription management.
- start a new red team vulnerability scan against a target ai application.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- list all available attack categories for red team vulnerability scans.
- cloud security engineer
- designs and implements network security architectures and policies.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- mssp operator
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- sase admin
- create a new red team scan target for ai application vulnerability testing.
- iam admin
- enterprise browser policy management and secure browsing.
- ai security
- list ai profiles
- network security
- sd wan operator
- manages logging infrastructure, integrations, and platform automation.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- submit an asynchronous scan of ai model inputs/outputs for threats.
- get async scan results
- delete red team target
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- network security engineer
- list red team targets
slug: ai-security
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
