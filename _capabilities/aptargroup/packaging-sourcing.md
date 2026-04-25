---
consumed_apis:
- aptar
description: Workflow capability for sourcing dispensing and packaging solutions from AptarGroup. Supports product development teams browsing sustainable packaging options and requesting samples for beauty, pharmaceutical, and food products.
layout: capability
name: AptarGroup Packaging Sourcing
operations: []
personas: []
provider_name: AptarGroup
provider_slug: aptargroup
search_terms:
- manages packaging supplier relationships and sample requests
- manufacturing
- browsing dispensing and packaging product options
- find sustainable packaging
- aptargroup
- finds sustainable dispensing and packaging solutions from aptargroup
- gets detailed specifications for a specific aptargroup packaging product
- requesting and tracking product samples for evaluation
- sustainability
- evaluates and sources packaging solutions for consumer products
- dispensing
- get packaging specs
- browse and sample sustainable packaging solutions from aptargroup
- consumer goods
- order packaging samples
- packaging
- submits a sample request for aptargroup packaging evaluation
- product development
slug: packaging-sourcing
tags:
- AptarGroup
- Packaging
- Product Development
- Sustainability
- Manufacturing
tools:
- description: Finds sustainable dispensing and packaging solutions from AptarGroup
  hints:
    idempotent: true
    readOnly: true
  name: find-sustainable-packaging
- description: Gets detailed specifications for a specific AptarGroup packaging product
  hints:
    idempotent: true
    readOnly: true
  name: get-packaging-specs
- description: Submits a sample request for AptarGroup packaging evaluation
  hints:
    destructive: false
    readOnly: false
  name: order-packaging-samples
---
