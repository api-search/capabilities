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
- api security configuration and policy management
- manage api security configurations and posture
- list and check status of security configuration activations
- create a new akamai api security configuration
- discover apis
- api discovery
- threat protection
- api inventory and discovery
- real-time api threat detection and blocking
- posture management
- create a new api security configuration
- akamai
- list configurations
- list configuration activations
- security automation
- monitors api discovery, threat detection, and posture findings
- get api discovery
- check activation status
- API Security Analyst
- list security policies
- list security configurations
- Security Engineer
- get api discovery results
- cloud security
- create security configuration
- create configuration
- list policies
- list security policies within a configuration
- configuration activations
- api posture assessment and vulnerability management
- api security
- list activations
- runtime protection
- manages api security configurations and activations
- list all api security configurations
- security policy management
- list all akamai api security configurations
- get api inventory including shadow and zombie api findings
- api security configuration management
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
