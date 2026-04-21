---
consumed_apis:
- akamai-api-security
description: Unified workflow for managing Akamai API Security configurations, policies, and threat protection. Covers security posture management, API discovery, and configuration activation for security teams.
layout: capability
name: Akamai API Security Management
operations:
- description: List all API security configurations
  method: GET
  name: list-configurations
  path: /v1/configurations
- description: Create a new API security configuration
  method: POST
  name: create-configuration
  path: /v1/configurations
- description: List security policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Get API discovery results
  method: GET
  name: get-api-discovery
  path: /v1/api-discovery
- description: List configuration activations
  method: GET
  name: list-activations
  path: /v1/activations
personas: []
provider_name: Akamai API Security
provider_slug: akamai-api-security
search_terms:
- list all api security configurations
- runtime protection
- list security policies
- monitors api discovery, threat detection, and posture findings
- configuration activations
- list and check status of security configuration activations
- get api discovery
- Security Engineer
- list configurations
- api posture assessment and vulnerability management
- create security configuration
- security policy management
- api security configuration and policy management
- check activation status
- api inventory and discovery
- create a new akamai api security configuration
- posture management
- threat protection
- api security configuration management
- manages api security configurations and activations
- create configuration
- discover apis
- real-time api threat detection and blocking
- list security configurations
- list policies
- list configuration activations
- security automation
- get api inventory including shadow and zombie api findings
- list all akamai api security configurations
- create a new api security configuration
- manage api security configurations and posture
- API Security Analyst
- api security
- get api discovery results
- list security policies within a configuration
- list activations
- api discovery
- akamai
- cloud security
slug: api-security-management
tags:
- Akamai
- API Security
- Posture Management
- Runtime Protection
- Security Automation
tools:
- description: List all Akamai API Security configurations
  hints:
    openWorld: true
    readOnly: true
  name: list-security-configurations
- description: Create a new Akamai API Security configuration
  hints:
    destructive: false
    readOnly: false
  name: create-security-configuration
- description: List security policies within a configuration
  hints:
    openWorld: true
    readOnly: true
  name: list-security-policies
- description: Get API inventory including shadow and zombie API findings
  hints:
    openWorld: true
    readOnly: true
  name: discover-apis
- description: List and check status of security configuration activations
  hints:
    openWorld: true
    readOnly: true
  name: check-activation-status
---
