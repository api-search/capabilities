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
- unified workflow for amazon license manager resource management
- cost management
- workflow
- license configurations create license configuratio
- license management
- license configurations list license configurations
- aws
- Administrator
- license configurations get license configuration
- software licensing
- manages resources and configurations
- integrates api into applications
- compliance
- gets detailed information about the specified license configuration.
- amazon license manager
- Developer
- lists the license configurations for your account.
- creates a license configuration.
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
