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
- akamai
- list security configurations
- runtime protection
- api inventory and discovery
- API Security Analyst
- security automation
- real-time api threat detection and blocking
- list all akamai api security configurations
- posture management
- check activation status
- list security policies
- create security configuration
- create a new api security configuration
- list and check status of security configuration activations
- monitors api discovery, threat detection, and posture findings
- api discovery
- threat protection
- api security configuration management
- get api discovery results
- manages api security configurations and activations
- cloud security
- list all api security configurations
- api security configuration and policy management
- list policies
- create a new akamai api security configuration
- Security Engineer
- configuration activations
- list configuration activations
- manage api security configurations and posture
- discover apis
- list security policies within a configuration
- get api inventory including shadow and zombie api findings
- list configurations
- api security
- api posture assessment and vulnerability management
- security policy management
- list activations
- create configuration
- get api discovery
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
