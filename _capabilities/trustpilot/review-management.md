---
categories: []
consumed_apis:
- trustpilot-business-units
- trustpilot-service-reviews
- trustpilot-invitations
description: Unified review management capability combining business unit profiles, service review management, and invitation workflows. Used by customer experience teams and CRM integrations to monitor reviews, respond to customer feedback, tag and categorize reviews, and automate post-purchase review invitation campaigns.
layout: capability
name: Trustpilot Review Management
operations:
- description: Search for business units by name or domain.
  method: GET
  name: search-business-units
  path: /v1/business-units/search
- description: Get company trust profile including TrustScore and review counts.
  method: GET
  name: get-business-unit-profile
  path: /v1/business-units/{businessUnitId}/profile
- description: Get reviews for a business unit with star and language filtering.
  method: GET
  name: get-reviews
  path: /v1/business-units/{businessUnitId}/reviews
- description: Get details for a specific review.
  method: GET
  name: get-review
  path: /v1/reviews/{reviewId}
- description: Post a company reply to a review.
  method: POST
  name: create-review-reply
  path: /v1/reviews/{reviewId}/reply
- description: Get tags for a review.
  method: GET
  name: get-review-tags
  path: /v1/reviews/{reviewId}/tags
- description: Send review invitations to customers.
  method: POST
  name: send-email-invitations
  path: /v1/invitations/email
- description: Create a unique review invitation link.
  method: POST
  name: create-invitation-link
  path: /v1/invitations/links
- description: Get the most recent reviews in a specific language.
  method: GET
  name: get-latest-reviews
  path: /v1/reviews/latest
