---
categories: []
consumed_apis: []
description: The Azure Blob Storage REST API provides programmatic access to unstructured data storage in Azure. It supports operations on the Blob service, containers, and blobs, including block blobs, append blobs, and page blobs. Blobs can store any type of text or binary data such as documents, media files, and application installers. Blob Storage is optimized for storing massive amounts of unstructured data accessible via HTTP or HTTPS from anywhere in the world.
layout: capability
name: Azure Blob Storage REST API
operations:
- description: Azure Blob Storage List containers
  method: GET
  name: listcontainers
  path: /
- description: Azure Blob Storage Get Blob service properties
  method: GET
  name: getblobserviceproperties
  path: /?restype=service&comp=properties
- description: Azure Blob Storage Set Blob service properties
  method: PUT
  name: setblobserviceproperties
  path: /?restype=service&comp=properties
- description: Azure Blob Storage Get Blob service stats
  method: GET
  name: getblobservicestats
  path: /?restype=service&comp=stats
- description: Azure Blob Storage Get user delegation key
  method: POST
  name: getuserdelegationkey
  path: /?restype=service&comp=userdelegationkey
- description: Azure Blob Storage Submit blob batch
  method: POST
  name: submitblobbatch
  path: /?restype=service&comp=batch
- description: Azure Blob Storage Find blobs by tags
  method: GET
  name: findblobsbytags
  path: /?comp=blobs
- description: Azure Blob Storage Create container
  method: PUT
  name: createcontainer
  path: /{container}
- description: Azure Blob Storage Get container properties
  method: GET
  name: getcontainerproperties
  path: /{container}
- description: Azure Blob Storage Delete container
  method: DELETE
  name: deletecontainer
  path: /{container}
- description: Azure Blob Storage List blobs
  method: GET
  name: listblobs
  path: /{container}?restype=container&comp=list
- description: Azure Blob Storage Get container metadata
  method: GET
  name: getcontainermetadata
  path: /{container}?restype=container&comp=metadata
- description: Azure Blob Storage Set container metadata
  method: PUT
  name: setcontainermetadata
  path: /{container}?restype=container&comp=metadata
- description: Azure Blob Storage Get container ACL
  method: GET
  name: getcontaineracl
  path: /{container}?restype=container&comp=acl
- description: Azure Blob Storage Set container ACL
  method: PUT
  name: setcontaineracl
  path: /{container}?restype=container&comp=acl
- description: Azure Blob Storage Lease container
  method: PUT
  name: leasecontainer
  path: /{container}?restype=container&comp=lease
- description: Azure Blob Storage Restore container
  method: PUT
  name: restorecontainer
  path: /{container}?restype=container&comp=undelete
- description: Azure Blob Storage Put blob
  method: PUT
  name: putblob
  path: /{container}/{blob}
- description: Azure Blob Storage Get blob
  method: GET
  name: getblob
  path: /{container}/{blob}
- description: Azure Blob Storage Delete blob
  method: DELETE
  name: deleteblob
  path: /{container}/{blob}
- description: Azure Blob Storage Get blob metadata
  method: GET
  name: getblobmetadata
  path: /{container}/{blob}?comp=metadata
- description: Azure Blob Storage Set blob metadata
  method: PUT
  name: setblobmetadata
  path: /{container}/{blob}?comp=metadata
- description: Azure Blob Storage Set blob HTTP headers
  method: PUT
  name: setblobhttpheaders
  path: /{container}/{blob}?comp=properties
- description: Azure Blob Storage Get blob tags
  method: GET
  name: getblobtags
  path: /{container}/{blob}?comp=tags
- description: Azure Blob Storage Set blob tags
  method: PUT
  name: setblobtags
  path: /{container}/{blob}?comp=tags
- description: Azure Blob Storage Lease blob
  method: PUT
  name: leaseblob
  path: /{container}/{blob}?comp=lease
- description: Azure Blob Storage Snapshot blob
  method: PUT
  name: snapshotblob
  path: /{container}/{blob}?comp=snapshot
- description: Azure Blob Storage Copy blob
  method: PUT
  name: copyblob
  path: /{container}/{blob}?comp=copy
- description: Azure Blob Storage Abort copy blob
  method: PUT
  name: abortcopyblob
  path: /{container}/{blob}?comp=copy&copyid={copyId}
