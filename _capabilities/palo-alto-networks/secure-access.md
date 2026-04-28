---
categories: []
consumed_apis:
- prisma-access
- ztna-connector
- prisma-sd-wan
- sase-config-orchestration
- sase-5g
- sase-multitenant-interconnect
description: Unified secure access capability for managing remote networks, ZTNA connectors, SD-WAN sites, 5G network slices, and SASE configuration across Prisma Access, ZTNA Connector, SD-WAN, Config Orchestration, and 5G APIs.
layout: capability
name: Palo Alto Networks Secure Access
operations:
- description: List all remote networks with pagination.
  method: GET
  name: list-remote-networks
  path: /v1/remote-networks
- description: Create a new remote network.
  method: POST
  name: create-remote-network
  path: /v1/remote-networks
- description: Get a specific remote network by ID.
  method: GET
  name: get-remote-network
  path: /v1/remote-networks/{id}
- description: Update a specific remote network by ID.
  method: PUT
  name: update-remote-network
  path: /v1/remote-networks/{id}
- description: Delete a specific remote network by ID.
  method: DELETE
  name: delete-remote-network
  path: /v1/remote-networks/{id}
- description: List all service connections with pagination.
  method: GET
  name: list-service-connections
  path: /v1/service-connections
- description: Create a new service connection.
  method: POST
  name: create-service-connection
  path: /v1/service-connections
- description: Get a specific service connection by ID.
  method: GET
  name: get-service-connection
  path: /v1/service-connections/{id}
- description: Update a specific service connection by ID.
  method: PUT
  name: update-service-connection
  path: /v1/service-connections/{id}
- description: Delete a specific service connection by ID.
  method: DELETE
  name: delete-service-connection
  path: /v1/service-connections/{id}
- description: Get mobile agent infrastructure settings.
  method: GET
  name: get-mobile-agent-settings
  path: /v1/mobile-agent-settings
- description: Create or update mobile agent infrastructure settings.
  method: POST
  name: create-mobile-agent-settings
  path: /v1/mobile-agent-settings
- description: List all IKE gateways with pagination.
  method: GET
  name: list-ike-gateways
  path: /v1/ike-gateways
- description: List all orchestrated remote networks with optional filtering.
  method: GET
  name: list-orchestrated-remote-networks
  path: /v1/orchestrated-remote-networks
- description: Create a new orchestrated remote network configuration.
  method: POST
  name: create-orchestrated-remote-network
  path: /v1/orchestrated-remote-networks
- description: Get details of a specific orchestrated remote network by ID.
  method: GET
  name: get-orchestrated-remote-network
  path: /v1/orchestrated-remote-networks/{id}
- description: Update an existing orchestrated remote network configuration.
  method: PUT
  name: update-orchestrated-remote-network
  path: /v1/orchestrated-remote-networks/{id}
- description: Delete an orchestrated remote network by ID.
  method: DELETE
  name: delete-orchestrated-remote-network
  path: /v1/orchestrated-remote-networks/{id}
- description: Refresh the IKE gateway for a specific remote network.
  method: POST
  name: refresh-ike-gateway
  path: /v1/orchestrated-remote-networks/{id}/refresh-ike-gateway
- description: Get bandwidth allocations optionally filtered by location.
  method: GET
  name: get-bandwidth-allocations
  path: /v1/bandwidth-allocations
- description: List all available Prisma Access locations.
  method: GET
  name: list-access-locations
  path: /v1/access-locations
- description: Get the onboarding status for a specific resource.
  method: GET
  name: get-onboarding-status
  path: /v1/onboarding-status/{id}
- description: List all ZTNA connectors.
  method: GET
  name: list-ztna-connectors
  path: /v1/ztna-connectors
- description: Create a new ZTNA connector.
  method: POST
  name: create-ztna-connector
  path: /v1/ztna-connectors
- description: Get a specific ZTNA connector by ID.
  method: GET
  name: get-ztna-connector
  path: /v1/ztna-connectors/{connector_id}
