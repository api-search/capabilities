---
categories: []
consumed_apis: []
description: The Litmus Email Analytics API provides REST endpoints for retrieving email campaign engagement metrics including read rates, deletion rates, device types, email clients, geographic data, and forwarding activity. Campaign data is accessed by GUID and returns detailed activity summary reports. Analytics data is collected via a tracking pixel embedded in sent emails and the API surfaces aggregated engagement breakdowns.
layout: capability
name: Litmus Email Analytics API
operations:
- description: Litmus List campaigns
  method: GET
  name: listcampaigns
  path: /campaigns
- description: Litmus Create a campaign
  method: POST
  name: createcampaign
  path: /campaigns
- description: Litmus Get a campaign
  method: GET
  name: getcampaign
  path: /campaigns/{campaignGuid}
- description: Litmus Delete a campaign
  method: DELETE
  name: deletecampaign
  path: /campaigns/{campaignGuid}
- description: Litmus Get campaign engagement summary
  method: GET
  name: getcampaignsummary
  path: /campaigns/{campaignGuid}/summary
- description: Litmus Get campaign email client breakdown
  method: GET
  name: getcampaignclientbreakdown
  path: /campaigns/{campaignGuid}/clients
- description: Litmus Get campaign geographic breakdown
  method: GET
  name: getcampaigngeobreakdown
  path: /campaigns/{campaignGuid}/geo
- description: Litmus Get campaign device breakdown
  method: GET
  name: getcampaigndevicebreakdown
  path: /campaigns/{campaignGuid}/devices
- description: Litmus Get campaign read time distribution
  method: GET
  name: getcampaignreadtimes
  path: /campaigns/{campaignGuid}/read-times
