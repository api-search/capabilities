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
- browser security
- red team operator
- delete a specific browser policy by id.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- list all browser deployments with pagination.
- network architect
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- data loss prevention, saas security monitoring, and identity security posture.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- create browser policy
- executes containment, eradication, and recovery actions during security incidents.
- get browser policy
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- vulnerability manager
- firewall policy management, network objects, and cloud-native firewall configuration.
- sase admin
- secures ai applications with runtime scanning and vulnerability assessment.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- cybersecurity
- delete browser policy
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get sessions for a specific browser user.
- monitors and remediates cloud security misconfigurations and compliance violations.
- investigates dlp incidents and manages sensitive data protection policies.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- analyzes suspicious files and samples for malware characteristics.
- update a specific browser policy by id.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- prisma access
- conducts automated adversarial testing against ai systems and llm applications.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- enterprise browser
- network security engineer
- manages enterprise browser policies and secure browsing configurations.
- xdr
- ai runtime security scanning and automated red teaming for ai applications.
- enterprise browser policy management and secure browsing.
- threat intel analyst
- soar
- platform engineer
- update browser policy
- manages multi-tenant hierarchies and service group configurations for mssps.
- manages logging infrastructure, integrations, and platform automation.
- investigates security incidents, triages alerts, and coordinates response actions.
- ai security engineer
- subscription manager
- incident responder
- create a new browser policy.
- designs and implements network security architectures and policies.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- cloud security
- saas security admin
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- create browser deployment
- manages multi-tenant security operations at scale for managed service providers.
- manages service accounts, roles, and access policies for platform api access.
- manage browser deployments across platforms.
- soc analyst
- identity and access management, tenant hierarchies, and subscription management.
- mssp operator
- network operations
- threat intelligence
- sre
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- proactively searches for threats and iocs across telemetry data.
- designs sase and sd-wan network architectures for secure remote access.
- list browser deployments
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- digital experience monitoring, log management, and best practice assessment.
- cloud security engineer
- list browser users
- get sessions for a specific user.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- enterprise it
- firewall
- data protection analyst
- palo alto networks
- firewall admin
- browser security admin
- iam admin
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- researches threat actors, malware campaigns, and vulnerability trends.
- network security
- threat hunter
- cloud security posture management, compliance monitoring, and workload protection.
- get a specific browser policy by id.
- manage enterprise browser security policies.
- tenant operator
- sase
- manage a specific browser policy by id.
- create a new browser deployment.
- list enterprise browser users.
- sd wan operator
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- list all browser users with pagination.
- compliance team
- manage enterprise browser policies, user sessions, and deployments.
- list all browser policies with pagination.
- list browser policies
- compliance officer
- get user sessions
- monitors network health, performance, and digital experience metrics.
- malware researcher
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