- description: Azure Blob Storage Undelete blob
  method: PUT
  name: undeleteblob
  path: /{container}/{blob}?comp=undelete
- description: Azure Blob Storage Set blob tier
  method: PUT
  name: setblobtier
  path: /{container}/{blob}?comp=tier
- description: Azure Blob Storage Set blob immutability policy
  method: PUT
  name: setblobimmutabilitypolicy
  path: /{container}/{blob}?comp=immutabilityPolicies
- description: Azure Blob Storage Delete blob immutability policy
  method: DELETE
  name: deleteblobimmutabilitypolicy
  path: /{container}/{blob}?comp=immutabilityPolicies
- description: Azure Blob Storage Set blob legal hold
  method: PUT
  name: setbloblegalhold
  path: /{container}/{blob}?comp=legalhold
- description: Azure Blob Storage Put block
  method: PUT
  name: putblock
  path: /{container}/{blob}?comp=block
- description: Azure Blob Storage Put block list
  method: PUT
  name: putblocklist
  path: /{container}/{blob}?comp=blocklist
- description: Azure Blob Storage Get block list
  method: GET
  name: getblocklist
  path: /{container}/{blob}?comp=blocklist
- description: Azure Blob Storage Put block from URL
  method: PUT
  name: putblockfromurl
  path: /{container}/{blob}?comp=block&fromURL
- description: Azure Blob Storage Put page
  method: PUT
  name: putpage
  path: /{container}/{blob}?comp=page
- description: Azure Blob Storage Get page ranges
  method: GET
  name: getpageranges
  path: /{container}/{blob}?comp=pagelist
- description: Azure Blob Storage Get page ranges diff
  method: GET
  name: getpagerangesdiff
  path: /{container}/{blob}?comp=pagelist&diff
- description: Azure Blob Storage Incremental copy blob
  method: PUT
  name: incrementalcopyblob
  path: /{container}/{blob}?comp=incrementalcopy
- description: Azure Blob Storage Append block
  method: PUT
  name: appendblock
  path: /{container}/{blob}?comp=appendblock
- description: Azure Blob Storage Append block from URL
  method: PUT
  name: appendblockfromurl
  path: /{container}/{blob}?comp=appendblock&fromURL
