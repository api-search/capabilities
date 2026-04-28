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
- lists the license configurations for your account.
- cost management
- gets detailed information about the specified license configuration.
- license management
- software licensing
- workflow
- license configurations list license configurations
- license configurations create license configuratio
- unified workflow for amazon license manager resource management
- aws
- creates a license configuration.
- Developer
- manages resources and configurations
- compliance
- Administrator
- amazon license manager
- license configurations get license configuration
- integrates api into applications
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
