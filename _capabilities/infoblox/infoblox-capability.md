---
categories: []
consumed_apis: []
description: RESTful API for managing Infoblox NIOS DDI (DNS, DHCP, IPAM) services, network objects, and configuration. The WAPI uses standard HTTP methods for CRUD operations and supports JSON and XML input and output formats. Authentication is handled via HTTP basic authentication or certificate-based authentication, and sessions can be maintained using cookies returned after initial authentication. The API follows a resource-oriented design where each NIOS object type is accessible as a REST resource.
layout: capability
name: Infoblox WAPI (Web API)
operations:
- description: Infoblox List DNS A records
  method: GET
  name: listarecords
  path: /record:a
- description: Infoblox Create a DNS A record
  method: POST
  name: createarecord
  path: /record:a
- description: Infoblox Get a DNS A record
  method: GET
  name: getarecord
  path: /record:a/{ref}
- description: Infoblox Update a DNS A record
  method: PUT
  name: updatearecord
  path: /record:a/{ref}
- description: Infoblox Delete a DNS A record
  method: DELETE
  name: deletearecord
  path: /record:a/{ref}
- description: Infoblox List DNS AAAA records
  method: GET
  name: listaaaarecords
  path: /record:aaaa
- description: Infoblox Create a DNS AAAA record
  method: POST
  name: createaaaarecord
  path: /record:aaaa
- description: Infoblox List DNS CNAME records
  method: GET
  name: listcnamerecords
  path: /record:cname
- description: Infoblox Create a DNS CNAME record
  method: POST
  name: createcnamerecord
  path: /record:cname
- description: Infoblox List DNS MX records
  method: GET
  name: listmxrecords
  path: /record:mx
- description: Infoblox Create a DNS MX record
  method: POST
  name: createmxrecord
  path: /record:mx
- description: Infoblox List DNS TXT records
  method: GET
  name: listtxtrecords
  path: /record:txt
- description: Infoblox Create a DNS TXT record
  method: POST
  name: createtxtrecord
  path: /record:txt
- description: Infoblox List DNS PTR records
  method: GET
  name: listptrrecords
  path: /record:ptr
- description: Infoblox Create a DNS PTR record
  method: POST
  name: createptrrecord
  path: /record:ptr
- description: Infoblox List DNS host records
  method: GET
  name: listhostrecords
  path: /record:host
- description: Infoblox Create a DNS host record
  method: POST
  name: createhostrecord
  path: /record:host
- description: Infoblox List authoritative DNS zones
  method: GET
  name: listauthoritativezones
  path: /zone_auth
- description: Infoblox Create an authoritative DNS zone
  method: POST
  name: createauthoritativezone
  path: /zone_auth
- description: Infoblox List forward DNS zones
  method: GET
  name: listforwardzones
  path: /zone_forward
- description: Infoblox List DHCP networks
  method: GET
  name: listnetworks
  path: /network
- description: Infoblox Create a network
  method: POST
  name: createnetwork
  path: /network
- description: Infoblox List network views
  method: GET
  name: listnetworkviews
  path: /networkview
- description: Infoblox List IPv4 addresses
  method: GET
  name: listipv4addresses
  path: /ipv4address
- description: Infoblox List DHCP ranges
  method: GET
  name: listdhcpranges
  path: /range
- description: Infoblox Create a DHCP range
  method: POST
  name: createdhcprange
  path: /range
- description: Infoblox List DHCP fixed addresses
  method: GET
  name: listfixedaddresses
  path: /fixedaddress
- description: Infoblox Create a DHCP fixed address
  method: POST
  name: createfixedaddress
  path: /fixedaddress
- description: Infoblox List DHCP leases
  method: GET
  name: listdhcpleases
  path: /lease
- description: Infoblox Get Grid information
  method: GET
  name: getgrid
  path: /grid
- description: Infoblox List Grid members
  method: GET
  name: listmembers
  path: /member