personas: []
provider_name: Azure Blob Storage
provider_slug: microsoft-azure-blob-storage
search_terms:
- azure blob storage get block list
- getblobmetadata
- setblobhttpheaders
- azure blob storage snapshot blob
- api
- getblocklist
- deleteblob
- azure blob storage get user delegation key
- azure blob storage get container metadata
- leaseblob
- undeleteblob
- microsoft
- getblobserviceproperties
- getblob
- azure blob storage set blob metadata
- azure blob storage set container metadata
- azure blob storage put block
- azure blob storage delete container
- getpagerangesdiff
- findblobsbytags
- azure blob storage lease container
- azure blob storage append block from url
- azure blob storage incremental copy blob
- blobs
- setcontaineracl
- putblockfromurl
- azure blob storage get container acl
- setblobserviceproperties
- azure blob storage abort copy blob
- azure blob storage submit blob batch
- azure blob storage delete blob immutability policy
- cloud storage
- azure blob storage get blob
- azure blob storage put blob
- azure blob storage get container properties
- blob
- createcontainer
- azure blob storage set blob service properties
- putblob
- object storage
- setblobtags
- appendblockfromurl
- getcontainermetadata
- appendblock
- storage
- getcontaineracl
- leasecontainer
- azure
- azure blob storage list blobs
- putblock
- azure blob storage restore container
- setblobtier
- azure blob storage set container acl
- listblobs
- azure blob storage put block from url
- setblobmetadata
- setcontainermetadata
- deleteblobimmutabilitypolicy
- azure blob storage get blob tags
- azure blob storage copy blob
- copyblob
- azure blob storage set blob legal hold
- azure blob storage put page
- azure blob storage get blob service properties
- getblobservicestats
- azure blob storage list containers
- deletecontainer
- snapshotblob
- incrementalcopyblob
- abortcopyblob
- azure blob storage get page ranges diff
- submitblobbatch
- azure blob storage get blob metadata
- azure blob storage put block list
- putpage
- setblobimmutabilitypolicy
- azure blob storage lease blob
- getblobtags
- getuserdelegationkey
- azure blob storage set blob http headers
- azure blob storage get page ranges
- azure blob storage set blob tier
- azure blob storage find blobs by tags
- restorecontainer
- azure blob storage create container
- azure blob storage get blob service stats
- getpageranges
- azure blob storage undelete blob
- setbloblegalhold
- listcontainers
- azure blob storage set blob immutability policy
- getcontainerproperties
- azure blob storage delete blob
- putblocklist
- azure blob storage append block
- azure blob storage set blob tags
slug: microsoft-azure-blob-storage-capability
source_filename: microsoft-azure-blob-storage-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Blob Storage REST API\n  description: The Azure Blob Storage REST API provides programmatic access to unstructured data storage in Azure. It supports\n    operations on the Blob service, containers, and blobs, including block blobs, append blobs, and page blobs. Blobs can\n    store any type of text or binary data such as documents, media files, and application installers. Blob Storage is optimized\n    for storing massive amounts of unstructured data accessible via HTTP or HTTPS from anywhere in the world.\n  tags:\n  - Microsoft\n  - Azure\n  - Blob\n  - Storage\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-azure-blob-storage\n    baseUri: https://mystorageaccount.blob.core.windows.net\n    description: Azure Blob Storage REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{MICROSOFT_AZURE_BLOB_STORAGE_TOKEN}}'\n\
  \    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: listcontainers\n        method: GET\n        description: Azure Blob Storage List containers\n        inputParameters:\n        - name: comp\n          in: query\n          type: string\n          required: true\n        - name: prefix\n          in: query\n          type: string\n          description: Filters results to return only containers whose names begin with the specified prefix.\n        - name: marker\n          in: query\n          type: string\n          description: Continuation token for retrieving the next page of results. Returned in the NextMarker element of a\n            previous response.\n        - name: maxresults\n          in: query\n          type: integer\n          description: Maximum number of containers to return in a single response. Defaults to 5000 if not specified.\n        - name: include\n          in: query\n          type: string\n          description: Specifies\
  \ additional datasets to include in the response such as metadata, deleted containers, or system\n            containers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restype-service-comp-properties\n      path: /?restype=service&comp=properties\n      operations:\n      - name: getblobserviceproperties\n        method: GET\n        description: Azure Blob Storage Get Blob service properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setblobserviceproperties\n        method: PUT\n        description: Azure Blob Storage Set Blob service properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restype-service-comp-stats\n      path: /?restype=service&comp=stats\n      operations:\n      - name: getblobservicestats\n\
  \        method: GET\n        description: Azure Blob Storage Get Blob service stats\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restype-service-comp-userdelegationkey\n      path: /?restype=service&comp=userdelegationkey\n      operations:\n      - name: getuserdelegationkey\n        method: POST\n        description: Azure Blob Storage Get user delegation key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restype-service-comp-batch\n      path: /?restype=service&comp=batch\n      operations:\n      - name: submitblobbatch\n        method: POST\n        description: Azure Blob Storage Submit blob batch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comp-blobs\n      path: /?comp=blobs\n      operations:\n  \
  \    - name: findblobsbytags\n        method: GET\n        description: Azure Blob Storage Find blobs by tags\n        inputParameters:\n        - name: where\n          in: query\n          type: string\n          required: true\n          description: SQL-like filter expression for blob index tags, for example \"tagkey\"='tagvalue'.\n        - name: marker\n          in: query\n          type: string\n          description: Continuation token for pagination.\n        - name: maxresults\n          in: query\n          type: integer\n          description: Maximum number of blobs to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container\n      path: /{container}\n      operations:\n      - name: createcontainer\n        method: PUT\n        description: Azure Blob Storage Create container\n        inputParameters:\n        - name: restype\n          in: query\n          type: string\n\
  \          required: true\n        - name: x-ms-blob-public-access\n          in: header\n          type: string\n          description: Specifies whether data in the container may be accessed publicly and the level of access.\n        - name: x-ms-default-encryption-scope\n          in: header\n          type: string\n          description: The default encryption scope for the container.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getcontainerproperties\n        method: GET\n        description: Azure Blob Storage Get container properties\n        inputParameters:\n        - name: restype\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontainer\n        method: DELETE\n        description: Azure Blob Storage Delete container\n\
  \        inputParameters:\n        - name: restype\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-restype-container-comp-list\n      path: /{container}?restype=container&comp=list\n      operations:\n      - name: listblobs\n        method: GET\n        description: Azure Blob Storage List blobs\n        inputParameters:\n        - name: prefix\n          in: query\n          type: string\n          description: Filters results to return only blobs whose names begin with the specified prefix.\n        - name: delimiter\n          in: query\n          type: string\n          description: Delimiter character used to traverse a virtual hierarchy of blobs as though it were a file system.\n        - name: marker\n          in: query\n          type: string\n          description: Continuation token for pagination.\n   \
  \     - name: maxresults\n          in: query\n          type: integer\n          description: Maximum number of blobs to return.\n        - name: include\n          in: query\n          type: string\n          description: Specifies additional datasets to include such as snapshots, metadata, uncommitted blobs, copy, deleted,\n            tags, versions, deletedwithversions, immutabilitypolicy,\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-restype-container-comp-metadata\n      path: /{container}?restype=container&comp=metadata\n      operations:\n      - name: getcontainermetadata\n        method: GET\n        description: Azure Blob Storage Get container metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setcontainermetadata\n        method: PUT\n        description: Azure Blob Storage\
  \ Set container metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-restype-container-comp-acl\n      path: /{container}?restype=container&comp=acl\n      operations:\n      - name: getcontaineracl\n        method: GET\n        description: Azure Blob Storage Get container ACL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setcontaineracl\n        method: PUT\n        description: Azure Blob Storage Set container ACL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-restype-container-comp-lease\n      path: /{container}?restype=container&comp=lease\n      operations:\n      - name: leasecontainer\n        method: PUT\n        description: Azure Blob Storage Lease container\n        inputParameters:\n\
  \        - name: x-ms-lease-action\n          in: header\n          type: string\n          required: true\n          description: The lease action to perform.\n        - name: x-ms-lease-duration\n          in: header\n          type: integer\n          description: Duration of the lease in seconds. Set to -1 for an infinite lease, or between 15 and 60 seconds for\n            a fixed-duration lease.\n        - name: x-ms-proposed-lease-id\n          in: header\n          type: string\n          description: Proposed lease ID in GUID format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-restype-container-comp-undelete\n      path: /{container}?restype=container&comp=undelete\n      operations:\n      - name: restorecontainer\n        method: PUT\n        description: Azure Blob Storage Restore container\n        inputParameters:\n        - name: x-ms-deleted-container-name\n       \
  \   in: header\n          type: string\n          required: true\n          description: The name of the deleted container to restore.\n        - name: x-ms-deleted-container-version\n          in: header\n          type: string\n          required: true\n          description: The version of the deleted container to restore.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob\n      path: /{container}/{blob}\n      operations:\n      - name: putblob\n        method: PUT\n        description: Azure Blob Storage Put blob\n        inputParameters:\n        - name: x-ms-blob-type\n          in: header\n          type: string\n          required: true\n          description: The type of blob to create.\n        - name: Content-Length\n          in: header\n          type: integer\n          description: The length of the request body in bytes. Required for page blobs (set to 0 with x-ms-blob-content-length\n\
  \            for the actual size).\n        - name: Content-Type\n          in: header\n          type: string\n          description: The MIME content type of the blob.\n        - name: x-ms-blob-content-type\n          in: header\n          type: string\n          description: The content type to set for the blob.\n        - name: x-ms-access-tier\n          in: header\n          type: string\n          description: The tier to set on the blob.\n        - name: x-ms-blob-content-length\n          in: header\n          type: integer\n          description: Required for page blobs. Specifies the maximum size for the page blob, up to 8 TiB. Must be aligned\n            to a 512-byte boundary.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getblob\n        method: GET\n        description: Azure Blob Storage Get blob\n        inputParameters:\n        - name: Range\n          in: header\n     \
  \     type: string\n          description: Return only the bytes of the blob in the specified range, for example bytes=0-1023.\n        - name: snapshot\n          in: query\n          type: string\n          description: The snapshot identifier. When specified, the operation returns the snapshot of the blob.\n        - name: versionid\n          in: query\n          type: string\n          description: The version ID. When specified, the operation returns the specified version of the blob.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteblob\n        method: DELETE\n        description: Azure Blob Storage Delete blob\n        inputParameters:\n        - name: x-ms-delete-snapshots\n          in: header\n          type: string\n          description: Required if the blob has associated snapshots. Specifies whether to delete the blob and all snapshots\n            (include) or only the snapshots\
  \ (only).\n        - name: snapshot\n          in: query\n          type: string\n          description: The snapshot identifier. When specified, only the snapshot is deleted.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-metadata\n      path: /{container}/{blob}?comp=metadata\n      operations:\n      - name: getblobmetadata\n        method: GET\n        description: Azure Blob Storage Get blob metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setblobmetadata\n        method: PUT\n        description: Azure Blob Storage Set blob metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-properties\n      path: /{container}/{blob}?comp=properties\n      operations:\n\
  \      - name: setblobhttpheaders\n        method: PUT\n        description: Azure Blob Storage Set blob HTTP headers\n        inputParameters:\n        - name: x-ms-blob-content-type\n          in: header\n          type: string\n          description: The MIME content type of the blob.\n        - name: x-ms-blob-content-encoding\n          in: header\n          type: string\n          description: The content encoding of the blob.\n        - name: x-ms-blob-content-language\n          in: header\n          type: string\n          description: The content language of the blob.\n        - name: x-ms-blob-cache-control\n          in: header\n          type: string\n          description: The cache control directive for the blob.\n        - name: x-ms-blob-content-disposition\n          in: header\n          type: string\n          description: The content disposition of the blob.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: container-blob-comp-tags\n      path: /{container}/{blob}?comp=tags\n      operations:\n      - name: getblobtags\n        method: GET\n        description: Azure Blob Storage Get blob tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setblobtags\n        method: PUT\n        description: Azure Blob Storage Set blob tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-lease\n      path: /{container}/{blob}?comp=lease\n      operations:\n      - name: leaseblob\n        method: PUT\n        description: Azure Blob Storage Lease blob\n        inputParameters:\n        - name: x-ms-lease-action\n          in: header\n          type: string\n          required: true\n          description: The lease action to perform.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-snapshot\n      path: /{container}/{blob}?comp=snapshot\n      operations:\n      - name: snapshotblob\n        method: PUT\n        description: Azure Blob Storage Snapshot blob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-copy\n      path: /{container}/{blob}?comp=copy\n      operations:\n      - name: copyblob\n        method: PUT\n        description: Azure Blob Storage Copy blob\n        inputParameters:\n        - name: x-ms-copy-source\n          in: header\n          type: string\n          required: true\n          description: URL of the source blob, up to 2 KiB in length.\n        - name: x-ms-access-tier\n          in: header\n          type: string\n          description: The tier to set on the destination blob.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-copy-copyid-copyid\n      path: /{container}/{blob}?comp=copy&copyid={copyId}\n      operations:\n      - name: abortcopyblob\n        method: PUT\n        description: Azure Blob Storage Abort copy blob\n        inputParameters:\n        - name: copyId\n          in: query\n          type: string\n          required: true\n          description: The copy operation identifier returned by the Copy Blob response.\n        - name: x-ms-copy-action\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-undelete\n      path: /{container}/{blob}?comp=undelete\n      operations:\n      - name: undeleteblob\n        method: PUT\n        description: Azure Blob Storage Undelete blob\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-tier\n      path: /{container}/{blob}?comp=tier\n      operations:\n      - name: setblobtier\n        method: PUT\n        description: Azure Blob Storage Set blob tier\n        inputParameters:\n        - name: x-ms-access-tier\n          in: header\n          type: string\n          required: true\n          description: The access tier to set for the blob.\n        - name: x-ms-rehydrate-priority\n          in: header\n          type: string\n          description: Priority of rehydration when moving a blob out of the Archive tier. Standard priority may take up to\n            15 hours, High priority within 1 hour at a higher cost.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-immutabilitypolicies\n      path: /{container}/{blob}?comp=immutabilityPolicies\n\
  \      operations:\n      - name: setblobimmutabilitypolicy\n        method: PUT\n        description: Azure Blob Storage Set blob immutability policy\n        inputParameters:\n        - name: x-ms-immutability-policy-until-date\n          in: header\n          type: string\n          required: true\n          description: The date until which the immutability policy is in effect.\n        - name: x-ms-immutability-policy-mode\n          in: header\n          type: string\n          required: true\n          description: The mode of the immutability policy.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteblobimmutabilitypolicy\n        method: DELETE\n        description: Azure Blob Storage Delete blob immutability policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-legalhold\n\
  \      path: /{container}/{blob}?comp=legalhold\n      operations:\n      - name: setbloblegalhold\n        method: PUT\n        description: Azure Blob Storage Set blob legal hold\n        inputParameters:\n        - name: x-ms-legal-hold\n          in: header\n          type: boolean\n          required: true\n          description: Whether to set or clear the legal hold.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-block\n      path: /{container}/{blob}?comp=block\n      operations:\n      - name: putblock\n        method: PUT\n        description: Azure Blob Storage Put block\n        inputParameters:\n        - name: blockid\n          in: query\n          type: string\n          required: true\n          description: A base64-encoded block ID that identifies the block. All block IDs for a given blob must be the same\n            length.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-blocklist\n      path: /{container}/{blob}?comp=blocklist\n      operations:\n      - name: putblocklist\n        method: PUT\n        description: Azure Blob Storage Put block list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getblocklist\n        method: GET\n        description: Azure Blob Storage Get block list\n        inputParameters:\n        - name: blocklisttype\n          in: query\n          type: string\n          description: Specifies which type of block list to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-block-fromurl\n      path: /{container}/{blob}?comp=block&fromURL\n      operations:\n      - name: putblockfromurl\n     \
  \   method: PUT\n        description: Azure Blob Storage Put block from URL\n        inputParameters:\n        - name: blockid\n          in: query\n          type: string\n          required: true\n          description: A base64-encoded block ID that identifies the block.\n        - name: x-ms-copy-source\n          in: header\n          type: string\n          required: true\n          description: URL of the source data.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-page\n      path: /{container}/{blob}?comp=page\n      operations:\n      - name: putpage\n        method: PUT\n        description: Azure Blob Storage Put page\n        inputParameters:\n        - name: x-ms-page-write\n          in: header\n          type: string\n          required: true\n          description: The page write operation type.\n        - name: x-ms-range\n          in: header\n          type:\
  \ string\n          required: true\n          description: The byte range for the page write operation. Must be aligned to 512-byte boundaries. Format is bytes=startByte-endByte.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-pagelist\n      path: /{container}/{blob}?comp=pagelist\n      operations:\n      - name: getpageranges\n        method: GET\n        description: Azure Blob Storage Get page ranges\n        inputParameters:\n        - name: x-ms-range\n          in: header\n          type: string\n          description: Return only page ranges within the specified byte range.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-pagelist-diff\n      path: /{container}/{blob}?comp=pagelist&diff\n      operations:\n      - name: getpagerangesdiff\n        method: GET\n\
  \        description: Azure Blob Storage Get page ranges diff\n        inputParameters:\n        - name: prevsnapshot\n          in: query\n          type: string\n          required: true\n          description: The snapshot identifier for the previous snapshot.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-incrementalcopy\n      path: /{container}/{blob}?comp=incrementalcopy\n      operations:\n      - name: incrementalcopyblob\n        method: PUT\n        description: Azure Blob Storage Incremental copy blob\n        inputParameters:\n        - name: x-ms-copy-source\n          in: header\n          type: string\n          required: true\n          description: URL of the source page blob snapshot.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-appendblock\n\
  \      path: /{container}/{blob}?comp=appendblock\n      operations:\n      - name: appendblock\n        method: PUT\n        description: Azure Blob Storage Append block\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-blob-comp-appendblock-fromurl\n      path: /{container}/{blob}?comp=appendblock&fromURL\n      operations:\n      - name: appendblockfromurl\n        method: PUT\n        description: Azure Blob Storage Append block from URL\n        inputParameters:\n        - name: x-ms-copy-source\n          in: header\n          type: string\n          required: true\n          description: URL of the source data to append.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-azure-blob-storage-rest\n    description: REST adapter for Azure Blob\
  \ Storage REST API.\n    resources:\n    - path: /\n      name: listcontainers\n      operations:\n      - method: GET\n        name: listcontainers\n        description: Azure Blob Storage List containers\n        call: microsoft-azure-blob-storage.listcontainers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?restype=service&comp=properties\n      name: getblobserviceproperties\n      operations:\n      - method: GET\n        name: getblobserviceproperties\n        description: Azure Blob Storage Get Blob service properties\n        call: microsoft-azure-blob-storage.getblobserviceproperties\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?restype=service&comp=properties\n      name: setblobserviceproperties\n      operations:\n      - method: PUT\n        name: setblobserviceproperties\n        description: Azure Blob Storage Set Blob service properties\n        call: microsoft-azure-blob-storage.setblobserviceproperties\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?restype=service&comp=stats\n      name: getblobservicestats\n      operations:\n      - method: GET\n        name: getblobservicestats\n        description: Azure Blob Storage Get Blob service stats\n        call: microsoft-azure-blob-storage.getblobservicestats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?restype=service&comp=userdelegationkey\n      name: getuserdelegationkey\n      operations:\n      - method: POST\n        name: getuserdelegationkey\n        description: Azure Blob Storage Get user delegation key\n        call: microsoft-azure-blob-storage.getuserdelegationkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?restype=service&comp=batch\n      name: submitblobbatch\n      operations:\n      - method: POST\n        name: submitblobbatch\n        description: Azure Blob Storage Submit blob batch\n \
  \       call: microsoft-azure-blob-storage.submitblobbatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?comp=blobs\n      name: findblobsbytags\n      operations:\n      - method: GET\n        name: findblobsbytags\n        description: Azure Blob Storage Find blobs by tags\n        call: microsoft-azure-blob-storage.findblobsbytags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}\n      name: createcontainer\n      operations:\n      - method: PUT\n        name: createcontainer\n        description: Azure Blob Storage Create container\n        call: microsoft-azure-blob-storage.createcontainer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}\n      name: getcontainerproperties\n      operations:\n      - method: GET\n        name: getcontainerproperties\n        description: Azure Blob Storage Get container properties\n        call: microsoft-azure-blob-storage.getcontainerproperties\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}\n      name: deletecontainer\n      operations:\n      - method: DELETE\n        name: deletecontainer\n        description: Azure Blob Storage Delete container\n        call: microsoft-azure-blob-storage.deletecontainer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}?restype=container&comp=list\n      name: listblobs\n      operations:\n      - method: GET\n        name: listblobs\n        description: Azure Blob Storage List blobs\n        call: microsoft-azure-blob-storage.listblobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}?restype=container&comp=metadata\n      name: getcontainermetadata\n      operations:\n      - method: GET\n        name: getcontainermetadata\n        description: Azure Blob Storage Get container metadata\n        call: microsoft-azure-blob-storage.getcontainermetadata\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}?restype=container&comp=metadata\n      name: setcontainermetadata\n      operations:\n      - method: PUT\n        name: setcontainermetadata\n        description: Azure Blob Storage Set container metadata\n        call: microsoft-azure-blob-storage.setcontainermetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}?restype=container&comp=acl\n      name: getcontaineracl\n      operations:\n      - method: GET\n        name: getcontaineracl\n        description: Azure Blob Storage Get container ACL\n        call: microsoft-azure-blob-storage.getcontaineracl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}?restype=container&comp=acl\n      name: setcontaineracl\n      operations:\n      - method: PUT\n        name: setcontaineracl\n        description: Azure Blob Storage Set container ACL\n\
  \        call: microsoft-azure-blob-storage.setcontaineracl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}?restype=container&comp=lease\n      name: leasecontainer\n      operations:\n      - method: PUT\n        name: leasecontainer\n        description: Azure Blob Storage Lease container\n        call: microsoft-azure-blob-storage.leasecontainer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}?restype=container&comp=undelete\n      name: restorecontainer\n      operations:\n      - method: PUT\n        name: restorecontainer\n        description: Azure Blob Storage Restore container\n        call: microsoft-azure-blob-storage.restorecontainer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}/{blob}\n      name: putblob\n      operations:\n      - method: PUT\n        name: putblob\n        description: Azure Blob Storage Put blob\n\
  \        call: microsoft-azure-blob-storage.putblob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}/{blob}\n      name: getblob\n      operations:\n      - method: GET\n        name: getblob\n        description: Azure Blob Storage Get blob\n        call: microsoft-azure-blob-storage.getblob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}/{blob}\n      name: deleteblob\n      operations:\n      - method: DELETE\n        name: deleteblob\n        description: Azure Blob Storage Delete blob\n        call: microsoft-azure-blob-storage.deleteblob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}/{blob}?comp=metadata\n      name: getblobmetadata\n      operations:\n      - method: GET\n        name: getblobmetadata\n        description: Azure Blob Storage Get blob metadata\n        call: microsoft-azure-blob-storage.getblobmetadata\n     \
  \   outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}/{blob}?comp=metadata\n      name: setblobmetadata\n      operations:\n      - method: PUT\n        name: setblobmetadata\n        description: Azure Blob Storage Set blob metadata\n        call: microsoft-azure-blob-storage.setblobmetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{container}/{blob}?comp=properties\n      name: setblobhttpheaders\n      operations:\n      - method: PUT\n        name: setblobhttpheaders\n        description: Azure\n\n# --- truncated at 32 KB (56 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-blob-storage/refs/heads/main/capabilities/microsoft-azure-blob-storage-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-blob-storage/refs/heads/main/capabilities/microsoft-azure-blob-storage-capability.yaml
