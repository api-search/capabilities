---
categories:
- analytics
consumed_apis:
- campaign-manager
description: Unified workflow for managing digital advertising campaigns, ads, placements, and performance reports. Used by ad operations specialists and digital marketers.
layout: capability
name: Google Campaign Manager Campaign Management
operations:
- description: List campaigns.
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a campaign.
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: Get campaign details.
  method: GET
  name: get-campaign
  path: /v1/campaigns/{id}
- description: Update a campaign.
  method: PUT
  name: update-campaign
  path: /v1/campaigns/{id}
- description: List ads.
  method: GET
  name: list-ads
  path: /v1/ads
- description: Create an ad.
  method: POST
  name: create-ad
  path: /v1/ads
- description: Get ad details.
  method: GET
  name: get-ad
  path: /v1/ads/{id}
- description: Update an ad.
  method: PUT
  name: update-ad
  path: /v1/ads/{id}
- description: List placements.
  method: GET
  name: list-placements
  path: /v1/placements
- description: Create a placement.
  method: POST
  name: create-placement
  path: /v1/placements
- description: Get placement details.
  method: GET
  name: get-placement
  path: /v1/placements/{id}
- description: Update a placement.
  method: PUT
  name: update-placement
  path: /v1/placements/{id}
- description: Generate ad tags for placements.
  method: POST
  name: generate-placement-tags
  path: /v1/placement-tags
- description: List reports.
  method: GET
  name: list-reports
  path: /v1/reports
- description: Create a report.
  method: POST
  name: create-report
  path: /v1/reports
- description: Get report details.
  method: GET
  name: get-report
  path: /v1/reports/{id}
- description: Update a report.
  method: PUT
  name: update-report
  path: /v1/reports/{id}
- description: Delete a report.
  method: DELETE
  name: delete-report
  path: /v1/reports/{id}
- description: Run a report.
  method: POST
  name: run-report
  path: /v1/reports/{id}/run
