---
categories:
- data-engineering
consumed_apis:
- servicenow-import-set
- servicenow-cmdb-instance
- servicenow-attachment
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
- get attachment
- configuration management
- servicenow
- cmdb
- it service management
- t1
- insert a single record into an import set staging table.
- automation
- list attachments.
- upload a file as a binary stream attached to a record.
- data integration
- insert import set record
- get attachment metadata.
- get metadata for a specific attachment.
- list file attachment metadata.
- processes
- workflows
- insert multiple import set records
- enterprise platform
- insert multiple records into a staging table.
- cmdb configuration item operations.
- insert multiple records into an import set staging table.
- get cmdb instance
- import set operations.
- single ci operations.
- digital workflows
- etl
- attachments
- insert a record into a staging table.
- itsm
- file attachment operations.
- delete an attachment and its file content.
- list attachments
- upload attachment binary
- retrieve full details of a configuration item.
- workflow automation
- single attachment operations.
- list cis by class.
- get a specific ci.
- bulk import operations.
- download attachment file
- list cmdb instances
- delete attachment
- cloud services
- delete an attachment.
- list configuration items by cmdb class.
- download the binary file content of an attachment.
slug: data-integration-and-configuration
source_filename: data-integration-and-configuration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ServiceNow Data Integration And Configuration\"\n  description: \"Unified workflow for data integration and configuration management combining import sets for ETL, CMDB for configuration items, and attachment management. Used by integration engineers and CMDB administrators.\"\n  tags:\n    - ServiceNow\n    - Data Integration\n    - CMDB\n    - ETL\n    - Attachments\n    - Configuration Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SERVICENOW_USERNAME: SERVICENOW_USERNAME\n      SERVICENOW_PASSWORD: SERVICENOW_PASSWORD\n      SERVICENOW_INSTANCE: SERVICENOW_INSTANCE\n\ncapability:\n  consumes:\n    - import: servicenow-import-set\n      location: ./shared/import-set.yaml\n    - import: servicenow-cmdb-instance\n      location: ./shared/cmdb-instance.yaml\n    - import: servicenow-attachment\n      location: ./shared/attachment.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8082\n      namespace: servicenow-data-integration-api\n      description: \"Unified REST API for ServiceNow data integration and configuration management.\"\n      resources:\n        - path: /v1/import-sets/{stagingTableName}\n          name: import-sets\n          description: \"Import set operations.\"\n          operations:\n            - method: POST\n              name: insert-import-set-record\n              description: \"Insert a record into a staging table.\"\n              call: \"servicenow-import-set.insert-import-set-record\"\n              with:\n                stagingTableName: \"rest.stagingTableName\"\n                record_data: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/import-sets/{stagingTableName}/bulk\n          name: import-sets-bulk\n          description: \"Bulk import operations.\"\n          operations:\n            - method: POST\n     \
  \         name: insert-multiple-import-set-records\n              description: \"Insert multiple records into a staging table.\"\n              call: \"servicenow-import-set.insert-multiple-import-set-records\"\n              with:\n                stagingTableName: \"rest.stagingTableName\"\n                records: \"rest.records\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/cmdb-instances/{className}\n          name: cmdb-instances\n          description: \"CMDB configuration item operations.\"\n          operations:\n            - method: GET\n              name: list-cmdb-instances\n              description: \"List CIs by class.\"\n              call: \"servicenow-cmdb-instance.list-cmdb-instances\"\n              with:\n                className: \"rest.className\"\n                sysparm_query: \"rest.sysparm_query\"\n                sysparm_limit: \"rest.sysparm_limit\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/cmdb-instances/{className}/{sys_id}\n          name: cmdb-instance-detail\n          description: \"Single CI operations.\"\n          operations:\n            - method: GET\n              name: get-cmdb-instance\n              description: \"Get a specific CI.\"\n              call: \"servicenow-cmdb-instance.get-cmdb-instance\"\n              with:\n                className: \"rest.className\"\n                sys_id: \"rest.sys_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/attachments\n          name: attachments\n          description: \"File attachment operations.\"\n          operations:\n            - method: GET\n              name: list-attachments\n              description: \"List attachments.\"\n              call: \"servicenow-attachment.list-attachments\"\n              with:\n                sysparm_query:\
  \ \"rest.sysparm_query\"\n                sysparm_limit: \"rest.sysparm_limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/attachments/{sys_id}\n          name: attachment-detail\n          description: \"Single attachment operations.\"\n          operations:\n            - method: GET\n              name: get-attachment\n              description: \"Get attachment metadata.\"\n              call: \"servicenow-attachment.get-attachment\"\n              with:\n                sys_id: \"rest.sys_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n            - method: DELETE\n              name: delete-attachment\n              description: \"Delete an attachment.\"\n              call: \"servicenow-attachment.delete-attachment\"\n              with:\n                sys_id: \"rest.sys_id\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: servicenow-data-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted ServiceNow data integration and CMDB management.\"\n      tools:\n        - name: insert-import-set-record\n          description: \"Insert a single record into an import set staging table.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-import-set.insert-import-set-record\"\n          with:\n            stagingTableName: \"tools.stagingTableName\"\n            record_data: \"tools.record_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: insert-multiple-import-set-records\n          description: \"Insert multiple records into an import set staging table.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-import-set.insert-multiple-import-set-records\"\
  \n          with:\n            stagingTableName: \"tools.stagingTableName\"\n            records: \"tools.records\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: list-cmdb-instances\n          description: \"List configuration items by CMDB class.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-cmdb-instance.list-cmdb-instances\"\n          with:\n            className: \"tools.className\"\n            sysparm_query: \"tools.sysparm_query\"\n            sysparm_limit: \"tools.sysparm_limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: get-cmdb-instance\n          description: \"Retrieve full details of a configuration item.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-cmdb-instance.get-cmdb-instance\"\n   \
  \       with:\n            className: \"tools.className\"\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: list-attachments\n          description: \"List file attachment metadata.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-attachment.list-attachments\"\n          with:\n            sysparm_query: \"tools.sysparm_query\"\n            sysparm_limit: \"tools.sysparm_limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: get-attachment\n          description: \"Get metadata for a specific attachment.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-attachment.get-attachment\"\n          with:\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.result\"\n        - name: download-attachment-file\n          description: \"Download the binary file content of an attachment.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-attachment.download-attachment-file\"\n          with:\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-attachment\n          description: \"Delete an attachment and its file content.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"servicenow-attachment.delete-attachment\"\n          with:\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: upload-attachment-binary\n          description: \"Upload a file as a binary stream attached to a record.\"\n          hints:\n            readOnly:\
  \ false\n            idempotent: false\n          call: \"servicenow-attachment.upload-attachment-binary\"\n          with:\n            table_name: \"tools.table_name\"\n            table_sys_id: \"tools.table_sys_id\"\n            file_name: \"tools.file_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n"
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
