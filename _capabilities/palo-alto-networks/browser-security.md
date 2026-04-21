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
- investigates dlp incidents and manages sensitive data protection policies.
- ai security engineer
- browser security
- update a specific browser policy by id.
- manages logging infrastructure, integrations, and platform automation.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- enterprise browser
- firewall policy management, network objects, and cloud-native firewall configuration.
- cloud security posture management, compliance monitoring, and workload protection.
- threat hunter
- malware researcher
- enterprise it
- manage enterprise browser security policies.
- analyzes suspicious files and samples for malware characteristics.
- manages service accounts, roles, and access policies for platform api access.
- get a specific browser policy by id.
- digital experience monitoring, log management, and best practice assessment.
- create browser policy
- red team operator
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- palo alto networks
- secures ai applications with runtime scanning and vulnerability assessment.
- cloud security
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- cybersecurity
- xdr
- create a new browser policy.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- sase admin
- data loss prevention, saas security monitoring, and identity security posture.
- network architect
- list browser users
- investigates security incidents, triages alerts, and coordinates response actions.
- subscription manager
- list all browser deployments with pagination.
- proactively searches for threats and iocs across telemetry data.
- manage browser deployments across platforms.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- browser security admin
- list all browser policies with pagination.
- sd wan operator
- manage enterprise browser policies, user sessions, and deployments.
- monitors network health, performance, and digital experience metrics.
- manages enterprise browser policies and secure browsing configurations.
- iam admin
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- designs and implements network security architectures and policies.
- soar
- platform engineer
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- executes containment, eradication, and recovery actions during security incidents.
- saas security admin
- delete browser policy
- delete a specific browser policy by id.
- create a new browser deployment.
- designs sase and sd-wan network architectures for secure remote access.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- sre
- prisma access
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- list all browser users with pagination.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- threat intel analyst
- firewall
- cloud security engineer
- threat intelligence
- enterprise browser policy management and secure browsing.
- list enterprise browser users.
- incident responder
- conducts automated adversarial testing against ai systems and llm applications.
- manages multi-tenant security operations at scale for managed service providers.
- get sessions for a specific user.
- mssp operator
- ai runtime security scanning and automated red teaming for ai applications.
- data protection analyst
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- create browser deployment
- sase
- network security engineer
- get user sessions
- list browser deployments
- list browser policies
- network security
- monitors and remediates cloud security misconfigurations and compliance violations.
- identity and access management, tenant hierarchies, and subscription management.
- manages multi-tenant hierarchies and service group configurations for mssps.
- firewall admin
- update browser policy
- vulnerability manager
- get sessions for a specific browser user.
- soc analyst
- network operations
- manage a specific browser policy by id.
- compliance team
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- tenant operator
- compliance officer
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- researches threat actors, malware campaigns, and vulnerability trends.
- get browser policy
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
