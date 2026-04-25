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
- list attachments
- delete an attachment and its file content.
- digital workflows
- get attachment
- single attachment operations.
- cloud services
- workflow automation
- attachments
- insert multiple import set records
- processes
- insert import set record
- insert a single record into an import set staging table.
- data integration
- list file attachment metadata.
- upload a file as a binary stream attached to a record.
- get cmdb instance
- enterprise platform
- single ci operations.
- retrieve full details of a configuration item.
- automation
- list attachments.
- it service management
- bulk import operations.
- get metadata for a specific attachment.
- download attachment file
- insert a record into a staging table.
- itsm
- insert multiple records into an import set staging table.
- etl
- list cis by class.
- cmdb
- download the binary file content of an attachment.
- servicenow
- configuration management
- get attachment metadata.
- insert multiple records into a staging table.
- delete an attachment.
- cmdb configuration item operations.
- file attachment operations.
- list configuration items by cmdb class.
- workflows
- import set operations.
- delete attachment
- get a specific ci.
- upload attachment binary
- list cmdb instances
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
