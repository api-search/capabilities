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
- sase
- get results of a previously submitted asynchronous ai security scan.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- get a specific red team scan target by id.
- firewall admin
- list all available attack categories for red team scans.
- soc analyst
- delete a specific red team scan target by id.
- start red team scan
- start a new red team vulnerability scan against a target ai application.
- get the status of a red team vulnerability scan.
- create red team target
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- sre
- submit an asynchronous scan of ai model inputs/outputs for threats.
- platform engineer
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get or delete a specific red team scan target.
- start ai red team vulnerability scans.
- get red team scan results
- tenant operator
- threat intelligence
- ai runtime security scanning and automated red teaming for ai applications.
- manages multi-tenant hierarchies and service group configurations for mssps.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- ai security
- cloud security
- list all available attack categories for red team vulnerability scans.
- network security
- analyzes suspicious files and samples for malware characteristics.
- data protection analyst
- malware researcher
- saas security admin
- ai red teaming
- enterprise browser policy management and secure browsing.
- monitors network health, performance, and digital experience metrics.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- start a new red team vulnerability scan against a target.
- list available attack categories for red teaming.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- proactively searches for threats and iocs across telemetry data.
- get results of an asynchronous ai security scan.
- compliance officer
- compliance team
- submit a synchronous ai security scan.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- designs and implements network security architectures and policies.
- manages enterprise browser policies and secure browsing configurations.
- palo alto networks
- cloud security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- llm security
- data loss prevention, saas security monitoring, and identity security posture.
- submit async scan
- xdr
- prompt injection
- get a specific ai security profile.
- cloud security posture management, compliance monitoring, and workload protection.
- sd wan operator
- get red team scan status
- incident responder
- researches threat actors, malware campaigns, and vulnerability trends.
- list ai security profiles.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- submit a synchronous ai security scan of model inputs/outputs for threats like prompt injection, data leakage, and malicious content.
- get async scan results
- list attack categories
- executes containment, eradication, and recovery actions during security incidents.
- list all ai security profiles with pagination.
- iam admin
- manages service accounts, roles, and access policies for platform api access.
- cybersecurity
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- firewall
- conducts automated adversarial testing against ai systems and llm applications.
- list red team targets
- network architect
- subscription manager
- get results of a red team vulnerability scan with optional filters.
- submit sync scan
- manage ai red teaming scan targets.
- sase admin
- get results of a red team vulnerability scan.
- submit a synchronous scan of ai model inputs/outputs for threats.
- red team operator
- manage enterprise browser policies, user sessions, and deployments.
- ai security engineer
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- get the results of a previously submitted asynchronous scan.
- delete red team target
- create a new red team scan target for ai application vulnerability testing.
- manages logging infrastructure, integrations, and platform automation.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get red team target
- list all red team scan targets.
- investigates dlp incidents and manages sensitive data protection policies.
- get ai profile
- submit an asynchronous ai security scan of model inputs/outputs for threats.
- enterprise it
- get a specific ai security profile by name.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- list all red team scan targets with optional type filter.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- get results of a red team vulnerability scan with optional category and severity filters.
- browser security admin
- monitors and remediates cloud security misconfigurations and compliance violations.
- list ai profiles
- digital experience monitoring, log management, and best practice assessment.
- threat intel analyst
- vulnerability manager
- firewall policy management, network objects, and cloud-native firewall configuration.
- threat hunter
- secure access service edge with remote networking, sd-wan, and zero trust access.
- network security engineer
- secures ai applications with runtime scanning and vulnerability assessment.
- soar
- mssp operator
- network operations
- submit an asynchronous ai security scan.
- designs sase and sd-wan network architectures for secure remote access.
- manages multi-tenant security operations at scale for managed service providers.
- create a new red team scan target.
- identity and access management, tenant hierarchies, and subscription management.
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
