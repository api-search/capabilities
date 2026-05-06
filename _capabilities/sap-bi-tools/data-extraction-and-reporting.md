---
categories: []
consumed_apis: []
description: Workflow capability for extracting data from SAP Analytics Cloud models and managing BusinessObjects reports. Combines data export pipelines with traditional BI report scheduling and delivery. Used by data engineers, BI developers, and operations teams.
layout: capability
name: SAP BI Tools Data Extraction and Reporting
operations:
- description: List available namespaces for data export.
  method: GET
  name: list-namespaces
  path: /v1/namespaces
- description: List available models (providers) for data export.
  method: GET
  name: list-providers
  path: /v1/namespaces/{namespaceId}/providers
- description: Extract fact data from a planning model.
  method: GET
  name: get-fact-data
  path: /v1/models/{modelId}/fact-data
- description: Extract master data (dimension members) from a model.
  method: GET
  name: get-master-data
  path: /v1/models/{modelId}/master-data
- description: Browse reports in the InfoStore repository.
  method: GET
  name: browse-reports
  path: /v1/reports
- description: Schedule a BusinessObjects report for immediate execution.
  method: POST
  name: schedule-report
  path: /v1/reports/{reportId}/schedule
- description: List completed report instances in the BI Inbox.
  method: GET
  name: list-inbox-items
  path: /v1/inbox
