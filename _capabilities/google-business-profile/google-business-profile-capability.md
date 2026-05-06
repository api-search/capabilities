---
categories: []
consumed_apis: []
description: The Google Business Profile API provides an interface for managing business location information on Google. It enables developers to programmatically manage accounts, locations, reviews, media, posts, and more.
layout: capability
name: Google Business Profile API
operations:
- description: Google Business Profile List Accounts
  method: GET
  name: listaccounts
  path: /accounts
- description: Google Business Profile Get Account
  method: GET
  name: getaccount
  path: /accounts/{accountId}
- description: Google Business Profile List Locations
  method: GET
  name: listlocations
  path: /accounts/{accountId}/locations
- description: Google Business Profile Create Location
  method: POST
  name: createlocation
  path: /accounts/{accountId}/locations
- description: Google Business Profile Get Location
  method: GET
  name: getlocation
  path: /accounts/{accountId}/locations/{locationId}
- description: Google Business Profile Update Location
  method: PATCH
  name: updatelocation
  path: /accounts/{accountId}/locations/{locationId}
- description: Google Business Profile Delete Location
  method: DELETE
  name: deletelocation
  path: /accounts/{accountId}/locations/{locationId}
- description: Google Business Profile List Reviews
  method: GET
  name: listreviews
  path: /accounts/{accountId}/locations/{locationId}/reviews
- description: Google Business Profile Reply to Review
  method: PUT
  name: replytoreview
  path: /accounts/{accountId}/locations/{locationId}/reviews/{reviewId}/reply
- description: Google Business Profile List Media
  method: GET
  name: listmedia
  path: /accounts/{accountId}/locations/{locationId}/media
- description: Google Business Profile List Local Posts
  method: GET
  name: listlocalposts
  path: /accounts/{accountId}/locations/{locationId}/localPosts
- description: Google Business Profile Create Local Post
  method: POST
  name: createlocalpost
  path: /accounts/{accountId}/locations/{locationId}/localPosts
