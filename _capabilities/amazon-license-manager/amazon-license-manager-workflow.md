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
- license configurations create license configuratio
- amazon license manager
- creates a license configuration.
- license configurations get license configuration
- license management
- workflow
- aws
- Administrator
- software licensing
- unified workflow for amazon license manager resource management
- license configurations list license configurations
- manages resources and configurations
- compliance
- integrates api into applications
- lists the license configurations for your account.
- cost management
- Developer
- gets detailed information about the specified license configuration.
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
