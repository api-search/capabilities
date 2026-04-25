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
- vulnerability manager
- create a new red team scan target.
- sd wan operator
- enterprise browser policy management and secure browsing.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- designs and implements network security architectures and policies.
- firewall
- list ai profiles
- compliance officer
- list ai security profiles.
- manages enterprise browser policies and secure browsing configurations.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- data protection analyst
- get red team scan results
- mssp operator
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- executes containment, eradication, and recovery actions during security incidents.
- monitors network health, performance, and digital experience metrics.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- manages service accounts, roles, and access policies for platform api access.
- list all available attack categories for red team vulnerability scans.
- cybersecurity
- submit an asynchronous scan of ai model inputs/outputs for threats.
- threat intelligence
- malware researcher
- data loss prevention, saas security monitoring, and identity security posture.
- prompt injection
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- list attack categories
- analyzes suspicious files and samples for malware characteristics.
- list all red team scan targets.
- saas security admin
- manage ai red teaming scan targets.
- get red team scan status
- start a new red team vulnerability scan against a target ai application.
- list all available attack categories for red team scans.
- designs sase and sd-wan network architectures for secure remote access.
- submit an asynchronous ai security scan of model inputs/outputs for threats.
- firewall admin
- secures ai applications with runtime scanning and vulnerability assessment.
- list available attack categories for red teaming.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- submit a synchronous scan of ai model inputs/outputs for threats.
- red team operator
- submit async scan
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- sase
- get red team target
- get results of a previously submitted asynchronous ai security scan.
- ai runtime security scanning and automated red teaming for ai applications.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- network security engineer
- browser security admin
- llm security
- submit a synchronous ai security scan.
- create red team target
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- tenant operator
- investigates dlp incidents and manages sensitive data protection policies.
- threat intel analyst
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- submit a synchronous ai security scan of model inputs/outputs for threats like prompt injection, data leakage, and malicious content.
- get or delete a specific red team scan target.
- start red team scan
- subscription manager
- manages multi-tenant security operations at scale for managed service providers.
- network operations
- cloud security
- start a new red team vulnerability scan against a target.
- submit an asynchronous ai security scan.
- create a new red team scan target for ai application vulnerability testing.
- identity and access management, tenant hierarchies, and subscription management.
- soar
- incident responder
- get async scan results
- delete red team target
- get ai profile
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- soc analyst
- xdr
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- ai security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- list red team targets
- compliance team
- enterprise it
- cloud security engineer
- researches threat actors, malware campaigns, and vulnerability trends.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get results of a red team vulnerability scan with optional filters.
- manages logging infrastructure, integrations, and platform automation.
- ai red teaming
- get the status of a red team vulnerability scan.
- network security
- palo alto networks
- threat hunter
- get a specific red team scan target by id.
- monitors and remediates cloud security misconfigurations and compliance violations.
- ai security
- get results of a red team vulnerability scan.
- list all red team scan targets with optional type filter.
- proactively searches for threats and iocs across telemetry data.
- delete a specific red team scan target by id.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get results of a red team vulnerability scan with optional category and severity filters.
- submit sync scan
- firewall policy management, network objects, and cloud-native firewall configuration.
- sase admin
- cloud security posture management, compliance monitoring, and workload protection.
- get the results of a previously submitted asynchronous scan.
- network architect
- get a specific ai security profile by name.
- manage enterprise browser policies, user sessions, and deployments.
- get results of an asynchronous ai security scan.
- iam admin
- sre
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- digital experience monitoring, log management, and best practice assessment.
- get a specific ai security profile.
- list all ai security profiles with pagination.
- start ai red team vulnerability scans.
- conducts automated adversarial testing against ai systems and llm applications.
- platform engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
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