personas: []
provider_name: Google Campaign Manager
provider_slug: google-campaign-manager
search_terms:
- get ad details by id.
- individual campaign management.
- update report
- get campaign details.
- list ads.
- placement management.
- delete a report.
- campaign management.
- get report details.
- list campaigns.
- advertising
- update placement
- generate placement tags
- create a new report.
- create a placement.
- create a new ad.
- create an ad.
- list advertising campaigns.
- list ad placements.
- update an ad.
- update a report.
- campaign management
- individual ad management.
- generate ad tags for placements.
- google
- create report
- list placements
- update an existing placement.
- report execution.
- ad management.
- create ad
- create a report.
- create a new advertising campaign.
- get campaign
- list ads
- digital marketing
- placement tag generation.
- update a placement.
- individual report management.
- create placement
- create campaign
- delete report
- get ad details.
- analytics
- report management.
- update campaign
- run a report to generate results.
- get ad
- get placement details.
- get report
- run a report.
- list reports
- update an existing campaign.
- list placements.
- update ad
- get report details by id.
- update a campaign.
- get campaign details by id.
- individual placement management.
- reporting
- update an existing report.
- update an existing ad.
- create a campaign.
- run report
- create a new placement.
- get placement
- get placement details by id.
- list campaigns
- list reports.
slug: campaign-management
source_filename: campaign-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Campaign Manager Campaign Management\"\n  description: \"Unified workflow for managing digital advertising campaigns, ads, placements, and performance reports. Used by ad operations specialists and digital marketers.\"\n  tags:\n    - Google\n    - Advertising\n    - Campaign Management\n    - Reporting\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_OAUTH2_TOKEN: GOOGLE_OAUTH2_TOKEN\n\ncapability:\n  consumes:\n    - import: campaign-manager\n      location: ./shared/campaign-manager-360.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: campaign-management-api\n      description: \"Unified REST API for Google Campaign Manager 360 campaign management.\"\n      resources:\n        - path: /v1/campaigns\n          name: campaigns\n          description: \"Campaign management.\"\n          operations:\n            - method: GET\n          \
  \    name: list-campaigns\n              description: \"List campaigns.\"\n              call: \"campaign-manager.list-campaigns\"\n              with:\n                profileId: \"rest.profileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-campaign\n              description: \"Create a campaign.\"\n              call: \"campaign-manager.create-campaign\"\n              with:\n                profileId: \"rest.profileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/campaigns/{id}\n          name: campaign-details\n          description: \"Individual campaign management.\"\n          operations:\n            - method: GET\n              name: get-campaign\n              description: \"Get campaign details.\"\n              call: \"campaign-manager.get-campaign\"\n              with:\n             \
  \   profileId: \"rest.profileId\"\n                campaignId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-campaign\n              description: \"Update a campaign.\"\n              call: \"campaign-manager.update-campaign\"\n              with:\n                profileId: \"rest.profileId\"\n                campaignId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ads\n          name: ads\n          description: \"Ad management.\"\n          operations:\n            - method: GET\n              name: list-ads\n              description: \"List ads.\"\n              call: \"campaign-manager.list-ads\"\n              with:\n                profileId: \"rest.profileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n           \
  \ - method: POST\n              name: create-ad\n              description: \"Create an ad.\"\n              call: \"campaign-manager.create-ad\"\n              with:\n                profileId: \"rest.profileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ads/{id}\n          name: ad-details\n          description: \"Individual ad management.\"\n          operations:\n            - method: GET\n              name: get-ad\n              description: \"Get ad details.\"\n              call: \"campaign-manager.get-ad\"\n              with:\n                profileId: \"rest.profileId\"\n                adId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-ad\n              description: \"Update an ad.\"\n              call: \"campaign-manager.update-ad\"\n              with:\n                profileId:\
  \ \"rest.profileId\"\n                adId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/placements\n          name: placements\n          description: \"Placement management.\"\n          operations:\n            - method: GET\n              name: list-placements\n              description: \"List placements.\"\n              call: \"campaign-manager.list-placements\"\n              with:\n                profileId: \"rest.profileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-placement\n              description: \"Create a placement.\"\n              call: \"campaign-manager.create-placement\"\n              with:\n                profileId: \"rest.profileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/placements/{id}\n\
  \          name: placement-details\n          description: \"Individual placement management.\"\n          operations:\n            - method: GET\n              name: get-placement\n              description: \"Get placement details.\"\n              call: \"campaign-manager.get-placement\"\n              with:\n                profileId: \"rest.profileId\"\n                placementId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-placement\n              description: \"Update a placement.\"\n              call: \"campaign-manager.update-placement\"\n              with:\n                profileId: \"rest.profileId\"\n                placementId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/placement-tags\n          name: placement-tags\n          description: \"Placement tag generation.\"\
  \n          operations:\n            - method: POST\n              name: generate-placement-tags\n              description: \"Generate ad tags for placements.\"\n              call: \"campaign-manager.generate-placement-tags\"\n              with:\n                profileId: \"rest.profileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"Report management.\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List reports.\"\n              call: \"campaign-manager.list-reports\"\n              with:\n                profileId: \"rest.profileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-report\n              description: \"Create a report.\"\n              call: \"campaign-manager.create-report\"\
  \n              with:\n                profileId: \"rest.profileId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{id}\n          name: report-details\n          description: \"Individual report management.\"\n          operations:\n            - method: GET\n              name: get-report\n              description: \"Get report details.\"\n              call: \"campaign-manager.get-report\"\n              with:\n                profileId: \"rest.profileId\"\n                reportId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-report\n              description: \"Update a report.\"\n              call: \"campaign-manager.update-report\"\n              with:\n                profileId: \"rest.profileId\"\n                reportId: \"rest.id\"\n              outputParameters:\n    \
  \            - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-report\n              description: \"Delete a report.\"\n              call: \"campaign-manager.delete-report\"\n              with:\n                profileId: \"rest.profileId\"\n                reportId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{id}/run\n          name: report-run\n          description: \"Report execution.\"\n          operations:\n            - method: POST\n              name: run-report\n              description: \"Run a report.\"\n              call: \"campaign-manager.run-report\"\n              with:\n                profileId: \"rest.profileId\"\n                reportId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: campaign-management-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted campaign management and reporting.\"\n      tools:\n        - name: list-campaigns\n          description: \"List advertising campaigns.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campaign-manager.list-campaigns\"\n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-campaign\n          description: \"Get campaign details by ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campaign-manager.get-campaign\"\n          with:\n            profileId: \"tools.profileId\"\n            campaignId: \"tools.campaignId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-campaign\n          description: \"Create a new advertising campaign.\"\n       \
  \   hints:\n            readOnly: false\n          call: \"campaign-manager.create-campaign\"\n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-campaign\n          description: \"Update an existing campaign.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"campaign-manager.update-campaign\"\n          with:\n            profileId: \"tools.profileId\"\n            campaignId: \"tools.campaignId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ads\n          description: \"List ads.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campaign-manager.list-ads\"\n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n    \
  \    - name: get-ad\n          description: \"Get ad details by ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campaign-manager.get-ad\"\n          with:\n            profileId: \"tools.profileId\"\n            adId: \"tools.adId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-ad\n          description: \"Create a new ad.\"\n          hints:\n            readOnly: false\n          call: \"campaign-manager.create-ad\"\n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-ad\n          description: \"Update an existing ad.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"campaign-manager.update-ad\"\n          with:\n            profileId: \"tools.profileId\"\n            adId: \"tools.adId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-placements\n          description: \"List ad placements.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campaign-manager.list-placements\"\n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-placement\n          description: \"Get placement details by ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campaign-manager.get-placement\"\n          with:\n            profileId: \"tools.profileId\"\n            placementId: \"tools.placementId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-placement\n          description: \"Create a new placement.\"\n          hints:\n            readOnly: false\n          call: \"campaign-manager.create-placement\"\
  \n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-placement\n          description: \"Update an existing placement.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"campaign-manager.update-placement\"\n          with:\n            profileId: \"tools.profileId\"\n            placementId: \"tools.placementId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-placement-tags\n          description: \"Generate ad tags for placements.\"\n          hints:\n            readOnly: false\n          call: \"campaign-manager.generate-placement-tags\"\n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reports\n          description: \"List reports.\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campaign-manager.list-reports\"\n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-report\n          description: \"Get report details by ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"campaign-manager.get-report\"\n          with:\n            profileId: \"tools.profileId\"\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-report\n          description: \"Create a new report.\"\n          hints:\n            readOnly: false\n          call: \"campaign-manager.create-report\"\n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: update-report\n          description: \"Update an existing report.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"campaign-manager.update-report\"\n          with:\n            profileId: \"tools.profileId\"\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-report\n          description: \"Delete a report.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"campaign-manager.delete-report\"\n          with:\n            profileId: \"tools.profileId\"\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-report\n          description: \"Run a report to generate results.\"\n          hints:\n            readOnly: false\n          call: \"campaign-manager.run-report\"\
  \n          with:\n            profileId: \"tools.profileId\"\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-campaign-manager/refs/heads/main/capabilities/campaign-management.yaml
