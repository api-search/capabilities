---
categories: []
consumed_apis: []
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
- list community topics
- get community news feed
- social
- list topics
- digital experience
- community topics.
- create a new community topic.
- post to community feed
- feeds
- create topic
- retrieve the latest news feed posts for an experience cloud community.
- community social feed.
- post feed element
- cms content delivery for headless frontends.
- communities
- customer portal
- post a message or content to an experience cloud community feed.
- list cms content for delivery
- post to the community feed.
- headless cms
- content delivery
- crm
- partner portal
- list cms content items for delivery to headless frontend applications.
- list delivery content
- experience cloud
- create community topic
- engagement
- create a new discussion topic in an experience cloud community.
- salesforce experience cloud
- list community topics.
- topics
- cms
- chatter
- get the news feed for a community.
- list discussion topics in an experience cloud community.
- list cms content for delivery.
- get news feed
slug: community-engagement
source_filename: community-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Experience Cloud Community Engagement\n  description: Workflow capability for community engagement within Salesforce Experience Cloud. Combines social feeds, topics,\n    and CMS content delivery for community managers and digital experience developers building customer portals and partner\n    communities.\n  tags:\n  - Chatter\n  - Communities\n  - Content Delivery\n  - Engagement\n  - Feeds\n  - Headless CMS\n  - Salesforce Experience Cloud\n  - Social\n  - Topics\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_OAUTH2_TOKEN: SALESFORCE_OAUTH2_TOKEN\n    SALESFORCE_INSTANCE_URL: SALESFORCE_INSTANCE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: exp-cloud-communities\n    baseUri: '{{env.SALESFORCE_INSTANCE_URL}}/services/data/v59.0/connect/communities'\n    description: Salesforce Experience Cloud Connect Communities REST API.\n    authentication:\n     \
  \ type: bearer\n      token: '{{env.SALESFORCE_OAUTH2_TOKEN}}'\n    resources:\n    - name: feeds\n      path: /{communityId}/chatter/feeds/news\n      description: Community news feeds.\n      operations:\n      - name: get-news-feed\n        method: GET\n        description: Get the news feed for a community.\n        inputParameters:\n        - name: communityId\n          in: path\n          type: string\n          required: true\n          description: Community ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: feed\n          type: object\n          value: $.\n      - name: post-feed-element\n        method: POST\n        description: Post a feed element (text post, link, question).\n        inputParameters:\n        - name: communityId\n          in: path\n          type: string\n          required: true\n          description: Community ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: feedElement\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            body:\n              messageSegments: '{{tools.messageSegments}}'\n            feedElementType: '{{tools.feedElementType}}'\n    - name: topics\n      path: /{communityId}/chatter/topics\n      description: Community topics.\n      operations:\n      - name: list-topics\n        method: GET\n        description: List topics in a community.\n        inputParameters:\n        - name: communityId\n          in: path\n          type: string\n          required: true\n          description: Community ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: topics\n          type: object\n          value: $.\n      - name: create-topic\n        method: POST\n        description: Create a new community topic.\n        inputParameters:\n        - name: communityId\n          in: path\n          type: string\n          required: true\n          description: Community ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: topic\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n  - type: http\n    namespace: exp-cloud-cms\n    baseUri: '{{env.SALESFORCE_INSTANCE_URL}}/services/data/v59.0/connect/cms'\n    description: Salesforce CMS Connect API for content management.\n    authentication:\n      type: bearer\n      token: '{{env.SALESFORCE_OAUTH2_TOKEN}}'\n    resources:\n    - name: channels\n      path: /channels\n      description: CMS content delivery channels.\n      operations:\n      - name: list-channels\n        method: GET\n        description: List all CMS channels.\n        outputRawFormat: json\n        outputParameters:\n        - name: channels\n          type: object\n          value: $.\n      - name: get-channel\n        method: GET\n        description: Get a CMS channel by ID.\n        inputParameters:\n\
  \        - name: channelId\n          in: path\n          type: string\n          required: true\n          description: CMS channel ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: channel\n          type: object\n          value: $.\n    - name: contents\n      path: /contents\n      description: CMS content items.\n      operations:\n      - name: list-contents\n        method: GET\n        description: List CMS content items.\n        outputRawFormat: json\n        outputParameters:\n        - name: contents\n          type: object\n          value: $.\n      - name: create-content\n        method: POST\n        description: Create a new CMS content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: content\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            contentType: '{{tools.contentType}}'\n            body: '{{tools.body}}'\n\
  \      - name: get-content\n        method: GET\n        description: Get a CMS content item by ID.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Content ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: content\n          type: object\n          value: $.\n      - name: update-content\n        method: PATCH\n        description: Update a CMS content item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Content ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: content\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            body: '{{tools.body}}'\n      - name: publish-content\n        method: POST\n        description: Publish a CMS content\
  \ item.\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Content ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: exp-cloud-community-engagement-api\n    description: Unified REST API for Experience Cloud community engagement.\n    resources:\n    - path: /v1/communities/{communityId}/feed\n      name: community-feed\n      description: Community social feed.\n      operations:\n      - method: GET\n        name: get-news-feed\n        description: Get the news feed for a community.\n        call: exp-cloud-communities.get-news-feed\n        with:\n          communityId: rest.communityId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: post-feed-element\n        description: Post to the community\
  \ feed.\n        call: exp-cloud-communities.post-feed-element\n        with:\n          communityId: rest.communityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/communities/{communityId}/topics\n      name: community-topics\n      description: Community topics.\n      operations:\n      - method: GET\n        name: list-topics\n        description: List community topics.\n        call: exp-cloud-communities.list-topics\n        with:\n          communityId: rest.communityId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-topic\n        description: Create a new community topic.\n        call: exp-cloud-communities.create-topic\n        with:\n          communityId: rest.communityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cms/delivery/content\n      name: cms-delivery-content\n      description: CMS content delivery for\
  \ headless frontends.\n      operations:\n      - method: GET\n        name: list-delivery-content\n        description: List CMS content for delivery.\n        call: exp-cloud-cms.list-contents\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: exp-cloud-community-engagement-mcp\n    transport: http\n    description: MCP server for AI-assisted Experience Cloud community engagement.\n    tools:\n    - name: get-community-news-feed\n      description: Retrieve the latest news feed posts for an Experience Cloud community.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: exp-cloud-communities.get-news-feed\n      with:\n        communityId: tools.communityId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-to-community-feed\n      description: Post a message or content to an Experience Cloud community feed.\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n      call: exp-cloud-communities.post-feed-element\n      with:\n        communityId: tools.communityId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-community-topics\n      description: List discussion topics in an Experience Cloud community.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: exp-cloud-communities.list-topics\n      with:\n        communityId: tools.communityId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-community-topic\n      description: Create a new discussion topic in an Experience Cloud community.\n      hints:\n        readOnly: false\n        destructive: false\n      call: exp-cloud-communities.create-topic\n      with:\n        communityId: tools.communityId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cms-content-for-delivery\n      description: List CMS content items for delivery to headless frontend\
  \ applications.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: exp-cloud-cms.list-contents\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
