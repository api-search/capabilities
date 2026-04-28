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
- prisma access service connections.
- create ztna application
- list service connections
- update an existing sd-wan site.
- create a new remote network.
- 5g tenants.
- network security engineer
- list all orchestrated remote networks with optional filtering.
- cloud security
- ztna connector by id.
- create a new ztna application.
- delete a 5g network slice.
- delete ztna connector
- create a new path rule.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- sase
- designs and implements network security architectures and policies.
- prisma access service connection by id.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- list 5g security policies
- create a new 5g tenant.
- get a specific prisma access service connection by id.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- get onboarding status
- create a new 5g security policy.
- create fqdn rule
- compliance team
- soc analyst
- prisma access remote network by id.
- delete connector group
- list ztna applications
- update ztna connector
- list sdwan sites
- update an existing orchestrated remote network configuration.
- sre
- data loss prevention, saas security monitoring, and identity security posture.
- get network slice
- network security
- onboarding status.
- subnet rules.
- ike gateways.
- list all fqdn rules.
- create remote network
- create a new service connection.
- list all orchestrated remote networks with optional filtering by location and status.
- delete a network slice.
- get 5g security policy
- list subnet rules
- schedule connector upgrade
- 5g network slice by id.
- manages enterprise browser policies and secure browsing configurations.
- create orchestrated remote network
- refresh ike gateway for an orchestrated remote network.
- ztna applications.
- create a lan network for a specific site.
- manages service accounts, roles, and access policies for platform api access.
- update 5g security policy
- researches threat actors, malware campaigns, and vulnerability trends.
- create lan network
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- ztna licenses.
- cybersecurity
- get details of a specific orchestrated remote network by id.
- update ztna application
- 5g tenant by id.
- create wan interface
- manages multi-tenant security operations at scale for managed service providers.
- update a specific prisma access service connection by id.
- conducts automated adversarial testing against ai systems and llm applications.
- list access locations
- proactively searches for threats and iocs across telemetry data.
- delete 5g security policy
- create sdwan site
- list qos rules
- list ike gateways
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- get a specific service connection by id.
- get ztna application
- delete a 5g tenant.
- get a specific prisma access remote network by id.
- get bandwidth allocations optionally filtered by location.
- schedule ztna connector upgrade.
- ztna application by id.
- delete a specific ztna connector group by id.
- delete an sd-wan site.
- list all remote networks with pagination.
- create service connection
- qos rules.
- get application usage
- 5g security metrics.
- update a specific prisma access remote network by id.
- update a specific remote network by id.
- delete a specific prisma access remote network by id.
- sd wan operator
- monitors and remediates cloud security misconfigurations and compliance violations.
- get service connection
- update service connection
- data protection analyst
- list remote networks
- get ztna connector
- get the onboarding status for a specific resource.
- prisma access remote networks.
- compliance officer
- network architect
- create a new orchestrated remote network configuration.
- retrieve a list of sd-wan alarms.
- list network slices
- incident responder
- xdr
- create a new fqdn rule.
- wan interfaces for an sd-wan site.
- list all ztna connector groups.
- ztna connector group by id.
- fqdn rules.
- list ztna connectors
- threat intel analyst
- retrieve monitoring metrics for a specific site.
- investigates security incidents, triages alerts, and coordinates response actions.
- create a wan interface for a specific site.
- get sdwan site
- delete a 5g security policy.
- retrieve 5g security monitoring metrics.
- analyzes suspicious files and samples for malware characteristics.
- ai runtime security scanning and automated red teaming for ai applications.
- get ztna licenses
- retrieve a list of path rules.
- sd-wan sites.
- update a specific service connection by id.
- create mobile agent settings
- retrieve application usage metrics across the sd-wan.
- update sdwan site
- 5g network slices.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get ztna license information.
- retrieve wan interfaces for a specific site.
- create subnet rule
- retrieve details for a specific 5g security policy.
- ztna connectors.
- retrieve a list of sd-wan sites.
- delete sdwan site
- create a new 5g network slice.
- investigates dlp incidents and manages sensitive data protection policies.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- schedule an upgrade for a ztna connector.
- get a specific ztna connector group by id.
- delete a specific service connection by id.
- create path rule
- delete remote network
- mobile agent infrastructure settings.
- malware researcher
- ztna
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- cloud security engineer
- sd-wan site by id.
- update connector group
- get connector group
- update remote network
- get a specific remote network by id.
- create a new ztna connector.
- get site metrics
- retrieve details for a specific sd-wan site.
- list sdwan alarms
- list wan interfaces
- retrieve details for a specific 5g tenant.
- secures ai applications with runtime scanning and vulnerability assessment.
- cloud security posture management, compliance monitoring, and workload protection.
- iam admin
- list all available prisma access locations.
- list all ztna applications.
- 5g
- delete ztna application
- saas security admin
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- update a specific ztna connector by id.
- retrieve lan networks for a specific site.
- 5g security policy by id.
- delete 5g tenant
- manage enterprise browser policies, user sessions, and deployments.
- list all prisma access service connections with pagination.
- update an existing 5g security policy.
- get orchestrated remote network
- retrieve a list of 5g security policies.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- list lan networks
- create qos rule
- retrieve details for a specific network slice.
- bandwidth allocations.
- create a new subnet rule.
- tenant operator
- get 5g security metrics
- update an existing 5g tenant.
- create 5g security policy
- enterprise it
- monitors network health, performance, and digital experience metrics.
- create or update mobile agent infrastructure settings.
- list all ike gateways with pagination.
- path rules.
- update orchestrated remote network
- update a specific ztna application by id.
- lan networks for an sd-wan site.
- create connector group
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- refresh the ike gateway for a specific remote network.
- manages multi-tenant hierarchies and service group configurations for mssps.
- sd-wan alarms.
- ai security engineer
- identity and access management, tenant hierarchies, and subscription management.
- 5g security policies.
- retrieve details for a specific 5g network slice.
- application usage metrics.
- palo alto networks
- create a new sd-wan site.
- vulnerability manager
- sd-wan
- update a specific ztna connector group by id.
- subscription manager
- browser security admin
- create a new prisma access remote network.
- update network slice
- firewall policy management, network objects, and cloud-native firewall configuration.
- service provider interconnect
- list orchestrated remote networks
- get 5g tenant
- create a new prisma access service connection.
- firewall admin
- delete an orchestrated remote network by id.
- update an existing network slice.
- threat intelligence
- update 5g tenant
- delete a specific ztna connector by id.
- list all service connections with pagination.
- create ztna connector
- delete orchestrated remote network
- list fqdn rules
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- firewall
- list 5g tenants
- delete a specific prisma access service connection by id.
- secure access
- network operations
- designs sase and sd-wan network architectures for secure remote access.
- sd-wan site metrics.
- create network slice
- delete a specific remote network by id.
- retrieve a list of 5g tenants.
- delete a specific ztna application by id.
- digital experience monitoring, log management, and best practice assessment.
- threat hunter
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- soar
- sase admin
- get mobile agent settings
- list all prisma access remote networks with pagination.
- create a new ztna connector group.
- red team operator
- get bandwidth allocations
- retrieve a list of 5g network slices.
- prisma access locations.
- sase config orchestration remote network by id.
- get remote network
- list all ztna connectors.
- platform engineer
- delete network slice
- retrieve monitoring metrics for a specific sd-wan site.
- manages logging infrastructure, integrations, and platform automation.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- get a specific ztna application by id.
- refresh ike gateway
- list connector groups
- list all subnet rules.
- retrieve a list of qos rules.
- executes containment, eradication, and recovery actions during security incidents.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- create 5g tenant
- ztna connector groups.
- enterprise browser policy management and secure browsing.
- delete service connection
- sase config orchestration remote networks.
- get a specific ztna connector by id.
- get mobile agent infrastructure settings.
- create a new qos rule.
- list path rules
- update an existing 5g network slice.
- mssp operator
slug: secure-access
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Palo Alto Networks Secure Access\"\n  description: \"Unified secure access capability for managing remote networks, ZTNA connectors, SD-WAN sites, 5G network slices, and SASE configuration across Prisma Access, ZTNA Connector, SD-WAN, Config Orchestration, and 5G APIs.\"\n  tags:\n    - Palo Alto Networks\n    - Secure Access\n    - SASE\n    - SD-WAN\n    - ZTNA\n    - 5G\n    - Service Provider Interconnect\n  created: \"2026-04-16\"\n  modified: \"2026-04-16\"\n\nbinds:\n  - namespace: env\n    keys:\n      PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: prisma-access\n      location: ./shared/prisma-access.yaml\n    - import: ztna-connector\n      location: ./shared/ztna-connector.yaml\n    - import: prisma-sd-wan\n      location: ./shared/prisma-sd-wan.yaml\n    - import: sase-config-orchestration\n      location: ./shared/sase-config-orchestration.yaml\n    - import: sase-5g\n     \
  \ location: ./shared/sase-5g.yaml\n    - import: sase-multitenant-interconnect\n      location: ./shared/sase-multitenant-interconnect.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: secure-access-api\n      description: \"Unified REST API for secure access management.\"\n      resources:\n\n        # ── Remote Networks & VPN (Prisma Access) ────────────────────────\n        - path: /v1/remote-networks\n          name: remote-networks\n          description: \"Prisma Access remote networks.\"\n          operations:\n            - method: GET\n              name: list-remote-networks\n              description: \"List all remote networks with pagination.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"\
  prisma-access.list-remote-networks\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-remote-network\n              description: \"Create a new remote network.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: location\n                  in: body\n                  type: string\n                  required: true\n                - name: subnets\n                  in: body\n                  type: string\n                  required: true\n                - name: ike_gateway\n                  in: body\n                  type: string\n                  required: true\n              call: \"prisma-access.create-remote-network\"\n              with:\n    \
  \            name: \"rest.name\"\n                location: \"rest.location\"\n                subnets: \"rest.subnets\"\n                ike_gateway: \"rest.ike_gateway\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/remote-networks/{id}\n          name: remote-network\n          description: \"Prisma Access remote network by ID.\"\n          operations:\n            - method: GET\n              name: get-remote-network\n              description: \"Get a specific remote network by ID.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access.get-remote-network\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-remote-network\n\
  \              description: \"Update a specific remote network by ID.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access.update-remote-network\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-remote-network\n              description: \"Delete a specific remote network by ID.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access.delete-remote-network\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/service-connections\n\
  \          name: service-connections\n          description: \"Prisma Access service connections.\"\n          operations:\n            - method: GET\n              name: list-service-connections\n              description: \"List all service connections with pagination.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"prisma-access.list-service-connections\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-service-connection\n              description: \"Create a new service connection.\"\n              inputParameters:\n\
  \                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: ipsec_tunnel\n                  in: body\n                  type: string\n                  required: true\n                - name: region\n                  in: body\n                  type: string\n                  required: true\n              call: \"prisma-access.create-service-connection\"\n              with:\n                name: \"rest.name\"\n                ipsec_tunnel: \"rest.ipsec_tunnel\"\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/service-connections/{id}\n          name: service-connection\n          description: \"Prisma Access service connection by ID.\"\n          operations:\n            - method: GET\n              name: get-service-connection\n              description: \"Get a specific service connection\
  \ by ID.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access.get-service-connection\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-service-connection\n              description: \"Update a specific service connection by ID.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access.update-service-connection\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-service-connection\n              description:\
  \ \"Delete a specific service connection by ID.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-access.delete-service-connection\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/mobile-agent-settings\n          name: mobile-agent-settings\n          description: \"Mobile agent infrastructure settings.\"\n          operations:\n            - method: GET\n              name: get-mobile-agent-settings\n              description: \"Get mobile agent infrastructure settings.\"\n              call: \"prisma-access.get-mobile-agent-infrastructure-settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-mobile-agent-settings\n\
  \              description: \"Create or update mobile agent infrastructure settings.\"\n              inputParameters:\n                - name: settings\n                  in: body\n                  type: object\n                  required: true\n              call: \"prisma-access.create-mobile-agent-infrastructure-settings\"\n              with:\n                settings: \"rest.settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ike-gateways\n          name: ike-gateways\n          description: \"IKE gateways.\"\n          operations:\n            - method: GET\n              name: list-ike-gateways\n              description: \"List all IKE gateways with pagination.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n             \
  \     type: integer\n                  required: false\n              call: \"prisma-access.list-ike-gateways\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── SASE Orchestration ───────────────────────────────────────────\n        - path: /v1/orchestrated-remote-networks\n          name: orchestrated-remote-networks\n          description: \"SASE Config Orchestration remote networks.\"\n          operations:\n            - method: GET\n              name: list-orchestrated-remote-networks\n              description: \"List all orchestrated remote networks with optional filtering.\"\n              inputParameters:\n                - name: location\n                  in: query\n                  type: string\n                  required: false\n                - name: status\n                  in: query\n                \
  \  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"sase-config-orchestration.list-remote-networks\"\n              with:\n                location: \"rest.location\"\n                status: \"rest.status\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-orchestrated-remote-network\n              description: \"Create a new orchestrated remote network configuration.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n    \
  \            - name: location\n                  in: body\n                  type: string\n                  required: true\n                - name: subnets\n                  in: body\n                  type: object\n                  required: false\n                - name: ike_gateway\n                  in: body\n                  type: object\n                  required: false\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: bandwidth_mbps\n                  in: body\n                  type: integer\n                  required: false\n              call: \"sase-config-orchestration.create-remote-network\"\n              with:\n                name: \"rest.name\"\n                location: \"rest.location\"\n                subnets: \"rest.subnets\"\n                ike_gateway: \"rest.ike_gateway\"\n                description: \"rest.description\"\n                bandwidth_mbps:\
  \ \"rest.bandwidth_mbps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orchestrated-remote-networks/{id}\n          name: orchestrated-remote-network\n          description: \"SASE Config Orchestration remote network by ID.\"\n          operations:\n            - method: GET\n              name: get-orchestrated-remote-network\n              description: \"Get details of a specific orchestrated remote network by ID.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-config-orchestration.get-remote-network\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-orchestrated-remote-network\n              description: \"Update an\
  \ existing orchestrated remote network configuration.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n                - name: name\n                  in: body\n                  type: string\n                  required: false\n                - name: location\n                  in: body\n                  type: string\n                  required: false\n                - name: subnets\n                  in: body\n                  type: object\n                  required: false\n                - name: ike_gateway\n                  in: body\n                  type: object\n                  required: false\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: bandwidth_mbps\n                  in: body\n                  type: integer\n                  required: false\n      \
  \        call: \"sase-config-orchestration.update-remote-network\"\n              with:\n                id: \"rest.id\"\n                name: \"rest.name\"\n                location: \"rest.location\"\n                subnets: \"rest.subnets\"\n                ike_gateway: \"rest.ike_gateway\"\n                description: \"rest.description\"\n                bandwidth_mbps: \"rest.bandwidth_mbps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-orchestrated-remote-network\n              description: \"Delete an orchestrated remote network by ID.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-config-orchestration.delete-remote-network\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orchestrated-remote-networks/{id}/refresh-ike-gateway\n          name: refresh-ike-gateway\n          description: \"Refresh IKE gateway for an orchestrated remote network.\"\n          operations:\n            - method: POST\n              name: refresh-ike-gateway\n              description: \"Refresh the IKE gateway for a specific remote network.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-config-orchestration.refresh-ike-gateway\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bandwidth-allocations\n          name: bandwidth-allocations\n          description: \"Bandwidth allocations.\"\n          operations:\n            - method: GET\n       \
  \       name: get-bandwidth-allocations\n              description: \"Get bandwidth allocations optionally filtered by location.\"\n              inputParameters:\n                - name: location\n                  in: query\n                  type: string\n                  required: false\n              call: \"sase-config-orchestration.get-bandwidth-allocations\"\n              with:\n                location: \"rest.location\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/access-locations\n          name: access-locations\n          description: \"Prisma Access locations.\"\n          operations:\n            - method: GET\n              name: list-access-locations\n              description: \"List all available Prisma Access locations.\"\n              call: \"sase-config-orchestration.list-prisma-access-locations\"\n              outputParameters:\n                - type: array\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/onboarding-status/{id}\n          name: onboarding-status\n          description: \"Onboarding status.\"\n          operations:\n            - method: GET\n              name: get-onboarding-status\n              description: \"Get the onboarding status for a specific resource.\"\n              inputParameters:\n                - name: id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-config-orchestration.get-onboarding-status\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Zero Trust Network Access ────────────────────────────────────\n        - path: /v1/ztna-connectors\n          name: ztna-connectors\n          description: \"ZTNA connectors.\"\n          operations:\n            - method: GET\n              name: list-ztna-connectors\n              description:\
  \ \"List all ZTNA connectors.\"\n              inputParameters:\n                - name: group_id\n                  in: query\n                  type: string\n                  required: false\n                - name: status\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"ztna-connector.list-connectors\"\n              with:\n                group_id: \"rest.group_id\"\n                status: \"rest.status\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-ztna-connector\n     \
  \         description: \"Create a new ZTNA connector.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: group_id\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n              call: \"ztna-connector.create-connector\"\n              with:\n                name: \"rest.name\"\n                group_id: \"rest.group_id\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ztna-connectors/{connector_id}\n          name: ztna-connector\n          description: \"ZTNA connector by ID.\"\n          operations:\n            - method: GET\n              name: get-ztna-connector\n\
  \              description: \"Get a specific ZTNA connector by ID.\"\n              inputParameters:\n                - name: connector_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"ztna-connector.get-connector\"\n              with:\n                connector_id: \"rest.connector_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-ztna-connector\n              description: \"Update a specific ZTNA connector by ID.\"\n              inputParameters:\n                - name: connector_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"ztna-connector.update-connector\"\n              with:\n                connector_id: \"rest.connector_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \            - method: DELETE\n              name: delete-ztna-connector\n              description: \"Delete a specific ZTNA connector by ID.\"\n              inputParameters:\n                - name: connector_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"ztna-connector.delete-connector\"\n              with:\n                connector_id: \"rest.connector_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ztna-connectors/{connector_id}/upgrade\n          name: ztna-connector-upgrade\n          description: \"Schedule ZTNA connector upgrade.\"\n          operations:\n            - method: POST\n              name: schedule-connector-upgrade\n              description: \"Schedule an upgrade for a ZTNA connector.\"\n              inputParameters:\n                - name: connector_id\n                  in: path\n                  type: string\n\
  \                  required: true\n                - name: scheduled_at\n                  in: body\n                  type: string\n                  required: true\n                - name: target_version\n                  in: body\n                  type: string\n                  required: true\n              call: \"ztna-connector.schedule-connector-upgrade\"\n              with:\n                connector_id: \"rest.connector_id\"\n                scheduled_at: \"rest.scheduled_at\"\n                target_version: \"rest.target_version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/connector-groups\n          name: connector-groups\n          description: \"ZTNA connector groups.\"\n          operations:\n            - method: GET\n              name: list-connector-groups\n              description: \"List all ZTNA connector groups.\"\n              call: \"ztna-connector.list-connector-groups\"\n   \
  \           outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-connector-group\n              description: \"Create a new ZTNA connector group.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: region\n                  in: body\n                  type: string\n                  required: true\n              call: \"ztna-connector.create-connector-group\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/connector-groups/{group_id}\n\
  \          name: connector-group\n          description: \"ZTNA connector group by ID.\"\n          operations:\n            - method: GET\n              name: get-connector-group\n              description: \"Get a specific ZTNA connector group by ID.\"\n              inputParameters:\n                - name: group_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"ztna-connector.get-connector-group\"\n              with:\n                group_id: \"rest.group_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-connector-group\n              description: \"Update a specific ZTNA connector group by ID.\"\n              inputParameters:\n                - name: group_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"ztna-connector.update-connector-group\"\
  \n              with:\n                group_id: \"rest.group_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-connector-group\n              description: \"Delete a specific ZTNA connector group by ID.\"\n              inputParameters:\n                - name: group_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"ztna-connector.delete-connector-group\"\n              with:\n                group_id: \"rest.group_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ztna-applications\n          name: ztna-applications\n          description: \"ZTNA applications.\"\n          operations:\n            - method: GET\n              name: list-ztna-applications\n              description: \"List all ZTNA applications.\"\n             \
  \ call: \"ztna-connector.list-ztna-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-ztna-application\n              description: \"Create a new ZTNA application.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: group_id\n                  in: body\n                  type: string\n                  required: true\n                - name: fqdn\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: ports\n                  in: body\n                  type: object\n                  required: true\n                - name: protocols\n            \
  \      in: body\n                  type: object\n                  required: true\n                - name: enabled\n                  in: body\n                  type: boolean\n                  required: false\n              call: \"ztna-connector.create-ztna-application\"\n              with:\n                name: \"rest.name\"\n                group_id: \"rest.group_id\"\n                fqdn: \"rest.fqdn\"\n                description: \"rest.description\"\n                ports: \"rest.ports\"\n                protocols: \"rest.protocols\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ztna-applications/{app_id}\n          name: ztna-application\n          description: \"ZTNA application by ID.\"\n          operations:\n            - method: GET\n              name: get-ztna-application\n              description: \"Get a specific ZTNA application by ID.\"\n    \
  \          inputParameters:\n                - name: app_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"ztna-connector.get-ztna-application\"\n              with:\n                app_id: \"rest.app_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-ztna-application\n              description: \"Update a specific ZTNA application by ID.\"\n              inputParameters:\n                - name: app_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"ztna-connector.update-ztna-application\"\n              with:\n                app_id: \"rest.app_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-ztna-application\n              description:\
  \ \"Delete a specific ZTNA application by ID.\"\n              inputParameters:\n                - name: app_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"ztna-connector.delete-ztna-application\"\n              with:\n                app_id: \"rest.app_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fqdn-rules\n          name: fqdn-rules\n          description: \"FQDN rules.\"\n          operations:\n            - method: GET\n              name: list-fqdn-rules\n              description: \"List all FQDN rules.\"\n              call: \"ztna-connector.list-fqdn-rules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-fqdn-rule\n              description: \"Create a new FQDN rule.\"\n              inputParameters:\n              \
  \  - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: fqdn_pattern\n                  in: body\n                  type: string\n                  required: true\n                - name: group_id\n                  in: body\n                  type: string\n                  required: true\n                - name: ports\n                  in: body\n                  type: object\n                  required: true\n                - name: enabled\n                  in: body\n                  type: boolean\n                  required: false\n              call: \"ztna-connector.create-fqdn-rule\"\n              with:\n                name: \"rest.name\"\n                fqdn_pattern: \"rest.fqdn_pattern\"\n                group_id: \"rest.group_id\"\n                ports: \"rest.ports\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n              \
  \    mapping: \"$.\"\n\n        - path: /v1/subnet-rules\n          name: subnet-rules\n          description: \"Subnet rules.\"\n          operations:\n            - method: GET\n              name: list-subnet-rules\n              description: \"List all subnet rules.\"\n              call: \"ztna-connector.list-subnet-rules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-subnet-rule\n              description: \"Create a new subnet rule.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: subnet\n                  in: body\n                  type: string\n                  required: true\n                - name: group_id\n                  in: body\n                  type: string\n                  required: true\n                - name: enabled\n\
  \                  in: body\n                  type: boolean\n                  required: false\n              call: \"ztna-connector.create-subnet-rule\"\n              with:\n                name: \"rest.name\"\n                subnet: \"rest.subnet\"\n                group_id: \"rest.group_id\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ztna-licenses\n          name: ztna-licenses\n          description: \"ZTNA licenses.\"\n          operations:\n            - method: GET\n              name: get-ztna-licenses\n              description: \"Get ZTNA license information.\"\n              call: \"ztna-connector.get-ztna-licenses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── SD-WAN ───────────────────────────────────────────────────────\n        - path: /v1/sd-wan-sites\n          name: sd-wan-sites\n\
  \          description: \"SD-WAN sites.\"\n          operations:\n            - method: GET\n              name: list-sdwan-sites\n              description: \"Retrieve a list of SD-WAN sites.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n                - name: name\n                  in: query\n                  type: string\n                  required: false\n              call: \"prisma-sd-wan.list-sites\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-sdwan-site\n              description: \"Create\
  \ a new SD-WAN site.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: admin_state\n                  in: body\n                  type: string\n                  required: false\n                - name: element_cluster_role\n                  in: body\n                  type: string\n                  required: false\n                - name: address\n                  in: body\n                  type: object\n                  required: false\n                - name: location\n                  in: body\n                  type: object\n                  required: false\n                - name: tags\n                  in: body\n                  type: object\n                  required: false\n              call: \"prisma-sd-wan.create-site\"\
  \n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n                admin_state: \"rest.admin_state\"\n                element_cluster_role: \"rest.element_cluster_role\"\n                address: \"rest.address\"\n                location: \"rest.location\"\n                tags: \"rest.tags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sd-wan-sites/{site_id}\n          name: sd-wan-site\n          description: \"SD-WAN site by ID.\"\n          operations:\n            - method: GET\n              name: get-sdwan-site\n              description: \"Retrieve details for a specific SD-WAN site.\"\n              inputParameters:\n                - name: site_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-sd-wan.get-site\"\n              with:\n                site_id: \"rest.site_id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-sdwan-site\n              description: \"Update an existing SD-WAN site.\"\n              inputParameters:\n                - name: site_id\n                  in: path\n                  type: string\n                  required: true\n                - name: name\n                  in: body\n                  type: string\n                  required: false\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: admin_state\n                  in: body\n                  type: string\n                  required: false\n                - name: element_cluster_role\n                  in: body\n                  type: string\n                  required: false\n                - name: address\n                  in: body\n                 \
  \ type: object\n                  required: false\n                - name: location\n                  in: body\n                  type: object\n                  required: false\n                - name: tags\n                  in: body\n                  type: object\n                  required: false\n              call: \"prisma-sd-wan.update-site\"\n              with:\n                site_id: \"rest.site_id\"\n                name: \"rest.name\"\n                description: \"rest.description\"\n                admin_state: \"rest.admin_state\"\n                element_cluster_role: \"rest.element_cluster_role\"\n                address: \"rest.address\"\n                location: \"rest.location\"\n                tags: \"rest.tags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-sdwan-site\n              description: \"Delete an SD-WAN site.\"\n              inputParameters:\n\
  \                - name: site_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"prisma-sd-wan.delete-site\"\n              with:\n                site_id: \"rest.site_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sd-wan-sites/{site_id}/wan-interfaces\n          name: sd-wan-wan-interfaces\n          description: \"WAN interfaces for an SD-WAN site.\"\n          operations:\n            - method: GET\n              name: list-wan-interfaces\n              description: \"Retrieve WAN interfaces for a specific site.\"\n              inputParameters:\n                - name: site_id\n                  in: path\n                  type: string\n                  required: true\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n      \
  \            in: query\n                  type: integer\n                  required: false\n              call: \"prisma-sd-wan.list-site-wan-interfaces\"\n              with:\n                site_id: \"rest.site_id\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-wan-interface\n              description: \"Create a WAN interface for a specific site.\"\n              inputParameters:\n                - name: site_id\n                  in: path\n                  type: string\n                  required: true\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: type\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n          \
  \        in: body\n                  type: string\n                  required: false\n                - name: link_bw_down\n                  in: body\n                  type: integer\n                  required: false\n                - name: link_bw_up\n                  in: body\n                  type: integer\n                  required: false\n              call: \"prisma-sd-wan.create-site-wan-interface\"\n              with:\n                site_id: \"rest.site_id\"\n                name: \"rest.name\"\n                type: \"rest.type\"\n                description: \"rest.description\"\n                link_bw_down: \"rest.link_bw_down\"\n                link_bw_up: \"rest.link_bw_up\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sd-wan-sites/{site_id}/lan-networks\n          name: sd-wan-lan-networks\n          description: \"LAN networks for an SD-WAN site.\"\n          operations:\n           \
  \ - method: GET\n              name: list-lan-networks\n              description: \"Retrieve LAN networks for a specific site.\"\n              inputParameters:\n                - name: site_id\n                  in: path\n                  type: string\n                  required: true\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"prisma-sd-wan.list-site-lan-networks\"\n              with:\n                site_id: \"rest.site_id\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-lan-network\n              description: \"Create a LAN network for a specific site.\"\n     \
  \         inputParameters:\n                - name: site_id\n                  in: path\n                  type: string\n                  required: true\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: network\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: vlan_id\n                  in: body\n                  type: integer\n                  required: false\n                - name: dhcp_enabled\n                  in: body\n                  type: boolean\n                  required: false\n              call: \"prisma-sd-wan.create-site-lan-network\"\n              with:\n                site_id: \"rest.site_id\"\n                name: \"rest.name\"\n                network: \"rest.network\"\
  \n                description: \"rest.description\"\n                vlan_id: \"rest.vlan_id\"\n                dhcp_enabled: \"rest.dhcp_enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/qos-rules\n          name: qos-rules\n          description: \"QoS rules.\"\n          operations:\n            - method: GET\n              name: list-qos-rules\n              description: \"Retrieve a list of QoS rules.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"prisma-sd-wan.list-qos-rules\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n\
  \                  mapping: \"$.\"\n            - method: POST\n              name: create-qos-rule\n              description: \"Create a new QoS rule.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: priority\n                  in: body\n                  type: integer\n                  required: true\n                - name: dscp_class\n                  in: body\n                  type: string\n                  required: false\n                - name: app_filters\n                  in: body\n                  type: object\n                  required: false\n                - name: bandwidth_limit_up\n                  in: body\n                  type: integer\n                  required: false\n                - name: bandwidth_limit_down\n                  in: body\n                  type: integer\n                  required: false\n             \
  \ call: \"prisma-sd-wan.create-qos-rule\"\n              with:\n                name: \"rest.name\"\n                priority: \"rest.priority\"\n                dscp_class: \"rest.dscp_class\"\n                app_filters: \"rest.app_filters\"\n                bandwidth_limit_up: \"rest.bandwidth_limit_up\"\n                bandwidth_limit_down: \"rest.bandwidth_limit_down\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/path-rules\n          name: path-rules\n          description: \"Path rules.\"\n          operations:\n            - method: GET\n              name: list-path-rules\n              description: \"Retrieve a list of path rules.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n             \
  \     required: false\n              call: \"prisma-sd-wan.list-path-rules\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-path-rule\n              description: \"Create a new path rule.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: app_filters\n                  in: body\n                  type: object\n                  required: false\n                - name: preferred_paths\n                  in: body\n                  type: object\n                  required: false\n                - name: sla_threshold\n                  in: body\n                  type: object\n                  required: false\n              call: \"prisma-sd-wan.create-path-rule\"\
  \n              with:\n                name: \"rest.name\"\n                app_filters: \"rest.app_filters\"\n                preferred_paths: \"rest.preferred_paths\"\n                sla_threshold: \"rest.sla_threshold\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sd-wan-sites/{site_id}/metrics\n          name: sd-wan-site-metrics\n          description: \"SD-WAN site metrics.\"\n          operations:\n            - method: GET\n              name: get-site-metrics\n              description: \"Retrieve monitoring metrics for a specific site.\"\n              inputParameters:\n                - name: site_id\n                  in: path\n                  type: string\n                  required: true\n                - name: start_time\n                  in: query\n                  type: string\n                  required: false\n                - name: end_time\n                  in: query\n           \
  \       type: string\n                  required: false\n                - name: metric_type\n                  in: query\n                  type: string\n                  required: false\n                - name: granularity\n                  in: query\n                  type: string\n                  required: false\n              call: \"prisma-sd-wan.get-site-metrics\"\n              with:\n                site_id: \"rest.site_id\"\n                start_time: \"rest.start_time\"\n                end_time: \"rest.end_time\"\n                metric_type: \"rest.metric_type\"\n                granularity: \"rest.granularity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/application-usage\n          name: application-usage\n          description: \"Application usage metrics.\"\n          operations:\n            - method: GET\n              name: get-application-usage\n              description: \"Retrieve\
  \ application usage metrics across the SD-WAN.\"\n              inputParameters:\n                - name: start_time\n                  in: query\n                  type: string\n                  required: false\n                - name: end_time\n                  in: query\n                  type: string\n                  required: false\n                - name: site_id\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"prisma-sd-wan.get-application-usage\"\n              with:\n                start_time: \"rest.start_time\"\n                end_time: \"rest.end_time\"\n                site_id: \"rest.site_id\"\n                offset: \"rest.offset\"\n         \
  \       limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/sd-wan-alarms\n          name: sd-wan-alarms\n          description: \"SD-WAN alarms.\"\n          operations:\n            - method: GET\n              name: list-sdwan-alarms\n              description: \"Retrieve a list of SD-WAN alarms.\"\n              inputParameters:\n                - name: site_id\n                  in: query\n                  type: string\n                  required: false\n                - name: severity\n                  in: query\n                  type: string\n                  required: false\n                - name: acknowledged\n                  in: query\n                  type: boolean\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                 \
  \ in: query\n                  type: integer\n                  required: false\n              call: \"prisma-sd-wan.list-alarms\"\n              with:\n                site_id: \"rest.site_id\"\n                severity: \"rest.severity\"\n                acknowledged: \"rest.acknowledged\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # ── 5G Security ──────────────────────────────────────────────────\n        - path: /v1/network-slices\n          name: network-slices\n          description: \"5G network slices.\"\n          operations:\n            - method: GET\n              name: list-network-slices\n              description: \"Retrieve a list of 5G network slices.\"\n              inputParameters:\n                - name: status\n                  in: query\n                  type: string\n                  required: false\n           \
  \     - name: slice_type\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"sase-5g.list-network-slices\"\n              with:\n                status: \"rest.status\"\n                slice_type: \"rest.slice_type\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-network-slice\n              description: \"Create a new 5G network slice.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required:\
  \ true\n                - name: slice_type\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: sd\n                  in: body\n                  type: string\n                  required: false\n                - name: security_policy_id\n                  in: body\n                  type: string\n                  required: false\n              call: \"sase-5g.create-network-slice\"\n              with:\n                name: \"rest.name\"\n                slice_type: \"rest.slice_type\"\n                description: \"rest.description\"\n                sd: \"rest.sd\"\n                security_policy_id: \"rest.security_policy_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/network-slices/{slice_id}\n        \
  \  name: network-slice\n          description: \"5G network slice by ID.\"\n          operations:\n            - method: GET\n              name: get-network-slice\n              description: \"Retrieve details for a specific network slice.\"\n              inputParameters:\n                - name: slice_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-5g.get-network-slice\"\n              with:\n                slice_id: \"rest.slice_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-network-slice\n              description: \"Update an existing network slice.\"\n              inputParameters:\n                - name: slice_id\n                  in: path\n                  type: string\n                  required: true\n                - name: name\n                  in: body\n                  type: string\n\
  \                  required: false\n                - name: slice_type\n                  in: body\n                  type: string\n                  required: false\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: sd\n                  in: body\n                  type: string\n                  required: false\n                - name: security_policy_id\n                  in: body\n                  type: string\n                  required: false\n              call: \"sase-5g.update-network-slice\"\n              with:\n                slice_id: \"rest.slice_id\"\n                name: \"rest.name\"\n                slice_type: \"rest.slice_type\"\n                description: \"rest.description\"\n                sd: \"rest.sd\"\n                security_policy_id: \"rest.security_policy_id\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n            - method: DELETE\n              name: delete-network-slice\n              description: \"Delete a network slice.\"\n              inputParameters:\n                - name: slice_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-5g.delete-network-slice\"\n              with:\n                slice_id: \"rest.slice_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/5g-security-policies\n          name: 5g-security-policies\n          description: \"5G security policies.\"\n          operations:\n            - method: GET\n              name: list-5g-security-policies\n              description: \"Retrieve a list of 5G security policies.\"\n              inputParameters:\n                - name: slice_id\n                  in: query\n                  type: string\n                  required: false\n                -\
  \ name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"sase-5g.list-5g-security-policies\"\n              with:\n                slice_id: \"rest.slice_id\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-5g-security-policy\n              description: \"Create a new 5G security policy.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: threat_prevention\n\
  \                  in: body\n                  type: object\n                  required: false\n                - name: url_filtering\n                  in: body\n                  type: object\n                  required: false\n                - name: app_identification\n                  in: body\n                  type: object\n                  required: false\n                - name: decryption\n                  in: body\n                  type: object\n                  required: false\n                - name: log_forwarding\n                  in: body\n                  type: object\n                  required: false\n                - name: enabled\n                  in: body\n                  type: boolean\n                  required: false\n              call: \"sase-5g.create-5g-security-policy\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n                threat_prevention: \"rest.threat_prevention\"\n    \
  \            url_filtering: \"rest.url_filtering\"\n                app_identification: \"rest.app_identification\"\n                decryption: \"rest.decryption\"\n                log_forwarding: \"rest.log_forwarding\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/5g-security-policies/{policy_id}\n          name: 5g-security-policy\n          description: \"5G security policy by ID.\"\n          operations:\n            - method: GET\n              name: get-5g-security-policy\n              description: \"Retrieve details for a specific 5G security policy.\"\n              inputParameters:\n                - name: policy_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-5g.get-5g-security-policy\"\n              with:\n                policy_id: \"rest.policy_id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-5g-security-policy\n              description: \"Update an existing 5G security policy.\"\n              inputParameters:\n                - name: policy_id\n                  in: path\n                  type: string\n                  required: true\n                - name: name\n                  in: body\n                  type: string\n                  required: false\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: threat_prevention\n                  in: body\n                  type: object\n                  required: false\n                - name: url_filtering\n                  in: body\n                  type: object\n                  required: false\n                - name: app_identification\n                  in: body\n                  type: object\n\
  \                  required: false\n                - name: decryption\n                  in: body\n                  type: object\n                  required: false\n                - name: log_forwarding\n                  in: body\n                  type: object\n                  required: false\n                - name: enabled\n                  in: body\n                  type: boolean\n                  required: false\n              call: \"sase-5g.update-5g-security-policy\"\n              with:\n                policy_id: \"rest.policy_id\"\n                name: \"rest.name\"\n                description: \"rest.description\"\n                threat_prevention: \"rest.threat_prevention\"\n                url_filtering: \"rest.url_filtering\"\n                app_identification: \"rest.app_identification\"\n                decryption: \"rest.decryption\"\n                log_forwarding: \"rest.log_forwarding\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-5g-security-policy\n              description: \"Delete a 5G security policy.\"\n              inputParameters:\n                - name: policy_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-5g.delete-5g-security-policy\"\n              with:\n                policy_id: \"rest.policy_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/5g-tenants\n          name: 5g-tenants\n          description: \"5G tenants.\"\n          operations:\n            - method: GET\n              name: list-5g-tenants\n              description: \"Retrieve a list of 5G tenants.\"\n              call: \"sase-5g.list-5g-tenants\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n     \
  \       - method: POST\n              name: create-5g-tenant\n              description: \"Create a new 5G tenant.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: assigned_slices\n                  in: body\n                  type: object\n                  required: false\n                - name: default_policy_id\n                  in: body\n                  type: string\n                  required: false\n              call: \"sase-5g.create-5g-tenant\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n                assigned_slices: \"rest.assigned_slices\"\n                default_policy_id: \"rest.default_policy_id\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/5g-tenants/{tenant_id}\n          name: 5g-tenant\n          description: \"5G tenant by ID.\"\n          operations:\n            - method: GET\n              name: get-5g-tenant\n              description: \"Retrieve details for a specific 5G tenant.\"\n              inputParameters:\n                - name: tenant_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-5g.get-5g-tenant\"\n              with:\n                tenant_id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-5g-tenant\n              description: \"Update an existing 5G tenant.\"\n              inputParameters:\n                - name: tenant_id\n                  in: path\n                  type: string\n                  required: true\n\
  \                - name: name\n                  in: body\n                  type: string\n                  required: false\n                - name: description\n                  in: body\n                  type: string\n                  required: false\n                - name: assigned_slices\n                  in: body\n                  type: object\n                  required: false\n                - name: default_policy_id\n                  in: body\n                  type: string\n                  required: false\n              call: \"sase-5g.update-5g-tenant\"\n              with:\n                tenant_id: \"rest.tenant_id\"\n                name: \"rest.name\"\n                description: \"rest.description\"\n                assigned_slices: \"rest.assigned_slices\"\n                default_policy_id: \"rest.default_policy_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n         \
  \     name: delete-5g-tenant\n              description: \"Delete a 5G tenant.\"\n              inputParameters:\n                - name: tenant_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"sase-5g.delete-5g-tenant\"\n              with:\n                tenant_id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/5g-metrics\n          name: 5g-metrics\n          description: \"5G security metrics.\"\n          operations:\n            - method: GET\n              name: get-5g-security-metrics\n              description: \"Retrieve 5G security monitoring metrics.\"\n              inputParameters:\n                - name: slice_id\n                  in: query\n                  type: string\n                  required: false\n                - name: start_time\n                  in: query\n                  type: string\n\
  \                  required: false\n                - name: end_time\n                  in: query\n                  type: string\n                  required: false\n                - name: interval\n                  in: query\n                  type: string\n                  required: false\n              call: \"sase-5g.get-5g-security-metrics\"\n              with:\n                slice_id: \"rest.slice_id\"\n                start_time: \"rest.start_time\"\n                end_time: \"rest.end_time\"\n                interval: \"rest.interval\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: secure-access-mcp\n      transport: http\n      description: \"MCP server for AI-assisted secure access management.\"\n      tools:\n\n        # ── Prisma Access ────────────────────────────────────────────────\n        - name: list-remote-networks\n          description: \"List all Prisma\
  \ Access remote networks with pagination.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-access.list-remote-networks\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-remote-network\n          description: \"Create a new Prisma Access remote network.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name:\
  \ location\n              type: string\n              required: true\n            - name: subnets\n              type: string\n              required: true\n            - name: ike_gateway\n              type: string\n              required: true\n          call: \"prisma-access.create-remote-network\"\n          with:\n            name: \"tools.name\"\n            location: \"tools.location\"\n            subnets: \"tools.subnets\"\n            ike_gateway: \"tools.ike_gateway\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-remote-network\n          description: \"Get a specific Prisma Access remote network by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"prisma-access.get-remote-network\"\n       \
  \   with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-remote-network\n          description: \"Update a specific Prisma Access remote network by ID.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"prisma-access.update-remote-network\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-remote-network\n          description: \"Delete a specific Prisma Access remote network by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name:\
  \ id\n              type: string\n              required: true\n          call: \"prisma-access.delete-remote-network\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-service-connections\n          description: \"List all Prisma Access service connections with pagination.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-access.list-service-connections\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-service-connection\n\
  \          description: \"Create a new Prisma Access service connection.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: ipsec_tunnel\n              type: string\n              required: true\n            - name: region\n              type: string\n              required: true\n          call: \"prisma-access.create-service-connection\"\n          with:\n            name: \"tools.name\"\n            ipsec_tunnel: \"tools.ipsec_tunnel\"\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-service-connection\n          description: \"Get a specific Prisma Access service connection by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n   \
  \         idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"prisma-access.get-service-connection\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-service-connection\n          description: \"Update a specific Prisma Access service connection by ID.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"prisma-access.update-service-connection\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-service-connection\n          description:\
  \ \"Delete a specific Prisma Access service connection by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"prisma-access.delete-service-connection\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-mobile-agent-settings\n          description: \"Get mobile agent infrastructure settings.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"prisma-access.get-mobile-agent-infrastructure-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-mobile-agent-settings\n          description: \"Create\
  \ or update mobile agent infrastructure settings.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: settings\n              type: object\n              required: true\n          call: \"prisma-access.create-mobile-agent-infrastructure-settings\"\n          with:\n            settings: \"tools.settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ike-gateways\n          description: \"List all IKE gateways with pagination.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-access.list-ike-gateways\"\
  \n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ── ZTNA ─────────────────────────────────────────────────────────\n        - name: list-ztna-connectors\n          description: \"List all ZTNA connectors.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: group_id\n              type: string\n              required: false\n            - name: status\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"ztna-connector.list-connectors\"\n          with:\n            group_id: \"tools.group_id\"\n            status: \"\
  tools.status\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-ztna-connector\n          description: \"Create a new ZTNA connector.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: group_id\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n          call: \"ztna-connector.create-connector\"\n          with:\n            name: \"tools.name\"\n            group_id: \"tools.group_id\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        -\
  \ name: get-ztna-connector\n          description: \"Get a specific ZTNA connector by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: connector_id\n              type: string\n              required: true\n          call: \"ztna-connector.get-connector\"\n          with:\n            connector_id: \"tools.connector_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-ztna-connector\n          description: \"Update a specific ZTNA connector by ID.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: connector_id\n              type: string\n              required: true\n          call: \"ztna-connector.update-connector\"\n          with:\n       \
  \     connector_id: \"tools.connector_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-ztna-connector\n          description: \"Delete a specific ZTNA connector by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: connector_id\n              type: string\n              required: true\n          call: \"ztna-connector.delete-connector\"\n          with:\n            connector_id: \"tools.connector_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: schedule-connector-upgrade\n          description: \"Schedule an upgrade for a ZTNA connector.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n          \
  \  - name: connector_id\n              type: string\n              required: true\n            - name: scheduled_at\n              type: string\n              required: true\n            - name: target_version\n              type: string\n              required: true\n          call: \"ztna-connector.schedule-connector-upgrade\"\n          with:\n            connector_id: \"tools.connector_id\"\n            scheduled_at: \"tools.scheduled_at\"\n            target_version: \"tools.target_version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-connector-groups\n          description: \"List all ZTNA connector groups.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"ztna-connector.list-connector-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-connector-group\n\
  \          description: \"Create a new ZTNA connector group.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: region\n              type: string\n              required: true\n          call: \"ztna-connector.create-connector-group\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-connector-group\n          description: \"Get a specific ZTNA connector group by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n    \
  \        openWorld: true\n          inputParameters:\n            - name: group_id\n              type: string\n              required: true\n          call: \"ztna-connector.get-connector-group\"\n          with:\n            group_id: \"tools.group_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-connector-group\n          description: \"Update a specific ZTNA connector group by ID.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: group_id\n              type: string\n              required: true\n          call: \"ztna-connector.update-connector-group\"\n          with:\n            group_id: \"tools.group_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-connector-group\n          description: \"Delete a specific\
  \ ZTNA connector group by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: group_id\n              type: string\n              required: true\n          call: \"ztna-connector.delete-connector-group\"\n          with:\n            group_id: \"tools.group_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ztna-applications\n          description: \"List all ZTNA applications.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"ztna-connector.list-ztna-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-ztna-application\n          description: \"Create a new ZTNA application.\"\n          hints:\n     \
  \       readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: group_id\n              type: string\n              required: true\n            - name: fqdn\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: ports\n              type: object\n              required: true\n            - name: protocols\n              type: object\n              required: true\n            - name: enabled\n              type: boolean\n              required: false\n          call: \"ztna-connector.create-ztna-application\"\n          with:\n            name: \"tools.name\"\n            group_id: \"tools.group_id\"\n            fqdn: \"tools.fqdn\"\n            description: \"tools.description\"\n        \
  \    ports: \"tools.ports\"\n            protocols: \"tools.protocols\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-ztna-application\n          description: \"Get a specific ZTNA application by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: app_id\n              type: string\n              required: true\n          call: \"ztna-connector.get-ztna-application\"\n          with:\n            app_id: \"tools.app_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-ztna-application\n          description: \"Update a specific ZTNA application by ID.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld:\
  \ true\n          inputParameters:\n            - name: app_id\n              type: string\n              required: true\n          call: \"ztna-connector.update-ztna-application\"\n          with:\n            app_id: \"tools.app_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-ztna-application\n          description: \"Delete a specific ZTNA application by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: app_id\n              type: string\n              required: true\n          call: \"ztna-connector.delete-ztna-application\"\n          with:\n            app_id: \"tools.app_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-fqdn-rules\n          description: \"List all FQDN rules.\"\n          hints:\n     \
  \       readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"ztna-connector.list-fqdn-rules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-fqdn-rule\n          description: \"Create a new FQDN rule.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: fqdn_pattern\n              type: string\n              required: true\n            - name: group_id\n              type: string\n              required: true\n            - name: ports\n              type: object\n              required: true\n            - name: enabled\n              type: boolean\n              required: false\n          call: \"ztna-connector.create-fqdn-rule\"\n\
  \          with:\n            name: \"tools.name\"\n            fqdn_pattern: \"tools.fqdn_pattern\"\n            group_id: \"tools.group_id\"\n            ports: \"tools.ports\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-subnet-rules\n          description: \"List all subnet rules.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"ztna-connector.list-subnet-rules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-subnet-rule\n          description: \"Create a new subnet rule.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n           \
  \   required: true\n            - name: subnet\n              type: string\n              required: true\n            - name: group_id\n              type: string\n              required: true\n            - name: enabled\n              type: boolean\n              required: false\n          call: \"ztna-connector.create-subnet-rule\"\n          with:\n            name: \"tools.name\"\n            subnet: \"tools.subnet\"\n            group_id: \"tools.group_id\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-ztna-licenses\n          description: \"Get ZTNA license information.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"ztna-connector.get-ztna-licenses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ── SD-WAN ───────────────────────────────────────────────────────\n\
  \        - name: list-sdwan-sites\n          description: \"Retrieve a list of SD-WAN sites.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n            - name: name\n              type: string\n              required: false\n          call: \"prisma-sd-wan.list-sites\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-sdwan-site\n          description: \"Create a new SD-WAN site.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld:\
  \ true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: admin_state\n              type: string\n              required: false\n            - name: element_cluster_role\n              type: string\n              required: false\n            - name: address\n              type: object\n              required: false\n            - name: location\n              type: object\n              required: false\n            - name: tags\n              type: object\n              required: false\n          call: \"prisma-sd-wan.create-site\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            admin_state: \"tools.admin_state\"\n            element_cluster_role: \"tools.element_cluster_role\"\n            address: \"tools.address\"\n            location: \"tools.location\"\
  \n            tags: \"tools.tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-sdwan-site\n          description: \"Retrieve details for a specific SD-WAN site.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: site_id\n              type: string\n              required: true\n          call: \"prisma-sd-wan.get-site\"\n          with:\n            site_id: \"tools.site_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-sdwan-site\n          description: \"Update an existing SD-WAN site.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: site_id\n              type: string\n       \
  \       required: true\n            - name: name\n              type: string\n              required: false\n            - name: description\n              type: string\n              required: false\n            - name: admin_state\n              type: string\n              required: false\n            - name: element_cluster_role\n              type: string\n              required: false\n            - name: address\n              type: object\n              required: false\n            - name: location\n              type: object\n              required: false\n            - name: tags\n              type: object\n              required: false\n          call: \"prisma-sd-wan.update-site\"\n          with:\n            site_id: \"tools.site_id\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n            admin_state: \"tools.admin_state\"\n            element_cluster_role: \"tools.element_cluster_role\"\n            address: \"tools.address\"\n   \
  \         location: \"tools.location\"\n            tags: \"tools.tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-sdwan-site\n          description: \"Delete an SD-WAN site.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: site_id\n              type: string\n              required: true\n          call: \"prisma-sd-wan.delete-site\"\n          with:\n            site_id: \"tools.site_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-wan-interfaces\n          description: \"Retrieve WAN interfaces for a specific site.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: site_id\n\
  \              type: string\n              required: true\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-sd-wan.list-site-wan-interfaces\"\n          with:\n            site_id: \"tools.site_id\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-wan-interface\n          description: \"Create a WAN interface for a specific site.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: site_id\n              type: string\n              required: true\n            - name: name\n              type: string\n              required: true\n            - name: type\n           \
  \   type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: link_bw_down\n              type: integer\n              required: false\n            - name: link_bw_up\n              type: integer\n              required: false\n          call: \"prisma-sd-wan.create-site-wan-interface\"\n          with:\n            site_id: \"tools.site_id\"\n            name: \"tools.name\"\n            type: \"tools.type\"\n            description: \"tools.description\"\n            link_bw_down: \"tools.link_bw_down\"\n            link_bw_up: \"tools.link_bw_up\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-lan-networks\n          description: \"Retrieve LAN networks for a specific site.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n\
  \            - name: site_id\n              type: string\n              required: true\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-sd-wan.list-site-lan-networks\"\n          with:\n            site_id: \"tools.site_id\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-lan-network\n          description: \"Create a LAN network for a specific site.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: site_id\n              type: string\n              required: true\n            - name: name\n              type: string\n              required: true\n            - name:\
  \ network\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: vlan_id\n              type: integer\n              required: false\n            - name: dhcp_enabled\n              type: boolean\n              required: false\n          call: \"prisma-sd-wan.create-site-lan-network\"\n          with:\n            site_id: \"tools.site_id\"\n            name: \"tools.name\"\n            network: \"tools.network\"\n            description: \"tools.description\"\n            vlan_id: \"tools.vlan_id\"\n            dhcp_enabled: \"tools.dhcp_enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-qos-rules\n          description: \"Retrieve a list of QoS rules.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n\
  \            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-sd-wan.list-qos-rules\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-qos-rule\n          description: \"Create a new QoS rule.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: priority\n              type: integer\n              required: true\n            - name: dscp_class\n              type: string\n              required: false\n            - name: app_filters\n              type: object\n              required:\
  \ false\n            - name: bandwidth_limit_up\n              type: integer\n              required: false\n            - name: bandwidth_limit_down\n              type: integer\n              required: false\n          call: \"prisma-sd-wan.create-qos-rule\"\n          with:\n            name: \"tools.name\"\n            priority: \"tools.priority\"\n            dscp_class: \"tools.dscp_class\"\n            app_filters: \"tools.app_filters\"\n            bandwidth_limit_up: \"tools.bandwidth_limit_up\"\n            bandwidth_limit_down: \"tools.bandwidth_limit_down\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-path-rules\n          description: \"Retrieve a list of path rules.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              required:\
  \ false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-sd-wan.list-path-rules\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-path-rule\n          description: \"Create a new path rule.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: app_filters\n              type: object\n              required: false\n            - name: preferred_paths\n              type: object\n              required: false\n            - name: sla_threshold\n              type: object\n              required: false\n          call: \"prisma-sd-wan.create-path-rule\"\n \
  \         with:\n            name: \"tools.name\"\n            app_filters: \"tools.app_filters\"\n            preferred_paths: \"tools.preferred_paths\"\n            sla_threshold: \"tools.sla_threshold\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-site-metrics\n          description: \"Retrieve monitoring metrics for a specific SD-WAN site.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: site_id\n              type: string\n              required: true\n            - name: start_time\n              type: string\n              required: false\n            - name: end_time\n              type: string\n              required: false\n            - name: metric_type\n              type: string\n              required: false\n            - name: granularity\n              type: string\n\
  \              required: false\n          call: \"prisma-sd-wan.get-site-metrics\"\n          with:\n            site_id: \"tools.site_id\"\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n            metric_type: \"tools.metric_type\"\n            granularity: \"tools.granularity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-application-usage\n          description: \"Retrieve application usage metrics across the SD-WAN.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: start_time\n              type: string\n              required: false\n            - name: end_time\n              type: string\n              required: false\n            - name: site_id\n              type: string\n              required: false\n            - name: offset\n  \
  \            type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-sd-wan.get-application-usage\"\n          with:\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n            site_id: \"tools.site_id\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-sdwan-alarms\n          description: \"Retrieve a list of SD-WAN alarms.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: site_id\n              type: string\n              required: false\n            - name: severity\n              type: string\n              required: false\n            - name: acknowledged\n              type:\
  \ boolean\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"prisma-sd-wan.list-alarms\"\n          with:\n            site_id: \"tools.site_id\"\n            severity: \"tools.severity\"\n            acknowledged: \"tools.acknowledged\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        # ── Config Orchestration ─────────────────────────────────────────\n        - name: list-orchestrated-remote-networks\n          description: \"List all orchestrated remote networks with optional filtering by location and status.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name:\
  \ location\n              type: string\n              required: false\n            - name: status\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"sase-config-orchestration.list-remote-networks\"\n          with:\n            location: \"tools.location\"\n            status: \"tools.status\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-orchestrated-remote-network\n          description: \"Create a new orchestrated remote network configuration.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n         \
  \     type: string\n              required: true\n            - name: location\n              type: string\n              required: true\n            - name: subnets\n              type: object\n              required: false\n            - name: ike_gateway\n              type: object\n              required: false\n            - name: description\n              type: string\n              required: false\n            - name: bandwidth_mbps\n              type: integer\n              required: false\n          call: \"sase-config-orchestration.create-remote-network\"\n          with:\n            name: \"tools.name\"\n            location: \"tools.location\"\n            subnets: \"tools.subnets\"\n            ike_gateway: \"tools.ike_gateway\"\n            description: \"tools.description\"\n            bandwidth_mbps: \"tools.bandwidth_mbps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-orchestrated-remote-network\n  \
  \        description: \"Get details of a specific orchestrated remote network by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"sase-config-orchestration.get-remote-network\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-orchestrated-remote-network\n          description: \"Update an existing orchestrated remote network configuration.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n            - name: name\n              type: string\n              required:\
  \ false\n            - name: location\n              type: string\n              required: false\n            - name: subnets\n              type: object\n              required: false\n            - name: ike_gateway\n              type: object\n              required: false\n            - name: description\n              type: string\n              required: false\n            - name: bandwidth_mbps\n              type: integer\n              required: false\n          call: \"sase-config-orchestration.update-remote-network\"\n          with:\n            id: \"tools.id\"\n            name: \"tools.name\"\n            location: \"tools.location\"\n            subnets: \"tools.subnets\"\n            ike_gateway: \"tools.ike_gateway\"\n            description: \"tools.description\"\n            bandwidth_mbps: \"tools.bandwidth_mbps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-orchestrated-remote-network\n         \
  \ description: \"Delete an orchestrated remote network by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"sase-config-orchestration.delete-remote-network\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: refresh-ike-gateway\n          description: \"Refresh the IKE gateway for a specific remote network.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"sase-config-orchestration.refresh-ike-gateway\"\n          with:\n            id: \"tools.id\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-bandwidth-allocations\n          description: \"Get bandwidth allocations optionally filtered by location.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: location\n              type: string\n              required: false\n          call: \"sase-config-orchestration.get-bandwidth-allocations\"\n          with:\n            location: \"tools.location\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-access-locations\n          description: \"List all available Prisma Access locations.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters: []\n          call: \"sase-config-orchestration.list-prisma-access-locations\"\
  \n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-onboarding-status\n          description: \"Get the onboarding status for a specific resource.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n          call: \"sase-config-orchestration.get-onboarding-status\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ── 5G ───────────────────────────────────────────────────────────\n        - name: list-network-slices\n          description: \"Retrieve a list of 5G network slices.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n\
  \            - name: status\n              type: string\n              required: false\n            - name: slice_type\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"sase-5g.list-network-slices\"\n          with:\n            status: \"tools.status\"\n            slice_type: \"tools.slice_type\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-network-slice\n          description: \"Create a new 5G network slice.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required:\
  \ true\n            - name: slice_type\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: sd\n              type: string\n              required: false\n            - name: security_policy_id\n              type: string\n              required: false\n          call: \"sase-5g.create-network-slice\"\n          with:\n            name: \"tools.name\"\n            slice_type: \"tools.slice_type\"\n            description: \"tools.description\"\n            sd: \"tools.sd\"\n            security_policy_id: \"tools.security_policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-network-slice\n          description: \"Retrieve details for a specific 5G network slice.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n\
  \          inputParameters:\n            - name: slice_id\n              type: string\n              required: true\n          call: \"sase-5g.get-network-slice\"\n          with:\n            slice_id: \"tools.slice_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-network-slice\n          description: \"Update an existing 5G network slice.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: slice_id\n              type: string\n              required: true\n            - name: name\n              type: string\n              required: false\n            - name: slice_type\n              type: string\n              required: false\n            - name: description\n              type: string\n              required: false\n            - name: sd\n              type: string\n         \
  \     required: false\n            - name: security_policy_id\n              type: string\n              required: false\n          call: \"sase-5g.update-network-slice\"\n          with:\n            slice_id: \"tools.slice_id\"\n            name: \"tools.name\"\n            slice_type: \"tools.slice_type\"\n            description: \"tools.description\"\n            sd: \"tools.sd\"\n            security_policy_id: \"tools.security_policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-network-slice\n          description: \"Delete a 5G network slice.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: slice_id\n              type: string\n              required: true\n          call: \"sase-5g.delete-network-slice\"\n          with:\n            slice_id: \"tools.slice_id\"\n   \
  \       outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-5g-security-policies\n          description: \"Retrieve a list of 5G security policies.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: slice_id\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"sase-5g.list-5g-security-policies\"\n          with:\n            slice_id: \"tools.slice_id\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-5g-security-policy\n          description: \"Create a new 5G security policy.\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n            - name: description\n              type: string\n              required: false\n            - name: threat_prevention\n              type: object\n              required: false\n            - name: url_filtering\n              type: object\n              required: false\n            - name: app_identification\n              type: object\n              required: false\n            - name: decryption\n              type: object\n              required: false\n            - name: log_forwarding\n              type: object\n              required: false\n            - name: enabled\n              type: boolean\n              required: false\n          call: \"sase-5g.create-5g-security-policy\"\n          with:\n            name:\
  \ \"tools.name\"\n            description: \"tools.description\"\n            threat_prevention: \"tools.threat_prevention\"\n            url_filtering: \"tools.url_filtering\"\n            app_identification: \"tools.app_identification\"\n            decryption: \"tools.decryption\"\n            log_forwarding: \"tools.log_forwarding\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-5g-security-policy\n          description: \"Retrieve details for a specific 5G security policy.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: policy_id\n              type: string\n              required: true\n          call: \"sase-5g.get-5g-security-policy\"\n          with:\n            policy_id: \"tools.policy_id\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n\n        - name: update-5g-security-policy\n          description: \"Update an existing 5G security policy.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: policy_id\n              type: string\n              required: true\n            - name: name\n              type: string\n              required: false\n            - name: description\n              type: string\n              required: false\n            - name: threat_prevention\n              type: object\n              required: false\n            - name: url_filtering\n              type: object\n              required: false\n            - name: app_identification\n              type: object\n              required: false\n            - name: decryption\n              type: object\n              required: false\n            - name: log_forwarding\n\
  \              type: object\n              required: false\n            - name: enabled\n              type: boolean\n              required: false\n          call: \"sase-5g.update-5g-security-policy\"\n          with:\n            policy_id: \"tools.policy_id\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n            threat_prevention: \"tools.threat_prevention\"\n            url_filtering: \"tools.url_filtering\"\n            app_identification: \"tools.app_identification\"\n            decryption: \"tools.decryption\"\n            log_forwarding: \"tools.log_forwarding\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-5g-security-policy\n          description: \"Delete a 5G security policy.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n\
  \            - name: policy_id\n              type: string\n              required: true\n          call: \"sase-5g.delete-5g-security-policy\"\n          with:\n            policy_id: \"tools.policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-5g-tenants\n          description: \"Retrieve a list of 5G tenants.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"sase-5g.list-5g-tenants\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-5g-tenant\n          description: \"Create a new 5G tenant.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n   \
  \         - name: description\n              type: string\n              required: false\n            - name: assigned_slices\n              type: object\n              required: false\n            - name: default_policy_id\n              type: string\n              required: false\n          call: \"sase-5g.create-5g-tenant\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            assigned_slices: \"tools.assigned_slices\"\n            default_policy_id: \"tools.default_policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-5g-tenant\n          description: \"Retrieve details for a specific 5G tenant.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tenant_id\n              type: string\n              required: true\n        \
  \  call: \"sase-5g.get-5g-tenant\"\n          with:\n            tenant_id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-5g-tenant\n          description: \"Update an existing 5G tenant.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tenant_id\n              type: string\n              required: true\n            - name: name\n              type: string\n              required: false\n            - name: description\n              type: string\n              required: false\n            - name: assigned_slices\n              type: object\n              required: false\n            - name: default_policy_id\n              type: string\n              required: false\n          call: \"sase-5g.update-5g-tenant\"\n          with:\n            tenant_id: \"tools.tenant_id\"\
  \n            name: \"tools.name\"\n            description: \"tools.description\"\n            assigned_slices: \"tools.assigned_slices\"\n            default_policy_id: \"tools.default_policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-5g-tenant\n          description: \"Delete a 5G tenant.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tenant_id\n              type: string\n              required: true\n          call: \"sase-5g.delete-5g-tenant\"\n          with:\n            tenant_id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-5g-security-metrics\n          description: \"Retrieve 5G security monitoring metrics.\"\n          hints:\n            readOnly: true\n            destructive:\
  \ false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: slice_id\n              type: string\n              required: false\n            - name: start_time\n              type: string\n              required: false\n            - name: end_time\n              type: string\n              required: false\n            - name: interval\n              type: string\n              required: false\n          call: \"sase-5g.get-5g-security-metrics\"\n          with:\n            slice_id: \"tools.slice_id\"\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n            interval: \"tools.interval\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/secure-access.yaml
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