personas: []
provider_name: Trustpilot
provider_slug: trustpilot
search_terms:
- get the most recent reviews in a specific language.
- get public reviews for a business with filtering by stars and language.
- remove a company reply from a review.
- send email review invitations to customers after purchase or service delivery.
- get the trustscore, star rating distribution, and contact details for a business.
- create review reply
- invitations
- get review tags
- consumer reviews
- product reviews
- create invitation link
- get available email invitation templates for review requests.
- reviews
- retrieve all reviews for a business using cursor pagination for large review sets.
- latest reviews in a language
- search business units
- get company trust profile including trustscore and review counts.
- search for businesses on trustpilot to find their profile and trust score.
- set tags on a review to categorize it by topic, campaign, or issue type.
- get tags assigned to a review for categorization and filtering.
- get business unit reviews
- get review
- search for business units by name or domain.
- get all business unit reviews
- business unit reviews
- ratings
- customer experience
- get reviews for a business unit with star and language filtering.
- review reply management
- get invitation templates
- send review email invitations
- post a company reply to a review.
- get tags for a review.
- business unit trust profile
- get latest reviews
- business profiles
- get details of a specific trustpilot review including rating, text, and consumer info.
- review tag management
- search trustpilot business units
- delete review reply
- send email invitations
- individual review details
- generate a unique review invitation link to share with customers.
- get business unit profile
- trust
- create review invitation links
- create a unique review invitation link.
- get reviews
- send review invitations to customers.
- post a company reply to a customer review on trustpilot.
- set review tags
- get the most recent reviews in a specific language across trustpilot.
- get details for a specific review.
slug: review-management
source_filename: review-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trustpilot Review Management\"\n  description: >-\n    Unified review management capability combining business unit profiles, service review\n    management, and invitation workflows. Used by customer experience teams and CRM\n    integrations to monitor reviews, respond to customer feedback, tag and categorize\n    reviews, and automate post-purchase review invitation campaigns.\n  tags:\n    - Reviews\n    - Consumer Reviews\n    - Business Profiles\n    - Invitations\n    - Trust\n    - Ratings\n    - Customer Experience\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRUSTPILOT_API_KEY: TRUSTPILOT_API_KEY\n      TRUSTPILOT_OAUTH2_TOKEN: TRUSTPILOT_OAUTH2_TOKEN\n\ncapability:\n  consumes:\n    - import: trustpilot-business-units\n      location: ./shared/business-units.yaml\n    - import: trustpilot-service-reviews\n      location: ./shared/service-reviews.yaml\n    - import:\
  \ trustpilot-invitations\n      location: ./shared/invitations.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: trustpilot-review-management-api\n      description: \"Unified REST API for review monitoring, response, and invitation management.\"\n      resources:\n        - path: /v1/business-units/search\n          name: business-unit-search\n          description: \"Search Trustpilot business units\"\n          operations:\n            - method: GET\n              name: search-business-units\n              description: \"Search for business units by name or domain.\"\n              call: \"trustpilot-business-units.search-business-units\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/business-units/{businessUnitId}/profile\n          name: business-unit-profile\n          description: \"Business unit trust profile\"\n          operations:\n            - method: GET\n              name:\
  \ get-business-unit-profile\n              description: \"Get company trust profile including TrustScore and review counts.\"\n              call: \"trustpilot-business-units.get-business-unit-profile\"\n              with:\n                businessUnitId: \"rest.businessUnitId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/business-units/{businessUnitId}/reviews\n          name: reviews\n          description: \"Business unit reviews\"\n          operations:\n            - method: GET\n              name: get-reviews\n              description: \"Get reviews for a business unit with star and language filtering.\"\n              call: \"trustpilot-business-units.get-business-unit-reviews\"\n              with:\n                businessUnitId: \"rest.businessUnitId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reviews/{reviewId}\n     \
  \     name: review\n          description: \"Individual review details\"\n          operations:\n            - method: GET\n              name: get-review\n              description: \"Get details for a specific review.\"\n              call: \"trustpilot-service-reviews.get-review\"\n              with:\n                reviewId: \"rest.reviewId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reviews/{reviewId}/reply\n          name: review-reply\n          description: \"Review reply management\"\n          operations:\n            - method: POST\n              name: create-review-reply\n              description: \"Post a company reply to a review.\"\n              call: \"trustpilot-service-reviews.create-review-reply\"\n              with:\n                reviewId: \"rest.reviewId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reviews/{reviewId}/tags\n\
  \          name: review-tags\n          description: \"Review tag management\"\n          operations:\n            - method: GET\n              name: get-review-tags\n              description: \"Get tags for a review.\"\n              call: \"trustpilot-service-reviews.get-review-tags\"\n              with:\n                reviewId: \"rest.reviewId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invitations/email\n          name: email-invitations\n          description: \"Send review email invitations\"\n          operations:\n            - method: POST\n              name: send-email-invitations\n              description: \"Send review invitations to customers.\"\n              call: \"trustpilot-invitations.send-email-invitations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invitations/links\n          name: invitation-links\n  \
  \        description: \"Create review invitation links\"\n          operations:\n            - method: POST\n              name: create-invitation-link\n              description: \"Create a unique review invitation link.\"\n              call: \"trustpilot-invitations.create-invitation-link\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reviews/latest\n          name: latest-reviews\n          description: \"Latest reviews in a language\"\n          operations:\n            - method: GET\n              name: get-latest-reviews\n              description: \"Get the most recent reviews in a specific language.\"\n              call: \"trustpilot-service-reviews.get-latest-reviews\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: trustpilot-review-management-mcp\n      transport: http\n      description: \"MCP\
  \ server for AI-assisted review monitoring, response drafting, and invitation management.\"\n      tools:\n        - name: search-business-units\n          description: \"Search for businesses on Trustpilot to find their profile and trust score.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trustpilot-business-units.search-business-units\"\n          with:\n            name: \"tools.name\"\n            country: \"tools.country\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-business-unit-profile\n          description: \"Get the TrustScore, star rating distribution, and contact details for a business.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustpilot-business-units.get-business-unit-profile\"\n          with:\n            businessUnitId: \"tools.businessUnitId\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-business-unit-reviews\n          description: \"Get public reviews for a business with filtering by stars and language.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustpilot-business-units.get-business-unit-reviews\"\n          with:\n            businessUnitId: \"tools.businessUnitId\"\n            stars: \"tools.stars\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-all-business-unit-reviews\n          description: \"Retrieve all reviews for a business using cursor pagination for large review sets.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustpilot-business-units.get-all-business-unit-reviews\"\n          with:\n            businessUnitId: \"tools.businessUnitId\"\n            pageToken: \"tools.pageToken\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-review\n          description: \"Get details of a specific Trustpilot review including rating, text, and consumer info.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustpilot-service-reviews.get-review\"\n          with:\n            reviewId: \"tools.reviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-latest-reviews\n          description: \"Get the most recent reviews in a specific language across Trustpilot.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trustpilot-service-reviews.get-latest-reviews\"\n          with:\n            count: \"tools.count\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-review-reply\n          description:\
  \ \"Post a company reply to a customer review on Trustpilot.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trustpilot-service-reviews.create-review-reply\"\n          with:\n            reviewId: \"tools.reviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-review-reply\n          description: \"Remove a company reply from a review.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"trustpilot-service-reviews.delete-review-reply\"\n          with:\n            reviewId: \"tools.reviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-review-tags\n          description: \"Get tags assigned to a review for categorization and filtering.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"\
  trustpilot-service-reviews.get-review-tags\"\n          with:\n            reviewId: \"tools.reviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-review-tags\n          description: \"Set tags on a review to categorize it by topic, campaign, or issue type.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trustpilot-service-reviews.set-review-tags\"\n          with:\n            reviewId: \"tools.reviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-invitation-templates\n          description: \"Get available email invitation templates for review requests.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustpilot-invitations.get-invitation-templates\"\n          with:\n            businessUnitId: \"tools.businessUnitId\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n        - name: send-email-invitations\n          description: \"Send email review invitations to customers after purchase or service delivery.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trustpilot-invitations.send-email-invitations\"\n          with:\n            businessUnitId: \"tools.businessUnitId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-invitation-link\n          description: \"Generate a unique review invitation link to share with customers.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trustpilot-invitations.create-invitation-link\"\n          with:\n            businessUnitId: \"tools.businessUnitId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trustpilot/refs/heads/main/capabilities/review-management.yaml