- description: Update a specific ZTNA connector by ID.
  method: PUT
  name: update-ztna-connector
  path: /v1/ztna-connectors/{connector_id}
- description: Delete a specific ZTNA connector by ID.
  method: DELETE
  name: delete-ztna-connector
  path: /v1/ztna-connectors/{connector_id}
- description: Schedule an upgrade for a ZTNA connector.
  method: POST
  name: schedule-connector-upgrade
  path: /v1/ztna-connectors/{connector_id}/upgrade
- description: List all ZTNA connector groups.
  method: GET
  name: list-connector-groups
  path: /v1/connector-groups
- description: Create a new ZTNA connector group.
  method: POST
  name: create-connector-group
  path: /v1/connector-groups
- description: Get a specific ZTNA connector group by ID.
  method: GET
  name: get-connector-group
  path: /v1/connector-groups/{group_id}
- description: Update a specific ZTNA connector group by ID.
  method: PUT
  name: update-connector-group
  path: /v1/connector-groups/{group_id}
- description: Delete a specific ZTNA connector group by ID.
  method: DELETE
  name: delete-connector-group
  path: /v1/connector-groups/{group_id}
- description: List all ZTNA applications.
  method: GET
  name: list-ztna-applications
  path: /v1/ztna-applications
- description: Create a new ZTNA application.
  method: POST
  name: create-ztna-application
  path: /v1/ztna-applications
- description: Get a specific ZTNA application by ID.
  method: GET
  name: get-ztna-application
  path: /v1/ztna-applications/{app_id}
- description: Update a specific ZTNA application by ID.
  method: PUT
  name: update-ztna-application
  path: /v1/ztna-applications/{app_id}
- description: Delete a specific ZTNA application by ID.
  method: DELETE
  name: delete-ztna-application
  path: /v1/ztna-applications/{app_id}
- description: List all FQDN rules.
  method: GET
  name: list-fqdn-rules
  path: /v1/fqdn-rules
- description: Create a new FQDN rule.
  method: POST
  name: create-fqdn-rule
  path: /v1/fqdn-rules
- description: List all subnet rules.
  method: GET
  name: list-subnet-rules
  path: /v1/subnet-rules
- description: Create a new subnet rule.
  method: POST
  name: create-subnet-rule
  path: /v1/subnet-rules
- description: Get ZTNA license information.
  method: GET
  name: get-ztna-licenses
  path: /v1/ztna-licenses
- description: Retrieve a list of SD-WAN sites.
  method: GET
  name: list-sdwan-sites
  path: /v1/sd-wan-sites
- description: Create a new SD-WAN site.
  method: POST
  name: create-sdwan-site
  path: /v1/sd-wan-sites
- description: Retrieve details for a specific SD-WAN site.
  method: GET
  name: get-sdwan-site
  path: /v1/sd-wan-sites/{site_id}
- description: Update an existing SD-WAN site.
  method: PUT
  name: update-sdwan-site
  path: /v1/sd-wan-sites/{site_id}
- description: Delete an SD-WAN site.
  method: DELETE
  name: delete-sdwan-site
  path: /v1/sd-wan-sites/{site_id}
- description: Retrieve WAN interfaces for a specific site.
  method: GET
  name: list-wan-interfaces
  path: /v1/sd-wan-sites/{site_id}/wan-interfaces
- description: Create a WAN interface for a specific site.
  method: POST
  name: create-wan-interface
  path: /v1/sd-wan-sites/{site_id}/wan-interfaces
- description: Retrieve LAN networks for a specific site.
  method: GET
  name: list-lan-networks
  path: /v1/sd-wan-sites/{site_id}/lan-networks
- description: Create a LAN network for a specific site.
  method: POST
  name: create-lan-network
  path: /v1/sd-wan-sites/{site_id}/lan-networks
- description: Retrieve a list of QoS rules.
  method: GET
  name: list-qos-rules
  path: /v1/qos-rules
- description: Create a new QoS rule.
  method: POST
  name: create-qos-rule
  path: /v1/qos-rules
- description: Retrieve a list of path rules.
  method: GET
  name: list-path-rules
  path: /v1/path-rules
