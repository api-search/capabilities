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
- get a specific prisma access remote network by id.
- get bandwidth allocations optionally filtered by location.
- palo alto networks
- create remote network
- delete a specific remote network by id.
- schedule an upgrade for a ztna connector.
- create network slice
- delete an orchestrated remote network by id.
- list ztna connectors
- list all prisma access remote networks with pagination.
- delete a specific ztna connector by id.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- red team operator
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- delete orchestrated remote network
- create a new fqdn rule.
- list all orchestrated remote networks with optional filtering by location and status.
- update service connection
- onboarding status.
- subnet rules.
- list network slices
- create a new prisma access remote network.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- tenant operator
- list ztna applications
- create sdwan site
- create qos rule
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- delete 5g tenant
- get ztna application
- prisma access locations.
- retrieve a list of path rules.
- delete sdwan site
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- sd-wan site metrics.
- retrieve a list of sd-wan sites.
- get a specific remote network by id.
- list all ike gateways with pagination.
- ztna connector group by id.
- retrieve lan networks for a specific site.
- get application usage
- researches threat actors, malware campaigns, and vulnerability trends.
- saas security admin
- get details of a specific orchestrated remote network by id.
- get a specific prisma access service connection by id.
- compliance team
- get ztna connector
- get 5g security metrics
- retrieve monitoring metrics for a specific site.
- update orchestrated remote network
- sase
- sd wan operator
- executes containment, eradication, and recovery actions during security incidents.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manages multi-tenant hierarchies and service group configurations for mssps.
- get ztna license information.
- create a new 5g network slice.
- lan networks for an sd-wan site.
- threat hunter
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- create orchestrated remote network
- prisma access remote networks.
- list access locations
- get onboarding status
- create a new ztna connector group.
- data protection analyst
- update remote network
- proactively searches for threats and iocs across telemetry data.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- list subnet rules
- update a specific remote network by id.
- mobile agent infrastructure settings.
- list all fqdn rules.
- prisma access remote network by id.
- bandwidth allocations.
- update a specific ztna application by id.
- get site metrics
- retrieve application usage metrics across the sd-wan.
- 5g network slices.
- retrieve a list of 5g tenants.
- manages enterprise browser policies and secure browsing configurations.
- update ztna connector
- retrieve wan interfaces for a specific site.
- retrieve 5g security monitoring metrics.
- incident responder
- cloud security posture management, compliance monitoring, and workload protection.
- sd-wan
- ai security engineer
- update an existing 5g network slice.
- manage enterprise browser policies, user sessions, and deployments.
- get ztna licenses
- service provider interconnect
- create ztna application
- retrieve a list of qos rules.
- compliance officer
- designs and implements network security architectures and policies.
- sd-wan site by id.
- list orchestrated remote networks
- list fqdn rules
- create a new qos rule.
- sase admin
- network operations
- list lan networks
- update connector group
- delete a specific ztna application by id.
- retrieve monitoring metrics for a specific sd-wan site.
- delete ztna connector
- malware researcher
- monitors and remediates cloud security misconfigurations and compliance violations.
- network security
- investigates dlp incidents and manages sensitive data protection policies.
- get a specific ztna connector group by id.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- delete remote network
- subscription manager
- threat intelligence
- manages multi-tenant security operations at scale for managed service providers.
- list remote networks
- retrieve details for a specific 5g tenant.
- list all ztna connectors.
- retrieve details for a specific 5g network slice.
- data loss prevention, saas security monitoring, and identity security posture.
- create a lan network for a specific site.
- delete service connection
- create a new ztna connector.
- list qos rules
- prisma access service connections.
- retrieve a list of 5g security policies.
- 5g
- wan interfaces for an sd-wan site.
- 5g tenants.
- schedule ztna connector upgrade.
- list all prisma access service connections with pagination.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- schedule connector upgrade
- sd-wan alarms.
- create path rule
- delete a 5g tenant.
- list 5g security policies
- update 5g security policy
- update sdwan site
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- designs sase and sd-wan network architectures for secure remote access.
- refresh ike gateway for an orchestrated remote network.
- list connector groups
- create a new ztna application.
- create a new 5g tenant.
- conducts automated adversarial testing against ai systems and llm applications.
- analyzes suspicious files and samples for malware characteristics.
- delete ztna application
- ztna application by id.
- delete a 5g security policy.
- xdr
- application usage metrics.
- get the onboarding status for a specific resource.
- ztna
- delete network slice
- retrieve details for a specific 5g security policy.
- network architect
- create a new orchestrated remote network configuration.
- ztna applications.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- delete a specific service connection by id.
- ztna connectors.
- cybersecurity
- update ztna application
- list ike gateways
- update a specific ztna connector group by id.
- create service connection
- list sdwan alarms
- secures ai applications with runtime scanning and vulnerability assessment.
- delete a network slice.
- delete a specific prisma access service connection by id.
- sre
- 5g network slice by id.
- list path rules
- create a new 5g security policy.
- soc analyst
- firewall admin
- create subnet rule
- investigates security incidents, triages alerts, and coordinates response actions.
- get orchestrated remote network
- vulnerability manager
- get service connection
- refresh ike gateway
- network security engineer
- get bandwidth allocations
- get network slice
- mssp operator
- create mobile agent settings
- ztna connector groups.
- manages service accounts, roles, and access policies for platform api access.
- ike gateways.
- list all subnet rules.
- create 5g tenant
- 5g security policy by id.
- monitors network health, performance, and digital experience metrics.
- create a new service connection.
- firewall
- list all ztna connector groups.
- sase config orchestration remote networks.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- create wan interface
- create 5g security policy
- list all ztna applications.
- list all service connections with pagination.
- enterprise it
- ai runtime security scanning and automated red teaming for ai applications.
- retrieve details for a specific network slice.
- update a specific ztna connector by id.
- update a specific prisma access remote network by id.
- update 5g tenant
- list sdwan sites
- soar
- sd-wan sites.
- create a wan interface for a specific site.
- get mobile agent settings
- 5g security policies.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- refresh the ike gateway for a specific remote network.
- list all remote networks with pagination.
- update an existing 5g tenant.
- get a specific ztna application by id.
- create fqdn rule
- retrieve a list of 5g network slices.
- identity and access management, tenant hierarchies, and subscription management.
- delete an sd-wan site.
- get mobile agent infrastructure settings.
- get a specific service connection by id.
- path rules.
- manages logging infrastructure, integrations, and platform automation.
- create connector group
- update a specific prisma access service connection by id.
- iam admin
- update an existing sd-wan site.
- list service connections
- create lan network
- get a specific ztna connector by id.
- list all available prisma access locations.
- firewall policy management, network objects, and cloud-native firewall configuration.
- 5g tenant by id.
- update an existing orchestrated remote network configuration.
- fqdn rules.
- list 5g tenants
- delete 5g security policy
- create a new prisma access service connection.
- threat intel analyst
- update a specific service connection by id.
- sase config orchestration remote network by id.
- get connector group
- update an existing network slice.
- get remote network
- prisma access service connection by id.
- update an existing 5g security policy.
- get sdwan site
- create a new remote network.
- create a new sd-wan site.
- get 5g security policy
- ztna licenses.
- qos rules.
- delete a specific prisma access remote network by id.
- list wan interfaces
- create a new subnet rule.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- delete a 5g network slice.
- 5g security metrics.
- create ztna connector
- browser security admin
- digital experience monitoring, log management, and best practice assessment.
- create or update mobile agent infrastructure settings.
- list all orchestrated remote networks with optional filtering.
- delete connector group
- retrieve a list of sd-wan alarms.
- get 5g tenant
- secure access
- cloud security
- retrieve details for a specific sd-wan site.
- create a new path rule.
- cloud security engineer
- ztna connector by id.
- platform engineer
- update network slice
- enterprise browser policy management and secure browsing.
- delete a specific ztna connector group by id.
slug: secure-access
source_filename: secure-access.yaml
source_heading: Capability Spec
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
  \                  in: body\n                  type: boolean\n                  required: false\n              call: \"ztna-connector.create-subnet-rule\"\n              with:\n                name: \"rest.name\"\n                subnet: \"rest.subnet\"\n                group_id: \"rest.group_id\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ztna-licenses\n          name: ztna-licenses\n          description: \"ZTNA licenses.\"\n          operations:\n            - method: GET\n              name: get-ztna-licenses\n              description: \"Get ZTNA license information.\"\n              call: \"ztna-connector.get-ztna-licenses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── SD-WAN ────────�\n\n# --- truncated at 32 KB (120 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/secure-access.yaml\n"
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
