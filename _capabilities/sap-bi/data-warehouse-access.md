---
categories: []
consumed_apis:
- sap-bi-bw4hana
- sap-bi-datasphere
description: Workflow capability for accessing and querying data from SAP BW/4HANA data warehouse and SAP Datasphere platform. Enables data discovery, model browsing, connection management, and analytical data consumption. Used by data engineers, BI architects, and analytics platform administrators.
layout: capability
name: SAP Business Intelligence Data Warehouse Access
operations:
- description: List InfoProviders in BW/4HANA.
  method: GET
  name: list-info-providers
  path: /v1/info-providers
- description: Get InfoProvider details.
  method: GET
  name: get-info-provider
  path: /v1/info-providers/{infoProviderName}
- description: List Datasphere spaces.
  method: GET
  name: list-spaces
  path: /v1/spaces
- description: List data source connections.
  method: GET
  name: list-connections
  path: /v1/connections
- description: Browse the Datasphere data catalog.
  method: GET
  name: browse-catalog
  path: /v1/catalog
personas: []
provider_name: SAP Business Intelligence
provider_slug: sap-bi
search_terms:
- list info providers
- datasphere list spaces
- sap
- data source connections.
- list datasphere spaces.
- datasphere browse catalog
- browse the datasphere data catalog for available datasets and views.
- list sap datasphere spaces the user has access to.
- get metadata for a specific bw/4hana infoprovider.
- bw get info provider
- browse the datasphere data catalog.
- datasphere
- get configuration of a specific datasphere space.
- list all data source connections configured in datasphere.
- datasphere list connections
- browse catalog
- datasphere spaces.
- list spaces
- list data source connections.
- get info provider
- data catalog.
- bw list info providers
- analytics
- datasphere get space
- get infoprovider details.
- list all infoproviders (infocubes, dsos, compositeproviders) in sap bw/4hana.
- single infoprovider.
- bw/4hana infoproviders.
- list connections
- data warehouse
- reporting
- data visualization
- business intelligence
- list infoproviders in bw/4hana.
slug: data-warehouse-access
source_filename: data-warehouse-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP Business Intelligence Data Warehouse Access\"\n  description: \"Workflow capability for accessing and querying data from SAP BW/4HANA data warehouse and SAP Datasphere platform. Enables data discovery, model browsing, connection management, and analytical data consumption. Used by data engineers, BI architects, and analytics platform administrators.\"\n  tags:\n    - Business Intelligence\n    - Data Warehouse\n    - Datasphere\n    - SAP\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_BW_USERNAME: SAP_BW_USERNAME\n      SAP_BW_PASSWORD: SAP_BW_PASSWORD\n      SAP_DATASPHERE_OAUTH_TOKEN: SAP_DATASPHERE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: sap-bi-bw4hana\n      location: ./shared/bw4hana-odata.yaml\n    - import: sap-bi-datasphere\n      location: ./shared/datasphere.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: sap-bi-data-warehouse-api\n\
  \      description: \"Unified REST API for SAP data warehouse access and Datasphere platform management.\"\n      resources:\n        - path: /v1/info-providers\n          name: info-providers\n          description: \"BW/4HANA InfoProviders.\"\n          operations:\n            - method: GET\n              name: list-info-providers\n              description: \"List InfoProviders in BW/4HANA.\"\n              call: \"sap-bi-bw4hana.list-info-providers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/info-providers/{infoProviderName}\n          name: info-provider\n          description: \"Single InfoProvider.\"\n          operations:\n            - method: GET\n              name: get-info-provider\n              description: \"Get InfoProvider details.\"\n              call: \"sap-bi-bw4hana.get-info-provider\"\n              with:\n                infoProviderName: \"rest.infoProviderName\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/spaces\n          name: spaces\n          description: \"Datasphere spaces.\"\n          operations:\n            - method: GET\n              name: list-spaces\n              description: \"List Datasphere spaces.\"\n              call: \"sap-bi-datasphere.list-spaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connections\n          name: connections\n          description: \"Data source connections.\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List data source connections.\"\n              call: \"sap-bi-datasphere.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/catalog\n          name: catalog\n          description: \"Data catalog.\"\n          operations:\n\
  \            - method: GET\n              name: browse-catalog\n              description: \"Browse the Datasphere data catalog.\"\n              call: \"sap-bi-datasphere.list-catalog-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: sap-bi-data-warehouse-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP data warehouse access and platform management.\"\n      tools:\n        - name: bw-list-info-providers\n          description: \"List all InfoProviders (InfoCubes, DSOs, CompositeProviders) in SAP BW/4HANA.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-bi-bw4hana.list-info-providers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bw-get-info-provider\n          description: \"Get metadata for a specific BW/4HANA InfoProvider.\"\n   \
  \       hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-bi-bw4hana.get-info-provider\"\n          with:\n            infoProviderName: \"tools.infoProviderName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: datasphere-list-spaces\n          description: \"List SAP Datasphere spaces the user has access to.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-bi-datasphere.list-spaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: datasphere-get-space\n          description: \"Get configuration of a specific Datasphere space.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-bi-datasphere.get-space\"\n          with:\n            spaceId: \"tools.spaceId\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: datasphere-list-connections\n          description: \"List all data source connections configured in Datasphere.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-bi-datasphere.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: datasphere-browse-catalog\n          description: \"Browse the Datasphere data catalog for available datasets and views.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-bi-datasphere.list-catalog-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-bi/refs/heads/main/capabilities/data-warehouse-access.yaml
tags:
- Business Intelligence
- Data Warehouse
- Datasphere
- SAP
tools:
- description: List all InfoProviders (InfoCubes, DSOs, CompositeProviders) in SAP BW/4HANA.
  hints:
    openWorld: true
    readOnly: true
  name: bw-list-info-providers
- description: Get metadata for a specific BW/4HANA InfoProvider.
  hints:
    openWorld: false
    readOnly: true
  name: bw-get-info-provider
- description: List SAP Datasphere spaces the user has access to.
  hints:
    openWorld: true
    readOnly: true
  name: datasphere-list-spaces
- description: Get configuration of a specific Datasphere space.
  hints:
    openWorld: false
    readOnly: true
  name: datasphere-get-space
- description: List all data source connections configured in Datasphere.
  hints:
    openWorld: true
    readOnly: true
  name: datasphere-list-connections
- description: Browse the Datasphere data catalog for available datasets and views.
  hints:
    openWorld: true
    readOnly: true
  name: datasphere-browse-catalog
---