personas: []
provider_name: Google Business Profile
provider_slug: google-business-profile
search_terms:
- updatelocation
- listaccounts
- google business profile list accounts
- listreviews
- listmedia
- google business profile get location
- google business profile create location
- local business
- google
- business
- getaccount
- locations
- google business profile list media
- getlocation
- google business profile list locations
- google business profile reply to review
- createlocalpost
- createlocation
- api
- listlocalposts
- google business profile update location
- listlocations
- replytoreview
- profile
- google business profile list local posts
- business profiles
- google business profile create local post
- google business profile get account
- reviews
- google business profile list reviews
- deletelocation
- google business profile delete location
slug: google-business-profile-capability
source_filename: google-business-profile-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Business Profile API\n  description: The Google Business Profile API provides an interface for managing business location information on Google.\n    It enables developers to programmatically manage accounts, locations, reviews, media, posts, and more.\n  tags:\n  - Google\n  - Business\n  - Profile\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-business-profile\n    baseUri: https://mybusiness.googleapis.com/v4\n    description: Google Business Profile API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_BUSINESS_PROFILE_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      operations:\n      - name: listaccounts\n        method: GET\n        description: Google Business Profile List Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: accounts-accountid\n      path: /accounts/{accountId}\n      operations:\n      - name: getaccount\n        method: GET\n        description: Google Business Profile Get Account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-locations\n      path: /accounts/{accountId}/locations\n      operations:\n      - name: listlocations\n        method: GET\n        description: Google Business Profile List Locations\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlocation\n        method: POST\n        description: Google\
  \ Business Profile Create Location\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-locations-locationid\n      path: /accounts/{accountId}/locations/{locationId}\n      operations:\n      - name: getlocation\n        method: GET\n        description: Google Business Profile Get Location\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: locationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelocation\n        method: PATCH\n        description: Google Business Profile Update Location\n        inputParameters:\n\
  \        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: locationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelocation\n        method: DELETE\n        description: Google Business Profile Delete Location\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: locationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-locations-locationid-reviews\n      path: /accounts/{accountId}/locations/{locationId}/reviews\n      operations:\n      - name: listreviews\n        method: GET\n        description:\
  \ Google Business Profile List Reviews\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: locationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-locations-locationid-reviews-\n      path: /accounts/{accountId}/locations/{locationId}/reviews/{reviewId}/reply\n      operations:\n      - name: replytoreview\n        method: PUT\n        description: Google Business Profile Reply to Review\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: locationId\n          in: path\n          type: string\n          required: true\n        - name: reviewId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-locations-locationid-media\n      path: /accounts/{accountId}/locations/{locationId}/media\n      operations:\n      - name: listmedia\n        method: GET\n        description: Google Business Profile List Media\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: locationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-locations-locationid-localpos\n      path: /accounts/{accountId}/locations/{locationId}/localPosts\n      operations:\n      - name: listlocalposts\n        method: GET\n        description: Google Business Profile List Local Posts\n        inputParameters:\n        - name:\
  \ accountId\n          in: path\n          type: string\n          required: true\n        - name: locationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlocalpost\n        method: POST\n        description: Google Business Profile Create Local Post\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: locationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-business-profile-rest\n    description: REST adapter for Google Business Profile API.\n    resources:\n    - path: /accounts\n      name: listaccounts\n      operations:\n\
  \      - method: GET\n        name: listaccounts\n        description: Google Business Profile List Accounts\n        call: google-business-profile.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Google Business Profile Get Account\n        call: google-business-profile.getaccount\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/locations\n      name: listlocations\n      operations:\n      - method: GET\n        name: listlocations\n        description: Google Business Profile List Locations\n        call: google-business-profile.listlocations\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/locations\n\
  \      name: createlocation\n      operations:\n      - method: POST\n        name: createlocation\n        description: Google Business Profile Create Location\n        call: google-business-profile.createlocation\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/locations/{locationId}\n      name: getlocation\n      operations:\n      - method: GET\n        name: getlocation\n        description: Google Business Profile Get Location\n        call: google-business-profile.getlocation\n        with:\n          accountId: rest.accountId\n          locationId: rest.locationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/locations/{locationId}\n      name: updatelocation\n      operations:\n      - method: PATCH\n        name: updatelocation\n        description: Google Business Profile Update Location\n        call:\
  \ google-business-profile.updatelocation\n        with:\n          accountId: rest.accountId\n          locationId: rest.locationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/locations/{locationId}\n      name: deletelocation\n      operations:\n      - method: DELETE\n        name: deletelocation\n        description: Google Business Profile Delete Location\n        call: google-business-profile.deletelocation\n        with:\n          accountId: rest.accountId\n          locationId: rest.locationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/locations/{locationId}/reviews\n      name: listreviews\n      operations:\n      - method: GET\n        name: listreviews\n        description: Google Business Profile List Reviews\n        call: google-business-profile.listreviews\n        with:\n          accountId: rest.accountId\n          locationId: rest.locationId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/locations/{locationId}/reviews/{reviewId}/reply\n      name: replytoreview\n      operations:\n      - method: PUT\n        name: replytoreview\n        description: Google Business Profile Reply to Review\n        call: google-business-profile.replytoreview\n        with:\n          accountId: rest.accountId\n          locationId: rest.locationId\n          reviewId: rest.reviewId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/locations/{locationId}/media\n      name: listmedia\n      operations:\n      - method: GET\n        name: listmedia\n        description: Google Business Profile List Media\n        call: google-business-profile.listmedia\n        with:\n          accountId: rest.accountId\n          locationId: rest.locationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /accounts/{accountId}/locations/{locationId}/localPosts\n      name: listlocalposts\n      operations:\n      - method: GET\n        name: listlocalposts\n        description: Google Business Profile List Local Posts\n        call: google-business-profile.listlocalposts\n        with:\n          accountId: rest.accountId\n          locationId: rest.locationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/locations/{locationId}/localPosts\n      name: createlocalpost\n      operations:\n      - method: POST\n        name: createlocalpost\n        description: Google Business Profile Create Local Post\n        call: google-business-profile.createlocalpost\n        with:\n          accountId: rest.accountId\n          locationId: rest.locationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-business-profile-mcp\n    transport: http\n    description:\
  \ MCP adapter for Google Business Profile API for AI agent use.\n    tools:\n    - name: listaccounts\n      description: Google Business Profile List Accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-business-profile.listaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccount\n      description: Google Business Profile Get Account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-business-profile.getaccount\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlocations\n      description: Google Business Profile List Locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: google-business-profile.listlocations\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlocation\n      description: Google Business Profile Create Location\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-business-profile.createlocation\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlocation\n      description: Google Business Profile Get Location\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-business-profile.getlocation\n\
  \      with:\n        accountId: tools.accountId\n        locationId: tools.locationId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: locationId\n        type: string\n        description: locationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatelocation\n      description: Google Business Profile Update Location\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-business-profile.updatelocation\n      with:\n        accountId: tools.accountId\n        locationId: tools.locationId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: locationId\n        type: string\n        description: locationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: deletelocation\n      description: Google Business Profile Delete Location\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-business-profile.deletelocation\n      with:\n        accountId: tools.accountId\n        locationId: tools.locationId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: locationId\n        type: string\n        description: locationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreviews\n      description: Google Business Profile List Reviews\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-business-profile.listreviews\n      with:\n        accountId: tools.accountId\n        locationId: tools.locationId\n      inputParameters:\n      - name: accountId\n        type: string\n\
  \        description: accountId\n        required: true\n      - name: locationId\n        type: string\n        description: locationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replytoreview\n      description: Google Business Profile Reply to Review\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-business-profile.replytoreview\n      with:\n        accountId: tools.accountId\n        locationId: tools.locationId\n        reviewId: tools.reviewId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: locationId\n        type: string\n        description: locationId\n        required: true\n      - name: reviewId\n        type: string\n        description: reviewId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmedia\n\
  \      description: Google Business Profile List Media\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-business-profile.listmedia\n      with:\n        accountId: tools.accountId\n        locationId: tools.locationId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: locationId\n        type: string\n        description: locationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlocalposts\n      description: Google Business Profile List Local Posts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-business-profile.listlocalposts\n      with:\n        accountId: tools.accountId\n        locationId: tools.locationId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n\
  \        required: true\n      - name: locationId\n        type: string\n        description: locationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlocalpost\n      description: Google Business Profile Create Local Post\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-business-profile.createlocalpost\n      with:\n        accountId: tools.accountId\n        locationId: tools.locationId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: locationId\n        type: string\n        description: locationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_BUSINESS_PROFILE_TOKEN: GOOGLE_BUSINESS_PROFILE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-business-profile/refs/heads/main/capabilities/google-business-profile-capability.yaml
tags:
- Google
- Business
- Profile
- API
tools:
- description: Google Business Profile List Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Google Business Profile Get Account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Google Business Profile List Locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocations
- description: Google Business Profile Create Location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlocation
- description: Google Business Profile Get Location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocation
- description: Google Business Profile Update Location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatelocation
- description: Google Business Profile Delete Location
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelocation
- description: Google Business Profile List Reviews
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreviews
- description: Google Business Profile Reply to Review
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replytoreview
- description: Google Business Profile List Media
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmedia
- description: Google Business Profile List Local Posts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocalposts
- description: Google Business Profile Create Local Post
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlocalpost
---
