---
api_specs:
- filename: safeline-management-openapi.yml
  format: yaml
  label: safeline
  slug: safeline
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/safeline/refs/heads/main/openapi/safeline-management-openapi.yml
categories: []
consumed_apis:
- safeline
description: Unified workflow for managing web application firewall protection including website configuration, ACL rules, SSL certificates, security policies, and attack event analysis. Used by security engineers and IT admins to protect web applications.
layout: capability
name: SafeLine WAF Protection Management
operations:
- description: List all websites protected by SafeLine WAF
  method: GET
  name: list-websites
  path: /v1/websites
- description: Add a new website to WAF protection
  method: POST
  name: create-website
  path: /v1/websites
- description: Enable or disable WAF protection for a specific website
  method: POST
  name: toggle-website-protection
  path: /v1/websites/toggle
- description: List SSL certificates configured in SafeLine
  method: GET
  name: list-ssl-certificates
  path: /v1/ssl-certificates
- description: List traffic ACL rules
  method: GET
  name: list-acl-rules
  path: /v1/acl-rules
- description: Create a new ACL rule
  method: POST
  name: create-acl-rule
  path: /v1/acl-rules
- description: List whitelisted IP addresses
  method: GET
  name: list-acl-whitelist
  path: /v1/acl-whitelist
- description: Add IP or CIDR to whitelist
  method: POST
  name: add-to-acl-whitelist
  path: /v1/acl-whitelist
- description: List security policy groups
  method: GET
  name: list-policy-groups
  path: /v1/policy-groups
- description: Create a security policy group
  method: POST
  name: create-policy-group
  path: /v1/policy-groups
- description: Get security reports
  method: GET
  name: get-report-results
  path: /v1/reports
- description: Get ACL rule execution logs
  method: GET
  name: get-acl-execution-logs
  path: /v1/acl-logs
- description: Get SafeLine node system information
  method: GET
  name: get-node-info
  path: /v1/system/node
