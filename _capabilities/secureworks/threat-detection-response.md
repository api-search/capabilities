---
categories: []
consumed_apis:
- taegis-xdr
description: Unified threat detection and response capability for the Secureworks Taegis XDR platform. Enables SOC analysts and security engineers to query alerts, manage investigations, monitor endpoint assets, and enrich findings with threat intelligence across the entire Taegis security telemetry pipeline.
layout: capability
name: Secureworks Taegis Threat Detection and Response
operations:
- description: Query security alerts with GraphQL filters
  method: POST
  name: query-alerts
  path: /v1/alerts
- description: Query security investigations
  method: POST
  name: query-investigations
  path: /v1/investigations
- description: Query endpoint assets and agents
  method: POST
  name: query-endpoint-assets
  path: /v1/assets
- description: Query threat intelligence data
  method: POST
  name: query-threat-intelligence
  path: /v1/threat-intelligence
personas: []
provider_name: Secureworks
provider_slug: secureworks
search_terms:
- query the endpoint asset inventory including hostname, ip addresses, os, agent version, and isolation status
- incident response
- query active and closed security investigations in taegis xdr including priority, status, and assigned alerts
- query security alerts with graphql filters
- security alert queries
- query investigations
- query endpoint assets
- threat intelligence
- xdr
- endpoint asset inventory
- cybersecurity
- query threat intelligence indicators (ips, domains, urls, file hashes) for malicious activity assessment
- threat detection
- query security investigations
- mdr
- query security alerts from taegis xdr including severity, status, mitre technique, and affected assets
- query threat intelligence data
- security operations
- investigation management
- create investigation
- query xdr alerts
- query threat intelligence
- query alerts
- create a new security investigation in taegis xdr to track and coordinate incident response
- query endpoint assets and agents
- threat intelligence indicators
slug: threat-detection-response
source_filename: threat-detection-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Secureworks Taegis Threat Detection and Response\"\n  description: >-\n    Unified threat detection and response capability for the Secureworks Taegis XDR\n    platform. Enables SOC analysts and security engineers to query alerts, manage\n    investigations, monitor endpoint assets, and enrich findings with threat intelligence\n    across the entire Taegis security telemetry pipeline.\n  tags:\n    - XDR\n    - Threat Detection\n    - Incident Response\n    - Security Operations\n    - Cybersecurity\n    - MDR\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      TAEGIS_CLIENT_ID: TAEGIS_CLIENT_ID\n      TAEGIS_CLIENT_SECRET: TAEGIS_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: taegis-xdr\n      location: ./shared/taegis-xdr.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: threat-detection-api\n      description: \"Unified REST API for Secureworks\
  \ Taegis threat detection and response.\"\n      resources:\n        - path: /v1/alerts\n          name: alerts\n          description: \"Security alert queries\"\n          operations:\n            - method: POST\n              name: query-alerts\n              description: \"Query security alerts with GraphQL filters\"\n              call: \"taegis-xdr.query-alerts\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/investigations\n          name: investigations\n          description: \"Investigation management\"\n          operations:\n            - method: POST\n              name: query-investigations\n              description: \"Query security investigations\"\n              call: \"taegis-xdr.query-investigations\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/assets\n          name: endpoint-assets\n          description: \"Endpoint asset inventory\"\n          operations:\n            - method: POST\n              name: query-endpoint-assets\n              description: \"Query endpoint assets and agents\"\n              call: \"taegis-xdr.query-endpoint-assets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/threat-intelligence\n          name: threat-intelligence\n          description: \"Threat intelligence indicators\"\n          operations:\n            - method: POST\n              name: query-threat-intelligence\n              description: \"Query threat intelligence data\"\n              call: \"taegis-xdr.query-threat-intelligence\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: threat-detection-mcp\n      transport: http\n\
  \      description: \"MCP server for AI-assisted threat detection and response with Secureworks Taegis XDR.\"\n      tools:\n        - name: query-xdr-alerts\n          description: \"Query security alerts from Taegis XDR including severity, status, MITRE technique, and affected assets\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"taegis-xdr.query-alerts\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-investigations\n          description: \"Query active and closed security investigations in Taegis XDR including priority, status, and assigned alerts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"taegis-xdr.query-investigations\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-investigation\n          description: \"Create a new security investigation in Taegis XDR to track and coordinate incident response\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"taegis-xdr.mutate-investigation\"\n          with:\n            mutation: \"tools.mutation\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-endpoint-assets\n          description: \"Query the endpoint asset inventory including hostname, IP addresses, OS, agent version, and isolation status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"taegis-xdr.query-endpoint-assets\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-threat-intelligence\n          description: \"Query threat intelligence indicators (IPs, domains, URLs, file hashes) for malicious activity assessment\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"taegis-xdr.query-threat-intelligence\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/secureworks/refs/heads/main/capabilities/threat-detection-response.yaml
tags:
- XDR
- Threat Detection
- Incident Response
- Security Operations
- Cybersecurity
- MDR
tools:
- description: Query security alerts from Taegis XDR including severity, status, MITRE technique, and affected assets
  hints:
    openWorld: false
    readOnly: true
  name: query-xdr-alerts
- description: Query active and closed security investigations in Taegis XDR including priority, status, and assigned alerts
  hints:
    openWorld: false
    readOnly: true
  name: query-investigations
- description: Create a new security investigation in Taegis XDR to track and coordinate incident response
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-investigation
- description: Query the endpoint asset inventory including hostname, IP addresses, OS, agent version, and isolation status
  hints:
    openWorld: false
    readOnly: true
  name: query-endpoint-assets
- description: Query threat intelligence indicators (IPs, domains, URLs, file hashes) for malicious activity assessment
  hints:
    openWorld: false
    readOnly: true
  name: query-threat-intelligence
---
