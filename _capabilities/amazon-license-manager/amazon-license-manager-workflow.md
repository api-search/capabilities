---
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
- aws
- manages resources and configurations
- software licensing
- Developer
- license configurations get license configuration
- compliance
- unified workflow for amazon license manager resource management
- license management
- license configurations list license configurations
- creates a license configuration.
- amazon license manager
- Administrator
- lists the license configurations for your account.
- gets detailed information about the specified license configuration.
- cost management
- workflow
- integrates api into applications
- license configurations create license configuratio
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
