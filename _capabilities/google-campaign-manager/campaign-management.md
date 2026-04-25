---
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
- list ad placements.
- list reports
- update an existing ad.
- create a report.
- create report
- update a report.
- get report details.
- delete report
- create a new advertising campaign.
- update an existing campaign.
- create ad
- individual placement management.
- update campaign
- create a campaign.
- reporting
- update ad
- run a report.
- get campaign
- create a new ad.
- delete a report.
- individual campaign management.
- update an ad.
- get report
- get placement details by id.
- create a new report.
- ad management.
- update a campaign.
- list ads.
- update report
- report execution.
- campaign management.
- create a placement.
- list advertising campaigns.
- create a new placement.
- update a placement.
- list ads
- get campaign details.
- generate placement tags
- list placements.
- run a report to generate results.
- list campaigns.
- google
- update an existing placement.
- list reports.
- list placements
- advertising
- digital marketing
- update an existing report.
- create placement
- run report
- analytics
- create an ad.
- get report details by id.
- update placement
- generate ad tags for placements.
- individual ad management.
- get placement
- individual report management.
- get ad
- placement tag generation.
- list campaigns
- create campaign
- report management.
- campaign management
- get campaign details by id.
- placement management.
- get placement details.
- get ad details.
slug: campaign-management
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
