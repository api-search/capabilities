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
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- investigates dlp incidents and manages sensitive data protection policies.
- xdr
- create a new browser deployment.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- secures ai applications with runtime scanning and vulnerability assessment.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- list all browser policies with pagination.
- monitors network health, performance, and digital experience metrics.
- analyzes suspicious files and samples for malware characteristics.
- manages enterprise browser policies and secure browsing configurations.
- firewall policy management, network objects, and cloud-native firewall configuration.
- sre
- enterprise browser
- get user sessions
- designs sase and sd-wan network architectures for secure remote access.
- vulnerability manager
- soar
- firewall admin
- monitors and remediates cloud security misconfigurations and compliance violations.
- tenant operator
- list all browser users with pagination.
- soc analyst
- create a new browser policy.
- manages service accounts, roles, and access policies for platform api access.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- data loss prevention, saas security monitoring, and identity security posture.
- cloud security posture management, compliance monitoring, and workload protection.
- threat intelligence
- ai security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- manage browser deployments across platforms.
- compliance team
- enterprise it
- incident responder
- subscription manager
- malware researcher
- network operations
- manage enterprise browser policies, user sessions, and deployments.
- conducts automated adversarial testing against ai systems and llm applications.
- get sessions for a specific user.
- get a specific browser policy by id.
- threat intel analyst
- firewall
- browser security admin
- manage a specific browser policy by id.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- threat hunter
- browser security
- secure access service edge with remote networking, sd-wan, and zero trust access.
- compliance officer
- list browser deployments
- get browser policy
- get sessions for a specific browser user.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- update browser policy
- list enterprise browser users.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- ai runtime security scanning and automated red teaming for ai applications.
- saas security admin
- manages multi-tenant security operations at scale for managed service providers.
- create browser policy
- list browser users
- digital experience monitoring, log management, and best practice assessment.
- data protection analyst
- cloud security
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- platform engineer
- proactively searches for threats and iocs across telemetry data.
- network architect
- red team operator
- update a specific browser policy by id.
- executes containment, eradication, and recovery actions during security incidents.
- researches threat actors, malware campaigns, and vulnerability trends.
- sase
- delete a specific browser policy by id.
- cybersecurity
- list browser policies
- manages multi-tenant hierarchies and service group configurations for mssps.
- prisma access
- palo alto networks
- identity and access management, tenant hierarchies, and subscription management.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- cloud security engineer
- designs and implements network security architectures and policies.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- mssp operator
- list all browser deployments with pagination.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- create browser deployment
- manage enterprise browser security policies.
- sase admin
- iam admin
- enterprise browser policy management and secure browsing.
- network security
- sd wan operator
- manages logging infrastructure, integrations, and platform automation.
- delete browser policy
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- network security engineer
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
