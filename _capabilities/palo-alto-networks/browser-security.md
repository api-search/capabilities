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
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- manages service accounts, roles, and access policies for platform api access.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- manage enterprise browser policies, user sessions, and deployments.
- cloud security posture management, compliance monitoring, and workload protection.
- update browser policy
- compliance team
- subscription manager
- incident responder
- enterprise browser policy management and secure browsing.
- tenant operator
- red team operator
- mssp operator
- sase admin
- investigates dlp incidents and manages sensitive data protection policies.
- monitors network health, performance, and digital experience metrics.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- list browser users
- cloud security
- proactively searches for threats and iocs across telemetry data.
- conducts automated adversarial testing against ai systems and llm applications.
- sre
- list all browser users with pagination.
- data loss prevention, saas security monitoring, and identity security posture.
- list browser deployments
- manages enterprise browser policies and secure browsing configurations.
- manages logging infrastructure, integrations, and platform automation.
- ai runtime security scanning and automated red teaming for ai applications.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- firewall
- get a specific browser policy by id.
- network security
- manages multi-tenant security operations at scale for managed service providers.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- delete browser policy
- manage enterprise browser security policies.
- executes containment, eradication, and recovery actions during security incidents.
- data protection analyst
- list enterprise browser users.
- list browser policies
- palo alto networks
- vulnerability manager
- get browser policy
- xdr
- sase
- researches threat actors, malware campaigns, and vulnerability trends.
- monitors and remediates cloud security misconfigurations and compliance violations.
- soc analyst
- get user sessions
- delete a specific browser policy by id.
- create browser policy
- digital experience monitoring, log management, and best practice assessment.
- soar
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- update a specific browser policy by id.
- list all browser policies with pagination.
- sd wan operator
- manage a specific browser policy by id.
- secures ai applications with runtime scanning and vulnerability assessment.
- list all browser deployments with pagination.
- investigates security incidents, triages alerts, and coordinates response actions.
- network architect
- iam admin
- saas security admin
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get sessions for a specific user.
- manage browser deployments across platforms.
- create browser deployment
- browser security admin
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- network operations
- ai security engineer
- secure access service edge with remote networking, sd-wan, and zero trust access.
- create a new browser deployment.
- threat intelligence
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- designs sase and sd-wan network architectures for secure remote access.
- prisma access
- enterprise it
- cybersecurity
- create a new browser policy.
- compliance officer
- get sessions for a specific browser user.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- network security engineer
- browser security
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- platform engineer
- designs and implements network security architectures and policies.
- manages multi-tenant hierarchies and service group configurations for mssps.
- analyzes suspicious files and samples for malware characteristics.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- firewall policy management, network objects, and cloud-native firewall configuration.
- enterprise browser
- threat intel analyst
- firewall admin
- threat hunter
- identity and access management, tenant hierarchies, and subscription management.
- malware researcher
- cloud security engineer
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
