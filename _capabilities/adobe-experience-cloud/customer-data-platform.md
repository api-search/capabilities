---
categories:
- data-engineering
consumed_apis: []
description: Unified workflow for managing real-time customer profiles, audience segmentation, and data ingestion using Adobe Experience Platform. Designed for data engineers and customer data platform administrators.
layout: capability
name: Adobe Experience Cloud Customer Data Platform
operations:
- description: Get a unified customer profile.
  method: GET
  name: get-profile
  path: /v1/profiles
- description: List all datasets.
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: List audience segments.
  method: GET
  name: list-segments
  path: /v1/segments
- description: Create a new audience segment.
  method: POST
  name: create-segment
  path: /v1/segments
personas: []
provider_name: Adobe Experience Cloud
provider_slug: adobe-experience-cloud
search_terms:
- CDP Administrator
- retrieve a unified real-time customer profile from adobe experience platform by identity.
- adobe experience platform
- create audience segment
- digital marketing
- list audience segments
- audience segmentation
- engineer managing data pipelines, schemas, and datasets in experience platform.
- get a unified customer profile.
- analytics
- list datasets
- customer data platform
- list segments
- audience segments.
- list all datasets ingested into adobe experience platform.
- list all datasets.
- list audience segments.
- create a new audience segment.
- analytics, a/b testing, and journey orchestration for digital marketers.
- Data Engineer
- administrator managing customer profiles, segments, and identity resolution.
- profile management, audience segmentation, and data ingestion.
- create segment
- get profile
- a/b testing and content personalization.
- marketing professional using analytics, personalization, and journey tools.
- unified customer profiles.
- unified customer profiles and data management.
- data management
- Digital Marketer
- technical marketer integrating experience cloud apis into marketing stack.
- get customer profile
- list audience segment definitions in adobe experience platform.
- Marketing Technologist
- real-time profiles
- journey orchestration
- create a new audience segment using pql expression in adobe experience platform.
- data sets.
- digital analytics reporting and audience insights.
- campaign management
- customer experience
- multi-channel customer journey management.
- personalization
slug: customer-data-platform
source_filename: customer-data-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Experience Cloud Customer Data Platform\n  description: Unified workflow for managing real-time customer profiles, audience segmentation, and data ingestion using\n    Adobe Experience Platform. Designed for data engineers and customer data platform administrators.\n  tags:\n  - Adobe Experience Platform\n  - Customer Data Platform\n  - Real-Time Profiles\n  - Data Management\n  - Audience Segmentation\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_PLATFORM_ACCESS_TOKEN: ADOBE_PLATFORM_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: experience-platform\n    baseUri: https://platform.adobe.io\n    description: Adobe Experience Platform REST API.\n    authentication:\n      type: bearer\n      token: '{{ADOBE_PLATFORM_ACCESS_TOKEN}}'\n    resources:\n    - name: profiles\n      path: /data/core/ups/access/entities\n      description: Unified Profile access and\
  \ management.\n      operations:\n      - name: get-profile\n        method: GET\n        description: Retrieve a unified customer profile by identity.\n        inputParameters:\n        - name: schema.name\n          in: query\n          type: string\n          required: true\n          description: Profile schema class name.\n        - name: entityId\n          in: query\n          type: string\n          required: true\n          description: Entity identity value.\n        - name: entityIdNS\n          in: query\n          type: string\n          required: true\n          description: Identity namespace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets\n      path: /data/foundation/catalog/datasets\n      description: Dataset management.\n      operations:\n      - name: list-datasets\n        method: GET\n        description: List all datasets in the organization.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: segments\n      path: /data/core/ups/segment/definitions\n      description: Audience segment definitions.\n      operations:\n      - name: list-segments\n        method: GET\n        description: List audience segment definitions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-segment\n        method: POST\n        description: Create a new audience segment definition.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            expression:\n              type: PQL\n              format: pql/text\n              value: '{{tools.pqlExpression}}'\n  exposes:\n\
  \  - type: rest\n    port: 8081\n    namespace: customer-data-platform-api\n    description: Unified REST API for Adobe Experience Platform — profiles, datasets, and audience segments.\n    resources:\n    - path: /v1/profiles\n      name: profiles\n      description: Unified customer profiles.\n      operations:\n      - method: GET\n        name: get-profile\n        description: Get a unified customer profile.\n        call: experience-platform.get-profile\n        with:\n          entityId: rest.entityId\n          entityIdNS: rest.entityIdNS\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasets\n      name: datasets\n      description: Data sets.\n      operations:\n      - method: GET\n        name: list-datasets\n        description: List all datasets.\n        call: experience-platform.list-datasets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/segments\n      name: segments\n      description:\
  \ Audience segments.\n      operations:\n      - method: GET\n        name: list-segments\n        description: List audience segments.\n        call: experience-platform.list-segments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-segment\n        description: Create a new audience segment.\n        call: experience-platform.create-segment\n        with:\n          name: rest.name\n          pqlExpression: rest.pqlExpression\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: customer-data-platform-mcp\n    transport: http\n    description: MCP server for AI-assisted customer data management — query profiles, discover datasets, manage audience\n      segments.\n    tools:\n    - name: get-customer-profile\n      description: Retrieve a unified real-time customer profile from Adobe Experience Platform by identity.\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: experience-platform.get-profile\n      with:\n        entityId: tools.entityId\n        entityIdNS: tools.entityIdNS\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-datasets\n      description: List all datasets ingested into Adobe Experience Platform.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: experience-platform.list-datasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-audience-segments\n      description: List audience segment definitions in Adobe Experience Platform.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: experience-platform.list-segments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-audience-segment\n      description: Create a new audience segment using PQL expression in Adobe Experience Platform.\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: experience-platform.create-segment\n      with:\n        name: tools.name\n        pqlExpression: tools.pqlExpression\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-experience-cloud/refs/heads/main/capabilities/customer-data-platform.yaml
tags:
- Adobe Experience Platform
- Customer Data Platform
- Real-Time Profiles
- Data Management
- Audience Segmentation
tools:
- description: Retrieve a unified real-time customer profile from Adobe Experience Platform by identity.
  hints:
    openWorld: false
    readOnly: true
  name: get-customer-profile
- description: List all datasets ingested into Adobe Experience Platform.
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
- description: List audience segment definitions in Adobe Experience Platform.
  hints:
    openWorld: true
    readOnly: true
  name: list-audience-segments
- description: Create a new audience segment using PQL expression in Adobe Experience Platform.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-audience-segment
---