personas: []
provider_name: Infoblox
provider_slug: infoblox
search_terms:
- createnetwork
- listforwardzones
- dhcp
- infoblox list network views
- infoblox create a dhcp range
- ddi
- listdhcpleases
- createhostrecord
- dns
- createmxrecord
- listtxtrecords
- deletearecord
- listmembers
- ipam
- infoblox create an authoritative dns zone
- infoblox list forward dns zones
- infoblox create a dns txt record
- createptrrecord
- infoblox list dns host records
- infoblox create a network
- infoblox list dhcp ranges
- infoblox list dns ptr records
- infoblox create a dns host record
- createtxtrecord
- infoblox list dhcp networks
- getgrid
- infoblox create a dhcp fixed address
- cloud
- network management
- security
- infoblox get a dns a record
- infoblox list authoritative dns zones
- infoblox list dns a records
- infoblox create a dns ptr record
- listcnamerecords
- infoblox create a dns cname record
- infoblox list dns mx records
- listarecords
- listauthoritativezones
- infoblox list dns cname records
- infoblox list ipv4 addresses
- createarecord
- infoblox
- infoblox get grid information
- api
- listmxrecords
- infoblox update a dns a record
- listptrrecords
- infoblox create a dns a record
- listdhcpranges
- infoblox list dhcp fixed addresses
- infoblox list grid members
- createaaaarecord
- createcnamerecord
- listnetworks
- infoblox create a dns aaaa record
- infoblox list dns txt records
- createfixedaddress
- infoblox list dns aaaa records
- infoblox list dhcp leases
- infoblox delete a dns a record
- createauthoritativezone
- listipv4addresses
- infoblox create a dns mx record
- threat intelligence
- listnetworkviews
- listfixedaddresses
- listaaaarecords
- getarecord
- createdhcprange
- updatearecord
- listhostrecords
slug: infoblox-capability
source_filename: infoblox-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Infoblox WAPI (Web API)\n  description: RESTful API for managing Infoblox NIOS DDI (DNS, DHCP, IPAM) services, network objects, and configuration.\n    The WAPI uses standard HTTP methods for CRUD operations and supports JSON and XML input and output formats. Authentication\n    is handled via HTTP basic authentication or certificate-based authentication, and sessions can be maintained using cookies\n    returned after initial authentication. The API follows a resource-oriented design where each NIOS object type is accessible\n    as a REST resource.\n  tags:\n  - Infoblox\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: infoblox\n    baseUri: https://grid-master.example.com/wapi/v2.12\n    description: Infoblox WAPI (Web API) HTTP API.\n    authentication:\n      type: basic\n      username: '{{INFOBLOX_USERNAME}}'\n      password: '{{INFOBLOX_PASSWORD}}'\n    resources:\n\
  \    - name: record-a\n      path: /record:a\n      operations:\n      - name: listarecords\n        method: GET\n        description: Infoblox List DNS A records\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter by the fully qualified domain name of the A record.\n        - name: ipv4addr\n          in: query\n          type: string\n          description: Filter by the IPv4 address of the A record.\n        - name: view\n          in: query\n          type: string\n          description: Filter by the DNS view name.\n        - name: zone\n          in: query\n          type: string\n          description: Filter by the DNS zone name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createarecord\n        method: POST\n        description: Infoblox Create a DNS A record\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: record-a-ref\n      path: /record:a/{ref}\n      operations:\n      - name: getarecord\n        method: GET\n        description: Infoblox Get a DNS A record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatearecord\n        method: PUT\n        description: Infoblox Update a DNS A record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletearecord\n        method: DELETE\n        description: Infoblox Delete a DNS A record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: record-aaaa\n      path: /record:aaaa\n      operations:\n      - name: listaaaarecords\n        method: GET\n        description: Infoblox List DNS AAAA records\n\
  \        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter by the fully qualified domain name.\n        - name: ipv6addr\n          in: query\n          type: string\n          description: Filter by the IPv6 address.\n        - name: view\n          in: query\n          type: string\n          description: Filter by the DNS view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaaaarecord\n        method: POST\n        description: Infoblox Create a DNS AAAA record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: record-cname\n      path: /record:cname\n      operations:\n      - name: listcnamerecords\n        method: GET\n        description: Infoblox List DNS CNAME records\n        inputParameters:\n        - name: name\n    \
  \      in: query\n          type: string\n          description: Filter by the alias name.\n        - name: canonical\n          in: query\n          type: string\n          description: Filter by the canonical (target) name.\n        - name: view\n          in: query\n          type: string\n          description: Filter by the DNS view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcnamerecord\n        method: POST\n        description: Infoblox Create a DNS CNAME record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: record-mx\n      path: /record:mx\n      operations:\n      - name: listmxrecords\n        method: GET\n        description: Infoblox List DNS MX records\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter\
  \ by the domain name.\n        - name: mail_exchanger\n          in: query\n          type: string\n          description: Filter by the mail exchanger hostname.\n        - name: view\n          in: query\n          type: string\n          description: Filter by the DNS view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmxrecord\n        method: POST\n        description: Infoblox Create a DNS MX record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: record-txt\n      path: /record:txt\n      operations:\n      - name: listtxtrecords\n        method: GET\n        description: Infoblox List DNS TXT records\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter by the domain name.\n        - name: view\n          in: query\n\
  \          type: string\n          description: Filter by the DNS view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtxtrecord\n        method: POST\n        description: Infoblox Create a DNS TXT record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: record-ptr\n      path: /record:ptr\n      operations:\n      - name: listptrrecords\n        method: GET\n        description: Infoblox List DNS PTR records\n        inputParameters:\n        - name: ptrdname\n          in: query\n          type: string\n          description: Filter by the domain name the PTR record points to.\n        - name: ipv4addr\n          in: query\n          type: string\n          description: Filter by the IPv4 address for the PTR record.\n        - name: view\n          in: query\n          type: string\n      \
  \    description: Filter by the DNS view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createptrrecord\n        method: POST\n        description: Infoblox Create a DNS PTR record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: record-host\n      path: /record:host\n      operations:\n      - name: listhostrecords\n        method: GET\n        description: Infoblox List DNS host records\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter by the fully qualified domain name of the host.\n        - name: view\n          in: query\n          type: string\n          description: Filter by the DNS view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: createhostrecord\n        method: POST\n        description: Infoblox Create a DNS host record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zone-auth\n      path: /zone_auth\n      operations:\n      - name: listauthoritativezones\n        method: GET\n        description: Infoblox List authoritative DNS zones\n        inputParameters:\n        - name: fqdn\n          in: query\n          type: string\n          description: Filter by the fully qualified domain name of the zone.\n        - name: view\n          in: query\n          type: string\n          description: Filter by the DNS view name.\n        - name: zone_format\n          in: query\n          type: string\n          description: Filter by the zone format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createauthoritativezone\n\
  \        method: POST\n        description: Infoblox Create an authoritative DNS zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zone-forward\n      path: /zone_forward\n      operations:\n      - name: listforwardzones\n        method: GET\n        description: Infoblox List forward DNS zones\n        inputParameters:\n        - name: fqdn\n          in: query\n          type: string\n          description: Filter by the fully qualified domain name of the forward zone.\n        - name: view\n          in: query\n          type: string\n          description: Filter by the DNS view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network\n      path: /network\n      operations:\n      - name: listnetworks\n        method: GET\n        description: Infoblox List DHCP networks\n        inputParameters:\n\
  \        - name: network\n          in: query\n          type: string\n          description: Filter by the network address in CIDR notation (e.g. 10.0.0.0/24).\n        - name: network_view\n          in: query\n          type: string\n          description: Filter by the network view name.\n        - name: comment\n          in: query\n          type: string\n          description: Filter by the comment associated with the network.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnetwork\n        method: POST\n        description: Infoblox Create a network\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: networkview\n      path: /networkview\n      operations:\n      - name: listnetworkviews\n        method: GET\n        description: Infoblox List network views\n        inputParameters:\n        -\
  \ name: name\n          in: query\n          type: string\n          description: Filter by the network view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ipv4address\n      path: /ipv4address\n      operations:\n      - name: listipv4addresses\n        method: GET\n        description: Infoblox List IPv4 addresses\n        inputParameters:\n        - name: ip_address\n          in: query\n          type: string\n          description: Filter by the IPv4 address.\n        - name: network\n          in: query\n          type: string\n          description: Filter by the network in CIDR notation.\n        - name: status\n          in: query\n          type: string\n          description: Filter by the IP address status.\n        - name: network_view\n          in: query\n          type: string\n          description: Filter by the network view name.\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: range\n      path: /range\n      operations:\n      - name: listdhcpranges\n        method: GET\n        description: Infoblox List DHCP ranges\n        inputParameters:\n        - name: network\n          in: query\n          type: string\n          description: Filter by the parent network in CIDR notation.\n        - name: start_addr\n          in: query\n          type: string\n          description: Filter by the starting IP address of the range.\n        - name: end_addr\n          in: query\n          type: string\n          description: Filter by the ending IP address of the range.\n        - name: network_view\n          in: query\n          type: string\n          description: Filter by the network view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdhcprange\n        method:\
  \ POST\n        description: Infoblox Create a DHCP range\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fixedaddress\n      path: /fixedaddress\n      operations:\n      - name: listfixedaddresses\n        method: GET\n        description: Infoblox List DHCP fixed addresses\n        inputParameters:\n        - name: ipv4addr\n          in: query\n          type: string\n          description: Filter by the reserved IPv4 address.\n        - name: mac\n          in: query\n          type: string\n          description: Filter by the MAC address.\n        - name: network_view\n          in: query\n          type: string\n          description: Filter by the network view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfixedaddress\n        method: POST\n        description: Infoblox Create a DHCP\
  \ fixed address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lease\n      path: /lease\n      operations:\n      - name: listdhcpleases\n        method: GET\n        description: Infoblox List DHCP leases\n        inputParameters:\n        - name: address\n          in: query\n          type: string\n          description: Filter by the leased IPv4 address.\n        - name: network_view\n          in: query\n          type: string\n          description: Filter by the network view name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: grid\n      path: /grid\n      operations:\n      - name: getgrid\n        method: GET\n        description: Infoblox Get Grid information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: member\n      path: /member\n      operations:\n      - name: listmembers\n        method: GET\n        description: Infoblox List Grid members\n        inputParameters:\n        - name: host_name\n          in: query\n          type: string\n          description: Filter by the member hostname.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: infoblox-rest\n    description: REST adapter for Infoblox WAPI (Web API).\n    resources:\n    - path: /record:a\n      name: listarecords\n      operations:\n      - method: GET\n        name: listarecords\n        description: Infoblox List DNS A records\n        call: infoblox.listarecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:a\n      name: createarecord\n      operations:\n      - method: POST\n        name: createarecord\n        description:\
  \ Infoblox Create a DNS A record\n        call: infoblox.createarecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:a/{ref}\n      name: getarecord\n      operations:\n      - method: GET\n        name: getarecord\n        description: Infoblox Get a DNS A record\n        call: infoblox.getarecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:a/{ref}\n      name: updatearecord\n      operations:\n      - method: PUT\n        name: updatearecord\n        description: Infoblox Update a DNS A record\n        call: infoblox.updatearecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:a/{ref}\n      name: deletearecord\n      operations:\n      - method: DELETE\n        name: deletearecord\n        description: Infoblox Delete a DNS A record\n        call: infoblox.deletearecord\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /record:aaaa\n      name: listaaaarecords\n      operations:\n      - method: GET\n        name: listaaaarecords\n        description: Infoblox List DNS AAAA records\n        call: infoblox.listaaaarecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:aaaa\n      name: createaaaarecord\n      operations:\n      - method: POST\n        name: createaaaarecord\n        description: Infoblox Create a DNS AAAA record\n        call: infoblox.createaaaarecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:cname\n      name: listcnamerecords\n      operations:\n      - method: GET\n        name: listcnamerecords\n        description: Infoblox List DNS CNAME records\n        call: infoblox.listcnamerecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:cname\n      name: createcnamerecord\n      operations:\n      - method: POST\n   \
  \     name: createcnamerecord\n        description: Infoblox Create a DNS CNAME record\n        call: infoblox.createcnamerecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:mx\n      name: listmxrecords\n      operations:\n      - method: GET\n        name: listmxrecords\n        description: Infoblox List DNS MX records\n        call: infoblox.listmxrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:mx\n      name: createmxrecord\n      operations:\n      - method: POST\n        name: createmxrecord\n        description: Infoblox Create a DNS MX record\n        call: infoblox.createmxrecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:txt\n      name: listtxtrecords\n      operations:\n      - method: GET\n        name: listtxtrecords\n        description: Infoblox List DNS TXT records\n        call: infoblox.listtxtrecords\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /record:txt\n      name: createtxtrecord\n      operations:\n      - method: POST\n        name: createtxtrecord\n        description: Infoblox Create a DNS TXT record\n        call: infoblox.createtxtrecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:ptr\n      name: listptrrecords\n      operations:\n      - method: GET\n        name: listptrrecords\n        description: Infoblox List DNS PTR records\n        call: infoblox.listptrrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:ptr\n      name: createptrrecord\n      operations:\n      - method: POST\n        name: createptrrecord\n        description: Infoblox Create a DNS PTR record\n        call: infoblox.createptrrecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:host\n      name: listhostrecords\n      operations:\n\
  \      - method: GET\n        name: listhostrecords\n        description: Infoblox List DNS host records\n        call: infoblox.listhostrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /record:host\n      name: createhostrecord\n      operations:\n      - method: POST\n        name: createhostrecord\n        description: Infoblox Create a DNS host record\n        call: infoblox.createhostrecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /zone_auth\n      name: listauthoritativezones\n      operations:\n      - method: GET\n        name: listauthoritativezones\n        description: Infoblox List authoritative DNS zones\n        call: infoblox.listauthoritativezones\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /zone_auth\n      name: createauthoritativezone\n      operations:\n      - method: POST\n        name: createauthoritativezone\n        description:\
  \ Infoblox Create an authoritative DNS zone\n        call: infoblox.createauthoritativezone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /zone_forward\n      name: listforwardzones\n      operations:\n      - method: GET\n        name: listforwardzones\n        description: Infoblox List forward DNS zones\n        call: infoblox.listforwardzones\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network\n      name: listnetworks\n      operations:\n      - method: GET\n        name: listnetworks\n        description: Infoblox List DHCP networks\n        call: infoblox.listnetworks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network\n      name: createnetwork\n      operations:\n      - method: POST\n        name: createnetwork\n        description: Infoblox Create a network\n        call: infoblox.createnetwork\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /networkview\n      name: listnetworkviews\n      operations:\n      - method: GET\n        name: listnetworkviews\n        description: Infoblox List network views\n        call: infoblox.listnetworkviews\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ipv4address\n      name: listipv4addresses\n      operations:\n      - method: GET\n        name: listipv4addresses\n        description: Infoblox List IPv4 addresses\n        call: infoblox.listipv4addresses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /range\n      name: listdhcpranges\n      operations:\n      - method: GET\n        name: listdhcpranges\n        description: Infoblox List DHCP ranges\n        call: infoblox.listdhcpranges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /range\n      name: createdhcprange\n      operations:\n      - method: POST\n        name: createdhcprange\n\
  \        description: Infoblox Create a DHCP range\n        call: infoblox.createdhcprange\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fixedaddress\n      name: listfixedaddresses\n      operations:\n      - method: GET\n        name: listfixedaddresses\n        description: Infoblox List DHCP fixed addresses\n        call: infoblox.listfixedaddresses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fixedaddress\n      name: createfixedaddress\n      operations:\n      - method: POST\n        name: createfixedaddress\n        description: Infoblox Create a DHCP fixed address\n        call: infoblox.createfixedaddress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lease\n      name: listdhcpleases\n      operations:\n      - method: GET\n        name: listdhcpleases\n        description: Infoblox List DHCP leases\n        call: infoblox.listdhcpleases\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /grid\n      name: getgrid\n      operations:\n      - method: GET\n        name: getgrid\n        description: Infoblox Get Grid information\n        call: infoblox.getgrid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /member\n      name: listmembers\n      operations:\n      - method: GET\n        name: listmembers\n        description: Infoblox List Grid members\n        call: infoblox.listmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: infoblox-mcp\n    transport: http\n    description: MCP adapter for Infoblox WAPI (Web API) for AI agent use.\n    tools:\n    - name: listarecords\n      description: Infoblox List DNS A records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: infoblox.listarecords\n      with:\n        name: tools.name\n        ipv4addr:\
  \ tools.ipv4addr\n        view: tools.view\n        zone: tools.zone\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter by the fully qualified domain name of the A record.\n      - name: ipv4addr\n        type: string\n        description: Filter by the IPv4 address of the A record.\n      - name: view\n        type: string\n        description: Filter by the DNS view name.\n      - name: zone\n        type: string\n        description: Filter by the DNS zone name.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createarecord\n      description: Infoblox Create a DNS A record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infoblox.createarecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getarecord\n      description: Infoblox Get a DNS A record\n      hints:\n        readOnly: true\n        destructive: false\n  \
  \      idempotent: true\n      call: infoblox.getarecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatearecord\n      description: Infoblox Update a DNS A record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: infoblox.updatearecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletearecord\n      description: Infoblox Delete a DNS A record\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: infoblox.deletearecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaaaarecords\n      description: Infoblox List DNS AAAA records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: infoblox.listaaaarecords\n      with:\n        name: tools.name\n        ipv6addr: tools.ipv6addr\n        view: tools.view\n      inputParameters:\n\
  \      - name: name\n        type: string\n        description: Filter by the fully qualified domain name.\n      - name: ipv6addr\n        type: string\n        description: Filter by the IPv6 address.\n      - name: view\n        type: string\n        description: Filter by the DNS view name.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createaaaarecord\n      description: Infoblox Create a DNS AAAA record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infoblox.createaaaarecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcnamerecords\n      description: Infoblox List DNS CNAME records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: infoblox.listcnamerecords\n      with:\n        name: tools.name\n        canonical: tools.canonical\n        view: tools.view\n      inputParameters:\n      - name:\
  \ name\n        type: string\n        description: Filter by the alias name.\n      - name: canonical\n        type: string\n        description: Filter by the canonical (target) name.\n      - name: view\n        type: string\n        description: Filter by the DNS view name.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcnamerecord\n      description: Infoblox Create a DNS CNAME record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infoblox.createcnamerecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmxrecords\n      description: Infoblox List DNS MX records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: infoblox.listmxrecords\n      with:\n        name: tools.name\n        mail_exchanger: tools.mail_exchanger\n        view: tools.view\n      inputParameters:\n      - name: name\n     \
  \   type: string\n        description: Filter by the domain name.\n      - name: mail_exchanger\n        type: string\n        description: Filter by the mail exchanger hostname.\n      - name: view\n        type: string\n        description: Filter by the DNS view name.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmxrecord\n      description: Infoblox Create a DNS MX record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infoblox.createmxrecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtxtrecords\n      description: Infoblox List DNS TXT records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: infoblox.listtxtrecords\n      with:\n        name: tools.name\n        view: tools.view\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter by the domain\
  \ name.\n      - name: view\n        type: string\n        description: Filter by the DNS view name.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtxtrecord\n      description: Infoblox Create a DNS TXT record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infoblox.createtxtrecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listptrrecords\n      description: Infoblox List DNS PTR records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: infoblox.listptrrecords\n      with:\n        ptrdname: tools.ptrdname\n        ipv4addr: tools.ipv4addr\n        view: tools.view\n      inputParameters:\n      - name: ptrdname\n        type: string\n        description: Filter by the domain name the PTR record points to.\n      - name: ipv4addr\n        type: string\n        description: Filter by the IPv4 address\
  \ for the PTR record.\n      - name: view\n        type: string\n        description: Filter by the DNS view name.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createptrrecord\n      description: Infoblox Create a DNS PTR record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infoblox.createptrrecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listhostrecords\n      description: Infoblox List DNS host records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: infoblox.listhostrecords\n      with:\n        name: tools.name\n        view: tools.view\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter by the fully qualified domain name of the host.\n      - name: view\n        type: string\n        description: Filter by the DNS view name.\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createhostrecord\n      description: Infoblox Create a DNS host record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infoblox.createhostrecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listauthoritativezones\n      description: Infoblox List authoritative DNS zones\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: infoblox.listauthoritativezones\n      with:\n        fqdn: tools.fqdn\n        view: tools.view\n        zone_format: tools.zone_format\n      inputParameters:\n      - name: fqdn\n        type: string\n        description: Filter by the fully qualified domain name of the zone.\n      - name: view\n        type: string\n        description: Filter by the DNS view name.\n      - name: zone_format\n        type: string\n        description: Filter by the zone format.\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createauthoritativezone\n      description: Infoblox Create an authoritative DNS zone\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: infoblox.createauthoritativezone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listforwardzones\n      description: Infoblox List forward DNS zones\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: infoblox.listforwardzones\n      with:\n        fqdn: tools.fqdn\n        view: tools.view\n      inputParameters:\n      - name: fqdn\n        type: string\n        description: Filter by the fully qualified domain name of the forward zone.\n      - name: view\n        type: string\n        \n\n# --- truncated at 32 KB (37 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/infoblox/refs/heads/main/capabilities/infoblox-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/infoblox/refs/heads/main/capabilities/infoblox-capability.yaml
