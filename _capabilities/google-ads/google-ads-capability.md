---
categories: []
consumed_apis: []
description: The Google Ads API is the modern programmatic interface to Google Ads and the next generation of the AdWords API. It enables developers to interact directly with the Google Ads platform, vastly increasing the efficiency of managing large or complex Google Ads accounts and campaigns. The API allows for creating, reading, updating, and removing campaigns, ad groups, ads, keywords, and retrieving performance reports using Google Ads Query Language (GAQL).
layout: capability
name: Google Ads API
operations:
- description: Search Using Google Ads Query Language
  method: POST
  name: searchgoogleads
  path: /v18/customers/{customerId}/googleAds:search
- description: Search Stream Using Google Ads Query Language
  method: POST
  name: searchstreamgoogleads
  path: /v18/customers/{customerId}/googleAds:searchStream
- description: Google Ads Create, Update, or Remove Campaigns
  method: POST
  name: mutatecampaigns
  path: /v18/customers/{customerId}/campaigns:mutate
- description: Google Ads Create, Update, or Remove Ad Groups
  method: POST
  name: mutateadgroups
  path: /v18/customers/{customerId}/adGroups:mutate
- description: Google Ads Create, Update, or Remove Ads
  method: POST
  name: mutateadgroupads
  path: /v18/customers/{customerId}/adGroupAds:mutate
- description: Google Ads Create, Update, or Remove Keywords and Criteria
  method: POST
  name: mutateadgroupcriteria
  path: /v18/customers/{customerId}/adGroupCriteria:mutate
- description: Google Ads Create, Update, or Remove Campaign Budgets
  method: POST
  name: mutatecampaignbudgets
  path: /v18/customers/{customerId}/campaignBudgets:mutate
- description: Google Ads Create, Update, or Remove Bidding Strategies
  method: POST
  name: mutatebiddingstrategies
  path: /v18/customers/{customerId}/biddingStrategies:mutate
- description: Google Ads Get Customer Account Details
  method: GET
  name: getcustomer
  path: /v18/customers/{customerId}
- description: Google Ads List Accessible Customer Accounts
  method: GET
  name: listaccessiblecustomers
  path: /v18/customers:listAccessibleCustomers
