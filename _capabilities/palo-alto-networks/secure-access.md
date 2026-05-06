---
categories: []
consumed_apis: []
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
- mssp operator
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- schedule an upgrade for a ztna connector.
- delete a specific ztna application by id.
- update orchestrated remote network
- update a specific service connection by id.
- ztna connector groups.
- executes containment, eradication, and recovery actions during security incidents.
- platform engineer
- get orchestrated remote network
- list fqdn rules
- manage enterprise browser policies, user sessions, and deployments.
- 5g security metrics.
- create a new prisma access remote network.
- get a specific service connection by id.
- 5g tenants.
- list ztna connectors
- update remote network
- retrieve details for a specific 5g security policy.
- red team operator
- xdr
- create mobile agent settings
- list all ike gateways with pagination.
- prisma access service connections.
- sd-wan
- list 5g security policies
- 5g
- get application usage
- digital experience monitoring, log management, and best practice assessment.
- retrieve wan interfaces for a specific site.
- retrieve monitoring metrics for a specific sd-wan site.
- cloud security
- sase config orchestration remote networks.
- create connector group
- get a specific prisma access service connection by id.
- palo alto networks
- application usage metrics.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- malware researcher
- monitors network health, performance, and digital experience metrics.
- ztna connectors.
- create a new ztna application.
- create a new subnet rule.
- list 5g tenants
- qos rules.
- create a new prisma access service connection.
- secures ai applications with runtime scanning and vulnerability assessment.
- sase
- refresh ike gateway
- delete remote network
- ztna licenses.
- update a specific ztna connector by id.
- delete a specific remote network by id.
- get 5g security policy
- retrieve a list of 5g security policies.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- data loss prevention, saas security monitoring, and identity security posture.
- conducts automated adversarial testing against ai systems and llm applications.
- network architect
- create a new orchestrated remote network configuration.
- list all ztna connector groups.
- list all remote networks with pagination.
- get a specific ztna connector by id.
- create service connection
- ztna connector by id.
- create subnet rule
- sre
- compliance team
- manages service accounts, roles, and access policies for platform api access.
- update an existing network slice.
- ai runtime security scanning and automated red teaming for ai applications.
- delete orchestrated remote network
- subscription manager
- create a new path rule.
- retrieve details for a specific network slice.
- update an existing 5g network slice.
- list all ztna applications.
- 5g tenant by id.
- create qos rule
- list ztna applications
- firewall
- get 5g tenant
- list ike gateways
- get bandwidth allocations optionally filtered by location.
- list orchestrated remote networks
- update a specific prisma access remote network by id.
- manages multi-tenant security operations at scale for managed service providers.
- analyzes suspicious files and samples for malware characteristics.
- wan interfaces for an sd-wan site.
- sase config orchestration remote network by id.
- delete a 5g security policy.
- create ztna connector
- list wan interfaces
- cloud security posture management, compliance monitoring, and workload protection.
- saas security admin
- get sdwan site
- soc analyst
- delete network slice
- get 5g security metrics
- delete an sd-wan site.
- get ztna licenses
- 5g security policies.
- create lan network
- create or update mobile agent infrastructure settings.
- create a new ztna connector group.
- delete sdwan site
- 5g network slices.
- sd wan operator
- investigates security incidents, triages alerts, and coordinates response actions.
- tenant operator
- get mobile agent settings
- get a specific remote network by id.
- list all subnet rules.
- path rules.
- retrieve a list of qos rules.
- schedule ztna connector upgrade.
- update a specific remote network by id.
- data protection analyst
- iam admin
- update a specific ztna connector group by id.
- list access locations
- create a new ztna connector.
- list subnet rules
- create a lan network for a specific site.
- bandwidth allocations.
- ztna applications.
- list all prisma access remote networks with pagination.
- list all prisma access service connections with pagination.
- ztna connector group by id.
- 5g network slice by id.
- create remote network
- secure access service edge with remote networking, sd-wan, and zero trust access.
- prisma access service connection by id.
- network operations
- sd-wan site by id.
- designs and implements network security architectures and policies.
- ztna application by id.
- delete ztna application
- get mobile agent infrastructure settings.
- create a new 5g network slice.
- 5g security policy by id.
- threat intel analyst
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- get service connection
- monitors and remediates cloud security misconfigurations and compliance violations.
- update service connection
- retrieve a list of 5g network slices.
- enterprise it
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- delete 5g security policy
- prisma access locations.
- get site metrics
- create fqdn rule
- list lan networks
- retrieve monitoring metrics for a specific site.
- list remote networks
- retrieve a list of sd-wan alarms.
- create orchestrated remote network
- retrieve lan networks for a specific site.
- threat hunter
- list all available prisma access locations.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- get remote network
- researches threat actors, malware campaigns, and vulnerability trends.
- prisma access remote networks.
- sd-wan alarms.
- delete an orchestrated remote network by id.
- lan networks for an sd-wan site.
- list service connections
- list all service connections with pagination.
- list path rules
- list sdwan alarms
- delete service connection
- sase admin
- update an existing orchestrated remote network configuration.
- proactively searches for threats and iocs across telemetry data.
- create a new service connection.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- vulnerability manager
- manages logging infrastructure, integrations, and platform automation.
- sd-wan sites.
- get connector group
- list qos rules
- service provider interconnect
- create a new qos rule.
- update network slice
- update ztna connector
- incident responder
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- retrieve a list of 5g tenants.
- delete a specific service connection by id.
- ike gateways.
- retrieve details for a specific sd-wan site.
- identity and access management, tenant hierarchies, and subscription management.
- update an existing sd-wan site.
- update a specific prisma access service connection by id.
- onboarding status.
- create a new remote network.
- list all fqdn rules.
- update 5g security policy
- cybersecurity
- network security engineer
- create 5g security policy
- investigates dlp incidents and manages sensitive data protection policies.
- delete a specific ztna connector by id.
- list all ztna connectors.
- schedule connector upgrade
- list connector groups
- fqdn rules.
- subnet rules.
- delete a network slice.
- retrieve 5g security monitoring metrics.
- update an existing 5g tenant.
- create a wan interface for a specific site.
- delete a specific prisma access service connection by id.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- get details of a specific orchestrated remote network by id.
- get a specific ztna connector group by id.
- sd-wan site metrics.
- delete a 5g tenant.
- manages multi-tenant hierarchies and service group configurations for mssps.
- ai security engineer
- browser security admin
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- retrieve a list of sd-wan sites.
- create a new sd-wan site.
- compliance officer
- retrieve details for a specific 5g network slice.
- enterprise browser policy management and secure browsing.
- firewall policy management, network objects, and cloud-native firewall configuration.
- get a specific prisma access remote network by id.
- update an existing 5g security policy.
- delete a 5g network slice.
- create network slice
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get onboarding status
- update connector group
- delete a specific prisma access remote network by id.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- create a new 5g security policy.
- soar
- update sdwan site
- list sdwan sites
- secure access
- get bandwidth allocations
- get the onboarding status for a specific resource.
- update 5g tenant
- get ztna application
- create wan interface
- retrieve details for a specific 5g tenant.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- network security
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- list all orchestrated remote networks with optional filtering.
- ztna
- mobile agent infrastructure settings.
- get a specific ztna application by id.
- update ztna application
- create a new fqdn rule.
- firewall admin
- list all orchestrated remote networks with optional filtering by location and status.
- retrieve a list of path rules.
- create 5g tenant
- delete 5g tenant
- delete a specific ztna connector group by id.
- create ztna application
- refresh the ike gateway for a specific remote network.
- create path rule
- refresh ike gateway for an orchestrated remote network.
- designs sase and sd-wan network architectures for secure remote access.
- create sdwan site
- cloud security engineer
- create a new 5g tenant.
- get ztna license information.
- delete ztna connector
- prisma access remote network by id.
- update a specific ztna application by id.
- retrieve application usage metrics across the sd-wan.
- threat intelligence
- delete connector group
- get network slice
- get ztna connector
- list network slices
- manages enterprise browser policies and secure browsing configurations.
slug: secure-access
source_filename: secure-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Palo Alto Networks Secure Access\n  description: Unified secure access capability for managing remote networks, ZTNA connectors, SD-WAN sites, 5G network slices,\n    and SASE configuration across Prisma Access, ZTNA Connector, SD-WAN, Config Orchestration, and 5G APIs.\n  tags:\n  - Palo Alto Networks\n  - Secure Access\n  - SASE\n  - SD-WAN\n  - ZTNA\n  - 5G\n  - Service Provider Interconnect\n  created: '2026-04-16'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: prisma-access\n    baseUri: https://api.sase.paloaltonetworks.com/sse/config/v1\n    description: Prisma Access Configuration API for managing remote networks, service connections, mobile agent infrastructure,\n      and IKE gateways.\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_OAUTH_TOKEN}}'\n    resources:\n    - name: remote-networks\n\
  \      path: /remote-networks\n      operations:\n      - name: list-remote-networks\n        method: GET\n        description: List all remote networks with pagination.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-remote-network\n        method: POST\n        description: Create a new remote network.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: location\n          in: body\n          type: string\n          required: true\n        - name: subnets\n          in: body\n          type: string\n          required: true\n        - name: ike_gateway\n          in: body\n          type:\
  \ string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            location: '{{tools.location}}'\n            subnets: '{{tools.subnets}}'\n            ike_gateway: '{{tools.ike_gateway}}'\n    - name: remote-network\n      path: /remote-networks/{id}\n      operations:\n      - name: get-remote-network\n        method: GET\n        description: Get a specific remote network by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-remote-network\n        method: PUT\n        description: Update a specific remote network by ID.\n        inputParameters:\n        - name: id\n     \
  \     in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-remote-network\n        method: DELETE\n        description: Delete a specific remote network by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-connections\n      path: /service-connections\n      operations:\n      - name: list-service-connections\n        method: GET\n        description: List all service connections with pagination.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n \
  \         type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service-connection\n        method: POST\n        description: Create a new service connection.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: ipsec_tunnel\n          in: body\n          type: string\n          required: true\n        - name: region\n          in: body\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            ipsec_tunnel: '{{tools.ipsec_tunnel}}'\n            region: '{{tools.region}}'\n    - name: service-connection\n      path: /service-connections/{id}\n      operations:\n\
  \      - name: get-service-connection\n        method: GET\n        description: Get a specific service connection by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-service-connection\n        method: PUT\n        description: Update a specific service connection by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-service-connection\n        method: DELETE\n        description: Delete a specific service connection by ID.\n        inputParameters:\n        - name: id\n          in: path\n        \
  \  type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mobile-agent-infrastructure-settings\n      path: /mobile-agent/infrastructure-settings\n      operations:\n      - name: get-mobile-agent-infrastructure-settings\n        method: GET\n        description: Get mobile agent infrastructure settings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-mobile-agent-infrastructure-settings\n        method: POST\n        description: Create or update mobile agent infrastructure settings.\n        inputParameters:\n        - name: settings\n          in: body\n          type: object\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            settings: '{{tools.settings}}'\n    - name: ike-gateways\n      path: /ike-gateways\n      operations:\n      - name: list-ike-gateways\n        method: GET\n        description: List all IKE gateways with pagination.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: ztna-connector\n    baseUri: https://api.sase.paloaltonetworks.com/ztna\n    description: ZTNA Connector API for managing connectors, connector groups, applications, FQDN rules, subnet rules, and\n      licenses.\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_OAUTH_TOKEN}}'\n    resources:\n    - name: connectors\n      path: /v2/connectors\n    \
  \  operations:\n      - name: list-connectors\n        method: GET\n        description: List all ZTNA connectors.\n        inputParameters:\n        - name: group_id\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-connector\n        method: POST\n        description: Create a new ZTNA connector.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: group_id\n          in: body\n          type: string\n          required: true\n        - name: description\n\
  \          in: body\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            group_id: '{{tools.group_id}}'\n            description: '{{tools.description}}'\n    - name: connector\n      path: /v2/connectors/{connector_id}\n      operations:\n      - name: get-connector\n        method: GET\n        description: Get a specific ZTNA connector by ID.\n        inputParameters:\n        - name: connector_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-connector\n        method: PUT\n        description: Update a specific ZTNA connector by ID.\n        inputParameters:\n        - name: connector_id\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-connector\n        method: DELETE\n        description: Delete a specific ZTNA connector by ID.\n        inputParameters:\n        - name: connector_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connector-upgrade\n      path: /v2/connectors/{connector_id}/upgrade\n      operations:\n      - name: schedule-connector-upgrade\n        method: POST\n        description: Schedule an upgrade for a ZTNA connector.\n        inputParameters:\n        - name: connector_id\n          in: path\n          type: string\n          required: true\n        - name: scheduled_at\n\
  \          in: body\n          type: string\n          required: true\n        - name: target_version\n          in: body\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            scheduled_at: '{{tools.scheduled_at}}'\n            target_version: '{{tools.target_version}}'\n    - name: connector-groups\n      path: /v2/connector-groups\n      operations:\n      - name: list-connector-groups\n        method: GET\n        description: List all ZTNA connector groups.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-connector-group\n        method: POST\n        description: Create a new ZTNA connector group.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n      \
  \    required: true\n        - name: description\n          in: body\n          type: string\n          required: false\n        - name: region\n          in: body\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            region: '{{tools.region}}'\n    - name: connector-group\n      path: /v2/connector-groups/{group_id}\n      operations:\n      - name: get-connector-group\n        method: GET\n        description: Get a specific ZTNA connector group by ID.\n        inputParameters:\n        - name: group_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-connector-group\n\
  \        method: PUT\n        description: Update a specific ZTNA connector group by ID.\n        inputParameters:\n        - name: group_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-connector-group\n        method: DELETE\n        description: Delete a specific ZTNA connector group by ID.\n        inputParameters:\n        - name: group_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /v2/applications\n      operations:\n      - name: list-ztna-applications\n        method: GET\n        description: List all ZTNA applications.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-ztna-application\n        method: POST\n        description: Create a new ZTNA application.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: group_id\n          in: body\n          type: string\n          required: true\n        - name: fqdn\n          in: body\n          type: string\n          required: true\n        - name: description\n          in: body\n          type: string\n          required: false\n        - name: ports\n          in: body\n          type: object\n          required: true\n        - name: protocols\n          in: body\n          type: object\n          required: true\n        - name: enabled\n          in: body\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            group_id: '{{tools.group_id}}'\n            fqdn: '{{tools.fqdn}}'\n            description: '{{tools.description}}'\n            ports: '{{tools.ports}}'\n            protocols: '{{tools.protocols}}'\n            enabled: '{{tools.enabled}}'\n    - name: application\n      path: /v2/applications/{app_id}\n      operations:\n      - name: get-ztna-application\n        method: GET\n        description: Get a specific ZTNA application by ID.\n        inputParameters:\n        - name: app_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ztna-application\n        method: PUT\n        description: Update a specific ZTNA application by ID.\n        inputParameters:\n        - name: app_id\n          in: path\n     \
  \     type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-ztna-application\n        method: DELETE\n        description: Delete a specific ZTNA application by ID.\n        inputParameters:\n        - name: app_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fqdn-rules\n      path: /v2/fqdn-rules\n      operations:\n      - name: list-fqdn-rules\n        method: GET\n        description: List all FQDN rules.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-fqdn-rule\n        method: POST\n        description: Create a new FQDN rule.\n  \
  \      inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: fqdn_pattern\n          in: body\n          type: string\n          required: true\n        - name: group_id\n          in: body\n          type: string\n          required: true\n        - name: ports\n          in: body\n          type: object\n          required: true\n        - name: enabled\n          in: body\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            fqdn_pattern: '{{tools.fqdn_pattern}}'\n            group_id: '{{tools.group_id}}'\n            ports: '{{tools.ports}}'\n            enabled: '{{tools.enabled}}'\n    - name: subnet-rules\n      path: /v2/subnet-rules\n      operations:\n      - name: list-subnet-rules\n\
  \        method: GET\n        description: List all subnet rules.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-subnet-rule\n        method: POST\n        description: Create a new subnet rule.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: subnet\n          in: body\n          type: string\n          required: true\n        - name: group_id\n          in: body\n          type: string\n          required: true\n        - name: enabled\n          in: body\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            subnet: '{{tools.subnet}}'\n            group_id: '{{tools.group_id}}'\n\
  \            enabled: '{{tools.enabled}}'\n    - name: licenses\n      path: /v2/licenses\n      operations:\n      - name: get-ztna-licenses\n        method: GET\n        description: Get ZTNA license information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: prisma-sd-wan\n    baseUri: https://api.sase.paloaltonetworks.com\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_OAUTH_TOKEN}}'\n    resources:\n    - name: sites\n      path: /sdwan/config/v1/sites\n      operations:\n      - name: list-sites\n        method: GET\n        description: Retrieve a list of SD-WAN sites\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: name\n          in: query\n          type: string\n\
  \          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-site\n        method: POST\n        description: Create a new SD-WAN site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            admin_state: '{{tools.admin_state}}'\n            element_cluster_role: '{{tools.element_cluster_role}}'\n            address: '{{tools.address}}'\n            location: '{{tools.location}}'\n            tags: '{{tools.tags}}'\n    - name: site-by-id\n      path: /sdwan/config/v1/sites/{site_id}\n      operations:\n      - name: get-site\n        method: GET\n        description: Retrieve details for a specific SD-WAN site\n        inputParameters:\n        - name:\
  \ site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-site\n        method: PUT\n        description: Update an existing SD-WAN site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            admin_state: '{{tools.admin_state}}'\n            element_cluster_role: '{{tools.element_cluster_role}}'\n            address: '{{tools.address}}'\n            location: '{{tools.location}}'\n            tags: '{{tools.tags}}'\n      - name: delete-site\n        method: DELETE\n        description:\
  \ Delete an SD-WAN site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: site-wan-interfaces\n      path: /sdwan/config/v1/sites/{site_id}/wan-interfaces\n      operations:\n      - name: list-site-wan-interfaces\n        method: GET\n        description: Retrieve WAN interfaces for a specific site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-site-wan-interface\n    \
  \    method: POST\n        description: Create a WAN interface for a specific site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            description: '{{tools.description}}'\n            link_bw_down: '{{tools.link_bw_down}}'\n            link_bw_up: '{{tools.link_bw_up}}'\n    - name: site-lan-networks\n      path: /sdwan/config/v1/sites/{site_id}/lan-networks\n      operations:\n      - name: list-site-lan-networks\n        method: GET\n        description: Retrieve LAN networks for a specific site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: offset\n          in: query\n\
  \          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-site-lan-network\n        method: POST\n        description: Create a LAN network for a specific site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            network: '{{tools.network}}'\n            description: '{{tools.description}}'\n            vlan_id: '{{tools.vlan_id}}'\n            dhcp_enabled: '{{tools.dhcp_enabled}}'\n    - name: qos-rules\n      path: /sdwan/config/v1/policies/qos-rules\n   \
  \   operations:\n      - name: list-qos-rules\n        method: GET\n        description: Retrieve a list of QoS rules\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-qos-rule\n        method: POST\n        description: Create a new QoS rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            priority: '{{tools.priority}}'\n            dscp_class: '{{tools.dscp_class}}'\n            app_filters: '{{tools.app_filters}}'\n            bandwidth_limit_up: '{{tools.bandwidth_limit_up}}'\n            bandwidth_limit_down:\
  \ '{{tools.bandwidth_limit_down}}'\n    - name: path-rules\n      path: /sdwan/config/v1/policies/path-rules\n      operations:\n      - name: list-path-rules\n        method: GET\n        description: Retrieve a list of path rules\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-path-rule\n        method: POST\n        description: Create a new path rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            app_filters: '{{tools.app_filters}}'\n            preferred_paths: '{{tools.preferred_paths}}'\n\
  \            sla_threshold: '{{tools.sla_threshold}}'\n    - name: site-metrics\n      path: /sdwan/monitor/v1/sites/{site_id}/metrics\n      operations:\n      - name: get-site-metrics\n        method: GET\n        description: Retrieve monitoring metrics for a specific site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: start_time\n          in: query\n          type: string\n          required: false\n        - name: end_time\n          in: query\n          type: string\n          required: false\n        - name: metric_type\n          in: query\n          type: string\n          required: false\n        - name: granularity\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-usage\n      path: /sdwan/monitor/v1/applications\n\
  \      operations:\n      - name: get-application-usage\n        method: GET\n        description: Retrieve application usage metrics across the SD-WAN\n        inputParameters:\n        - name: start_time\n          in: query\n          type: string\n          required: false\n        - name: end_time\n          in: query\n          type: string\n          required: false\n        - name: site_id\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alarms\n      path: /sdwan/monitor/v1/alarms\n      operations:\n      - name: list-alarms\n        method: GET\n        description: Retrieve a list of SD-WAN alarms\n        inputParameters:\n\
  \        - name: site_id\n          in: query\n          type: string\n          required: false\n        - name: severity\n          in: query\n          type: string\n          required: false\n        - name: acknowledged\n          in: query\n          type: boolean\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sase-config-orchestration\n    baseUri: https://api.sase.paloaltonetworks.com/config-orchestration/v1\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_OAUTH_TOKEN}}'\n    resources:\n    - name: remote-networks\n      path: /remote-networks\n      operations:\n      - name: list-remote-networks\n        method: GET\n        description:\
  \ List all remote networks with optional filtering by location and status.\n        inputParameters:\n        - name: location\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-remote-network\n        method: POST\n        description: Create a new remote network configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            location: '{{tools.location}}'\n\
  \            subnets: '{{tools.subnets}}'\n            ike_gateway: '{{tools.ike_gateway}}'\n            description: '{{tools.description}}'\n            bandwidth_mbps: '{{tools.bandwidth_mbps}}'\n      - name: get-remote-network\n        method: GET\n        description: Get details of a specific remote network by ID.\n        path: /{id}\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-remote-network\n        method: PUT\n        description: Update an existing remote network configuration.\n        path: /{id}\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n   \
  \       type: json\n          data:\n            name: '{{tools.name}}'\n            location: '{{tools.location}}'\n            subnets: '{{tools.subnets}}'\n            ike_gateway: '{{tools.ike_gateway}}'\n            description: '{{tools.description}}'\n            bandwidth_mbps: '{{tools.bandwidth_mbps}}'\n      - name: delete-remote-network\n        method: DELETE\n        description: Delete a remote network by ID.\n        path: /{id}\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refresh-ike-gateway\n        method: POST\n        description: Refresh the IKE gateway for a specific remote network.\n        path: /{id}/refresh-ike-gateway\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bandwidth-allocations\n      path: /bandwidth-allocations\n      operations:\n      - name: get-bandwidth-allocations\n        method: GET\n        description: Get bandwidth allocations optionally filtered by location.\n        inputParameters:\n        - name: location\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /locations\n      operations:\n      - name: list-prisma-access-locations\n        method: GET\n        description: List all available Prisma Access locations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \n\n# --- truncated at 32 KB (147 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/secure-access.yaml\n"
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