tags:
- Infoblox
- API
tools:
- description: Infoblox List DNS A records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listarecords
- description: Infoblox Create a DNS A record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createarecord
- description: Infoblox Get a DNS A record
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getarecord
- description: Infoblox Update a DNS A record
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatearecord
- description: Infoblox Delete a DNS A record
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletearecord
- description: Infoblox List DNS AAAA records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaaaarecords
- description: Infoblox Create a DNS AAAA record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaaaarecord
- description: Infoblox List DNS CNAME records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcnamerecords
- description: Infoblox Create a DNS CNAME record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcnamerecord
- description: Infoblox List DNS MX records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmxrecords
- description: Infoblox Create a DNS MX record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmxrecord
- description: Infoblox List DNS TXT records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtxtrecords
- description: Infoblox Create a DNS TXT record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtxtrecord
- description: Infoblox List DNS PTR records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listptrrecords
- description: Infoblox Create a DNS PTR record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createptrrecord
- description: Infoblox List DNS host records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listhostrecords
- description: Infoblox Create a DNS host record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createhostrecord
- description: Infoblox List authoritative DNS zones
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauthoritativezones
- description: Infoblox Create an authoritative DNS zone
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createauthoritativezone
- description: Infoblox List forward DNS zones
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listforwardzones
- description: Infoblox List DHCP networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnetworks
- description: Infoblox Create a network
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnetwork
- description: Infoblox List network views
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnetworkviews
- description: Infoblox List IPv4 addresses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listipv4addresses
- description: Infoblox List DHCP ranges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdhcpranges
- description: Infoblox Create a DHCP range
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdhcprange
- description: Infoblox List DHCP fixed addresses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfixedaddresses
- description: Infoblox Create a DHCP fixed address
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfixedaddress
- description: Infoblox List DHCP leases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdhcpleases
- description: Infoblox Get Grid information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgrid
- description: Infoblox List Grid members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmembers
---
