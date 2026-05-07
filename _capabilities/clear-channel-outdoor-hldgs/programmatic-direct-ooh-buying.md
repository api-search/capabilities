---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Programmatic Direct Ooh Buying
operations: []
personas: []
provider_name: Clear Channel Outdoor Holdings
provider_slug: clear-channel-outdoor-hldgs
search_terms:
- programmatic
- out of home
- opendirect
- digital out of home
- advertising
- pdooh
- openrtb
slug: programmatic-direct-ooh-buying
source_filename: programmatic-direct-ooh-buying.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko.io/v1\nkind: Capability\nmetadata:\n  name: programmatic-direct-ooh-buying\n  title: Programmatic-Direct OOH Buying\n  description: >-\n    End-to-end workflow for buying Clear Channel Outdoor digital and static\n    OOH inventory through the CCO.IO Automated Direct API: discover displays\n    and networks, package them as products, build an order with line items,\n    attach creatives, and confirm the booking.\nuses:\n  - shared/clear-channel-outdoor-direct.yaml\nworkflow:\n  - step: discover-inventory\n    operation: search-displays\n    description: Discover digital displays matching campaign criteria (geo, format, resolution).\n  - step: select-network\n    operation: search-network-displays\n    description: Drill into a network and enumerate the screens it contains.\n  - step: build-product\n    operation: search-products\n    description: Locate or define the bookable product backing the chosen displays.\n  - step: get-pricing\n    operation: get-current-quote\n\
  \    description: Retrieve current pricing for the candidate flight.\n  - step: create-order\n    operation: create-order\n    description: Submit the order envelope (advertiser, brand, budget, dates, currency).\n  - step: confirm-order\n    operation: get-order\n    description: Poll the order to confirm APPROVED status.\n  - step: attach-creatives\n    operation: search-creatives-v2\n    description: Verify or attach ad creatives via the v2 creatives endpoint.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/clear-channel-outdoor-hldgs/refs/heads/main/capabilities/programmatic-direct-ooh-buying.yaml
tags: []
tools: []
---