personas: []
provider_name: SafeLine
provider_slug: safeline
search_terms:
- security policy groups
- web application firewall
- acl rule execution logs
- add to acl whitelist
- create a new api token for safeline management automation
- list policy groups
- add ip or cidr to whitelist
- get security reports
- create a new acl rule
- create website
- api gateway
- get acl rule execution logs
- waf
- list all web applications protected by safeline waf with their configuration
- open source
- get safeline system node information including cpu, memory, and version
- reverse proxy
- list all websites protected by safeline waf
- toggle website protection
- list all ssl/tls certificates managed by safeline
- add a new website to waf protection
- get safeline node system information
- list access control rules for blocking or allowing specific traffic patterns
- security
- list api tokens for programmatic access to safeline management
- list ssl certificates
- add an ip address or cidr block to the acl whitelist
- list security policy groups with their rule counts
- enable or disable waf protection for a specific website
- list api tokens
- security reports
- list whitelisted ip addresses
- ssl certificate management
- acl
- access control list rules
- list acl whitelist
- create a new acl rule to block or allow traffic based on ip, url, or headers
- create acl rule
- list traffic acl rules
- list ip addresses and cidr blocks in the acl whitelist
- get acl execution logs
- add a new web application to safeline waf protection
- list websites
- list acl rules
- create policy group
- list security policy groups
- get node info
- enable or disable website protection
- protected website management
- create a security policy group
- create api token
- list ssl certificates configured in safeline
- get logs of triggered acl rules showing blocked/allowed requests and source ips
- create a new security policy group for organizing waf rules
- get generated security reports showing attack statistics and traffic analysis
- system information
- get report results
- acl whitelist management
- proxy
slug: waf-protection-management
source_filename: waf-protection-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SafeLine WAF Protection Management\"\n  description: \"Unified workflow for managing web application firewall protection including website configuration, ACL rules, SSL certificates, security policies, and attack event analysis. Used by security engineers and IT admins to protect web applications.\"\n  tags:\n    - WAF\n    - Security\n    - Web Application Firewall\n    - Open Source\n    - Reverse Proxy\n    - ACL\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAFELINE_API_TOKEN: SAFELINE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: safeline\n      location: ./shared/safeline-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: waf-protection-api\n      description: \"Unified REST API for SafeLine WAF protection management.\"\n      resources:\n        - path: /v1/websites\n          name: websites\n          description: \"Protected\
  \ website management\"\n          operations:\n            - method: GET\n              name: list-websites\n              description: \"List all websites protected by SafeLine WAF\"\n              call: \"safeline.list-websites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-website\n              description: \"Add a new website to WAF protection\"\n              call: \"safeline.create-website\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/websites/toggle\n          name: website-protection\n          description: \"Enable or disable website protection\"\n          operations:\n            - method: POST\n              name: toggle-website-protection\n              description: \"Enable or disable WAF protection for a specific website\"\n              call: \"safeline.toggle-website-protection\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ssl-certificates\n          name: ssl-certificates\n          description: \"SSL certificate management\"\n          operations:\n            - method: GET\n              name: list-ssl-certificates\n              description: \"List SSL certificates configured in SafeLine\"\n              call: \"safeline.list-ssl-certificates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/acl-rules\n          name: acl-rules\n          description: \"Access control list rules\"\n          operations:\n            - method: GET\n              name: list-acl-rules\n              description: \"List traffic ACL rules\"\n              call: \"safeline.list-acl-rules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n           \
  \   name: create-acl-rule\n              description: \"Create a new ACL rule\"\n              call: \"safeline.create-acl-rule\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/acl-whitelist\n          name: acl-whitelist\n          description: \"ACL whitelist management\"\n          operations:\n            - method: GET\n              name: list-acl-whitelist\n              description: \"List whitelisted IP addresses\"\n              call: \"safeline.list-acl-whitelist\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-to-acl-whitelist\n              description: \"Add IP or CIDR to whitelist\"\n              call: \"safeline.add-to-acl-whitelist\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/policy-groups\n          name: policy-groups\n\
  \          description: \"Security policy groups\"\n          operations:\n            - method: GET\n              name: list-policy-groups\n              description: \"List security policy groups\"\n              call: \"safeline.list-policy-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-policy-group\n              description: \"Create a security policy group\"\n              call: \"safeline.create-policy-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reports\n          name: security-reports\n          description: \"Security reports\"\n          operations:\n            - method: GET\n              name: get-report-results\n              description: \"Get security reports\"\n              call: \"safeline.get-report-results\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/acl-logs\n          name: acl-execution-logs\n          description: \"ACL rule execution logs\"\n          operations:\n            - method: GET\n              name: get-acl-execution-logs\n              description: \"Get ACL rule execution logs\"\n              call: \"safeline.get-acl-execution-logs\"\n              with:\n                page: \"rest.page\"\n                start_time: \"rest.start_time\"\n                end_time: \"rest.end_time\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/system/node\n          name: node-info\n          description: \"System information\"\n          operations:\n            - method: GET\n              name: get-node-info\n              description: \"Get SafeLine node system information\"\n              call: \"safeline.get-node-info\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: waf-protection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WAF protection management and security configuration.\"\n      tools:\n        - name: list-websites\n          description: \"List all web applications protected by SafeLine WAF with their configuration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"safeline.list-websites\"\n          with:\n            page: \"tools.page\"\n            page_size: \"tools.page_size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-website\n          description: \"Add a new web application to SafeLine WAF protection\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"safeline.create-website\"\n          with:\n            name: \"tools.name\"\
  \n            upstream: \"tools.upstream\"\n            ports: \"tools.ports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: toggle-website-protection\n          description: \"Enable or disable WAF protection for a specific website\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"safeline.toggle-website-protection\"\n          with:\n            id: \"tools.id\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ssl-certificates\n          description: \"List all SSL/TLS certificates managed by SafeLine\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"safeline.list-ssl-certificates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-acl-rules\n\
  \          description: \"List access control rules for blocking or allowing specific traffic patterns\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"safeline.list-acl-rules\"\n          with:\n            page: \"tools.page\"\n            page_size: \"tools.page_size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-acl-rule\n          description: \"Create a new ACL rule to block or allow traffic based on IP, URL, or headers\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"safeline.create-acl-rule\"\n          with:\n            name: \"tools.name\"\n            action: \"tools.action\"\n            conditions: \"tools.conditions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-acl-whitelist\n          description: \"List IP\
  \ addresses and CIDR blocks in the ACL whitelist\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"safeline.list-acl-whitelist\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-to-acl-whitelist\n          description: \"Add an IP address or CIDR block to the ACL whitelist\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"safeline.add-to-acl-whitelist\"\n          with:\n            ip: \"tools.ip\"\n            comment: \"tools.comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-policy-groups\n          description: \"List security policy groups with their rule counts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"safeline.list-policy-groups\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n\n        - name: create-policy-group\n          description: \"Create a new security policy group for organizing WAF rules\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"safeline.create-policy-group\"\n          with:\n            name: \"tools.name\"\n            comment: \"tools.comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-report-results\n          description: \"Get generated security reports showing attack statistics and traffic analysis\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"safeline.get-report-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-acl-execution-logs\n          description: \"Get logs of triggered ACL rules showing blocked/allowed requests\
  \ and source IPs\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"safeline.get-acl-execution-logs\"\n          with:\n            page: \"tools.page\"\n            page_size: \"tools.page_size\"\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-node-info\n          description: \"Get SafeLine system node information including CPU, memory, and version\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"safeline.get-node-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-tokens\n          description: \"List API tokens for programmatic access to SafeLine management\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"safeline.list-api-tokens\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-api-token\n          description: \"Create a new API token for SafeLine management automation\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"safeline.create-api-token\"\n          with:\n            comment: \"tools.comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/safeline/refs/heads/main/capabilities/waf-protection-management.yaml
