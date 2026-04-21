---
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
- get a specific ci.
- delete an attachment.
- cloud services
- list file attachment metadata.
- download attachment file
- data integration
- delete attachment
- file attachment operations.
- enterprise platform
- it service management
- workflows
- delete an attachment and its file content.
- insert multiple records into an import set staging table.
- itsm
- automation
- get attachment metadata.
- insert multiple import set records
- bulk import operations.
- upload attachment binary
- configuration management
- servicenow
- get attachment
- list attachments
- single attachment operations.
- single ci operations.
- retrieve full details of a configuration item.
- list attachments.
- download the binary file content of an attachment.
- upload a file as a binary stream attached to a record.
- cmdb
- workflow automation
- list configuration items by cmdb class.
- attachments
- insert a single record into an import set staging table.
- get metadata for a specific attachment.
- insert multiple records into a staging table.
- list cmdb instances
- get cmdb instance
- cmdb configuration item operations.
- insert a record into a staging table.
- import set operations.
- processes
- insert import set record
- list cis by class.
- digital workflows
- etl
- t1
slug: data-integration-and-configuration
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
