---
categories: []
consumed_apis: []
description: The OpenFEMA API provides programmatic access to FEMA's public datasets including disaster declarations, public assistance, individual assistance, hazard mitigation, and the National Flood Insurance Program (NFIP).
layout: capability
name: OpenFEMA API
operations:
- description: List disaster declarations summaries
  method: GET
  name: listdisasterdeclarationssummaries
  path: /v2/DisasterDeclarationsSummaries
- description: List FEMA web disaster declarations
  method: GET
  name: listfemawebdisasterdeclarations
  path: /v1/FemaWebDisasterDeclarations
- description: List declaration denials
  method: GET
  name: listdeclarationdenials
  path: /v1/DeclarationDenials
- description: List public assistance funded project details
  method: GET
  name: listpublicassistancefundedprojectsdetails
  path: /v1/PublicAssistanceFundedProjectsDetails
- description: List individual assistance housing registrants for large disasters
  method: GET
  name: listindividualassistancehousingregistrants
  path: /v1/IndividualAssistanceHousingRegistrantsLargeDisasters
- description: List hazard mitigation grant program disaster summaries
  method: GET
  name: listhazardmitigationgrantprogramdisastersummarie
  path: /v2/HazardMitigationGrantProgramDisasterSummaries
- description: List NFIP policies
  method: GET
  name: listfimanfippolicies
  path: /v2/FimaNfipPolicies
- description: List NFIP claims
  method: GET
  name: listfimanfipclaims
  path: /v2/FimaNfipClaims
- description: List NFIP community status book entries
  method: GET
  name: listnfipcommunitystatusbook
  path: /v1/NfipCommunityStatusBook
- description: List OpenFEMA datasets
  method: GET
  name: listopenfemadatasets
  path: /v1/OpenFemaDataSets
- description: List FEMA regions
  method: GET
  name: listfemaregions
  path: /v2/FemaRegions
