---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Pdooh Rtb Supply
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
slug: pdooh-rtb-supply
source_filename: pdooh-rtb-supply.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko.io/v1\nkind: Capability\nmetadata:\n  name: pdooh-rtb-supply\n  title: pDOOH RTB Supply (DSP-Mediated)\n  description: >-\n    Programmatic Digital-Out-of-Home buying against Clear Channel Outdoor\n    inventory through DSP partner integrations using OpenRTB 2.6 with the\n    DOOH object extension. CCO does not expose RTB endpoints publicly; buyers\n    transact via DSPs that connect to CCO/SSP partners. This capability\n    documents the OpenRTB DOOH bid-request shape and venue taxonomy expected.\nexternalProtocol:\n  name: OpenRTB 2.6 DOOH\n  specification: https://github.com/InteractiveAdvertisingBureau/openrtb2.x/blob/main/2.6.md\n  schema: ../json-schema/clear-channel-outdoor-hldgs-openrtb-dooh-schema.json\n  taxonomy:\n    name: OpenOOH Venue Taxonomy\n    venuetypetax: 1\ndspPartners:\n  - Adelphic\n  - Adform\n  - Adomni\n  - AdQuick\n  - Campsite\n  - Displayce\n  - Google DV360\n  - Hivestack\n  - Nexxen\n  - OneView\n  - OutMoove\n  - Pulsepoint\n\
  \  - Quotient\n  - Simplifi\n  - Sito\n  - StackAdapt\n  - The Trade Desk\n  - Vistar Media\n  - Xandr\n  - Yahoo\n  - Zeta\naudienceData:\n  name: RADAR\n  description: Clear Channel Outdoor's first-party audience and attribution data suite based on aggregated mobile location data.\n  url: https://clearchanneloutdoor.com/radar-data-solutions/\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/clear-channel-outdoor-hldgs/refs/heads/main/capabilities/pdooh-rtb-supply.yaml
tags: []
tools: []
---
