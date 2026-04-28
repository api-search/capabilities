---
categories: []
consumed_apis:
- license-manager
description: Unified workflow capability for Amazon License Manager combining resource management and operations.
layout: capability
name: Amazon License Manager Workflow
operations: []
personas: []
provider_name: Amazon License Manager
provider_slug: amazon-license-manager
search_terms:
- integrates api into applications
- software licensing
- aws
- workflow
- amazon license manager
- unified workflow for amazon license manager resource management
- Administrator
- creates a license configuration.
- gets detailed information about the specified license configuration.
- lists the license configurations for your account.
- license configurations create license configuratio
- manages resources and configurations
- cost management
- compliance
- license configurations get license configuration
- Developer
- license management
- license configurations list license configurations
slug: amazon-license-manager-workflow
tags:
- Amazon License Manager
- AWS
- Workflow
tools:
- description: Creates a license configuration.
  hints:
    idempotent: false
    readOnly: false
  name: license-configurations-create-license-configuratio
- description: Lists the license configurations for your account.
  hints:
    idempotent: true
    readOnly: true
  name: license-configurations-list-license-configurations
- description: Gets detailed information about the specified license configuration.
  hints:
    idempotent: true
    readOnly: true
  name: license-configurations-get-license-configuration
---
