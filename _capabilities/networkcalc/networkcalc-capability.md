---
categories: []
consumed_apis: []
description: NetworkCalc provides RESTful APIs for network and security tools including a subnet calculator, DNS tools, security tools (TLS/SSL inspection, password generation), encoders, and a binary converter. The public APIs return JSON responses over HTTPS and use common HTTP verbs.
layout: capability
name: NetworkCalc API
operations:
- description: Subnet calculator (IPv4)
  method: GET
  name: get-ip-address
  path: /ip/{address}
- description: Subnet calculator (IPv6)
  method: GET
  name: get-ipv6-address
  path: /ipv6/{address}
- description: DNS lookup
  method: GET
  name: get-dns-lookup-domain
  path: /dns/lookup/{domain}
- description: SSL/TLS security scan
  method: GET
  name: get-security-scan-host
  path: /security/scan/{host}
- description: Encode or decode a value
  method: GET
  name: get-encoder-type-value
  path: /encoder/{type}/{value}
- description: Binary conversion
  method: GET
  name: get-binary-value
  path: /binary/{value}
personas: []
provider_name: NetworkCalc
provider_slug: networkcalc
search_terms:
- networking
- get security scan host
- binary conversion
- dns
- subnet calculator (ipv6)
- get ip address
- domains
- get binary value
- subnetting
- encode or decode a value
- security
- subnet calculator (ipv4)
- get dns lookup domain
- networkcalc
- dns lookup
- ssl/tls security scan
- get encoder type value
- api
- get ipv6 address
- calculator
slug: networkcalc-capability
source_filename: networkcalc-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NetworkCalc API\n  description: NetworkCalc provides RESTful APIs for network and security tools including a subnet calculator, DNS tools,\n    security tools (TLS/SSL inspection, password generation), encoders, and a binary converter. The public APIs return JSON\n    responses over HTTPS and use common HTTP verbs.\n  tags:\n  - Networkcalc\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: networkcalc\n    baseUri: https://networkcalc.com/api\n    description: NetworkCalc API HTTP API.\n    resources:\n    - name: ip-address\n      path: /ip/{address}\n      operations:\n      - name: get-ip-address\n        method: GET\n        description: Subnet calculator (IPv4)\n        inputParameters:\n        - name: address\n          in: path\n          type: string\n          required: true\n          description: IPv4 address with CIDR mask, for example 192.168.1.0/24.\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ipv6-address\n      path: /ipv6/{address}\n      operations:\n      - name: get-ipv6-address\n        method: GET\n        description: Subnet calculator (IPv6)\n        inputParameters:\n        - name: address\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dns-lookup-domain\n      path: /dns/lookup/{domain}\n      operations:\n      - name: get-dns-lookup-domain\n        method: GET\n        description: DNS lookup\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-scan-host\n\
  \      path: /security/scan/{host}\n      operations:\n      - name: get-security-scan-host\n        method: GET\n        description: SSL/TLS security scan\n        inputParameters:\n        - name: host\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: encoder-type-value\n      path: /encoder/{type}/{value}\n      operations:\n      - name: get-encoder-type-value\n        method: GET\n        description: Encode or decode a value\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n        - name: value\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: binary-value\n      path: /binary/{value}\n      operations:\n\
  \      - name: get-binary-value\n        method: GET\n        description: Binary conversion\n        inputParameters:\n        - name: value\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: networkcalc-rest\n    description: REST adapter for NetworkCalc API.\n    resources:\n    - path: /ip/{address}\n      name: get-ip-address\n      operations:\n      - method: GET\n        name: get-ip-address\n        description: Subnet calculator (IPv4)\n        call: networkcalc.get-ip-address\n        with:\n          address: rest.address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ipv6/{address}\n      name: get-ipv6-address\n      operations:\n      - method: GET\n        name: get-ipv6-address\n        description: Subnet calculator (IPv6)\n\
  \        call: networkcalc.get-ipv6-address\n        with:\n          address: rest.address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dns/lookup/{domain}\n      name: get-dns-lookup-domain\n      operations:\n      - method: GET\n        name: get-dns-lookup-domain\n        description: DNS lookup\n        call: networkcalc.get-dns-lookup-domain\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /security/scan/{host}\n      name: get-security-scan-host\n      operations:\n      - method: GET\n        name: get-security-scan-host\n        description: SSL/TLS security scan\n        call: networkcalc.get-security-scan-host\n        with:\n          host: rest.host\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /encoder/{type}/{value}\n      name: get-encoder-type-value\n      operations:\n      - method: GET\n        name:\
  \ get-encoder-type-value\n        description: Encode or decode a value\n        call: networkcalc.get-encoder-type-value\n        with:\n          type: rest.type\n          value: rest.value\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /binary/{value}\n      name: get-binary-value\n      operations:\n      - method: GET\n        name: get-binary-value\n        description: Binary conversion\n        call: networkcalc.get-binary-value\n        with:\n          value: rest.value\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: networkcalc-mcp\n    transport: http\n    description: MCP adapter for NetworkCalc API for AI agent use.\n    tools:\n    - name: get-ip-address\n      description: Subnet calculator (IPv4)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: networkcalc.get-ip-address\n      with:\n        address:\
  \ tools.address\n      inputParameters:\n      - name: address\n        type: string\n        description: IPv4 address with CIDR mask, for example 192.168.1.0/24.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ipv6-address\n      description: Subnet calculator (IPv6)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: networkcalc.get-ipv6-address\n      with:\n        address: tools.address\n      inputParameters:\n      - name: address\n        type: string\n        description: address\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dns-lookup-domain\n      description: DNS lookup\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: networkcalc.get-dns-lookup-domain\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n   \
  \     type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-security-scan-host\n      description: SSL/TLS security scan\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: networkcalc.get-security-scan-host\n      with:\n        host: tools.host\n      inputParameters:\n      - name: host\n        type: string\n        description: host\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-encoder-type-value\n      description: Encode or decode a value\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: networkcalc.get-encoder-type-value\n      with:\n        type: tools.type\n        value: tools.value\n      inputParameters:\n      - name: type\n        type: string\n        description: type\n        required: true\n      - name:\
  \ value\n        type: string\n        description: value\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-binary-value\n      description: Binary conversion\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: networkcalc.get-binary-value\n      with:\n        value: tools.value\n      inputParameters:\n      - name: value\n        type: string\n        description: value\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/networkcalc/refs/heads/main/capabilities/networkcalc-capability.yaml
tags:
- Networkcalc
- API
tools:
- description: Subnet calculator (IPv4)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-ip-address
- description: Subnet calculator (IPv6)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-ipv6-address
- description: DNS lookup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dns-lookup-domain
- description: SSL/TLS security scan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-security-scan-host
- description: Encode or decode a value
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-encoder-type-value
- description: Binary conversion
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-binary-value
---