- description: Create a new path rule.
  method: POST
  name: create-path-rule
  path: /v1/path-rules
- description: Retrieve monitoring metrics for a specific site.
  method: GET
  name: get-site-metrics
  path: /v1/sd-wan-sites/{site_id}/metrics
- description: Retrieve application usage metrics across the SD-WAN.
  method: GET
  name: get-application-usage
  path: /v1/application-usage
- description: Retrieve a list of SD-WAN alarms.
  method: GET
  name: list-sdwan-alarms
  path: /v1/sd-wan-alarms
- description: Retrieve a list of 5G network slices.
  method: GET
  name: list-network-slices
  path: /v1/network-slices
- description: Create a new 5G network slice.
  method: POST
  name: create-network-slice
  path: /v1/network-slices
- description: Retrieve details for a specific network slice.
  method: GET
  name: get-network-slice
  path: /v1/network-slices/{slice_id}
- description: Update an existing network slice.
  method: PUT
  name: update-network-slice
  path: /v1/network-slices/{slice_id}
- description: Delete a network slice.
  method: DELETE
  name: delete-network-slice
  path: /v1/network-slices/{slice_id}
- description: Retrieve a list of 5G security policies.
  method: GET
  name: list-5g-security-policies
  path: /v1/5g-security-policies
- description: Create a new 5G security policy.
  method: POST
  name: create-5g-security-policy
  path: /v1/5g-security-policies
- description: Retrieve details for a specific 5G security policy.
  method: GET
  name: get-5g-security-policy
  path: /v1/5g-security-policies/{policy_id}
- description: Update an existing 5G security policy.
  method: PUT
  name: update-5g-security-policy
  path: /v1/5g-security-policies/{policy_id}
- description: Delete a 5G security policy.
  method: DELETE
  name: delete-5g-security-policy
  path: /v1/5g-security-policies/{policy_id}
- description: Retrieve a list of 5G tenants.
  method: GET
  name: list-5g-tenants
  path: /v1/5g-tenants
- description: Create a new 5G tenant.
  method: POST
  name: create-5g-tenant
  path: /v1/5g-tenants
- description: Retrieve details for a specific 5G tenant.
  method: GET
  name: get-5g-tenant
  path: /v1/5g-tenants/{tenant_id}
- description: Update an existing 5G tenant.
  method: PUT
  name: update-5g-tenant
  path: /v1/5g-tenants/{tenant_id}
- description: Delete a 5G tenant.
  method: DELETE
  name: delete-5g-tenant
  path: /v1/5g-tenants/{tenant_id}
- description: Retrieve 5G security monitoring metrics.
  method: GET
  name: get-5g-security-metrics
  path: /v1/5g-metrics
personas:
- description: Designs SASE and SD-WAN network architectures for secure remote access.
  id: network-architect
  name: Network Architect
- description: Manages Prisma Access, SD-WAN, and ZTNA configurations for the SASE platform.
  id: sase-admin
  name: SASE Administrator