personas: []
provider_name: Google Ads
provider_slug: google-ads
search_terms:
- mutateadgroupcriteria
- google ads get customer account details
- marketing
- google
- google ads create, update, or remove campaigns
- searchstreamgoogleads
- google ads list accessible customer accounts
- google ads create, update, or remove keywords and criteria
- google ads create, update, or remove bidding strategies
- mutateadgroups
- google ads create, update, or remove ad groups
- ppc
- getcustomer
- search using google ads query language
- google ads create, update, or remove campaign budgets
- advertising
- api
- mutatecampaignbudgets
- listaccessiblecustomers
- mutatecampaigns
- searchgoogleads
- search stream using google ads query language
- mutatebiddingstrategies
- mutateadgroupads
- ads
- campaign management
- google ads create, update, or remove ads
- digital advertising
slug: google-ads-capability
source_filename: google-ads-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Ads API\n  description: The Google Ads API is the modern programmatic interface to Google Ads and the next generation of the AdWords\n    API. It enables developers to interact directly with the Google Ads platform, vastly increasing the efficiency of managing\n    large or complex Google Ads accounts and campaigns. The API allows for creating, reading, updating, and removing campaigns,\n    ad groups, ads, keywords, and retrieving performance reports using Google Ads Query Language (GAQL).\n  tags:\n  - Google\n  - Ads\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-ads\n    baseUri: https://googleads.googleapis.com\n    description: Google Ads API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ADS_TOKEN}}'\n    resources:\n    - name: v18-customers-customerid-googleads-search\n      path: /v18/customers/{customerId}/googleAds:search\n\
  \      operations:\n      - name: searchgoogleads\n        method: POST\n        description: Search Using Google Ads Query Language\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v18-customers-customerid-googleads-searchstream\n      path: /v18/customers/{customerId}/googleAds:searchStream\n      operations:\n      - name: searchstreamgoogleads\n        method: POST\n        description: Search Stream Using Google Ads Query Language\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v18-customers-customerid-campaigns-mutate\n      path: /v18/customers/{customerId}/campaigns:mutate\n      operations:\n      - name: mutatecampaigns\n        method: POST\n        description: Google Ads Create, Update, or Remove Campaigns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: v18-customers-customerid-adgroups-mutate\n      path: /v18/customers/{customerId}/adGroups:mutate\n      operations:\n      - name: mutateadgroups\n        method: POST\n        description: Google Ads Create, Update, or Remove Ad Groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v18-customers-customerid-adgroupads-mutate\n      path: /v18/customers/{customerId}/adGroupAds:mutate\n      operations:\n      - name: mutateadgroupads\n        method: POST\n        description: Google Ads Create, Update, or Remove Ads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v18-customers-customerid-adgroupcriteria-mutate\n      path: /v18/customers/{customerId}/adGroupCriteria:mutate\n      operations:\n      - name: mutateadgroupcriteria\n        method: POST\n\
  \        description: Google Ads Create, Update, or Remove Keywords and Criteria\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v18-customers-customerid-campaignbudgets-mutate\n      path: /v18/customers/{customerId}/campaignBudgets:mutate\n      operations:\n      - name: mutatecampaignbudgets\n        method: POST\n        description: Google Ads Create, Update, or Remove Campaign Budgets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v18-customers-customerid-biddingstrategies-mutat\n      path: /v18/customers/{customerId}/biddingStrategies:mutate\n      operations:\n      - name: mutatebiddingstrategies\n        method: POST\n        description: Google Ads Create, Update, or Remove Bidding Strategies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: v18-customers-customerid\n      path: /v18/customers/{customerId}\n      operations:\n      - name: getcustomer\n        method: GET\n        description: Google Ads Get Customer Account Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v18-customers-listaccessiblecustomers\n      path: /v18/customers:listAccessibleCustomers\n      operations:\n      - name: listaccessiblecustomers\n        method: GET\n        description: Google Ads List Accessible Customer Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-ads-rest\n    description: REST adapter for Google Ads API.\n    resources:\n    - path: /v18/customers/{customerId}/googleAds:search\n      name: searchgoogleads\n      operations:\n      - method: POST\n\
  \        name: searchgoogleads\n        description: Search Using Google Ads Query Language\n        call: google-ads.searchgoogleads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v18/customers/{customerId}/googleAds:searchStream\n      name: searchstreamgoogleads\n      operations:\n      - method: POST\n        name: searchstreamgoogleads\n        description: Search Stream Using Google Ads Query Language\n        call: google-ads.searchstreamgoogleads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v18/customers/{customerId}/campaigns:mutate\n      name: mutatecampaigns\n      operations:\n      - method: POST\n        name: mutatecampaigns\n        description: Google Ads Create, Update, or Remove Campaigns\n        call: google-ads.mutatecampaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v18/customers/{customerId}/adGroups:mutate\n      name: mutateadgroups\n\
  \      operations:\n      - method: POST\n        name: mutateadgroups\n        description: Google Ads Create, Update, or Remove Ad Groups\n        call: google-ads.mutateadgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v18/customers/{customerId}/adGroupAds:mutate\n      name: mutateadgroupads\n      operations:\n      - method: POST\n        name: mutateadgroupads\n        description: Google Ads Create, Update, or Remove Ads\n        call: google-ads.mutateadgroupads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v18/customers/{customerId}/adGroupCriteria:mutate\n      name: mutateadgroupcriteria\n      operations:\n      - method: POST\n        name: mutateadgroupcriteria\n        description: Google Ads Create, Update, or Remove Keywords and Criteria\n        call: google-ads.mutateadgroupcriteria\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v18/customers/{customerId}/campaignBudgets:mutate\n\
  \      name: mutatecampaignbudgets\n      operations:\n      - method: POST\n        name: mutatecampaignbudgets\n        description: Google Ads Create, Update, or Remove Campaign Budgets\n        call: google-ads.mutatecampaignbudgets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v18/customers/{customerId}/biddingStrategies:mutate\n      name: mutatebiddingstrategies\n      operations:\n      - method: POST\n        name: mutatebiddingstrategies\n        description: Google Ads Create, Update, or Remove Bidding Strategies\n        call: google-ads.mutatebiddingstrategies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v18/customers/{customerId}\n      name: getcustomer\n      operations:\n      - method: GET\n        name: getcustomer\n        description: Google Ads Get Customer Account Details\n        call: google-ads.getcustomer\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v18/customers:listAccessibleCustomers\n      name: listaccessiblecustomers\n      operations:\n      - method: GET\n        name: listaccessiblecustomers\n        description: Google Ads List Accessible Customer Accounts\n        call: google-ads.listaccessiblecustomers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-ads-mcp\n    transport: http\n    description: MCP adapter for Google Ads API for AI agent use.\n    tools:\n    - name: searchgoogleads\n      description: Search Using Google Ads Query Language\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-ads.searchgoogleads\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchstreamgoogleads\n      description: Search Stream Using Google Ads Query Language\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: google-ads.searchstreamgoogleads\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mutatecampaigns\n      description: Google Ads Create, Update, or Remove Campaigns\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-ads.mutatecampaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mutateadgroups\n      description: Google Ads Create, Update, or Remove Ad Groups\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-ads.mutateadgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mutateadgroupads\n      description: Google Ads Create, Update, or Remove Ads\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-ads.mutateadgroupads\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: mutateadgroupcriteria\n      description: Google Ads Create, Update, or Remove Keywords and Criteria\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-ads.mutateadgroupcriteria\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mutatecampaignbudgets\n      description: Google Ads Create, Update, or Remove Campaign Budgets\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-ads.mutatecampaignbudgets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mutatebiddingstrategies\n      description: Google Ads Create, Update, or Remove Bidding Strategies\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-ads.mutatebiddingstrategies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcustomer\n      description:\
  \ Google Ads Get Customer Account Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-ads.getcustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaccessiblecustomers\n      description: Google Ads List Accessible Customer Accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-ads.listaccessiblecustomers\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ADS_TOKEN: GOOGLE_ADS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-ads/refs/heads/main/capabilities/google-ads-capability.yaml
tags:
- Google
- Ads
- API
tools:
- description: Search Using Google Ads Query Language
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchgoogleads
- description: Search Stream Using Google Ads Query Language
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchstreamgoogleads
- description: Google Ads Create, Update, or Remove Campaigns
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mutatecampaigns
- description: Google Ads Create, Update, or Remove Ad Groups
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mutateadgroups
- description: Google Ads Create, Update, or Remove Ads
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mutateadgroupads
- description: Google Ads Create, Update, or Remove Keywords and Criteria
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mutateadgroupcriteria
- description: Google Ads Create, Update, or Remove Campaign Budgets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mutatecampaignbudgets
- description: Google Ads Create, Update, or Remove Bidding Strategies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mutatebiddingstrategies
- description: Google Ads Get Customer Account Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustomer
- description: Google Ads List Accessible Customer Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccessiblecustomers
---