personas: []
provider_name: Litmus
provider_slug: litmus
search_terms:
- litmus get campaign read time distribution
- quality assurance
- litmus get a campaign
- litmus delete a campaign
- getcampaigngeobreakdown
- api
- createcampaign
- litmus
- getcampaigndevicebreakdown
- litmus list campaigns
- getcampaignsummary
- marketing tools
- getcampaignclientbreakdown
- getcampaign
- developer tools
- litmus get campaign engagement summary
- litmus create a campaign
- listcampaigns
- getcampaignreadtimes
- deletecampaign
- litmus get campaign email client breakdown
- litmus get campaign device breakdown
- litmus get campaign geographic breakdown
- email testing
slug: litmus-capability
source_filename: litmus-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Litmus Email Analytics API\n  description: The Litmus Email Analytics API provides REST endpoints for retrieving email campaign engagement metrics including\n    read rates, deletion rates, device types, email clients, geographic data, and forwarding activity. Campaign data is accessed\n    by GUID and returns detailed activity summary reports. Analytics data is collected via a tracking pixel embedded in sent\n    emails and the API surfaces aggregated engagement breakdowns.\n  tags:\n  - Litmus\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: litmus\n    baseUri: https://analytics-api.litmus.com/api/v1\n    description: Litmus Email Analytics API HTTP API.\n    authentication:\n      type: basic\n      username: '{{LITMUS_USERNAME}}'\n      password: '{{LITMUS_PASSWORD}}'\n    resources:\n    - name: campaigns\n      path: /campaigns\n      operations:\n      - name:\
  \ listcampaigns\n        method: GET\n        description: Litmus List campaigns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcampaign\n        method: POST\n        description: Litmus Create a campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns-campaignguid\n      path: /campaigns/{campaignGuid}\n      operations:\n      - name: getcampaign\n        method: GET\n        description: Litmus Get a campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecampaign\n        method: DELETE\n        description: Litmus Delete a campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns-campaignguid-summary\n\
  \      path: /campaigns/{campaignGuid}/summary\n      operations:\n      - name: getcampaignsummary\n        method: GET\n        description: Litmus Get campaign engagement summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns-campaignguid-clients\n      path: /campaigns/{campaignGuid}/clients\n      operations:\n      - name: getcampaignclientbreakdown\n        method: GET\n        description: Litmus Get campaign email client breakdown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns-campaignguid-geo\n      path: /campaigns/{campaignGuid}/geo\n      operations:\n      - name: getcampaigngeobreakdown\n        method: GET\n        description: Litmus Get campaign geographic breakdown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: campaigns-campaignguid-devices\n      path: /campaigns/{campaignGuid}/devices\n      operations:\n      - name: getcampaigndevicebreakdown\n        method: GET\n        description: Litmus Get campaign device breakdown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns-campaignguid-read-times\n      path: /campaigns/{campaignGuid}/read-times\n      operations:\n      - name: getcampaignreadtimes\n        method: GET\n        description: Litmus Get campaign read time distribution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: litmus-rest\n    description: REST adapter for Litmus Email Analytics API.\n    resources:\n    - path: /campaigns\n      name: listcampaigns\n      operations:\n      - method: GET\n        name:\
  \ listcampaigns\n        description: Litmus List campaigns\n        call: litmus.listcampaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaigns\n      name: createcampaign\n      operations:\n      - method: POST\n        name: createcampaign\n        description: Litmus Create a campaign\n        call: litmus.createcampaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaigns/{campaignGuid}\n      name: getcampaign\n      operations:\n      - method: GET\n        name: getcampaign\n        description: Litmus Get a campaign\n        call: litmus.getcampaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaigns/{campaignGuid}\n      name: deletecampaign\n      operations:\n      - method: DELETE\n        name: deletecampaign\n        description: Litmus Delete a campaign\n        call: litmus.deletecampaign\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /campaigns/{campaignGuid}/summary\n      name: getcampaignsummary\n      operations:\n      - method: GET\n        name: getcampaignsummary\n        description: Litmus Get campaign engagement summary\n        call: litmus.getcampaignsummary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaigns/{campaignGuid}/clients\n      name: getcampaignclientbreakdown\n      operations:\n      - method: GET\n        name: getcampaignclientbreakdown\n        description: Litmus Get campaign email client breakdown\n        call: litmus.getcampaignclientbreakdown\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaigns/{campaignGuid}/geo\n      name: getcampaigngeobreakdown\n      operations:\n      - method: GET\n        name: getcampaigngeobreakdown\n        description: Litmus Get campaign geographic breakdown\n        call: litmus.getcampaigngeobreakdown\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /campaigns/{campaignGuid}/devices\n      name: getcampaigndevicebreakdown\n      operations:\n      - method: GET\n        name: getcampaigndevicebreakdown\n        description: Litmus Get campaign device breakdown\n        call: litmus.getcampaigndevicebreakdown\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaigns/{campaignGuid}/read-times\n      name: getcampaignreadtimes\n      operations:\n      - method: GET\n        name: getcampaignreadtimes\n        description: Litmus Get campaign read time distribution\n        call: litmus.getcampaignreadtimes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: litmus-mcp\n    transport: http\n    description: MCP adapter for Litmus Email Analytics API for AI agent use.\n    tools:\n    - name: listcampaigns\n      description: Litmus List campaigns\n      hints:\n     \
  \   readOnly: true\n        destructive: false\n        idempotent: true\n      call: litmus.listcampaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcampaign\n      description: Litmus Create a campaign\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: litmus.createcampaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcampaign\n      description: Litmus Get a campaign\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: litmus.getcampaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecampaign\n      description: Litmus Delete a campaign\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: litmus.deletecampaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcampaignsummary\n\
  \      description: Litmus Get campaign engagement summary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: litmus.getcampaignsummary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcampaignclientbreakdown\n      description: Litmus Get campaign email client breakdown\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: litmus.getcampaignclientbreakdown\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcampaigngeobreakdown\n      description: Litmus Get campaign geographic breakdown\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: litmus.getcampaigngeobreakdown\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcampaigndevicebreakdown\n      description: Litmus Get campaign device breakdown\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: litmus.getcampaigndevicebreakdown\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcampaignreadtimes\n      description: Litmus Get campaign read time distribution\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: litmus.getcampaignreadtimes\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LITMUS_USERNAME: LITMUS_USERNAME\n    LITMUS_PASSWORD: LITMUS_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/litmus/refs/heads/main/capabilities/litmus-capability.yaml
tags:
- Litmus
- API
tools:
- description: Litmus List campaigns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcampaigns
- description: Litmus Create a campaign
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcampaign
- description: Litmus Get a campaign
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampaign
- description: Litmus Delete a campaign
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecampaign
- description: Litmus Get campaign engagement summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampaignsummary
- description: Litmus Get campaign email client breakdown
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampaignclientbreakdown
- description: Litmus Get campaign geographic breakdown
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampaigngeobreakdown
- description: Litmus Get campaign device breakdown
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampaigndevicebreakdown
- description: Litmus Get campaign read time distribution
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampaignreadtimes
---
