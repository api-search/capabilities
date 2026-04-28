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
- firewall policy management, network objects, and cloud-native firewall configuration.
- sase admin
- designs and implements network security architectures and policies.
- designs sase and sd-wan network architectures for secure remote access.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- monitors and remediates cloud security misconfigurations and compliance violations.
- manages multi-tenant security operations at scale for managed service providers.
- mssp operator
- delete a specific browser policy by id.
- threat hunter
- network architect
- manages multi-tenant hierarchies and service group configurations for mssps.
- incident responder
- network operations
- sase
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- soar
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- iam admin
- executes containment, eradication, and recovery actions during security incidents.
- analyzes suspicious files and samples for malware characteristics.
- get a specific browser policy by id.
- manage enterprise browser policies, user sessions, and deployments.
- manages logging infrastructure, integrations, and platform automation.
- palo alto networks
- manage browser deployments across platforms.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- list all browser users with pagination.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- list browser policies
- vulnerability manager
- cybersecurity
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- malware researcher
- manages enterprise browser policies and secure browsing configurations.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- list browser users
- manages service accounts, roles, and access policies for platform api access.
- firewall
- cloud security engineer
- data protection analyst
- soc analyst
- proactively searches for threats and iocs across telemetry data.
- red team operator
- get browser policy
- list all browser policies with pagination.
- browser security
- update a specific browser policy by id.
- get sessions for a specific browser user.
- digital experience monitoring, log management, and best practice assessment.
- threat intelligence
- secures ai applications with runtime scanning and vulnerability assessment.
- subscription manager
- ai runtime security scanning and automated red teaming for ai applications.
- get sessions for a specific user.
- list browser deployments
- compliance officer
- get user sessions
- network security engineer
- cloud security
- data loss prevention, saas security monitoring, and identity security posture.
- saas security admin
- enterprise browser policy management and secure browsing.
- firewall admin
- tenant operator
- threat intel analyst
- cloud security posture management, compliance monitoring, and workload protection.
- investigates dlp incidents and manages sensitive data protection policies.
- list enterprise browser users.
- create browser policy
- manage enterprise browser security policies.
- compliance team
- delete browser policy
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- investigates security incidents, triages alerts, and coordinates response actions.
- list all browser deployments with pagination.
- manage a specific browser policy by id.
- conducts automated adversarial testing against ai systems and llm applications.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- enterprise browser
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- researches threat actors, malware campaigns, and vulnerability trends.
- network security
- ai security engineer
- update browser policy
- browser security admin
- monitors network health, performance, and digital experience metrics.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- create a new browser deployment.
- create a new browser policy.
- xdr
- sd wan operator
- prisma access
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- create browser deployment
- sre
- platform engineer
- enterprise it
- identity and access management, tenant hierarchies, and subscription management.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
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
