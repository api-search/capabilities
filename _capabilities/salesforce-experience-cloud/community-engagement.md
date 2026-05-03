---
categories: []
consumed_apis:
- exp-cloud-communities
- exp-cloud-cms
description: Workflow capability for community engagement within Salesforce Experience Cloud. Combines social feeds, topics, and CMS content delivery for community managers and digital experience developers building customer portals and partner communities.
layout: capability
name: Salesforce Experience Cloud Community Engagement
operations:
- description: Get the news feed for a community.
  method: GET
  name: get-news-feed
  path: /v1/communities/{communityId}/feed
- description: Post to the community feed.
  method: POST
  name: post-feed-element
  path: /v1/communities/{communityId}/feed
- description: List community topics.
  method: GET
  name: list-topics
  path: /v1/communities/{communityId}/topics
- description: Create a new community topic.
  method: POST
  name: create-topic
  path: /v1/communities/{communityId}/topics
- description: List CMS content for delivery.
  method: GET
  name: list-delivery-content
  path: /v1/cms/delivery/content
personas: []
provider_name: Salesforce Experience Cloud
provider_slug: salesforce-experience-cloud
search_terms:
- create topic
- cms content delivery for headless frontends.
- get community news feed
- list delivery content
- post to community feed
- feeds
- topics
- chatter
- community social feed.
- retrieve the latest news feed posts for an experience cloud community.
- customer portal
- create community topic
- communities
- create a new discussion topic in an experience cloud community.
- engagement
- community topics.
- list community topics.
- post a message or content to an experience cloud community feed.
- crm
- list discussion topics in an experience cloud community.
- list cms content for delivery
- digital experience
- list community topics
- partner portal
- cms
- create a new community topic.
- list topics
- post feed element
- headless cms
- content delivery
- list cms content items for delivery to headless frontend applications.
- experience cloud
- social
- get news feed
- post to the community feed.
- list cms content for delivery.
- salesforce experience cloud
- get the news feed for a community.
slug: community-engagement
source_filename: community-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Experience Cloud Community Engagement\"\n  description: >-\n    Workflow capability for community engagement within Salesforce Experience Cloud.\n    Combines social feeds, topics, and CMS content delivery for community managers\n    and digital experience developers building customer portals and partner communities.\n  tags:\n    - Chatter\n    - Communities\n    - Content Delivery\n    - Engagement\n    - Feeds\n    - Headless CMS\n    - Salesforce Experience Cloud\n    - Social\n    - Topics\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_OAUTH2_TOKEN: SALESFORCE_OAUTH2_TOKEN\n      SALESFORCE_INSTANCE_URL: SALESFORCE_INSTANCE_URL\n\ncapability:\n  consumes:\n    - import: exp-cloud-communities\n      location: ./shared/connect-communities-api.yaml\n    - import: exp-cloud-cms\n      location: ./shared/cms-connect-api.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8081\n      namespace: exp-cloud-community-engagement-api\n      description: \"Unified REST API for Experience Cloud community engagement.\"\n      resources:\n        - path: /v1/communities/{communityId}/feed\n          name: community-feed\n          description: \"Community social feed.\"\n          operations:\n            - method: GET\n              name: get-news-feed\n              description: \"Get the news feed for a community.\"\n              call: \"exp-cloud-communities.get-news-feed\"\n              with:\n                communityId: \"rest.communityId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: post-feed-element\n              description: \"Post to the community feed.\"\n              call: \"exp-cloud-communities.post-feed-element\"\n              with:\n                communityId: \"rest.communityId\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n        - path: /v1/communities/{communityId}/topics\n          name: community-topics\n          description: \"Community topics.\"\n          operations:\n            - method: GET\n              name: list-topics\n              description: \"List community topics.\"\n              call: \"exp-cloud-communities.list-topics\"\n              with:\n                communityId: \"rest.communityId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-topic\n              description: \"Create a new community topic.\"\n              call: \"exp-cloud-communities.create-topic\"\n              with:\n                communityId: \"rest.communityId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cms/delivery/content\n          name: cms-delivery-content\n\
  \          description: \"CMS content delivery for headless frontends.\"\n          operations:\n            - method: GET\n              name: list-delivery-content\n              description: \"List CMS content for delivery.\"\n              call: \"exp-cloud-cms.list-contents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: exp-cloud-community-engagement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Experience Cloud community engagement.\"\n      tools:\n        - name: get-community-news-feed\n          description: \"Retrieve the latest news feed posts for an Experience Cloud community.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"exp-cloud-communities.get-news-feed\"\n          with:\n            communityId: \"tools.communityId\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n        - name: post-to-community-feed\n          description: \"Post a message or content to an Experience Cloud community feed.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"exp-cloud-communities.post-feed-element\"\n          with:\n            communityId: \"tools.communityId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-community-topics\n          description: \"List discussion topics in an Experience Cloud community.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"exp-cloud-communities.list-topics\"\n          with:\n            communityId: \"tools.communityId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-community-topic\n          description: \"Create a new discussion topic in an Experience Cloud community.\"\n     \
  \     hints:\n            readOnly: false\n            destructive: false\n          call: \"exp-cloud-communities.create-topic\"\n          with:\n            communityId: \"tools.communityId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cms-content-for-delivery\n          description: \"List CMS content items for delivery to headless frontend applications.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"exp-cloud-cms.list-contents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-experience-cloud/refs/heads/main/capabilities/community-engagement.yaml
tags:
- Chatter
- Communities
- Content Delivery
- Engagement
- Feeds
- Headless CMS
- Salesforce Experience Cloud
- Social
- Topics
tools:
- description: Retrieve the latest news feed posts for an Experience Cloud community.
  hints:
    idempotent: true
    readOnly: true
  name: get-community-news-feed
- description: Post a message or content to an Experience Cloud community feed.
  hints:
    destructive: false
    readOnly: false
  name: post-to-community-feed
- description: List discussion topics in an Experience Cloud community.
  hints:
    idempotent: true
    readOnly: true
  name: list-community-topics
- description: Create a new discussion topic in an Experience Cloud community.
  hints:
    destructive: false
    readOnly: false
  name: create-community-topic
- description: List CMS content items for delivery to headless frontend applications.
  hints:
    idempotent: true
    readOnly: true
  name: list-cms-content-for-delivery
---
