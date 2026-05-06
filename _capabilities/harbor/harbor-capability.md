---
categories: []
consumed_apis: []
description: The Harbor API enables programmatic access to the Harbor community platform, allowing brands to manage their superfan community, rewards programs, and engagement features. Harbor is a no-code tool that lets brands build owned community platforms where superfans can engage and earn rewards. The API provides endpoints for managing members, challenges, rewards, redemptions, leaderboards, and community events. Authentication uses bearer tokens obtained via OAuth 2.0 client credentials.
layout: capability
name: Harbor API
operations:
- description: Harbor List community members
  method: GET
  name: listmembers
  path: /communities/{communityId}/members
- description: Harbor Create a community member
  method: POST
  name: createmember
  path: /communities/{communityId}/members
- description: Harbor Get a community member
  method: GET
  name: getmember
  path: /communities/{communityId}/members/{memberId}
- description: Harbor Update a community member
  method: PATCH
  name: updatemember
  path: /communities/{communityId}/members/{memberId}
- description: Harbor Award points to a member
  method: POST
  name: awardpoints
  path: /communities/{communityId}/members/{memberId}/points
- description: Harbor List challenges
  method: GET
  name: listchallenges
  path: /communities/{communityId}/challenges
- description: Harbor Create a challenge
  method: POST
  name: createchallenge
  path: /communities/{communityId}/challenges
- description: Harbor Mark a challenge as completed by a member
  method: POST
  name: completechallenge
  path: /communities/{communityId}/challenges/{challengeId}/complete
- description: Harbor List rewards
  method: GET
  name: listrewards
  path: /communities/{communityId}/rewards
- description: Harbor List redemptions
  method: GET
  name: listredemptions
  path: /communities/{communityId}/redemptions
- description: Harbor Create a redemption request
  method: POST
  name: createredemption
  path: /communities/{communityId}/redemptions
- description: Harbor Get community leaderboard
  method: GET
  name: getleaderboard
  path: /communities/{communityId}/leaderboard
- description: Harbor Get community details
  method: GET
  name: getcommunity
  path: /communities/{communityId}