personas: []
provider_name: Federal Emergency Management Agency
provider_slug: federal-emergency-management-agency
search_terms:
- disasters
- listdeclarationdenials
- hazard mitigation
- list individual assistance housing registrants for large disasters
- listfimanfippolicies
- listnfipcommunitystatusbook
- list nfip claims
- listfemaregions
- list nfip community status book entries
- list fema regions
- list fema web disaster declarations
- list nfip policies
- list openfema datasets
- api
- list hazard mitigation grant program disaster summaries
- listhazardmitigationgrantprogramdisastersummarie
- listindividualassistancehousingregistrants
- list declaration denials
- emergencies
- listdisasterdeclarationssummaries
- management
- listfemawebdisasterdeclarations
- list public assistance funded project details
- listopenfemadatasets
- federal government
- agency
- flood insurance
- list disaster declarations summaries
- federal
- emergency
- listpublicassistancefundedprojectsdetails
- listfimanfipclaims
slug: federal-emergency-management-agency-capability
source_filename: federal-emergency-management-agency-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenFEMA API\n  description: The OpenFEMA API provides programmatic access to FEMA's public datasets including disaster declarations, public\n    assistance, individual assistance, hazard mitigation, and the National Flood Insurance Program (NFIP).\n  tags:\n  - Federal\n  - Emergency\n  - Management\n  - Agency\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: federal-emergency-management-agency\n    baseUri: https://www.fema.gov/api/open\n    description: OpenFEMA API HTTP API.\n    resources:\n    - name: v2-disasterdeclarationssummaries\n      path: /v2/DisasterDeclarationsSummaries\n      operations:\n      - name: listdisasterdeclarationssummaries\n        method: GET\n        description: List disaster declarations summaries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ v1-femawebdisasterdeclarations\n      path: /v1/FemaWebDisasterDeclarations\n      operations:\n      - name: listfemawebdisasterdeclarations\n        method: GET\n        description: List FEMA web disaster declarations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-declarationdenials\n      path: /v1/DeclarationDenials\n      operations:\n      - name: listdeclarationdenials\n        method: GET\n        description: List declaration denials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-publicassistancefundedprojectsdetails\n      path: /v1/PublicAssistanceFundedProjectsDetails\n      operations:\n      - name: listpublicassistancefundedprojectsdetails\n        method: GET\n        description: List public assistance funded project details\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-individualassistancehousingregistrantslargedi\n      path: /v1/IndividualAssistanceHousingRegistrantsLargeDisasters\n      operations:\n      - name: listindividualassistancehousingregistrants\n        method: GET\n        description: List individual assistance housing registrants for large disasters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-hazardmitigationgrantprogramdisastersummaries\n      path: /v2/HazardMitigationGrantProgramDisasterSummaries\n      operations:\n      - name: listhazardmitigationgrantprogramdisastersummarie\n        method: GET\n        description: List hazard mitigation grant program disaster summaries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-fimanfippolicies\n      path: /v2/FimaNfipPolicies\n\
  \      operations:\n      - name: listfimanfippolicies\n        method: GET\n        description: List NFIP policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-fimanfipclaims\n      path: /v2/FimaNfipClaims\n      operations:\n      - name: listfimanfipclaims\n        method: GET\n        description: List NFIP claims\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-nfipcommunitystatusbook\n      path: /v1/NfipCommunityStatusBook\n      operations:\n      - name: listnfipcommunitystatusbook\n        method: GET\n        description: List NFIP community status book entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-openfemadatasets\n      path: /v1/OpenFemaDataSets\n      operations:\n      - name:\
  \ listopenfemadatasets\n        method: GET\n        description: List OpenFEMA datasets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-femaregions\n      path: /v2/FemaRegions\n      operations:\n      - name: listfemaregions\n        method: GET\n        description: List FEMA regions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: federal-emergency-management-agency-rest\n    description: REST adapter for OpenFEMA API.\n    resources:\n    - path: /v2/DisasterDeclarationsSummaries\n      name: listdisasterdeclarationssummaries\n      operations:\n      - method: GET\n        name: listdisasterdeclarationssummaries\n        description: List disaster declarations summaries\n        call: federal-emergency-management-agency.listdisasterdeclarationssummaries\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/FemaWebDisasterDeclarations\n      name: listfemawebdisasterdeclarations\n      operations:\n      - method: GET\n        name: listfemawebdisasterdeclarations\n        description: List FEMA web disaster declarations\n        call: federal-emergency-management-agency.listfemawebdisasterdeclarations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeclarationDenials\n      name: listdeclarationdenials\n      operations:\n      - method: GET\n        name: listdeclarationdenials\n        description: List declaration denials\n        call: federal-emergency-management-agency.listdeclarationdenials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/PublicAssistanceFundedProjectsDetails\n      name: listpublicassistancefundedprojectsdetails\n      operations:\n      - method: GET\n        name: listpublicassistancefundedprojectsdetails\n\
  \        description: List public assistance funded project details\n        call: federal-emergency-management-agency.listpublicassistancefundedprojectsdetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/IndividualAssistanceHousingRegistrantsLargeDisasters\n      name: listindividualassistancehousingregistrants\n      operations:\n      - method: GET\n        name: listindividualassistancehousingregistrants\n        description: List individual assistance housing registrants for large disasters\n        call: federal-emergency-management-agency.listindividualassistancehousingregistrants\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/HazardMitigationGrantProgramDisasterSummaries\n      name: listhazardmitigationgrantprogramdisastersummarie\n      operations:\n      - method: GET\n        name: listhazardmitigationgrantprogramdisastersummarie\n        description: List hazard mitigation grant program\
  \ disaster summaries\n        call: federal-emergency-management-agency.listhazardmitigationgrantprogramdisastersummarie\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/FimaNfipPolicies\n      name: listfimanfippolicies\n      operations:\n      - method: GET\n        name: listfimanfippolicies\n        description: List NFIP policies\n        call: federal-emergency-management-agency.listfimanfippolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/FimaNfipClaims\n      name: listfimanfipclaims\n      operations:\n      - method: GET\n        name: listfimanfipclaims\n        description: List NFIP claims\n        call: federal-emergency-management-agency.listfimanfipclaims\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/NfipCommunityStatusBook\n      name: listnfipcommunitystatusbook\n      operations:\n      - method: GET\n        name: listnfipcommunitystatusbook\n\
  \        description: List NFIP community status book entries\n        call: federal-emergency-management-agency.listnfipcommunitystatusbook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/OpenFemaDataSets\n      name: listopenfemadatasets\n      operations:\n      - method: GET\n        name: listopenfemadatasets\n        description: List OpenFEMA datasets\n        call: federal-emergency-management-agency.listopenfemadatasets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/FemaRegions\n      name: listfemaregions\n      operations:\n      - method: GET\n        name: listfemaregions\n        description: List FEMA regions\n        call: federal-emergency-management-agency.listfemaregions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: federal-emergency-management-agency-mcp\n    transport: http\n    description: MCP adapter for\
  \ OpenFEMA API for AI agent use.\n    tools:\n    - name: listdisasterdeclarationssummaries\n      description: List disaster declarations summaries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-emergency-management-agency.listdisasterdeclarationssummaries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfemawebdisasterdeclarations\n      description: List FEMA web disaster declarations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-emergency-management-agency.listfemawebdisasterdeclarations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeclarationdenials\n      description: List declaration denials\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-emergency-management-agency.listdeclarationdenials\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listpublicassistancefundedprojectsdetails\n      description: List public assistance funded project details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-emergency-management-agency.listpublicassistancefundedprojectsdetails\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listindividualassistancehousingregistrants\n      description: List individual assistance housing registrants for large disasters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-emergency-management-agency.listindividualassistancehousingregistrants\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listhazardmitigationgrantprogramdisastersummarie\n      description: List hazard mitigation grant program disaster summaries\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: federal-emergency-management-agency.listhazardmitigationgrantprogramdisastersummarie\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfimanfippolicies\n      description: List NFIP policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-emergency-management-agency.listfimanfippolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfimanfipclaims\n      description: List NFIP claims\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-emergency-management-agency.listfimanfipclaims\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnfipcommunitystatusbook\n      description: List NFIP community status book entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n     \
  \ call: federal-emergency-management-agency.listnfipcommunitystatusbook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listopenfemadatasets\n      description: List OpenFEMA datasets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-emergency-management-agency.listopenfemadatasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfemaregions\n      description: List FEMA regions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-emergency-management-agency.listfemaregions\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/federal-emergency-management-agency/refs/heads/main/capabilities/federal-emergency-management-agency-capability.yaml
tags:
- Federal
- Emergency
- Management
- Agency
- API
tools:
- description: List disaster declarations summaries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdisasterdeclarationssummaries
- description: List FEMA web disaster declarations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfemawebdisasterdeclarations
- description: List declaration denials
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeclarationdenials
- description: List public assistance funded project details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpublicassistancefundedprojectsdetails
- description: List individual assistance housing registrants for large disasters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listindividualassistancehousingregistrants
- description: List hazard mitigation grant program disaster summaries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listhazardmitigationgrantprogramdisastersummarie
- description: List NFIP policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfimanfippolicies
- description: List NFIP claims
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfimanfipclaims
- description: List NFIP community status book entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnfipcommunitystatusbook
- description: List OpenFEMA datasets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listopenfemadatasets
- description: List FEMA regions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfemaregions
---
