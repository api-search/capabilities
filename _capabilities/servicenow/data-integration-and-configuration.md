---
categories:
- data-engineering
consumed_apis: []
description: Unified workflow for data integration and configuration management combining import sets for ETL, CMDB for configuration items, and attachment management. Used by integration engineers and CMDB administrators.
layout: capability
name: ServiceNow Data Integration And Configuration
operations:
- description: Insert a record into a staging table.
  method: POST
  name: insert-import-set-record
  path: /v1/import-sets/{stagingTableName}
- description: Insert multiple records into a staging table.
  method: POST
  name: insert-multiple-import-set-records
  path: /v1/import-sets/{stagingTableName}/bulk
- description: List CIs by class.
  method: GET
  name: list-cmdb-instances
  path: /v1/cmdb-instances/{className}
- description: Get a specific CI.
  method: GET
  name: get-cmdb-instance
  path: /v1/cmdb-instances/{className}/{sys_id}
- description: List attachments.
  method: GET
  name: list-attachments
  path: /v1/attachments
- description: Get attachment metadata.
  method: GET
  name: get-attachment
  path: /v1/attachments/{sys_id}
- description: Delete an attachment.
  method: DELETE
  name: delete-attachment
  path: /v1/attachments/{sys_id}
personas: []
provider_name: ServiceNow
provider_slug: servicenow
search_terms:
- configuration management
- list cmdb instances
- get attachment metadata.
- data integration
- it service management
- insert multiple records into a staging table.
- insert a single record into an import set staging table.
- list file attachment metadata.
- insert a record into a staging table.
- get attachment
- import set operations.
- upload attachment binary
- list attachments
- get metadata for a specific attachment.
- cloud services
- attachments
- cmdb
- insert import set record
- list cis by class.
- list configuration items by cmdb class.
- etl
- get a specific ci.
- enterprise platform
- digital workflows
- servicenow
- single attachment operations.
- delete an attachment.
- delete attachment
- insert multiple records into an import set staging table.
- delete an attachment and its file content.
- bulk import operations.
- itsm
- insert multiple import set records
- processes
- list attachments.
- t1
- workflow automation
- file attachment operations.
- workflows
- download the binary file content of an attachment.
- download attachment file
- retrieve full details of a configuration item.
- cmdb configuration item operations.
- upload a file as a binary stream attached to a record.
- single ci operations.
- get cmdb instance
- automation
slug: data-integration-and-configuration
source_filename: data-integration-and-configuration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ServiceNow Data Integration And Configuration\n  description: Unified workflow for data integration and configuration management combining import sets for ETL, CMDB for\n    configuration items, and attachment management. Used by integration engineers and CMDB administrators.\n  tags:\n  - ServiceNow\n  - Data Integration\n  - CMDB\n  - ETL\n  - Attachments\n  - Configuration Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SERVICENOW_USERNAME: SERVICENOW_USERNAME\n    SERVICENOW_PASSWORD: SERVICENOW_PASSWORD\n    SERVICENOW_INSTANCE: SERVICENOW_INSTANCE\ncapability:\n  consumes:\n  - type: http\n    namespace: servicenow-import-set\n    baseUri: https://{{SERVICENOW_INSTANCE}}.service-now.com/api/now\n    description: ServiceNow Import Set API for bulk data loading and ETL workflows.\n    authentication:\n      type: basic\n      username: '{{SERVICENOW_USERNAME}}'\n      password:\
  \ '{{SERVICENOW_PASSWORD}}'\n    resources:\n    - name: import-sets\n      path: /import\n      description: Import set staging table operations.\n      operations:\n      - name: insert-import-set-record\n        method: POST\n        path: /{stagingTableName}\n        description: Insert a single record into an import set staging table.\n        inputParameters:\n        - name: stagingTableName\n          in: path\n          type: string\n          required: true\n          description: The name of the import set staging table.\n        body:\n          type: json\n          data: '{{tools.record_data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: insert-multiple-import-set-records\n        method: POST\n        path: /{stagingTableName}/insertMultiple\n        description: Insert multiple records into an import set staging table.\n        inputParameters:\n        - name: stagingTableName\n\
  \          in: path\n          type: string\n          required: true\n          description: The name of the import set staging table.\n        body:\n          type: json\n          data:\n            records: '{{tools.records}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n  - type: http\n    namespace: servicenow-cmdb-instance\n    baseUri: https://{{SERVICENOW_INSTANCE}}.service-now.com/api/now/cmdb\n    description: ServiceNow CMDB Instance API for querying configuration items.\n    authentication:\n      type: basic\n      username: '{{SERVICENOW_USERNAME}}'\n      password: '{{SERVICENOW_PASSWORD}}'\n    resources:\n    - name: cmdb-instances\n      path: /instance\n      description: Configuration item instance operations.\n      operations:\n      - name: list-cmdb-instances\n        method: GET\n        path: /{className}\n        description: List configuration items by CMDB class.\n  \
  \      inputParameters:\n        - name: className\n          in: path\n          type: string\n          required: true\n          description: The CMDB class name (e.g., cmdb_ci_server, cmdb_ci_linux_server).\n        - name: sysparm_query\n          in: query\n          type: string\n          required: false\n          description: Encoded query string to filter CI records.\n        - name: sysparm_limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return.\n        - name: sysparm_offset\n          in: query\n          type: integer\n          required: false\n          description: Starting record index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: get-cmdb-instance\n        method: GET\n        path: /{className}/{sys_id}\n        description: Retrieve full details of a specific configuration\
  \ item.\n        inputParameters:\n        - name: className\n          in: path\n          type: string\n          required: true\n          description: The CMDB class name.\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The unique sys_id of the configuration item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n  - type: http\n    namespace: servicenow-attachment\n    baseUri: https://{{SERVICENOW_INSTANCE}}.service-now.com/api/now\n    description: ServiceNow Attachment API for managing file attachments on records.\n    authentication:\n      type: basic\n      username: '{{SERVICENOW_USERNAME}}'\n      password: '{{SERVICENOW_PASSWORD}}'\n    resources:\n    - name: attachments\n      path: /attachment\n      description: File attachment operations.\n      operations:\n      - name: list-attachments\n        method: GET\n    \
  \    description: Retrieve metadata for file attachments with optional filtering.\n        inputParameters:\n        - name: sysparm_query\n          in: query\n          type: string\n          required: false\n          description: Encoded query string to filter attachments.\n        - name: sysparm_limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of attachment records to return.\n        - name: sysparm_offset\n          in: query\n          type: integer\n          required: false\n          description: Starting record index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: get-attachment\n        method: GET\n        path: /{sys_id}\n        description: Retrieve metadata for a single attachment by sys_id.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n\
  \          required: true\n          description: The unique system identifier for the attachment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: delete-attachment\n        method: DELETE\n        path: /{sys_id}\n        description: Delete an attachment and its file content.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The unique system identifier for the attachment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: download-attachment-file\n        method: GET\n        path: /{sys_id}/file\n        description: Download the binary file content of an attachment.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ The unique system identifier for the attachment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-attachment-binary\n        method: POST\n        path: /file\n        description: Upload a file as a binary stream attached to a table record.\n        inputParameters:\n        - name: table_name\n          in: query\n          type: string\n          required: true\n          description: The table to which the file is attached.\n        - name: table_sys_id\n          in: query\n          type: string\n          required: true\n          description: The sys_id of the record to attach the file to.\n        - name: file_name\n          in: query\n          type: string\n          required: true\n          description: The file name including extension.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n \
  \ exposes:\n  - type: rest\n    port: 8082\n    namespace: servicenow-data-integration-api\n    description: Unified REST API for ServiceNow data integration and configuration management.\n    resources:\n    - path: /v1/import-sets/{stagingTableName}\n      name: import-sets\n      description: Import set operations.\n      operations:\n      - method: POST\n        name: insert-import-set-record\n        description: Insert a record into a staging table.\n        call: servicenow-import-set.insert-import-set-record\n        with:\n          stagingTableName: rest.stagingTableName\n          record_data: rest.body\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/import-sets/{stagingTableName}/bulk\n      name: import-sets-bulk\n      description: Bulk import operations.\n      operations:\n      - method: POST\n        name: insert-multiple-import-set-records\n        description: Insert multiple records into a staging table.\n        call:\
  \ servicenow-import-set.insert-multiple-import-set-records\n        with:\n          stagingTableName: rest.stagingTableName\n          records: rest.records\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/cmdb-instances/{className}\n      name: cmdb-instances\n      description: CMDB configuration item operations.\n      operations:\n      - method: GET\n        name: list-cmdb-instances\n        description: List CIs by class.\n        call: servicenow-cmdb-instance.list-cmdb-instances\n        with:\n          className: rest.className\n          sysparm_query: rest.sysparm_query\n          sysparm_limit: rest.sysparm_limit\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/cmdb-instances/{className}/{sys_id}\n      name: cmdb-instance-detail\n      description: Single CI operations.\n      operations:\n      - method: GET\n        name: get-cmdb-instance\n        description: Get a specific\
  \ CI.\n        call: servicenow-cmdb-instance.get-cmdb-instance\n        with:\n          className: rest.className\n          sys_id: rest.sys_id\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/attachments\n      name: attachments\n      description: File attachment operations.\n      operations:\n      - method: GET\n        name: list-attachments\n        description: List attachments.\n        call: servicenow-attachment.list-attachments\n        with:\n          sysparm_query: rest.sysparm_query\n          sysparm_limit: rest.sysparm_limit\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/attachments/{sys_id}\n      name: attachment-detail\n      description: Single attachment operations.\n      operations:\n      - method: GET\n        name: get-attachment\n        description: Get attachment metadata.\n        call: servicenow-attachment.get-attachment\n        with:\n          sys_id:\
  \ rest.sys_id\n        outputParameters:\n        - type: object\n          mapping: $.result\n      - method: DELETE\n        name: delete-attachment\n        description: Delete an attachment.\n        call: servicenow-attachment.delete-attachment\n        with:\n          sys_id: rest.sys_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: servicenow-data-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted ServiceNow data integration and CMDB management.\n    tools:\n    - name: insert-import-set-record\n      description: Insert a single record into an import set staging table.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-import-set.insert-import-set-record\n      with:\n        stagingTableName: tools.stagingTableName\n        record_data: tools.record_data\n      outputParameters:\n      - type: object\n        mapping: $.result\n    -\
  \ name: insert-multiple-import-set-records\n      description: Insert multiple records into an import set staging table.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-import-set.insert-multiple-import-set-records\n      with:\n        stagingTableName: tools.stagingTableName\n        records: tools.records\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-cmdb-instances\n      description: List configuration items by CMDB class.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-cmdb-instance.list-cmdb-instances\n      with:\n        className: tools.className\n        sysparm_query: tools.sysparm_query\n        sysparm_limit: tools.sysparm_limit\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-cmdb-instance\n      description: Retrieve full details of a configuration item.\n      hints:\n        readOnly:\
  \ true\n        idempotent: true\n      call: servicenow-cmdb-instance.get-cmdb-instance\n      with:\n        className: tools.className\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-attachments\n      description: List file attachment metadata.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-attachment.list-attachments\n      with:\n        sysparm_query: tools.sysparm_query\n        sysparm_limit: tools.sysparm_limit\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-attachment\n      description: Get metadata for a specific attachment.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: servicenow-attachment.get-attachment\n      with:\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: download-attachment-file\n  \
  \    description: Download the binary file content of an attachment.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: servicenow-attachment.download-attachment-file\n      with:\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-attachment\n      description: Delete an attachment and its file content.\n      hints:\n        destructive: true\n        idempotent: true\n      call: servicenow-attachment.delete-attachment\n      with:\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-attachment-binary\n      description: Upload a file as a binary stream attached to a record.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-attachment.upload-attachment-binary\n      with:\n        table_name: tools.table_name\n        table_sys_id: tools.table_sys_id\n        file_name: tools.file_name\n \
  \     outputParameters:\n      - type: object\n        mapping: $.result\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/servicenow/refs/heads/main/capabilities/data-integration-and-configuration.yaml
tags:
- ServiceNow
- Data Integration
- CMDB
- ETL
- Attachments
- Configuration Management
tools:
- description: Insert a single record into an import set staging table.
  hints:
    idempotent: false
    readOnly: false
  name: insert-import-set-record
- description: Insert multiple records into an import set staging table.
  hints:
    idempotent: false
    readOnly: false
  name: insert-multiple-import-set-records
- description: List configuration items by CMDB class.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-cmdb-instances
- description: Retrieve full details of a configuration item.
  hints:
    idempotent: true
    readOnly: true
  name: get-cmdb-instance
- description: List file attachment metadata.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-attachments
- description: Get metadata for a specific attachment.
  hints:
    idempotent: true
    readOnly: true
  name: get-attachment
- description: Download the binary file content of an attachment.
  hints:
    idempotent: true
    readOnly: true
  name: download-attachment-file
- description: Delete an attachment and its file content.
  hints:
    destructive: true
    idempotent: true
  name: delete-attachment
- description: Upload a file as a binary stream attached to a record.
  hints:
    idempotent: false
    readOnly: false
  name: upload-attachment-binary
---