personas: []
provider_name: Harbor
provider_slug: harbor
search_terms:
- harbor create a community member
- getmember
- createredemption
- harbor create a redemption request
- harbor update a community member
- harbor list challenges
- harbor list redemptions
- loyalty
- createmember
- community
- listrewards
- listmembers
- harbor get a community member
- harbor
- harbor get community details
- createchallenge
- harbor create a challenge
- completechallenge
- harbor list rewards
- getcommunity
- listchallenges
- api
- harbor mark a challenge as completed by a member
- engagement
- listredemptions
- harbor award points to a member
- awardpoints
- harbor get community leaderboard
- getleaderboard
- harbor list community members
- superfans
- updatemember
slug: harbor-capability
source_filename: harbor-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Harbor API\n  description: The Harbor API enables programmatic access to the Harbor community platform, allowing brands to manage their\n    superfan community, rewards programs, and engagement features. Harbor is a no-code tool that lets brands build owned community\n    platforms where superfans can engage and earn rewards. The API provides endpoints for managing members, challenges, rewards,\n    redemptions, leaderboards, and community events. Authentication uses bearer tokens obtained via OAuth 2.0 client credentials.\n  tags:\n  - Harbor\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: harbor\n    baseUri: https://api.harbor.gg/v1\n    description: Harbor API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HARBOR_TOKEN}}'\n    resources:\n    - name: communities-communityid-members\n      path: /communities/{communityId}/members\n      operations:\n\
  \      - name: listmembers\n        method: GET\n        description: Harbor List community members\n        inputParameters:\n        - name: tier\n          in: query\n          type: string\n          description: Filter members by loyalty tier name.\n        - name: status\n          in: query\n          type: string\n          description: Filter by member status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmember\n        method: POST\n        description: Harbor Create a community member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: communities-communityid-members-memberid\n      path: /communities/{communityId}/members/{memberId}\n      operations:\n      - name: getmember\n        method: GET\n        description: Harbor Get a community member\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemember\n        method: PATCH\n        description: Harbor Update a community member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: communities-communityid-members-memberid-points\n      path: /communities/{communityId}/members/{memberId}/points\n      operations:\n      - name: awardpoints\n        method: POST\n        description: Harbor Award points to a member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: communities-communityid-challenges\n      path: /communities/{communityId}/challenges\n      operations:\n      - name: listchallenges\n        method: GET\n        description: Harbor List challenges\n        inputParameters:\n        - name: status\n          in: query\n          type:\
  \ string\n          description: Filter by challenge status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchallenge\n        method: POST\n        description: Harbor Create a challenge\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: communities-communityid-challenges-challengeid-c\n      path: /communities/{communityId}/challenges/{challengeId}/complete\n      operations:\n      - name: completechallenge\n        method: POST\n        description: Harbor Mark a challenge as completed by a member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: communities-communityid-rewards\n      path: /communities/{communityId}/rewards\n      operations:\n      - name: listrewards\n        method: GET\n        description:\
  \ Harbor List rewards\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by reward availability status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: communities-communityid-redemptions\n      path: /communities/{communityId}/redemptions\n      operations:\n      - name: listredemptions\n        method: GET\n        description: Harbor List redemptions\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by redemption status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createredemption\n        method: POST\n        description: Harbor Create a redemption request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: communities-communityid-leaderboard\n      path: /communities/{communityId}/leaderboard\n      operations:\n      - name: getleaderboard\n        method: GET\n        description: Harbor Get community leaderboard\n        inputParameters:\n        - name: period\n          in: query\n          type: string\n          description: Time period for leaderboard calculation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: communities-communityid\n      path: /communities/{communityId}\n      operations:\n      - name: getcommunity\n        method: GET\n        description: Harbor Get community details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: harbor-rest\n    description: REST adapter for Harbor API.\n    resources:\n\
  \    - path: /communities/{communityId}/members\n      name: listmembers\n      operations:\n      - method: GET\n        name: listmembers\n        description: Harbor List community members\n        call: harbor.listmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/members\n      name: createmember\n      operations:\n      - method: POST\n        name: createmember\n        description: Harbor Create a community member\n        call: harbor.createmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/members/{memberId}\n      name: getmember\n      operations:\n      - method: GET\n        name: getmember\n        description: Harbor Get a community member\n        call: harbor.getmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/members/{memberId}\n      name: updatemember\n \
  \     operations:\n      - method: PATCH\n        name: updatemember\n        description: Harbor Update a community member\n        call: harbor.updatemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/members/{memberId}/points\n      name: awardpoints\n      operations:\n      - method: POST\n        name: awardpoints\n        description: Harbor Award points to a member\n        call: harbor.awardpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/challenges\n      name: listchallenges\n      operations:\n      - method: GET\n        name: listchallenges\n        description: Harbor List challenges\n        call: harbor.listchallenges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/challenges\n      name: createchallenge\n      operations:\n      - method: POST\n        name: createchallenge\n\
  \        description: Harbor Create a challenge\n        call: harbor.createchallenge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/challenges/{challengeId}/complete\n      name: completechallenge\n      operations:\n      - method: POST\n        name: completechallenge\n        description: Harbor Mark a challenge as completed by a member\n        call: harbor.completechallenge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/rewards\n      name: listrewards\n      operations:\n      - method: GET\n        name: listrewards\n        description: Harbor List rewards\n        call: harbor.listrewards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/redemptions\n      name: listredemptions\n      operations:\n      - method: GET\n        name: listredemptions\n        description: Harbor List\
  \ redemptions\n        call: harbor.listredemptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/redemptions\n      name: createredemption\n      operations:\n      - method: POST\n        name: createredemption\n        description: Harbor Create a redemption request\n        call: harbor.createredemption\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}/leaderboard\n      name: getleaderboard\n      operations:\n      - method: GET\n        name: getleaderboard\n        description: Harbor Get community leaderboard\n        call: harbor.getleaderboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /communities/{communityId}\n      name: getcommunity\n      operations:\n      - method: GET\n        name: getcommunity\n        description: Harbor Get community details\n        call: harbor.getcommunity\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: harbor-mcp\n    transport: http\n    description: MCP adapter for Harbor API for AI agent use.\n    tools:\n    - name: listmembers\n      description: Harbor List community members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor.listmembers\n      with:\n        tier: tools.tier\n        status: tools.status\n      inputParameters:\n      - name: tier\n        type: string\n        description: Filter members by loyalty tier name.\n      - name: status\n        type: string\n        description: Filter by member status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmember\n      description: Harbor Create a community member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor.createmember\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getmember\n      description: Harbor Get a community member\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor.getmember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatemember\n      description: Harbor Update a community member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor.updatemember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: awardpoints\n      description: Harbor Award points to a member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor.awardpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listchallenges\n      description: Harbor List challenges\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ harbor.listchallenges\n      with:\n        status: tools.status\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by challenge status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createchallenge\n      description: Harbor Create a challenge\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor.createchallenge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: completechallenge\n      description: Harbor Mark a challenge as completed by a member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor.completechallenge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrewards\n      description: Harbor List rewards\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor.listrewards\n\
  \      with:\n        status: tools.status\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by reward availability status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listredemptions\n      description: Harbor List redemptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor.listredemptions\n      with:\n        status: tools.status\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by redemption status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createredemption\n      description: Harbor Create a redemption request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harbor.createredemption\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getleaderboard\n      description:\
  \ Harbor Get community leaderboard\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor.getleaderboard\n      with:\n        period: tools.period\n      inputParameters:\n      - name: period\n        type: string\n        description: Time period for leaderboard calculation.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcommunity\n      description: Harbor Get community details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harbor.getcommunity\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HARBOR_TOKEN: HARBOR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/harbor/refs/heads/main/capabilities/harbor-capability.yaml
tags:
- Harbor
- API
tools:
- description: Harbor List community members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmembers
- description: Harbor Create a community member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmember
- description: Harbor Get a community member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmember
- description: Harbor Update a community member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatemember
- description: Harbor Award points to a member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: awardpoints
- description: Harbor List challenges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchallenges
- description: Harbor Create a challenge
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchallenge
- description: Harbor Mark a challenge as completed by a member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completechallenge
- description: Harbor List rewards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrewards
- description: Harbor List redemptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listredemptions
- description: Harbor Create a redemption request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createredemption
- description: Harbor Get community leaderboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getleaderboard
- description: Harbor Get community details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcommunity
---
