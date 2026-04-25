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
- monitors and remediates cloud security misconfigurations and compliance violations.
- manage browser deployments across platforms.
- delete a specific browser policy by id.
- network security
- get a specific browser policy by id.
- firewall
- compliance team
- designs sase and sd-wan network architectures for secure remote access.
- palo alto networks
- saas security admin
- investigates security incidents, triages alerts, and coordinates response actions.
- cloud security
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- ai security engineer
- executes containment, eradication, and recovery actions during security incidents.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- data loss prevention, saas security monitoring, and identity security posture.
- network architect
- manages enterprise browser policies and secure browsing configurations.
- create browser deployment
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- digital experience monitoring, log management, and best practice assessment.
- delete browser policy
- list enterprise browser users.
- tenant operator
- iam admin
- enterprise it
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- create a new browser policy.
- manages multi-tenant security operations at scale for managed service providers.
- firewall policy management, network objects, and cloud-native firewall configuration.
- update a specific browser policy by id.
- conducts automated adversarial testing against ai systems and llm applications.
- red team operator
- analyzes suspicious files and samples for malware characteristics.
- sd wan operator
- get sessions for a specific user.
- proactively searches for threats and iocs across telemetry data.
- firewall admin
- platform engineer
- manage enterprise browser policies, user sessions, and deployments.
- list all browser policies with pagination.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- data protection analyst
- sase
- secures ai applications with runtime scanning and vulnerability assessment.
- create browser policy
- sre
- get sessions for a specific browser user.
- browser security
- get browser policy
- cloud security engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
- enterprise browser policy management and secure browsing.
- monitors network health, performance, and digital experience metrics.
- manages logging infrastructure, integrations, and platform automation.
- mssp operator
- researches threat actors, malware campaigns, and vulnerability trends.
- threat intel analyst
- list browser deployments
- threat intelligence
- ai runtime security scanning and automated red teaming for ai applications.
- list browser policies
- threat hunter
- malware researcher
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- identity and access management, tenant hierarchies, and subscription management.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- vulnerability manager
- list all browser deployments with pagination.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- incident responder
- browser security admin
- enterprise browser
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- soar
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- prisma access
- investigates dlp incidents and manages sensitive data protection policies.
- cloud security posture management, compliance monitoring, and workload protection.
- update browser policy
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- subscription manager
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- sase admin
- network security engineer
- manage a specific browser policy by id.
- network operations
- list browser users
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- xdr
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages service accounts, roles, and access policies for platform api access.
- soc analyst
- cybersecurity
- designs and implements network security architectures and policies.
- compliance officer
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- list all browser users with pagination.
- get user sessions
- manage enterprise browser security policies.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- create a new browser deployment.
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