tags:
- Microsoft
- Azure
- Blob
- Storage
- API
tools:
- description: Azure Blob Storage List containers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontainers
- description: Azure Blob Storage Get Blob service properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblobserviceproperties
- description: Azure Blob Storage Set Blob service properties
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setblobserviceproperties
- description: Azure Blob Storage Get Blob service stats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblobservicestats
- description: Azure Blob Storage Get user delegation key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getuserdelegationkey
- description: Azure Blob Storage Submit blob batch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitblobbatch
- description: Azure Blob Storage Find blobs by tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findblobsbytags
- description: Azure Blob Storage Create container
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createcontainer
- description: Azure Blob Storage Get container properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontainerproperties
- description: Azure Blob Storage Delete container
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontainer
- description: Azure Blob Storage List blobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblobs
- description: Azure Blob Storage Get container metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontainermetadata
- description: Azure Blob Storage Set container metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setcontainermetadata
- description: Azure Blob Storage Get container ACL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontaineracl
- description: Azure Blob Storage Set container ACL
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setcontaineracl
- description: Azure Blob Storage Lease container
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: leasecontainer
- description: Azure Blob Storage Restore container
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: restorecontainer
- description: Azure Blob Storage Put blob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putblob
- description: Azure Blob Storage Get blob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblob
- description: Azure Blob Storage Delete blob
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteblob
- description: Azure Blob Storage Get blob metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblobmetadata
- description: Azure Blob Storage Set blob metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setblobmetadata
- description: Azure Blob Storage Set blob HTTP headers
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setblobhttpheaders
- description: Azure Blob Storage Get blob tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblobtags
- description: Azure Blob Storage Set blob tags
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setblobtags
- description: Azure Blob Storage Lease blob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: leaseblob
- description: Azure Blob Storage Snapshot blob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: snapshotblob
- description: Azure Blob Storage Copy blob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: copyblob
- description: Azure Blob Storage Abort copy blob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: abortcopyblob
- description: Azure Blob Storage Undelete blob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: undeleteblob
- description: Azure Blob Storage Set blob tier
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setblobtier
- description: Azure Blob Storage Set blob immutability policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setblobimmutabilitypolicy
- description: Azure Blob Storage Delete blob immutability policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteblobimmutabilitypolicy
- description: Azure Blob Storage Set blob legal hold
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setbloblegalhold
- description: Azure Blob Storage Put block
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putblock
- description: Azure Blob Storage Put block list
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putblocklist
- description: Azure Blob Storage Get block list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblocklist
- description: Azure Blob Storage Put block from URL
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putblockfromurl
- description: Azure Blob Storage Put page
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putpage
- description: Azure Blob Storage Get page ranges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpageranges
- description: Azure Blob Storage Get page ranges diff
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpagerangesdiff
- description: Azure Blob Storage Incremental copy blob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: incrementalcopyblob
- description: Azure Blob Storage Append block
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: appendblock
- description: Azure Blob Storage Append block from URL
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: appendblockfromurl
---
