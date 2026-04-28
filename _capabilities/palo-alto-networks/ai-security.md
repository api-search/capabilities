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
- threat intel analyst
- analyzes suspicious files and samples for malware characteristics.
- ai security
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- get a specific red team scan target by id.
- enterprise browser policy management and secure browsing.
- compliance team
- conducts automated adversarial testing against ai systems and llm applications.
- list all available attack categories for red team vulnerability scans.
- browser security admin
- create red team target
- submit an asynchronous scan of ai model inputs/outputs for threats.
- create a new red team scan target for ai application vulnerability testing.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- llm security
- cloud security posture management, compliance monitoring, and workload protection.
- sre
- list available attack categories for red teaming.
- designs sase and sd-wan network architectures for secure remote access.
- ai runtime security scanning and automated red teaming for ai applications.
- manage ai red teaming scan targets.
- submit a synchronous scan of ai model inputs/outputs for threats.
- saas security admin
- submit a synchronous ai security scan.
- firewall admin
- platform engineer
- list attack categories
- researches threat actors, malware campaigns, and vulnerability trends.
- red team operator
- sd wan operator
- start a new red team vulnerability scan against a target.
- manages multi-tenant hierarchies and service group configurations for mssps.
- network security engineer
- monitors network health, performance, and digital experience metrics.
- submit an asynchronous ai security scan of model inputs/outputs for threats.
- list all available attack categories for red team scans.
- cloud security
- mssp operator
- cloud security engineer
- start red team scan
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get results of a red team vulnerability scan with optional category and severity filters.
- firewall
- threat hunter
- secures ai applications with runtime scanning and vulnerability assessment.
- network security
- network operations
- data protection analyst
- start a new red team vulnerability scan against a target ai application.
- enterprise it
- get a specific ai security profile by name.
- delete red team target
- start ai red team vulnerability scans.
- list ai profiles
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- soc analyst
- submit sync scan
- network architect
- get red team scan status
- get red team target
- submit a synchronous ai security scan of model inputs/outputs for threats like prompt injection, data leakage, and malicious content.
- get a specific ai security profile.
- get red team scan results
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- submit an asynchronous ai security scan.
- get results of a red team vulnerability scan.
- tenant operator
- manage enterprise browser policies, user sessions, and deployments.
- get async scan results
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- create a new red team scan target.
- ai security engineer
- get ai profile
- get the results of a previously submitted asynchronous scan.
- proactively searches for threats and iocs across telemetry data.
- sase admin
- list all red team scan targets with optional type filter.
- investigates dlp incidents and manages sensitive data protection policies.
- monitors and remediates cloud security misconfigurations and compliance violations.
- list red team targets
- subscription manager
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- firewall policy management, network objects, and cloud-native firewall configuration.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- delete a specific red team scan target by id.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get the status of a red team vulnerability scan.
- iam admin
- palo alto networks
- list ai security profiles.
- malware researcher
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- ai red teaming
- prompt injection
- soar
- submit async scan
- threat intelligence
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- sase
- manages multi-tenant security operations at scale for managed service providers.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- incident responder
- manages service accounts, roles, and access policies for platform api access.
- list all ai security profiles with pagination.
- vulnerability manager
- list all red team scan targets.
- cybersecurity
- digital experience monitoring, log management, and best practice assessment.
- manages logging infrastructure, integrations, and platform automation.
- xdr
- executes containment, eradication, and recovery actions during security incidents.
- compliance officer
- get or delete a specific red team scan target.
- get results of a red team vulnerability scan with optional filters.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- designs and implements network security architectures and policies.
- identity and access management, tenant hierarchies, and subscription management.
- manages enterprise browser policies and secure browsing configurations.
- data loss prevention, saas security monitoring, and identity security posture.
- get results of a previously submitted asynchronous ai security scan.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- get results of an asynchronous ai security scan.
- investigates security incidents, triages alerts, and coordinates response actions.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
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
