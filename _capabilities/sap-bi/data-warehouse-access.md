---
categories: []
consumed_apis: []
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
- get info provider
- get configuration of a specific datasphere space.
- browse catalog
- list datasphere spaces.
- list infoproviders in bw/4hana.
- datasphere list spaces
- bw/4hana infoproviders.
- reporting
- bw list info providers
- analytics
- datasphere get space
- bw get info provider
- get infoprovider details.
- browse the datasphere data catalog.
- list all data source connections configured in datasphere.
- list info providers
- data source connections.
- data visualization
- data warehouse
- datasphere
- sap
- list spaces
- single infoprovider.
- datasphere browse catalog
- business intelligence
- list connections
- list all infoproviders (infocubes, dsos, compositeproviders) in sap bw/4hana.
- get metadata for a specific bw/4hana infoprovider.
- datasphere list connections
- list sap datasphere spaces the user has access to.
- browse the datasphere data catalog for available datasets and views.
- datasphere spaces.
- data catalog.
- list data source connections.
slug: data-warehouse-access
source_filename: data-warehouse-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP Business Intelligence Data Warehouse Access\n  description: Workflow capability for accessing and querying data from SAP BW/4HANA data warehouse and SAP Datasphere platform.\n    Enables data discovery, model browsing, connection management, and analytical data consumption. Used by data engineers,\n    BI architects, and analytics platform administrators.\n  tags:\n  - Business Intelligence\n  - Data Warehouse\n  - Datasphere\n  - SAP\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_BW_USERNAME: SAP_BW_USERNAME\n    SAP_BW_PASSWORD: SAP_BW_PASSWORD\n    SAP_DATASPHERE_OAUTH_TOKEN: SAP_DATASPHERE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sap-bi-bw4hana\n    baseUri: https://{server}:{port}/sap/opu/odata/sap\n    description: SAP BW/4HANA OData API for data warehouse access.\n    authentication:\n      type: basic\n      username: '{{SAP_BW_USERNAME}}'\n      password:\
  \ '{{SAP_BW_PASSWORD}}'\n    resources:\n    - name: info-providers\n      path: /RSOD_INFOPROV_SRV/InfoProviders\n      description: Access InfoProvider metadata and data.\n      operations:\n      - name: list-info-providers\n        method: GET\n        description: List all InfoProviders in the BW/4HANA system.\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-info-provider\n        method: GET\n        description: Get details of a specific InfoProvider.\n        inputParameters:\n        - name: infoProviderName\n          in: path\n          type: string\n          required:\
  \ true\n          description: The InfoProvider name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sap-bi-datasphere\n    baseUri: https://{tenant}.datasphere.cloud.sap/api/v1\n    description: SAP Datasphere REST API for space management, connections, data flows, and catalog.\n    authentication:\n      type: bearer\n      token: '{{SAP_DATASPHERE_OAUTH_TOKEN}}'\n    resources:\n    - name: spaces\n      path: /spaces\n      description: Manage Datasphere spaces.\n      operations:\n      - name: list-spaces\n        method: GET\n        description: List all Datasphere spaces.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: create-space\n        method: POST\n        description: Create a new Datasphere space.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: get-space\n        method: GET\n        description: Get details of a specific space.\n        inputParameters:\n        - name: spaceId\n          in: path\n          type: string\n          required: true\n          description: The space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /connections\n      description: Manage data source connections.\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all data source connections.\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalog\n      path: /catalog\n      description: Browse the Datasphere data catalog.\n      operations:\n      - name: list-catalog-items\n        method: GET\n        description: Browse the Datasphere data catalog.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: sap-bi-data-warehouse-api\n    description: Unified REST API for SAP data warehouse access and Datasphere platform management.\n    resources:\n    - path: /v1/info-providers\n      name: info-providers\n      description: BW/4HANA InfoProviders.\n      operations:\n      - method: GET\n        name: list-info-providers\n        description: List InfoProviders in BW/4HANA.\n        call: sap-bi-bw4hana.list-info-providers\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /v1/info-providers/{infoProviderName}\n      name: info-provider\n      description: Single InfoProvider.\n      operations:\n      - method: GET\n        name: get-info-provider\n        description: Get InfoProvider details.\n        call: sap-bi-bw4hana.get-info-provider\n        with:\n          infoProviderName: rest.infoProviderName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spaces\n      name: spaces\n      description: Datasphere spaces.\n      operations:\n      - method: GET\n        name: list-spaces\n        description: List Datasphere spaces.\n        call: sap-bi-datasphere.list-spaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Data source connections.\n      operations:\n      - method: GET\n        name: list-connections\n        description: List data source connections.\n\
  \        call: sap-bi-datasphere.list-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalog\n      name: catalog\n      description: Data catalog.\n      operations:\n      - method: GET\n        name: browse-catalog\n        description: Browse the Datasphere data catalog.\n        call: sap-bi-datasphere.list-catalog-items\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: sap-bi-data-warehouse-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP data warehouse access and platform management.\n    tools:\n    - name: bw-list-info-providers\n      description: List all InfoProviders (InfoCubes, DSOs, CompositeProviders) in SAP BW/4HANA.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-bi-bw4hana.list-info-providers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bw-get-info-provider\n\
  \      description: Get metadata for a specific BW/4HANA InfoProvider.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sap-bi-bw4hana.get-info-provider\n      with:\n        infoProviderName: tools.infoProviderName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datasphere-list-spaces\n      description: List SAP Datasphere spaces the user has access to.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-bi-datasphere.list-spaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datasphere-get-space\n      description: Get configuration of a specific Datasphere space.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sap-bi-datasphere.get-space\n      with:\n        spaceId: tools.spaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datasphere-list-connections\n      description: List all data source connections\
  \ configured in Datasphere.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-bi-datasphere.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datasphere-browse-catalog\n      description: Browse the Datasphere data catalog for available datasets and views.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-bi-datasphere.list-catalog-items\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