tags:
- Reviews
- Consumer Reviews
- Business Profiles
- Invitations
- Trust
- Ratings
- Customer Experience
tools:
- description: Search for businesses on Trustpilot to find their profile and trust score.
  hints:
    openWorld: true
    readOnly: true
  name: search-business-units
- description: Get the TrustScore, star rating distribution, and contact details for a business.
  hints:
    openWorld: false
    readOnly: true
  name: get-business-unit-profile
- description: Get public reviews for a business with filtering by stars and language.
  hints:
    openWorld: false
    readOnly: true
  name: get-business-unit-reviews
- description: Retrieve all reviews for a business using cursor pagination for large review sets.
  hints:
    openWorld: false
    readOnly: true
  name: get-all-business-unit-reviews
- description: Get details of a specific Trustpilot review including rating, text, and consumer info.
  hints:
    openWorld: false
    readOnly: true
  name: get-review
- description: Get the most recent reviews in a specific language across Trustpilot.
  hints:
    openWorld: true
    readOnly: true
  name: get-latest-reviews
- description: Post a company reply to a customer review on Trustpilot.
  hints:
    openWorld: false
    readOnly: false
  name: create-review-reply
- description: Remove a company reply from a review.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-review-reply
- description: Get tags assigned to a review for categorization and filtering.
  hints:
    openWorld: false
    readOnly: true
  name: get-review-tags
- description: Set tags on a review to categorize it by topic, campaign, or issue type.
  hints:
    openWorld: false
    readOnly: false
  name: set-review-tags
- description: Get available email invitation templates for review requests.
  hints:
    openWorld: false
    readOnly: true
  name: get-invitation-templates
- description: Send email review invitations to customers after purchase or service delivery.
  hints:
    openWorld: false
    readOnly: false
  name: send-email-invitations
- description: Generate a unique review invitation link to share with customers.
  hints:
    openWorld: false
    readOnly: false
  name: create-invitation-link
---