tags:
- WAF
- Security
- Web Application Firewall
- Open Source
- Reverse Proxy
- ACL
tools:
- description: List all web applications protected by SafeLine WAF with their configuration
  hints:
    openWorld: false
    readOnly: true
  name: list-websites
- description: Add a new web application to SafeLine WAF protection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-website
- description: Enable or disable WAF protection for a specific website
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: toggle-website-protection
- description: List all SSL/TLS certificates managed by SafeLine
  hints:
    openWorld: false
    readOnly: true
  name: list-ssl-certificates
- description: List access control rules for blocking or allowing specific traffic patterns
  hints:
    openWorld: false
    readOnly: true
  name: list-acl-rules
- description: Create a new ACL rule to block or allow traffic based on IP, URL, or headers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-acl-rule
- description: List IP addresses and CIDR blocks in the ACL whitelist
  hints:
    openWorld: false
    readOnly: true
  name: list-acl-whitelist
- description: Add an IP address or CIDR block to the ACL whitelist
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: add-to-acl-whitelist
- description: List security policy groups with their rule counts
  hints:
    openWorld: false
    readOnly: true
  name: list-policy-groups
- description: Create a new security policy group for organizing WAF rules
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-policy-group
- description: Get generated security reports showing attack statistics and traffic analysis
  hints:
    openWorld: false
    readOnly: true
  name: get-report-results
- description: Get logs of triggered ACL rules showing blocked/allowed requests and source IPs
  hints:
    openWorld: false
    readOnly: true
  name: get-acl-execution-logs
- description: Get SafeLine system node information including CPU, memory, and version
  hints:
    openWorld: false
    readOnly: true
  name: get-node-info
- description: List API tokens for programmatic access to SafeLine management
  hints:
    openWorld: false
    readOnly: true
  name: list-api-tokens
- description: Create a new API token for SafeLine management automation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-token
---
