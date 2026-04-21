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
- create ad
- update a campaign.
- placement tag generation.
- create a new ad.
- update an existing placement.
- list ads
- create a report.
- digital marketing
- update an ad.
- individual placement management.
- list ad placements.
- get placement details by id.
- list placements.
- update an existing report.
- run a report.
- update a report.
- individual report management.
- update campaign
- run a report to generate results.
- placement management.
- create an ad.
- list reports.
- campaign management.
- list placements
- update an existing ad.
- report execution.
- create a new report.
- google
- create a new placement.
- individual ad management.
- get ad
- get campaign details by id.
- get ad details by id.
- update ad
- create placement
- update placement
- get campaign details.
- delete a report.
- update an existing campaign.
- get placement details.
- list advertising campaigns.
- report management.
- create a new advertising campaign.
- reporting
- get campaign
- campaign management
- list campaigns.
- list reports
- advertising
- run report
- create report
- delete report
- get placement
- ad management.
- get report
- list campaigns
- get ad details.
- generate placement tags
- create campaign
- get report details by id.
- create a placement.
- update report
- list ads.
- create a campaign.
- get report details.
- analytics
- update a placement.
- generate ad tags for placements.
- individual campaign management.
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
