---
consumed_apis:
- prisma-access-browser
description: Browser security capability for managing enterprise browser policies, user sessions, and deployments through the Prisma Access Browser API.
layout: capability
name: Palo Alto Networks Browser Security
operations:
- description: List all browser policies with pagination.
  method: GET
  name: list-browser-policies
  path: /v1/browser-policies
- description: Create a new browser policy.
  method: POST
  name: create-browser-policy
  path: /v1/browser-policies
- description: Get a specific browser policy by ID.
  method: GET
  name: get-browser-policy
  path: /v1/browser-policies/{policy_id}
- description: Update a specific browser policy by ID.
  method: PUT
  name: update-browser-policy
  path: /v1/browser-policies/{policy_id}
- description: Delete a specific browser policy by ID.
  method: DELETE
  name: delete-browser-policy
  path: /v1/browser-policies/{policy_id}
- description: List all browser users with pagination.
  method: GET
  name: list-browser-users
  path: /v1/browser-users
- description: Get sessions for a specific user.
  method: GET
  name: get-user-sessions
  path: /v1/browser-users/{user_id}/sessions
- description: List all browser deployments with pagination.
  method: GET
  name: list-browser-deployments
  path: /v1/browser-deployments
- description: Create a new browser deployment.
  method: POST
  name: create-browser-deployment
  path: /v1/browser-deployments
personas:
- description: Manages enterprise browser policies and secure browsing configurations.
  id: browser-security-admin
  name: Browser Security Admin
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- vulnerability manager
- sd wan operator
- enterprise browser policy management and secure browsing.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- designs and implements network security architectures and policies.
- firewall
- compliance officer
- manages enterprise browser policies and secure browsing configurations.
- update a specific browser policy by id.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- data protection analyst
- create browser deployment
- mssp operator
- update browser policy
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- executes containment, eradication, and recovery actions during security incidents.
- monitors network health, performance, and digital experience metrics.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- manages service accounts, roles, and access policies for platform api access.
- cybersecurity
- threat intelligence
- malware researcher
- data loss prevention, saas security monitoring, and identity security posture.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- delete browser policy
- analyzes suspicious files and samples for malware characteristics.
- saas security admin
- list all browser policies with pagination.
- designs sase and sd-wan network architectures for secure remote access.
- firewall admin
- secures ai applications with runtime scanning and vulnerability assessment.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- red team operator
- delete a specific browser policy by id.
- enterprise browser
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- sase
- create browser policy
- ai runtime security scanning and automated red teaming for ai applications.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- network security engineer
- browser security admin
- list all browser deployments with pagination.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- get sessions for a specific user.
- tenant operator
- investigates dlp incidents and manages sensitive data protection policies.
- threat intel analyst
- manage a specific browser policy by id.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- list browser deployments
- browser security
- subscription manager
- manages multi-tenant security operations at scale for managed service providers.
- network operations
- cloud security
- create a new browser deployment.
- identity and access management, tenant hierarchies, and subscription management.
- soar
- incident responder
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- create a new browser policy.
- list browser users
- soc analyst
- xdr
- get user sessions
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- ai security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- list all browser users with pagination.
- compliance team
- enterprise it
- cloud security engineer
- researches threat actors, malware campaigns, and vulnerability trends.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- manages logging infrastructure, integrations, and platform automation.
- network security
- palo alto networks
- threat hunter
- list enterprise browser users.
- monitors and remediates cloud security misconfigurations and compliance violations.
- proactively searches for threats and iocs across telemetry data.
- get sessions for a specific browser user.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- firewall policy management, network objects, and cloud-native firewall configuration.
- sase admin
- cloud security posture management, compliance monitoring, and workload protection.
- prisma access
- network architect
- manage enterprise browser policies, user sessions, and deployments.
- manage browser deployments across platforms.
- get a specific browser policy by id.
- get browser policy
- manage enterprise browser security policies.
- iam admin
- sre
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- digital experience monitoring, log management, and best practice assessment.
- list browser policies
- conducts automated adversarial testing against ai systems and llm applications.
- platform engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
slug: browser-security
tags:
- Palo Alto Networks
- Browser Security
- Enterprise Browser
- Prisma Access
tools:
- description: List all browser policies with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-browser-policies
- description: Create a new browser policy.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-browser-policy
- description: Get a specific browser policy by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-browser-policy
- description: Update a specific browser policy by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-browser-policy
- description: Delete a specific browser policy by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-browser-policy
- description: List all browser users with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-browser-users
- description: Get sessions for a specific user.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-user-sessions
- description: List all browser deployments with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-browser-deployments
- description: Create a new browser deployment.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-browser-deployment
---
