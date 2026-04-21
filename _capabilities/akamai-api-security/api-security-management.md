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
- list all akamai api security configurations
- check activation status
- list configuration activations
- api inventory and discovery
- api security
- Security Engineer
- list configurations
- configuration activations
- posture management
- api discovery
- API Security Analyst
- security policy management
- create configuration
- create a new akamai api security configuration
- list security policies
- real-time api threat detection and blocking
- manage api security configurations and posture
- list activations
- get api inventory including shadow and zombie api findings
- api posture assessment and vulnerability management
- api security configuration management
- create a new api security configuration
- cloud security
- get api discovery results
- monitors api discovery, threat detection, and posture findings
- get api discovery
- list security policies within a configuration
- list all api security configurations
- runtime protection
- akamai
- security automation
- threat protection
- list policies
- create security configuration
- list and check status of security configuration activations
- manages api security configurations and activations
- discover apis
- api security configuration and policy management
- list security configurations
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
