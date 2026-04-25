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
- Developer
- Administrator
- amazon license manager
- license configurations list license configurations
- unified workflow for amazon license manager resource management
- cost management
- license configurations create license configuratio
- workflow
- aws
- lists the license configurations for your account.
- license configurations get license configuration
- software licensing
- gets detailed information about the specified license configuration.
- license management
- creates a license configuration.
- manages resources and configurations
- compliance
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
