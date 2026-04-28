---
categories: []
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
- prisma access
- sase
- manage browser deployments across platforms.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- list browser users
- firewall admin
- soc analyst
- get a specific browser policy by id.
- list browser deployments
- get sessions for a specific browser user.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- sre
- create a new browser policy.
- list enterprise browser users.
- delete a specific browser policy by id.
- platform engineer
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- tenant operator
- manage enterprise browser security policies.
- threat intelligence
- ai runtime security scanning and automated red teaming for ai applications.
- manages multi-tenant hierarchies and service group configurations for mssps.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- cloud security
- network security
- analyzes suspicious files and samples for malware characteristics.
- data protection analyst
- malware researcher
- list all browser policies with pagination.
- saas security admin
- get browser policy
- list all browser deployments with pagination.
- enterprise browser policy management and secure browsing.
- monitors network health, performance, and digital experience metrics.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- proactively searches for threats and iocs across telemetry data.
- compliance officer
- create browser deployment
- compliance team
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- designs and implements network security architectures and policies.
- manages enterprise browser policies and secure browsing configurations.
- palo alto networks
- cloud security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- data loss prevention, saas security monitoring, and identity security posture.
- xdr
- update a specific browser policy by id.
- cloud security posture management, compliance monitoring, and workload protection.
- sd wan operator
- create a new browser deployment.
- update browser policy
- incident responder
- researches threat actors, malware campaigns, and vulnerability trends.
- list all browser users with pagination.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- executes containment, eradication, and recovery actions during security incidents.
- iam admin
- manages service accounts, roles, and access policies for platform api access.
- cybersecurity
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- firewall
- conducts automated adversarial testing against ai systems and llm applications.
- network architect
- subscription manager
- sase admin
- red team operator
- list browser policies
- manage enterprise browser policies, user sessions, and deployments.
- ai security engineer
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- browser security
- manages logging infrastructure, integrations, and platform automation.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- manage a specific browser policy by id.
- investigates dlp incidents and manages sensitive data protection policies.
- enterprise browser
- delete browser policy
- get sessions for a specific user.
- enterprise it
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- create browser policy
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- browser security admin
- monitors and remediates cloud security misconfigurations and compliance violations.
- digital experience monitoring, log management, and best practice assessment.
- get user sessions
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
- designs sase and sd-wan network architectures for secure remote access.
- manages multi-tenant security operations at scale for managed service providers.
- identity and access management, tenant hierarchies, and subscription management.
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
