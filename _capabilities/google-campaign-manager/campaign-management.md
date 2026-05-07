---
categories:
- analytics
consumed_apis: []
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
- report execution.
- analytics
- get ad
- create placement
- generate placement tags
- get campaign details.
- get placement details.
- individual report management.
- get report
- digital marketing
- update ad
- update an ad.
- update an existing campaign.
- get placement
- create report
- list ad placements.
- list reports
- generate ad tags for placements.
- delete report
- get ad details.
- placement management.
- list reports.
- google
- placement tag generation.
- get placement details by id.
- get campaign
- update an existing ad.
- list placements
- list campaigns
- create a campaign.
- list campaigns.
- campaign management.
- update placement
- create a report.
- individual ad management.
- create a new placement.
- update a report.
- get report details by id.
- campaign management
- create a new report.
- update campaign
- individual campaign management.
- update report
- delete a report.
- get ad details by id.
- create a new advertising campaign.
- create a new ad.
- run a report.
- update an existing placement.
- list advertising campaigns.
- create an ad.
- list placements.
- create campaign
- get campaign details by id.
- reporting
- ad management.
- update a campaign.
- list ads.
- list ads
- report management.
- update a placement.
- get report details.
- advertising
- create a placement.
- run a report to generate results.
- individual placement management.
- create ad
- update an existing report.
- run report
slug: campaign-management
source_filename: campaign-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Campaign Manager Campaign Management\n  description: Unified workflow for managing digital advertising campaigns, ads, placements, and performance reports. Used\n    by ad operations specialists and digital marketers.\n  tags:\n  - Google\n  - Advertising\n  - Campaign Management\n  - Reporting\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_OAUTH2_TOKEN: GOOGLE_OAUTH2_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: campaign-manager\n    baseUri: https://dfareporting.googleapis.com/dfareporting/v4\n    description: Campaign Manager 360 API for managing campaigns, ads, placements, and reports.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_OAUTH2_TOKEN}}'\n    resources:\n    - name: campaigns\n      path: /userprofiles/{profileId}/campaigns\n      description: Manage advertising campaigns.\n      operations:\n      - name: list-campaigns\n      \
  \  method: GET\n        description: List campaigns, optionally filtered.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-campaign\n        method: POST\n        description: Create a new campaign.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            advertiserId: '{{tools.advertiserId}}'\n    - name: campaign-details\n      path: /userprofiles/{profileId}/campaigns/{campaignId}\n      description:\
  \ Manage individual campaigns.\n      operations:\n      - name: get-campaign\n        method: GET\n        description: Get a campaign by ID.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        - name: campaignId\n          in: path\n          type: string\n          required: true\n          description: Campaign ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-campaign\n        method: PUT\n        description: Update a campaign.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        - name: campaignId\n          in: path\n          type: string\n          required: true\n          description: Campaign ID.\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: ads\n      path: /userprofiles/{profileId}/ads\n      description: Manage ads within campaigns.\n      operations:\n      - name: list-ads\n        method: GET\n        description: List ads.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ad\n        method: POST\n        description: Create a new ad.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            campaignId: '{{tools.campaignId}}'\n    - name: ad-details\n      path: /userprofiles/{profileId}/ads/{adId}\n      description: Manage individual ads.\n      operations:\n      - name: get-ad\n        method: GET\n        description: Get an ad by ID.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        - name: adId\n          in: path\n          type: string\n          required: true\n          description: Ad ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ad\n        method: PUT\n        description: Update an ad.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n\
  \          required: true\n          description: User profile ID.\n        - name: adId\n          in: path\n          type: string\n          required: true\n          description: Ad ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: placements\n      path: /userprofiles/{profileId}/placements\n      description: Manage ad placements.\n      operations:\n      - name: list-placements\n        method: GET\n        description: List placements.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-placement\n        method: POST\n        description:\
  \ Create a new placement.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            campaignId: '{{tools.campaignId}}'\n    - name: placement-details\n      path: /userprofiles/{profileId}/placements/{placementId}\n      description: Manage individual placements.\n      operations:\n      - name: get-placement\n        method: GET\n        description: Get a placement by ID.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        - name: placementId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Placement ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-placement\n        method: PUT\n        description: Update a placement.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        - name: placementId\n          in: path\n          type: string\n          required: true\n          description: Placement ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: placement-tags\n      path: /userprofiles/{profileId}/placements/generatetags\n      description: Generate placement tags.\n      operations:\n      - name: generate-placement-tags\n        method: POST\n        description: Generate\
  \ ad tags for placements.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /userprofiles/{profileId}/reports\n      description: Manage reports.\n      operations:\n      - name: list-reports\n        method: GET\n        description: List reports.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-report\n        method: POST\n        description: Create a new report.\n        inputParameters:\n        - name: profileId\n          in: path\n          type:\
  \ string\n          required: true\n          description: User profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n    - name: report-details\n      path: /userprofiles/{profileId}/reports/{reportId}\n      description: Manage individual reports.\n      operations:\n      - name: get-report\n        method: GET\n        description: Get a report by ID.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: update-report\n        method: PUT\n        description: Update a report.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-report\n        method: DELETE\n        description: Delete a report.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: report-run\n      path: /userprofiles/{profileId}/reports/{reportId}/run\n      description: Run reports.\n      operations:\n      - name: run-report\n        method: POST\n        description: Run a report.\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: User profile ID.\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: campaign-management-api\n    description: Unified REST API for Google Campaign Manager 360 campaign management.\n    resources:\n    - path: /v1/campaigns\n      name: campaigns\n      description:\
  \ Campaign management.\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List campaigns.\n        call: campaign-manager.list-campaigns\n        with:\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-campaign\n        description: Create a campaign.\n        call: campaign-manager.create-campaign\n        with:\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{id}\n      name: campaign-details\n      description: Individual campaign management.\n      operations:\n      - method: GET\n        name: get-campaign\n        description: Get campaign details.\n        call: campaign-manager.get-campaign\n        with:\n          profileId: rest.profileId\n          campaignId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \      - method: PUT\n        name: update-campaign\n        description: Update a campaign.\n        call: campaign-manager.update-campaign\n        with:\n          profileId: rest.profileId\n          campaignId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ads\n      name: ads\n      description: Ad management.\n      operations:\n      - method: GET\n        name: list-ads\n        description: List ads.\n        call: campaign-manager.list-ads\n        with:\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ad\n        description: Create an ad.\n        call: campaign-manager.create-ad\n        with:\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ads/{id}\n      name: ad-details\n      description: Individual ad management.\n      operations:\n\
  \      - method: GET\n        name: get-ad\n        description: Get ad details.\n        call: campaign-manager.get-ad\n        with:\n          profileId: rest.profileId\n          adId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-ad\n        description: Update an ad.\n        call: campaign-manager.update-ad\n        with:\n          profileId: rest.profileId\n          adId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/placements\n      name: placements\n      description: Placement management.\n      operations:\n      - method: GET\n        name: list-placements\n        description: List placements.\n        call: campaign-manager.list-placements\n        with:\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-placement\n        description:\
  \ Create a placement.\n        call: campaign-manager.create-placement\n        with:\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/placements/{id}\n      name: placement-details\n      description: Individual placement management.\n      operations:\n      - method: GET\n        name: get-placement\n        description: Get placement details.\n        call: campaign-manager.get-placement\n        with:\n          profileId: rest.profileId\n          placementId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-placement\n        description: Update a placement.\n        call: campaign-manager.update-placement\n        with:\n          profileId: rest.profileId\n          placementId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/placement-tags\n      name: placement-tags\n    \
  \  description: Placement tag generation.\n      operations:\n      - method: POST\n        name: generate-placement-tags\n        description: Generate ad tags for placements.\n        call: campaign-manager.generate-placement-tags\n        with:\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Report management.\n      operations:\n      - method: GET\n        name: list-reports\n        description: List reports.\n        call: campaign-manager.list-reports\n        with:\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-report\n        description: Create a report.\n        call: campaign-manager.create-report\n        with:\n          profileId: rest.profileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{id}\n\
  \      name: report-details\n      description: Individual report management.\n      operations:\n      - method: GET\n        name: get-report\n        description: Get report details.\n        call: campaign-manager.get-report\n        with:\n          profileId: rest.profileId\n          reportId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-report\n        description: Update a report.\n        call: campaign-manager.update-report\n        with:\n          profileId: rest.profileId\n          reportId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-report\n        description: Delete a report.\n        call: campaign-manager.delete-report\n        with:\n          profileId: rest.profileId\n          reportId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{id}/run\n\
  \      name: report-run\n      description: Report execution.\n      operations:\n      - method: POST\n        name: run-report\n        description: Run a report.\n        call: campaign-manager.run-report\n        with:\n          profileId: rest.profileId\n          reportId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: campaign-management-mcp\n    transport: http\n    description: MCP server for AI-assisted campaign management and reporting.\n    tools:\n    - name: list-campaigns\n      description: List advertising campaigns.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campaign-manager.list-campaigns\n      with:\n        profileId: tools.profileId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-campaign\n      description: Get campaign details by ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campaign-manager.get-campaign\n\
  \      with:\n        profileId: tools.profileId\n        campaignId: tools.campaignId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-campaign\n      description: Create a new advertising campaign.\n      hints:\n        readOnly: false\n      call: campaign-manager.create-campaign\n      with:\n        profileId: tools.profileId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-campaign\n      description: Update an existing campaign.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: campaign-manager.update-campaign\n      with:\n        profileId: tools.profileId\n        campaignId: tools.campaignId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ads\n      description: List ads.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campaign-manager.list-ads\n      with:\n        profileId: tools.profileId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-ad\n      description: Get ad details by ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campaign-manager.get-ad\n      with:\n        profileId: tools.profileId\n        adId: tools.adId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ad\n      description: Create a new ad.\n      hints:\n        readOnly: false\n      call: campaign-manager.create-ad\n      with:\n        profileId: tools.profileId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-ad\n      description: Update an existing ad.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: campaign-manager.update-ad\n      with:\n        profileId: tools.profileId\n        adId: tools.adId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-placements\n      description: List ad placements.\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: campaign-manager.list-placements\n      with:\n        profileId: tools.profileId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-placement\n      description: Get placement details by ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campaign-manager.get-placement\n      with:\n        profileId: tools.profileId\n        placementId: tools.placementId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-placement\n      description: Create a new placement.\n      hints:\n        readOnly: false\n      call: campaign-manager.create-placement\n      with:\n        profileId: tools.profileId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-placement\n      description: Update an existing placement.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: campaign-manager.update-placement\n\
  \      with:\n        profileId: tools.profileId\n        placementId: tools.placementId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-placement-tags\n      description: Generate ad tags for placements.\n      hints:\n        readOnly: false\n      call: campaign-manager.generate-placement-tags\n      with:\n        profileId: tools.profileId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List reports.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campaign-manager.list-reports\n      with:\n        profileId: tools.profileId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report\n      description: Get report details by ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: campaign-manager.get-report\n      with:\n        profileId: tools.profileId\n        reportId: tools.reportId\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-report\n      description: Create a new report.\n      hints:\n        readOnly: false\n      call: campaign-manager.create-report\n      with:\n        profileId: tools.profileId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-report\n      description: Update an existing report.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: campaign-manager.update-report\n      with:\n        profileId: tools.profileId\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-report\n      description: Delete a report.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: campaign-manager.delete-report\n      with:\n        profileId: tools.profileId\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: run-report\n      description: Run a report to generate results.\n      hints:\n        readOnly: false\n      call: campaign-manager.run-report\n      with:\n        profileId: tools.profileId\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
