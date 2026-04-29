---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Clearstream Post Trade
operations: []
personas: []
provider_name: Clearstream
provider_slug: clearstream
search_terms:
- settlement
- securities
- post-trade infrastructure
- iso 15022
- swift
- iso 20022
- custody
- collateral management
- capital markets
- financial services
slug: clearstream-post-trade
source_yaml: "# Naftiko capabilities profile for Clearstream post-trade services.\n# Clearstream's developer surface is message-based (SWIFT FIN/FileAct,\n# ISO 15022 MT and ISO 20022 MX) rather than REST. The capabilities below\n# describe high-value verbs that an agent could invoke through\n# ClearstreamXact, Xact via SWIFT, Xact File Transfer, CASCADE, Vestima,\n# and CmaX channels.\nprovider: clearstream\nname: Clearstream\ndescription: >-\n  Capabilities cover settlement instruction, custody account inquiry,\n  corporate-action processing, triparty collateral management, and fund\n  order routing across Clearstream's connectivity products. Messages\n  follow ISO 15022 / ISO 20022 standards.\ncapabilities:\n  - id: clearstream.settlement.instruct\n    name: Instruct settlement\n    description: >-\n      Submit a delivery- or receive-versus-payment / free-of-payment\n      settlement instruction over Xact via SWIFT or Xact File Transfer.\n    api: clearstream:xact-via-swift\n    inputs:\n\
  \      - safekeeping-account\n      - isin\n      - quantity\n      - settlement-date\n      - delivery-type\n      - counterparty-bic\n      - amount\n      - currency\n    outputs:\n      - message-reference\n      - status\n      - matching-status\n\n  - id: clearstream.settlement.status\n    name: Get settlement status\n    description: Retrieve current status of a previously submitted settlement instruction.\n    api: clearstream:xact-via-swift\n    inputs:\n      - message-reference\n      - safekeeping-account\n    outputs:\n      - status\n      - matching-status\n      - settlement-date\n\n  - id: clearstream.custody.holdings\n    name: Get custody holdings\n    description: Retrieve end-of-day or intraday holdings for a custody account.\n    api: clearstream:xact-file-transfer\n    inputs:\n      - safekeeping-account\n      - as-of-date\n    outputs:\n      - holdings\n      - statement-id\n\n  - id: clearstream.corporate-actions.list\n    name: List corporate action notifications\n\
  \    description: Retrieve corporate-action notifications for held positions.\n    api: clearstream:xact-file-transfer\n    inputs:\n      - safekeeping-account\n      - from-date\n      - to-date\n    outputs:\n      - events\n\n  - id: clearstream.corporate-actions.elect\n    name: Submit corporate action election\n    description: Submit a voluntary or choice corporate-action election.\n    api: clearstream:xact-via-swift\n    inputs:\n      - event-id\n      - safekeeping-account\n      - option-code\n      - quantity\n    outputs:\n      - message-reference\n      - status\n\n  - id: clearstream.collateral.allocate\n    name: Allocate triparty collateral\n    description: Allocate or substitute collateral against an exposure in CmaX.\n    api: clearstream:cmax\n    inputs:\n      - exposure-id\n      - collateral-giver\n      - collateral-taker\n      - target-value\n      - eligibility-set\n    outputs:\n      - allocation-id\n      - status\n\n  - id: clearstream.collateral.exposure\n\
  \    name: Get triparty exposure\n    description: Retrieve current value, haircut, and coverage for a triparty exposure.\n    api: clearstream:cmax\n    inputs:\n      - exposure-id\n    outputs:\n      - market-value\n      - haircut\n      - coverage\n\n  - id: clearstream.funds.subscribe\n    name: Submit fund subscription\n    description: Route a fund subscription order via Vestima.\n    api: clearstream:vestima\n    inputs:\n      - isin\n      - investor\n      - amount\n      - currency\n      - trade-date\n    outputs:\n      - order-reference\n      - status\n\n  - id: clearstream.funds.redeem\n    name: Submit fund redemption\n    description: Route a fund redemption order via Vestima.\n    api: clearstream:vestima\n    inputs:\n      - isin\n      - investor\n      - units\n      - trade-date\n    outputs:\n      - order-reference\n      - status\n\n  - id: clearstream.cascade.instruct\n    name: Instruct CASCADE settlement\n    description: Submit a domestic German CSD settlement\
  \ instruction via CASCADE.\n    api: clearstream:cascade\n    inputs:\n      - account\n      - isin\n      - quantity\n      - settlement-date\n      - counterparty\n    outputs:\n      - message-reference\n      - status\n\n  - id: clearstream.reporting.statement\n    name: Retrieve statement\n    description: Pull holding, transaction or fee statements via Xact File Transfer.\n    api: clearstream:xact-file-transfer\n    inputs:\n      - safekeeping-account\n      - statement-type\n      - as-of-date\n      - format\n    outputs:\n      - statement-id\n      - file-uri\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/clearstream/refs/heads/main/capabilities/clearstream-post-trade.yaml
tags: []
tools: []
---