personas: []
provider_name: SAP BI Tools
provider_slug: sap-bi-tools
search_terms:
- list inbox items
- get model metadata
- list completed report instances in the bi inbox.
- reporting
- analytics
- list available models (providers) for data export.
- model providers for data export.
- schedule a businessobjects report for immediate execution.
- get fact data
- browse reports
- list completed report instances in the user's bi inbox.
- extract master data
- businessobjects report repository.
- extract master data (dimension members) from an analytics model.
- data visualization
- get odata metadata describing the structure of a planning model.
- list providers
- list namespaces
- sap
- data export namespaces.
- data export
- model fact data.
- model master data.
- browse reports in the infostore repository.
- extract master data (dimension members) from a model.
- extract fact data from a planning model.
- bi user inbox.
- business intelligence
- get master data
- extract fact data (transactional records) from an analytics model.
- search for businessobjects reports and documents in the cms repository.
- list analytics models available for data export from sap analytics cloud.
- list available namespaces for data export.
- schedule a report for execution.
- list export models
- search reports
- extract fact data
- schedule report
slug: data-extraction-and-reporting
source_filename: data-extraction-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP BI Tools Data Extraction and Reporting\n  description: Workflow capability for extracting data from SAP Analytics Cloud models and managing BusinessObjects reports.\n    Combines data export pipelines with traditional BI report scheduling and delivery. Used by data engineers, BI developers,\n    and operations teams.\n  tags:\n  - Analytics\n  - Business Intelligence\n  - Data Export\n  - Reporting\n  - SAP\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_AC_OAUTH_TOKEN: SAP_AC_OAUTH_TOKEN\n    SAP_BOBJ_LOGON_TOKEN: SAP_BOBJ_LOGON_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: analytics-cloud-data-export\n    baseUri: https://{tenant}.{datacenter}.sapanalytics.cloud/api/v1/dataexport\n    description: SAP Analytics Cloud Data Export API for extracting fact data and master data from planning models.\n    authentication:\n      type: bearer\n      token: '{{SAP_AC_OAUTH_TOKEN}}'\n\
  \    resources:\n    - name: namespaces\n      path: /administration/Namespaces\n      description: Administration service for discovering namespaces.\n      operations:\n      - name: list-namespaces\n        method: GET\n        description: List available namespaces for data export.\n        inputParameters:\n        - name: $format\n          in: query\n          type: string\n          required: false\n          description: Response format (JSON or XML)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: providers\n      path: /administration/Namespaces(NamespaceID='{namespaceId}')/Providers\n      description: List available providers (models) for data export.\n      operations:\n      - name: list-providers\n        method: GET\n        description: List available providers (models) in a namespace.\n        inputParameters:\n        - name: namespaceId\n          in: path\n          type: string\n\
  \          required: true\n          description: The namespace identifier (typically 'sac')\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Records to skip for pagination\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-metadata\n      path: /providers/sac/{modelId}/$metadata\n      description: OData metadata for a specific model.\n      operations:\n      - name: get-model-metadata\n        method: GET\n        description: Get OData metadata for a model describing its structure.\n        inputParameters:\n        - name: modelId\n\
  \          in: path\n          type: string\n          required: true\n          description: The unique provider (model) identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fact-data\n      path: /providers/sac/{modelId}/FactData\n      description: Fact data from a specific model.\n      operations:\n      - name: get-fact-data\n        method: GET\n        description: Retrieve fact data (transactional records) from a model.\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: The unique provider (model) identifier\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Records to skip for\
  \ pagination\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Comma-separated properties to include\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: master-data\n      path: /providers/sac/{modelId}/MasterData\n      description: Master data from a specific model.\n      operations:\n      - name: get-master-data\n        method: GET\n        description: Retrieve master data overview from a model.\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: The unique provider (model) identifier\n        - name: $top\n          in: query\n          type: integer\n          required: false\n         \
  \ description: Maximum records to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: businessobjects-bi-platform\n    baseUri: http://{server}:{port}/biprws\n    description: SAP BusinessObjects BI Platform RESTful Web Services for report management and CMS repository access.\n    authentication:\n      type: apikey\n      key: X-SAP-LogonToken\n      value: '{{SAP_BOBJ_LOGON_TOKEN}}'\n      placement: header\n    resources:\n    - name: authentication\n      path: /logon/long\n      description: Logon and logoff for session token management.\n      operations:\n      - name: logon\n        method: POST\n        description: Authenticate and obtain a logon token for subsequent API calls.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n     \
  \       userName: '{{tools.userName}}'\n            password: '{{tools.password}}'\n            auth: secEnterprise\n      - name: logoff\n        method: POST\n        description: Invalidate the current logon token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: infostore\n      path: /v1/infostore\n      description: Browse and query the CMS InfoStore repository.\n      operations:\n      - name: get-infostore-root\n        method: GET\n        description: Get the root entry of the InfoStore repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-infostore-object\n        method: GET\n        description: Get a specific InfoStore object by its CMS ID.\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description:\
  \ The CMS object identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-infostore-children\n        method: GET\n        description: List children of a specific InfoStore folder.\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The CMS object identifier of the parent\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number (1-based)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cms-query\n      path: /v1/cmsquery\n      description: Execute CMS queries against the BI Platform repository.\n\
  \      operations:\n      - name: execute-cms-query\n        method: POST\n        description: Execute a CMS query against the BI Platform repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n    - name: scheduling\n      path: /v1/infostore/{documentId}/scheduleForms/now\n      description: Schedule documents for execution.\n      operations:\n      - name: schedule-document\n        method: POST\n        description: Schedule a document for immediate execution.\n        inputParameters:\n        - name: documentId\n          in: path\n          type: string\n          required: true\n          description: The CMS ID of the document to schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            format: '{{tools.format}}'\n    - name: inbox\n      path: /v1/inbox\n      description: BI Inbox items.\n      operations:\n      - name: list-inbox-items\n        method: GET\n        description: List items in the authenticated user's BI Inbox.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: data-extraction-reporting-api\n    description: Unified REST API for SAP data extraction and BI report management.\n    resources:\n    - path: /v1/namespaces\n      name: namespaces\n      description: Data export namespaces.\n      operations:\n      - method: GET\n        name: list-namespaces\n        description: List available namespaces for data export.\n        call:\
  \ analytics-cloud-data-export.list-namespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespaceId}/providers\n      name: providers\n      description: Model providers for data export.\n      operations:\n      - method: GET\n        name: list-providers\n        description: List available models (providers) for data export.\n        call: analytics-cloud-data-export.list-providers\n        with:\n          namespaceId: rest.namespaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{modelId}/fact-data\n      name: fact-data\n      description: Model fact data.\n      operations:\n      - method: GET\n        name: get-fact-data\n        description: Extract fact data from a planning model.\n        call: analytics-cloud-data-export.get-fact-data\n        with:\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/models/{modelId}/master-data\n      name: master-data\n      description: Model master data.\n      operations:\n      - method: GET\n        name: get-master-data\n        description: Extract master data (dimension members) from a model.\n        call: analytics-cloud-data-export.get-master-data\n        with:\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: BusinessObjects report repository.\n      operations:\n      - method: GET\n        name: browse-reports\n        description: Browse reports in the InfoStore repository.\n        call: businessobjects-bi-platform.get-infostore-root\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{reportId}/schedule\n      name: report-schedule\n      description: Schedule a report for execution.\n      operations:\n      - method: POST\n        name: schedule-report\n\
  \        description: Schedule a BusinessObjects report for immediate execution.\n        call: businessobjects-bi-platform.schedule-document\n        with:\n          documentId: rest.reportId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inbox\n      name: inbox\n      description: BI user inbox.\n      operations:\n      - method: GET\n        name: list-inbox-items\n        description: List completed report instances in the BI Inbox.\n        call: businessobjects-bi-platform.list-inbox-items\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: data-extraction-reporting-mcp\n    transport: http\n    description: MCP server for AI-assisted data extraction and BI report management.\n    tools:\n    - name: list-export-models\n      description: List analytics models available for data export from SAP Analytics Cloud.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: analytics-cloud-data-export.list-providers\n      with:\n        namespaceId: tools.namespaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-model-metadata\n      description: Get OData metadata describing the structure of a planning model.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: analytics-cloud-data-export.get-model-metadata\n      with:\n        modelId: tools.modelId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extract-fact-data\n      description: Extract fact data (transactional records) from an analytics model.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: analytics-cloud-data-export.get-fact-data\n      with:\n        modelId: tools.modelId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extract-master-data\n      description: Extract master data (dimension members) from an analytics model.\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: analytics-cloud-data-export.get-master-data\n      with:\n        modelId: tools.modelId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-reports\n      description: Search for BusinessObjects reports and documents in the CMS repository.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: businessobjects-bi-platform.execute-cms-query\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-report\n      description: Schedule a BusinessObjects report for immediate execution.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: businessobjects-bi-platform.schedule-document\n      with:\n        documentId: tools.documentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-inbox-items\n   \
  \   description: List completed report instances in the user's BI Inbox.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: businessobjects-bi-platform.list-inbox-items\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-bi-tools/refs/heads/main/capabilities/data-extraction-and-reporting.yaml
tags:
- Analytics
- Business Intelligence
- Data Export
- Reporting
- SAP
tools:
- description: List analytics models available for data export from SAP Analytics Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-export-models
- description: Get OData metadata describing the structure of a planning model.
  hints:
    openWorld: false
    readOnly: true
  name: get-model-metadata
- description: Extract fact data (transactional records) from an analytics model.
  hints:
    openWorld: false
    readOnly: true
  name: extract-fact-data
- description: Extract master data (dimension members) from an analytics model.
  hints:
    openWorld: false
    readOnly: true
  name: extract-master-data
- description: Search for BusinessObjects reports and documents in the CMS repository.
  hints:
    openWorld: true
    readOnly: true
  name: search-reports
- description: Schedule a BusinessObjects report for immediate execution.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: schedule-report
- description: List completed report instances in the user's BI Inbox.
  hints:
    openWorld: true
    readOnly: true
  name: list-inbox-items
---