tags:
- Google
- Advertising
- Campaign Management
- Reporting
tools:
- description: List advertising campaigns.
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: Get campaign details by ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-campaign
- description: Create a new advertising campaign.
  hints:
    readOnly: false
  name: create-campaign
- description: Update an existing campaign.
  hints:
    idempotent: true
    readOnly: false
  name: update-campaign
- description: List ads.
  hints:
    openWorld: true
    readOnly: true
  name: list-ads
- description: Get ad details by ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-ad
- description: Create a new ad.
  hints:
    readOnly: false
  name: create-ad
- description: Update an existing ad.
  hints:
    idempotent: true
    readOnly: false
  name: update-ad
- description: List ad placements.
  hints:
    openWorld: true
    readOnly: true
  name: list-placements
- description: Get placement details by ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-placement
- description: Create a new placement.
  hints:
    readOnly: false
  name: create-placement
- description: Update an existing placement.
  hints:
    idempotent: true
    readOnly: false
  name: update-placement
- description: Generate ad tags for placements.
  hints:
    readOnly: false
  name: generate-placement-tags
- description: List reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Get report details by ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-report
- description: Create a new report.
  hints:
    readOnly: false
  name: create-report
- description: Update an existing report.
  hints:
    idempotent: true
    readOnly: false
  name: update-report
- description: Delete a report.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-report
- description: Run a report to generate results.
  hints:
    readOnly: false
  name: run-report
---