- description: Manages SD-WAN sites, WAN interfaces, and path policies for branch connectivity.
  id: sd-wan-operator
  name: SD-WAN Operator
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- refresh ike gateway for an orchestrated remote network.
- list sdwan sites
- firewall policy management, network objects, and cloud-native firewall configuration.
- get sdwan site
- create a lan network for a specific site.
- refresh the ike gateway for a specific remote network.
- sase admin
- designs and implements network security architectures and policies.
- get bandwidth allocations optionally filtered by location.
- 5g security policy by id.
- designs sase and sd-wan network architectures for secure remote access.
- list service connections
- update a specific ztna application by id.
- delete ztna application
- get the onboarding status for a specific resource.
- get mobile agent settings
- list network slices
- delete 5g tenant
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- 5g security policies.
- list all ike gateways with pagination.
- create a new fqdn rule.
- monitors and remediates cloud security misconfigurations and compliance violations.
- create a new prisma access remote network.
- update a specific prisma access remote network by id.
- delete a specific ztna connector by id.
- list all fqdn rules.
- manages multi-tenant security operations at scale for managed service providers.
- get 5g security metrics
- prisma access service connection by id.
- mssp operator
- create a new 5g tenant.
- delete a 5g security policy.
- path rules.
- create a new 5g security policy.
- threat hunter
- delete a specific ztna application by id.
- update a specific remote network by id.
- list wan interfaces
- retrieve monitoring metrics for a specific site.
- get a specific ztna connector group by id.
- network architect
- manages multi-tenant hierarchies and service group configurations for mssps.
- retrieve wan interfaces for a specific site.
- retrieve a list of sd-wan sites.
- update a specific prisma access service connection by id.
- incident responder
- network operations
- retrieve details for a specific 5g tenant.
- create subnet rule
- create a wan interface for a specific site.
- update 5g security policy
- update an existing 5g tenant.
- list ztna connectors
- sase
- get mobile agent infrastructure settings.
- retrieve a list of 5g network slices.
- sd-wan site metrics.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- soar
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- iam admin
- list access locations
- delete sdwan site
- executes containment, eradication, and recovery actions during security incidents.
- get ztna license information.
- analyzes suspicious files and samples for malware characteristics.
- get ztna connector
- get ztna application
- manage enterprise browser policies, user sessions, and deployments.
- update an existing 5g network slice.
- get remote network
- create path rule
- delete a specific ztna connector group by id.
- palo alto networks
- manages logging infrastructure, integrations, and platform automation.
- 5g
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- list all ztna connectors.
- get application usage
- create network slice
- get a specific service connection by id.
- ztna
- list ike gateways
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- cybersecurity
- ike gateways.
- vulnerability manager
- get 5g tenant
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- update an existing orchestrated remote network configuration.
- malware researcher
- manages enterprise browser policies and secure browsing configurations.
- list connector groups
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- retrieve a list of path rules.
- get 5g security policy
- delete a specific prisma access service connection by id.
- manages service accounts, roles, and access policies for platform api access.
- sd-wan site by id.
- firewall
- list orchestrated remote networks
- ztna connectors.
- create lan network
- get site metrics
- 5g tenants.
- cloud security engineer
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- retrieve a list of 5g tenants.
- bandwidth allocations.
- create 5g security policy
- data protection analyst
- update a specific ztna connector by id.
- 5g security metrics.
- application usage metrics.
- create orchestrated remote network
- soc analyst
- ztna licenses.
- delete remote network
- create a new 5g network slice.
- update orchestrated remote network
- retrieve lan networks for a specific site.
- refresh ike gateway
- retrieve a list of 5g security policies.
- proactively searches for threats and iocs across telemetry data.
- red team operator
- list fqdn rules
- delete a network slice.
- list 5g tenants
- get details of a specific orchestrated remote network by id.
- prisma access remote networks.
- get connector group
- create ztna application
- get ztna licenses
- fqdn rules.
- qos rules.
- digital experience monitoring, log management, and best practice assessment.
- threat intelligence
- subnet rules.
- update a specific service connection by id.
- secures ai applications with runtime scanning and vulnerability assessment.
- create a new ztna application.
- create a new ztna connector group.
- create sdwan site
- list all remote networks with pagination.
- subscription manager
- delete 5g security policy
- onboarding status.
- get bandwidth allocations
- update 5g tenant
- ai runtime security scanning and automated red teaming for ai applications.
- create a new prisma access service connection.
- ztna connector groups.
- list sdwan alarms
- get a specific remote network by id.
- get a specific prisma access service connection by id.
- list all orchestrated remote networks with optional filtering.
- list remote networks
- delete an sd-wan site.
- compliance officer
- delete a 5g network slice.
- update ztna connector
- service provider interconnect
- list 5g security policies
- network security engineer
- retrieve details for a specific 5g network slice.
- schedule connector upgrade
- cloud security
- create service connection
- data loss prevention, saas security monitoring, and identity security posture.
- ztna connector by id.
- prisma access remote network by id.
- saas security admin
- enterprise browser policy management and secure browsing.
- update sdwan site
- update an existing network slice.
- firewall admin
- tenant operator
- list all ztna connector groups.
- create a new remote network.
- prisma access locations.
- threat intel analyst
- cloud security posture management, compliance monitoring, and workload protection.
- update an existing 5g security policy.
- lan networks for an sd-wan site.
- 5g network slices.
- delete a specific prisma access remote network by id.
- list all orchestrated remote networks with optional filtering by location and status.
- list ztna applications
- list all ztna applications.
- update network slice
- investigates dlp incidents and manages sensitive data protection policies.
- create ztna connector
- compliance team
- delete a specific remote network by id.
- update remote network
- sd-wan sites.
- retrieve a list of qos rules.
- update a specific ztna connector group by id.
- mobile agent infrastructure settings.
- schedule ztna connector upgrade.
- create a new qos rule.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- retrieve details for a specific sd-wan site.
- delete an orchestrated remote network by id.
- create a new service connection.
- delete a specific service connection by id.
- schedule an upgrade for a ztna connector.
- investigates security incidents, triages alerts, and coordinates response actions.
- create a new sd-wan site.
- sase config orchestration remote networks.
- list qos rules
- get network slice
- create 5g tenant
- sd-wan alarms.
- delete ztna connector
- create mobile agent settings
- list all prisma access remote networks with pagination.
- conducts automated adversarial testing against ai systems and llm applications.
- delete connector group
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- 5g tenant by id.
- secure access
- list all available prisma access locations.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- researches threat actors, malware campaigns, and vulnerability trends.
- retrieve a list of sd-wan alarms.
- retrieve details for a specific network slice.
- ai security engineer
- list all service connections with pagination.
- get onboarding status
- network security
- create fqdn rule
- retrieve details for a specific 5g security policy.
- browser security admin
- delete service connection
- wan interfaces for an sd-wan site.
- create a new path rule.
- update service connection
- list lan networks
- list path rules
- get a specific prisma access remote network by id.
- monitors network health, performance, and digital experience metrics.
- ztna applications.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- sd-wan
- delete orchestrated remote network
- get service connection
- create qos rule
- retrieve application usage metrics across the sd-wan.
- 5g network slice by id.
- xdr
- create a new subnet rule.
- sd wan operator
- create connector group
- sase config orchestration remote network by id.
- update an existing sd-wan site.
- prisma access service connections.
- update connector group
- update ztna application
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- ztna connector group by id.
- create a new orchestrated remote network configuration.
- retrieve 5g security monitoring metrics.
- get orchestrated remote network
- list all subnet rules.
- sre
- create wan interface
- ztna application by id.
- platform engineer
- enterprise it
- list all prisma access service connections with pagination.
- get a specific ztna application by id.
- list subnet rules
- create remote network
- create or update mobile agent infrastructure settings.
- delete a 5g tenant.
- delete network slice
- retrieve monitoring metrics for a specific sd-wan site.
- identity and access management, tenant hierarchies, and subscription management.
- get a specific ztna connector by id.
- create a new ztna connector.
slug: secure-access
tags:
- Palo Alto Networks
- Secure Access
- SASE
- SD-WAN
- ZTNA
- 5G
- Service Provider Interconnect
tools:
- description: List all Prisma Access remote networks with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-remote-networks
- description: Create a new Prisma Access remote network.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-remote-network
- description: Get a specific Prisma Access remote network by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-remote-network
- description: Update a specific Prisma Access remote network by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-remote-network
- description: Delete a specific Prisma Access remote network by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-remote-network
- description: List all Prisma Access service connections with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-service-connections
- description: Create a new Prisma Access service connection.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-service-connection
- description: Get a specific Prisma Access service connection by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-service-connection
- description: Update a specific Prisma Access service connection by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-service-connection
- description: Delete a specific Prisma Access service connection by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-service-connection
- description: Get mobile agent infrastructure settings.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-mobile-agent-settings
- description: Create or update mobile agent infrastructure settings.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-mobile-agent-settings
- description: List all IKE gateways with pagination.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-ike-gateways
- description: List all ZTNA connectors.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-ztna-connectors
- description: Create a new ZTNA connector.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-ztna-connector
- description: Get a specific ZTNA connector by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-ztna-connector
- description: Update a specific ZTNA connector by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-ztna-connector
- description: Delete a specific ZTNA connector by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-ztna-connector
- description: Schedule an upgrade for a ZTNA connector.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: schedule-connector-upgrade
- description: List all ZTNA connector groups.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-connector-groups
- description: Create a new ZTNA connector group.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-connector-group
- description: Get a specific ZTNA connector group by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-connector-group
- description: Update a specific ZTNA connector group by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-connector-group
- description: Delete a specific ZTNA connector group by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-connector-group
- description: List all ZTNA applications.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-ztna-applications
- description: Create a new ZTNA application.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-ztna-application
- description: Get a specific ZTNA application by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-ztna-application
- description: Update a specific ZTNA application by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-ztna-application
- description: Delete a specific ZTNA application by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-ztna-application
- description: List all FQDN rules.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-fqdn-rules
- description: Create a new FQDN rule.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-fqdn-rule
- description: List all subnet rules.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-subnet-rules
- description: Create a new subnet rule.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-subnet-rule
- description: Get ZTNA license information.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-ztna-licenses
- description: Retrieve a list of SD-WAN sites.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-sdwan-sites
- description: Create a new SD-WAN site.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-sdwan-site
- description: Retrieve details for a specific SD-WAN site.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-sdwan-site
- description: Update an existing SD-WAN site.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-sdwan-site
- description: Delete an SD-WAN site.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-sdwan-site
- description: Retrieve WAN interfaces for a specific site.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-wan-interfaces
- description: Create a WAN interface for a specific site.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-wan-interface
- description: Retrieve LAN networks for a specific site.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-lan-networks
- description: Create a LAN network for a specific site.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-lan-network
- description: Retrieve a list of QoS rules.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-qos-rules
- description: Create a new QoS rule.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-qos-rule
- description: Retrieve a list of path rules.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-path-rules
- description: Create a new path rule.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-path-rule
- description: Retrieve monitoring metrics for a specific SD-WAN site.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-site-metrics
- description: Retrieve application usage metrics across the SD-WAN.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-application-usage
- description: Retrieve a list of SD-WAN alarms.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-sdwan-alarms
- description: List all orchestrated remote networks with optional filtering by location and status.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-orchestrated-remote-networks
- description: Create a new orchestrated remote network configuration.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-orchestrated-remote-network
- description: Get details of a specific orchestrated remote network by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-orchestrated-remote-network
- description: Update an existing orchestrated remote network configuration.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-orchestrated-remote-network
- description: Delete an orchestrated remote network by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-orchestrated-remote-network
- description: Refresh the IKE gateway for a specific remote network.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: refresh-ike-gateway
- description: Get bandwidth allocations optionally filtered by location.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-bandwidth-allocations
- description: List all available Prisma Access locations.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-access-locations
- description: Get the onboarding status for a specific resource.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-onboarding-status
- description: Retrieve a list of 5G network slices.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-network-slices
- description: Create a new 5G network slice.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-network-slice
- description: Retrieve details for a specific 5G network slice.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-network-slice
- description: Update an existing 5G network slice.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-network-slice
- description: Delete a 5G network slice.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-network-slice
- description: Retrieve a list of 5G security policies.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-5g-security-policies
- description: Create a new 5G security policy.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-5g-security-policy
- description: Retrieve details for a specific 5G security policy.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-5g-security-policy
- description: Update an existing 5G security policy.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-5g-security-policy
- description: Delete a 5G security policy.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-5g-security-policy
- description: Retrieve a list of 5G tenants.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-5g-tenants
- description: Create a new 5G tenant.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-5g-tenant
- description: Retrieve details for a specific 5G tenant.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-5g-tenant
- description: Update an existing 5G tenant.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-5g-tenant
- description: Delete a 5G tenant.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-5g-tenant
- description: Retrieve 5G security monitoring metrics.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-5g-security-metrics
---
