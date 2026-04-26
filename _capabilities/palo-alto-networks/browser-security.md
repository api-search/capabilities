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
- compliance officer
- create a new browser policy.
- vulnerability manager
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- threat intelligence
- monitors network health, performance, and digital experience metrics.
- soar
- analyzes suspicious files and samples for malware characteristics.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- firewall
- xdr
- update browser policy
- incident responder
- manage enterprise browser policies, user sessions, and deployments.
- subscription manager
- proactively searches for threats and iocs across telemetry data.
- list browser policies
- threat intel analyst
- soc analyst
- create browser policy
- tenant operator
- ai runtime security scanning and automated red teaming for ai applications.
- secures ai applications with runtime scanning and vulnerability assessment.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- enterprise browser policy management and secure browsing.
- enterprise it
- network security engineer
- sase admin
- investigates dlp incidents and manages sensitive data protection policies.
- create a new browser deployment.
- manages multi-tenant hierarchies and service group configurations for mssps.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- list browser deployments
- data loss prevention, saas security monitoring, and identity security posture.
- malware researcher
- delete a specific browser policy by id.
- cloud security
- ai security engineer
- firewall policy management, network objects, and cloud-native firewall configuration.
- update a specific browser policy by id.
- compliance team
- sre
- conducts automated adversarial testing against ai systems and llm applications.
- manages multi-tenant security operations at scale for managed service providers.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- list all browser policies with pagination.
- data protection analyst
- list browser users
- list all browser users with pagination.
- sase
- manages enterprise browser policies and secure browsing configurations.
- identity and access management, tenant hierarchies, and subscription management.
- monitors and remediates cloud security misconfigurations and compliance violations.
- manage a specific browser policy by id.
- browser security
- manages service accounts, roles, and access policies for platform api access.
- red team operator
- researches threat actors, malware campaigns, and vulnerability trends.
- iam admin
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- cloud security engineer
- manages logging infrastructure, integrations, and platform automation.
- mssp operator
- manage enterprise browser security policies.
- investigates security incidents, triages alerts, and coordinates response actions.
- palo alto networks
- list enterprise browser users.
- network security
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- prisma access
- executes containment, eradication, and recovery actions during security incidents.
- cloud security posture management, compliance monitoring, and workload protection.
- threat hunter
- create browser deployment
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- network operations
- get a specific browser policy by id.
- list all browser deployments with pagination.
- manage browser deployments across platforms.
- saas security admin
- designs and implements network security architectures and policies.
- get browser policy
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- delete browser policy
- digital experience monitoring, log management, and best practice assessment.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- get user sessions
- designs sase and sd-wan network architectures for secure remote access.
- network architect
- browser security admin
- cybersecurity
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- get sessions for a specific user.
- get sessions for a specific browser user.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- firewall admin
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- enterprise browser
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- sd wan operator
- platform engineer
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
