---
categories: []
consumed_apis: []
description: <p/>
layout: capability
name: Amazon Simple Storage Service
operations:
- description: Amazon S3 - AbortMultipartUpload
  method: DELETE
  name: abortmultipartupload
  path: /{Bucket}/{Key}#uploadId
- description: Amazon S3 - CompleteMultipartUpload
  method: POST
  name: completemultipartupload
  path: /{Bucket}/{Key}#uploadId
- description: Amazon S3 - ListParts
  method: GET
  name: listparts
  path: /{Bucket}/{Key}#uploadId
- description: Amazon S3 - CopyObject
  method: PUT
  name: copyobject
  path: /{Bucket}/{Key}#x-amz-copy-source
- description: Amazon S3 - CreateBucket
  method: PUT
  name: createbucket
  path: /{Bucket}
- description: Amazon S3 - DeleteBucket
  method: DELETE
  name: deletebucket
  path: /{Bucket}
- description: Amazon S3 - ListObjects
  method: GET
  name: listobjects
  path: /{Bucket}
- description: Amazon S3 - CreateMultipartUpload
  method: POST
  name: createmultipartupload
  path: /{Bucket}/{Key}#uploads
- description: Amazon S3 - DeleteBucketAnalyticsConfiguration
  method: DELETE
  name: deletebucketanalyticsconfiguration
  path: /{Bucket}#analytics&id
- description: Amazon S3 - GetBucketAnalyticsConfiguration
  method: GET
  name: getbucketanalyticsconfiguration
  path: /{Bucket}#analytics&id
- description: Amazon S3 - PutBucketAnalyticsConfiguration
  method: PUT
  name: putbucketanalyticsconfiguration
  path: /{Bucket}#analytics&id
- description: Amazon S3 - DeleteBucketCors
  method: DELETE
  name: deletebucketcors
  path: /{Bucket}#cors
- description: Amazon S3 - GetBucketCors
  method: GET
  name: getbucketcors
  path: /{Bucket}#cors
- description: Amazon S3 - PutBucketCors
  method: PUT
  name: putbucketcors
  path: /{Bucket}#cors
- description: Amazon S3 - DeleteBucketEncryption
  method: DELETE
  name: deletebucketencryption
  path: /{Bucket}#encryption
- description: Amazon S3 - GetBucketEncryption
  method: GET
  name: getbucketencryption
  path: /{Bucket}#encryption
- description: Amazon S3 - PutBucketEncryption
  method: PUT
  name: putbucketencryption
  path: /{Bucket}#encryption
- description: Amazon S3 - DeleteBucketIntelligentTieringConfiguration
  method: DELETE
  name: deletebucketintelligenttieringconfiguration
  path: /{Bucket}#intelligent-tiering&id
- description: Amazon S3 - GetBucketIntelligentTieringConfiguration
  method: GET
  name: getbucketintelligenttieringconfiguration
  path: /{Bucket}#intelligent-tiering&id
- description: Amazon S3 - PutBucketIntelligentTieringConfiguration
  method: PUT
  name: putbucketintelligenttieringconfiguration
  path: /{Bucket}#intelligent-tiering&id
- description: Amazon S3 - DeleteBucketInventoryConfiguration
  method: DELETE
  name: deletebucketinventoryconfiguration
  path: /{Bucket}#inventory&id
- description: Amazon S3 - GetBucketInventoryConfiguration
  method: GET
  name: getbucketinventoryconfiguration
  path: /{Bucket}#inventory&id
- description: Amazon S3 - PutBucketInventoryConfiguration
  method: PUT
  name: putbucketinventoryconfiguration
  path: /{Bucket}#inventory&id
- description: Amazon S3 - DeleteBucketLifecycle
  method: DELETE
  name: deletebucketlifecycle
  path: /{Bucket}#lifecycle
- description: Amazon S3 - GetBucketLifecycleConfiguration
  method: GET
  name: getbucketlifecycleconfiguration
  path: /{Bucket}#lifecycle
- description: Amazon S3 - PutBucketLifecycleConfiguration
  method: PUT
  name: putbucketlifecycleconfiguration
  path: /{Bucket}#lifecycle
- description: Amazon S3 - DeleteBucketMetricsConfiguration
  method: DELETE
  name: deletebucketmetricsconfiguration
  path: /{Bucket}#metrics&id
- description: Amazon S3 - GetBucketMetricsConfiguration
  method: GET
  name: getbucketmetricsconfiguration
  path: /{Bucket}#metrics&id
- description: Amazon S3 - PutBucketMetricsConfiguration
  method: PUT
  name: putbucketmetricsconfiguration
  path: /{Bucket}#metrics&id
- description: Amazon S3 - DeleteBucketOwnershipControls
  method: DELETE
  name: deletebucketownershipcontrols
  path: /{Bucket}#ownershipControls
- description: Amazon S3 - GetBucketOwnershipControls
  method: GET
  name: getbucketownershipcontrols
  path: /{Bucket}#ownershipControls
- description: Amazon S3 - PutBucketOwnershipControls
  method: PUT
  name: putbucketownershipcontrols
  path: /{Bucket}#ownershipControls
- description: Amazon S3 - DeleteBucketPolicy
  method: DELETE
  name: deletebucketpolicy
  path: /{Bucket}#policy
- description: Amazon S3 - GetBucketPolicy
  method: GET
  name: getbucketpolicy
  path: /{Bucket}#policy
- description: Amazon S3 - PutBucketPolicy
  method: PUT
  name: putbucketpolicy
  path: /{Bucket}#policy
- description: Amazon S3 - DeleteBucketReplication
  method: DELETE
  name: deletebucketreplication
  path: /{Bucket}#replication
- description: Amazon S3 - GetBucketReplication
  method: GET
  name: getbucketreplication
  path: /{Bucket}#replication
- description: Amazon S3 - PutBucketReplication
  method: PUT
  name: putbucketreplication
  path: /{Bucket}#replication
- description: Amazon S3 - DeleteBucketTagging
  method: DELETE
  name: deletebuckettagging
  path: /{Bucket}#tagging
- description: Amazon S3 - GetBucketTagging
  method: GET
  name: getbuckettagging
  path: /{Bucket}#tagging
- description: Amazon S3 - PutBucketTagging
  method: PUT
  name: putbuckettagging
  path: /{Bucket}#tagging
- description: Amazon S3 - DeleteBucketWebsite
  method: DELETE
  name: deletebucketwebsite
  path: /{Bucket}#website
- description: Amazon S3 - GetBucketWebsite
  method: GET
  name: getbucketwebsite
  path: /{Bucket}#website
- description: Amazon S3 - PutBucketWebsite
  method: PUT
  name: putbucketwebsite
  path: /{Bucket}#website
- description: Amazon S3 - DeleteObject
  method: DELETE
  name: deleteobject
  path: /{Bucket}/{Key}
- description: Amazon S3 - GetObject
  method: GET
  name: getobject
  path: /{Bucket}/{Key}
- description: Amazon S3 - PutObject
  method: PUT
  name: putobject
  path: /{Bucket}/{Key}
- description: Amazon S3 - DeleteObjectTagging
  method: DELETE
  name: deleteobjecttagging
  path: /{Bucket}/{Key}#tagging
- description: Amazon S3 - GetObjectTagging
  method: GET
  name: getobjecttagging
  path: /{Bucket}/{Key}#tagging
- description: Amazon S3 - PutObjectTagging
  method: PUT
  name: putobjecttagging
  path: /{Bucket}/{Key}#tagging
- description: Amazon S3 - DeleteObjects
  method: POST
  name: deleteobjects
  path: /{Bucket}#delete
- description: Amazon S3 - DeletePublicAccessBlock
  method: DELETE
  name: deletepublicaccessblock
  path: /{Bucket}#publicAccessBlock
- description: Amazon S3 - GetPublicAccessBlock
  method: GET
  name: getpublicaccessblock
  path: /{Bucket}#publicAccessBlock
- description: Amazon S3 - PutPublicAccessBlock
  method: PUT
  name: putpublicaccessblock
  path: /{Bucket}#publicAccessBlock
- description: Amazon S3 - GetBucketAccelerateConfiguration
  method: GET
  name: getbucketaccelerateconfiguration
  path: /{Bucket}#accelerate
- description: Amazon S3 - PutBucketAccelerateConfiguration
  method: PUT
  name: putbucketaccelerateconfiguration
  path: /{Bucket}#accelerate
- description: Amazon S3 - GetBucketAcl
  method: GET
  name: getbucketacl
  path: /{Bucket}#acl
- description: Amazon S3 - PutBucketAcl
  method: PUT
  name: putbucketacl
  path: /{Bucket}#acl
- description: Amazon S3 - GetBucketLifecycle
  method: GET
  name: getbucketlifecycle
  path: /{Bucket}#lifecycle&deprecated!
- description: Amazon S3 - PutBucketLifecycle
  method: PUT
  name: putbucketlifecycle
  path: /{Bucket}#lifecycle&deprecated!
personas: []
provider_name: Amazon S3 API
provider_slug: aws-s3
search_terms:
- deletebucketcors
- deletebucketownershipcontrols
- amazon s3 - getobjecttagging
- getpublicaccessblock
- amazon s3 - getbucketanalyticsconfiguration
- amazon s3 - putbucketaccelerateconfiguration
- amazon s3 - putbucketacl
- deletebucketinventoryconfiguration
- deletebuckettagging
- amazon s3 - getbucketownershipcontrols
- amazon s3 - getpublicaccessblock
- amazon s3 - deletebucketownershipcontrols
- copyobject
- amazon s3 - deleteobject
- amazon s3 - deletebuckettagging
- getbucketmetricsconfiguration
- getbucketwebsite
- amazon s3 - deletebucketreplication
- amazon s3 - putbucketintelligenttieringconfiguration
- amazon s3 - deletebucketintelligenttieringconfiguration
- amazon s3 - deletebucketwebsite
- api
- deletebucketwebsite
- getbucketownershipcontrols
- getobject
- getbucketanalyticsconfiguration
- putbucketacl
- amazon s3 - abortmultipartupload
- s3
- putbucketcors
- getbucketlifecycle
- getbucketcors
- getbucketreplication
- amazon s3 - listparts
- getbucketintelligenttieringconfiguration
- amazon s3 - putbucketmetricsconfiguration
- amazon s3 - getbucketwebsite
- putobjecttagging
- storage
- object storage
- putobject
- amazon s3 - getbucketintelligenttieringconfiguration
- amazon s3 - putbucketownershipcontrols
- amazon s3 - putbuckettagging
- amazon s3 - putbucketlifecycle
- amazon s3 - deletebucketlifecycle
- amazon s3 - putobject
- putbucketencryption
- putbucketinventoryconfiguration
- getbuckettagging
- amazon s3 - getbucketinventoryconfiguration
- deletebucketintelligenttieringconfiguration
- deletebucketencryption
- deleteobjecttagging
- amazon s3 - listobjects
- listparts
- amazon s3 - createmultipartupload
- deletebucketreplication
- amazon s3 - deletebucketanalyticsconfiguration
- putbucketintelligenttieringconfiguration
- amazon s3 - getbucketreplication
- amazon s3 - deletebucketencryption
- amazon s3 - deletebucket
- amazon s3 - getbuckettagging
- amazon s3 - getbucketacl
- aws
- amazon s3 - putbucketinventoryconfiguration
- putbucketpolicy
- amazon s3 - completemultipartupload
- deletebucketanalyticsconfiguration
- amazon s3 - createbucket
- amazon s3 - deletebucketpolicy
- amazon s3 - putbucketlifecycleconfiguration
- getbucketlifecycleconfiguration
- putbucketlifecycleconfiguration
- completemultipartupload
- putbucketaccelerateconfiguration
- amazon s3 - putpublicaccessblock
- amazon s3 - deletebucketcors
- deletepublicaccessblock
- amazon s3 - getbucketmetricsconfiguration
- putbucketownershipcontrols
- amazon s3 - putbucketpolicy
- createmultipartupload
- amazon s3 - getobject
- putbucketmetricsconfiguration
- putbucketwebsite
- amazon s3 - putbucketreplication
- deletebucketmetricsconfiguration
- getbucketacl
- createbucket
- putbucketreplication
- amazon s3 - getbucketaccelerateconfiguration
- putbucketanalyticsconfiguration
- amazon s3 - getbucketpolicy
- amazon s3 - putbucketcors
- deletebucketpolicy
- deletebucketlifecycle
- getbucketpolicy
- abortmultipartupload
- amazon s3 - getbucketcors
- putbuckettagging
- amazon s3 - deleteobjecttagging
- getbucketaccelerateconfiguration
- amazon s3 - copyobject
- amazon s3 - putbucketanalyticsconfiguration
- listobjects
- amazon s3 - getbucketlifecycle
- getobjecttagging
- deletebucket
- getbucketinventoryconfiguration
- amazon s3 - putbucketwebsite
- amazon s3 - getbucketencryption
- amazon s3 - getbucketlifecycleconfiguration
- deleteobjects
- amazon s3 - deletebucketmetricsconfiguration
- cloud storage
- amazon s3 - deleteobjects
- amazon s3 - putbucketencryption
- getbucketencryption
- amazon s3 - deletepublicaccessblock
- putpublicaccessblock
- amazon s3 - deletebucketinventoryconfiguration
- putbucketlifecycle
- deleteobject
- amazon s3 - putobjecttagging
slug: aws-s3-capability
source_filename: aws-s3-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Simple Storage Service\n  description: <p/>\n  tags:\n  - Aws\n  - S3\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: aws-s3\n    baseUri: http://s3.us-east-1.amazonaws.com\n    description: Amazon Simple Storage Service HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AWS_S3_TOKEN}}'\n    resources:\n    - name: bucket-key-uploadid\n      path: /{Bucket}/{Key}#uploadId\n      operations:\n      - name: abortmultipartupload\n        method: DELETE\n        description: Amazon S3 - AbortMultipartUpload\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: <p>The bucket name to which the upload was taking place. </p> <p>When using this action with an access\n            point, you must direct requests to the access\
  \ point hostn\n        - name: Key\n          in: path\n          type: string\n          required: true\n          description: Key of the object for which the multipart upload was initiated.\n        - name: uploadId\n          in: query\n          type: string\n          required: true\n          description: Upload ID that identifies the multipart upload.\n        - name: x-amz-request-payer\n          in: header\n          type: string\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If the bucket is owned by a different account, the request\n            fails with the HTTP status code <code>403 Forbidden</cod\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: completemultipartupload\n        method: POST\n        description: Amazon S3 - CompleteMultipartUpload\n        inputParameters:\n\
  \        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: <p>Name of the bucket to which the multipart upload was initiated.</p> <p>When using this action with\n            an access point, you must direct requests to the access po\n        - name: Key\n          in: path\n          type: string\n          required: true\n          description: Object key for which the multipart upload was initiated.\n        - name: uploadId\n          in: query\n          type: string\n          required: true\n          description: ID for the initiated multipart upload.\n        - name: x-amz-checksum-crc32\n          in: header\n          type: string\n          description: This header can be used as a data integrity check to verify that the data received is the same data\n            that was originally sent. This header specifies the base64-e\n        - name: x-amz-checksum-crc32c\n          in: header\n          type: string\n       \
  \   description: This header can be used as a data integrity check to verify that the data received is the same data\n            that was originally sent. This header specifies the base64-e\n        - name: x-amz-checksum-sha1\n          in: header\n          type: string\n          description: This header can be used as a data integrity check to verify that the data received is the same data\n            that was originally sent. This header specifies the base64-e\n        - name: x-amz-checksum-sha256\n          in: header\n          type: string\n          description: This header can be used as a data integrity check to verify that the data received is the same data\n            that was originally sent. This header specifies the base64-e\n        - name: x-amz-request-payer\n          in: header\n          type: string\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If\
  \ the bucket is owned by a different account, the request\n            fails with the HTTP status code <code>403 Forbidden</cod\n        - name: x-amz-server-side-encryption-customer-algorithm\n          in: header\n          type: string\n          description: The server-side encryption (SSE) algorithm used to encrypt the object. This parameter is needed only\n            when the object was created using a checksum algorithm. For\n        - name: x-amz-server-side-encryption-customer-key\n          in: header\n          type: string\n          description: The server-side encryption (SSE) customer managed key. This parameter is needed only when the object\n            was created using a checksum algorithm. For more informatio\n        - name: x-amz-server-side-encryption-customer-key-MD5\n          in: header\n          type: string\n          description: The MD5 server-side encryption (SSE) customer managed key. This parameter is needed only when the object\n            was created\
  \ using a checksum algorithm. For more inform\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listparts\n        method: GET\n        description: Amazon S3 - ListParts\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: <p>The name of the bucket to which the parts are being uploaded. </p> <p>When using this action with\n            an access point, you must direct requests to the access poi\n        - name: Key\n          in: path\n          type: string\n          required: true\n          description: Object key for which the multipart upload was initiated.\n        - name: max-parts\n          in: query\n          type: integer\n          description: Sets the maximum number of parts to return.\n        - name: part-number-marker\n          in: query\n          type: integer\n          description:\
  \ Specifies the part after which listing should begin. Only parts with higher part numbers will be listed.\n        - name: uploadId\n          in: query\n          type: string\n          required: true\n          description: Upload ID identifying the multipart upload whose parts are being listed.\n        - name: x-amz-request-payer\n          in: header\n          type: string\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If the bucket is owned by a different account, the request\n            fails with the HTTP status code <code>403 Forbidden</cod\n        - name: x-amz-server-side-encryption-customer-algorithm\n          in: header\n          type: string\n          description: The server-side encryption (SSE) algorithm used to encrypt the object. This parameter is needed only\n            when the object was created using a checksum algorithm. For\n        - name: x-amz-server-side-encryption-customer-key\n\
  \          in: header\n          type: string\n          description: The server-side encryption (SSE) customer managed key. This parameter is needed only when the object\n            was created using a checksum algorithm. For more informatio\n        - name: x-amz-server-side-encryption-customer-key-MD5\n          in: header\n          type: string\n          description: The MD5 server-side encryption (SSE) customer managed key. This parameter is needed only when the object\n            was created using a checksum algorithm. For more inform\n        - name: MaxParts\n          in: query\n          type: string\n          description: Pagination limit\n        - name: PartNumberMarker\n          in: query\n          type: string\n          description: Pagination token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-key-x-amz-copy-source\n      path: /{Bucket}/{Key}#x-amz-copy-source\n\
  \      operations:\n      - name: copyobject\n        method: PUT\n        description: Amazon S3 - CopyObject\n        inputParameters:\n        - name: x-amz-acl\n          in: header\n          type: string\n          description: <p>The canned ACL to apply to the object.</p> <p>This action is not supported by Amazon S3 on Outposts.</p>\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: <p>The name of the destination bucket.</p> <p>When using this action with an access point, you must\n            direct requests to the access point hostname. The access poi\n        - name: Cache-Control\n          in: header\n          type: string\n          description: Specifies caching behavior along the request/reply chain.\n        - name: x-amz-checksum-algorithm\n          in: header\n          type: string\n          description: Indicates the algorithm you want Amazon S3 to use to create the checksum for the object. For more\
  \ information,\n            see <a href=\"https://docs.aws.amazon.com/AmazonS3\n        - name: Content-Disposition\n          in: header\n          type: string\n          description: Specifies presentational information for the object.\n        - name: Content-Encoding\n          in: header\n          type: string\n          description: Specifies what content encodings have been applied to the object and thus what decoding mechanisms\n            must be applied to obtain the media-type referenced by the Co\n        - name: Content-Language\n          in: header\n          type: string\n          description: The language the content is in.\n        - name: Content-Type\n          in: header\n          type: string\n          description: A standard MIME type describing the format of the object data.\n        - name: x-amz-copy-source\n          in: header\n          type: string\n          required: true\n          description: <p>Specifies the source object for the copy operation.\
  \ You specify the value in one of two formats,\n            depending on whether you want to access the source object th\n        - name: x-amz-copy-source-if-match\n          in: header\n          type: string\n          description: Copies the object if its entity tag (ETag) matches the specified tag.\n        - name: x-amz-copy-source-if-modified-since\n          in: header\n          type: string\n          description: Copies the object if it has been modified since the specified time.\n        - name: x-amz-copy-source-if-none-match\n          in: header\n          type: string\n          description: Copies the object if its entity tag (ETag) is different than the specified ETag.\n        - name: x-amz-copy-source-if-unmodified-since\n          in: header\n          type: string\n          description: Copies the object if it hasn't been modified since the specified time.\n        - name: Expires\n          in: header\n          type: string\n          description: The date and\
  \ time at which the object is no longer cacheable.\n        - name: x-amz-grant-full-control\n          in: header\n          type: string\n          description: <p>Gives the grantee READ, READ_ACP, and WRITE_ACP permissions on the object.</p> <p>This action is\n            not supported by Amazon S3 on Outposts.</p>\n        - name: x-amz-grant-read\n          in: header\n          type: string\n          description: <p>Allows grantee to read the object data and its metadata.</p> <p>This action is not supported by\n            Amazon S3 on Outposts.</p>\n        - name: x-amz-grant-read-acp\n          in: header\n          type: string\n          description: <p>Allows grantee to read the object ACL.</p> <p>This action is not supported by Amazon S3 on Outposts.</p>\n        - name: x-amz-grant-write-acp\n          in: header\n          type: string\n          description: <p>Allows grantee to write the ACL for the applicable object.</p> <p>This action is not supported by\n         \
  \   Amazon S3 on Outposts.</p>\n        - name: Key\n          in: path\n          type: string\n          required: true\n          description: The key of the destination object.\n        - name: x-amz-metadata-directive\n          in: header\n          type: string\n          description: Specifies whether the metadata is copied from the source object or replaced with metadata provided\n            in the request.\n        - name: x-amz-tagging-directive\n          in: header\n          type: string\n          description: Specifies whether the object tag-set are copied from the source object or replaced with tag-set provided\n            in the request.\n        - name: x-amz-server-side-encryption\n          in: header\n          type: string\n          description: The server-side encryption algorithm used when storing this object in Amazon S3 (for example, AES256,\n            aws:kms).\n        - name: x-amz-storage-class\n          in: header\n          type: string\n        \
  \  description: By default, Amazon S3 uses the STANDARD Storage Class to store newly created objects. The STANDARD\n            storage class provides high durability and high availability.\n        - name: x-amz-website-redirect-location\n          in: header\n          type: string\n          description: If the bucket is configured as a website, redirects requests for this object to another object in the\n            same bucket or to an external URL. Amazon S3 stores the va\n        - name: x-amz-server-side-encryption-customer-algorithm\n          in: header\n          type: string\n          description: Specifies the algorithm to use to when encrypting the object (for example, AES256).\n        - name: x-amz-server-side-encryption-customer-key\n          in: header\n          type: string\n          description: 'Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value\n            is used to store the object and then it is discarded; Amazon\
  \ '\n        - name: x-amz-server-side-encryption-customer-key-MD5\n          in: header\n          type: string\n          description: Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header\n            for a message integrity check to ensure that the encryp\n        - name: x-amz-server-side-encryption-aws-kms-key-id\n          in: header\n          type: string\n          description: Specifies the Amazon Web Services KMS key ID to use for object encryption. All GET and PUT requests\n            for an object protected by Amazon Web Services KMS will fail\n        - name: x-amz-server-side-encryption-context\n          in: header\n          type: string\n          description: Specifies the Amazon Web Services KMS Encryption Context to use for object encryption. The value of\n            this header is a base64-encoded UTF-8 string holding JSON wi\n        - name: x-amz-server-side-encryption-bucket-key-enabled\n          in: header\n\
  \          type: boolean\n          description: <p>Specifies whether Amazon S3 should use an S3 Bucket Key for object encryption with server-side encryption\n            using AWS KMS (SSE-KMS). Setting this header to <co\n        - name: x-amz-copy-source-server-side-encryption-customer-algorithm\n          in: header\n          type: string\n          description: Specifies the algorithm to use when decrypting the source object (for example, AES256).\n        - name: x-amz-copy-source-server-side-encryption-customer-key\n          in: header\n          type: string\n          description: Specifies the customer-provided encryption key for Amazon S3 to use to decrypt the source object. The\n            encryption key provided in this header must be one that wa\n        - name: x-amz-copy-source-server-side-encryption-customer-key-MD5\n          in: header\n          type: string\n          description: Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon\
  \ S3 uses this header\n            for a message integrity check to ensure that the encryp\n        - name: x-amz-request-payer\n          in: header\n          type: string\n        - name: x-amz-tagging\n          in: header\n          type: string\n          description: 'The tag-set for the object destination object this value must be used in conjunction with the <code>TaggingDirective</code>.\n            The tag-set must be encoded as URL '\n        - name: x-amz-object-lock-mode\n          in: header\n          type: string\n          description: The Object Lock mode that you want to apply to the copied object.\n        - name: x-amz-object-lock-retain-until-date\n          in: header\n          type: string\n          description: The date and time when you want the copied object's Object Lock to expire.\n        - name: x-amz-object-lock-legal-hold\n          in: header\n          type: string\n          description: Specifies whether you want to apply a legal hold to the copied\
  \ object.\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: 'The account ID of the expected destination bucket owner. If the destination bucket is owned by a different\n            account, the request fails with the HTTP status code '\n        - name: x-amz-source-expected-bucket-owner\n          in: header\n          type: string\n          description: 'The account ID of the expected source bucket owner. If the source bucket is owned by a different account,\n            the request fails with the HTTP status code <code>403 '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket\n      path: /{Bucket}\n      operations:\n      - name: createbucket\n        method: PUT\n        description: Amazon S3 - CreateBucket\n        inputParameters:\n        - name: x-amz-acl\n          in: header\n          type: string\n          description:\
  \ The canned ACL to apply to the bucket.\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: The name of the bucket to create.\n        - name: x-amz-grant-full-control\n          in: header\n          type: string\n          description: Allows grantee the read, write, read ACP, and write ACP permissions on the bucket.\n        - name: x-amz-grant-read\n          in: header\n          type: string\n          description: Allows grantee to list the objects in the bucket.\n        - name: x-amz-grant-read-acp\n          in: header\n          type: string\n          description: Allows grantee to read the bucket ACL.\n        - name: x-amz-grant-write\n          in: header\n          type: string\n          description: <p>Allows grantee to create new objects in the bucket.</p> <p>For the bucket and object owners of existing\n            objects, also allows deletions and overwrites of thos\n        - name: x-amz-grant-write-acp\n\
  \          in: header\n          type: string\n          description: Allows grantee to write the ACL for the applicable bucket.\n        - name: x-amz-bucket-object-lock-enabled\n          in: header\n          type: boolean\n          description: Specifies whether you want S3 Object Lock to be enabled for the new bucket.\n        - name: x-amz-object-ownership\n          in: header\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebucket\n        method: DELETE\n        description: Amazon S3 - DeleteBucket\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Specifies the bucket being deleted.\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If the bucket is owned\
  \ by a different account, the request\n            fails with the HTTP status code <code>403 Forbidden</cod\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listobjects\n        method: GET\n        description: Amazon S3 - ListObjects\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: <p>The name of the bucket containing the objects.</p> <p>When using this action with an access point,\n            you must direct requests to the access point hostname. The\n        - name: delimiter\n          in: query\n          type: string\n          description: A delimiter is a character you use to group keys.\n        - name: encoding-type\n          in: query\n          type: string\n        - name: marker\n          in: query\n          type: string\n          description: Marker is where you want Amazon S3 to\
  \ start listing from. Amazon S3 starts listing after this specified\n            key. Marker can be any key in the bucket.\n        - name: max-keys\n          in: query\n          type: integer\n          description: Sets the maximum number of keys returned in the response. By default the action returns up to 1,000\n            key names. The response might contain fewer keys but will ne\n        - name: prefix\n          in: query\n          type: string\n          description: Limits the response to keys that begin with the specified prefix.\n        - name: x-amz-request-payer\n          in: header\n          type: string\n          description: Confirms that the requester knows that she or he will be charged for the list objects request. Bucket\n            owners need not specify this parameter in their requests.\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If the bucket\
  \ is owned by a different account, the request\n            fails with the HTTP status code <code>403 Forbidden</cod\n        - name: MaxKeys\n          in: query\n          type: string\n          description: Pagination limit\n        - name: Marker\n          in: query\n          type: string\n          description: Pagination token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-key-uploads\n      path: /{Bucket}/{Key}#uploads\n      operations:\n      - name: createmultipartupload\n        method: POST\n        description: Amazon S3 - CreateMultipartUpload\n        inputParameters:\n        - name: x-amz-acl\n          in: header\n          type: string\n          description: <p>The canned ACL to apply to the object.</p> <p>This action is not supported by Amazon S3 on Outposts.</p>\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n     \
  \     description: <p>The name of the bucket to which to initiate the upload</p> <p>When using this action with an access\n            point, you must direct requests to the access point hostn\n        - name: Cache-Control\n          in: header\n          type: string\n          description: Specifies caching behavior along the request/reply chain.\n        - name: Content-Disposition\n          in: header\n          type: string\n          description: Specifies presentational information for the object.\n        - name: Content-Encoding\n          in: header\n          type: string\n          description: Specifies what content encodings have been applied to the object and thus what decoding mechanisms\n            must be applied to obtain the media-type referenced by the Co\n        - name: Content-Language\n          in: header\n          type: string\n          description: The language the content is in.\n        - name: Content-Type\n          in: header\n          type: string\n\
  \          description: A standard MIME type describing the format of the object data.\n        - name: Expires\n          in: header\n          type: string\n          description: The date and time at which the object is no longer cacheable.\n        - name: x-amz-grant-full-control\n          in: header\n          type: string\n          description: <p>Gives the grantee READ, READ_ACP, and WRITE_ACP permissions on the object.</p> <p>This action is\n            not supported by Amazon S3 on Outposts.</p>\n        - name: x-amz-grant-read\n          in: header\n          type: string\n          description: <p>Allows grantee to read the object data and its metadata.</p> <p>This action is not supported by\n            Amazon S3 on Outposts.</p>\n        - name: x-amz-grant-read-acp\n          in: header\n          type: string\n          description: <p>Allows grantee to read the object ACL.</p> <p>This action is not supported by Amazon S3 on Outposts.</p>\n        - name: x-amz-grant-write-acp\n\
  \          in: header\n          type: string\n          description: <p>Allows grantee to write the ACL for the applicable object.</p> <p>This action is not supported by\n            Amazon S3 on Outposts.</p>\n        - name: Key\n          in: path\n          type: string\n          required: true\n          description: Object key for which the multipart upload is to be initiated.\n        - name: x-amz-server-side-encryption\n          in: header\n          type: string\n          description: The server-side encryption algorithm used when storing this object in Amazon S3 (for example, AES256,\n            aws:kms).\n        - name: x-amz-storage-class\n          in: header\n          type: string\n          description: By default, Amazon S3 uses the STANDARD Storage Class to store newly created objects. The STANDARD\n            storage class provides high durability and high availability.\n        - name: x-amz-website-redirect-location\n          in: header\n          type: string\n\
  \          description: If the bucket is configured as a website, redirects requests for this object to another object in the\n            same bucket or to an external URL. Amazon S3 stores the va\n        - name: x-amz-server-side-encryption-customer-algorithm\n          in: header\n          type: string\n          description: Specifies the algorithm to use to when encrypting the object (for example, AES256).\n        - name: x-amz-server-side-encryption-customer-key\n          in: header\n          type: string\n          description: 'Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value\n            is used to store the object and then it is discarded; Amazon '\n        - name: x-amz-server-side-encryption-customer-key-MD5\n          in: header\n          type: string\n          description: Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header\n            for a message integrity check\
  \ to ensure that the encryp\n        - name: x-amz-server-side-encryption-aws-kms-key-id\n          in: header\n          type: string\n          description: Specifies the ID of the symmetric customer managed key to use for object encryption. All GET and PUT\n            requests for an object protected by Amazon Web Services KMS\n        - name: x-amz-server-side-encryption-context\n          in: header\n          type: string\n          description: Specifies the Amazon Web Services KMS Encryption Context to use for object encryption. The value of\n            this header is a base64-encoded UTF-8 string holding JSON wi\n        - name: x-amz-server-side-encryption-bucket-key-enabled\n          in: header\n          type: boolean\n          description: <p>Specifies whether Amazon S3 should use an S3 Bucket Key for object encryption with server-side encryption\n            using AWS KMS (SSE-KMS). Setting this header to <co\n        - name: x-amz-request-payer\n          in: header\n\
  \          type: string\n        - name: x-amz-tagging\n          in: header\n          type: string\n          description: The tag-set for the object. The tag-set must be encoded as URL Query parameters.\n        - name: x-amz-object-lock-mode\n          in: header\n          type: string\n          description: Specifies the Object Lock mode that you want to apply to the uploaded object.\n        - name: x-amz-object-lock-retain-until-date\n          in: header\n          type: string\n          description: Specifies the date and time when you want the Object Lock to expire.\n        - name: x-amz-object-lock-legal-hold\n          in: header\n          type: string\n          description: Specifies whether you want to apply a legal hold to the uploaded object.\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If the bucket is owned by a different account, the request\n    \
  \        fails with the HTTP status code <code>403 Forbidden</cod\n        - name: x-amz-checksum-algorithm\n          in: header\n          type: string\n          description: Indicates the algorithm you want Amazon S3 to use to create the checksum for the object. For more information,\n            see <a href=\"https://docs.aws.amazon.com/AmazonS3\n        - name: uploads\n          in: query\n          type: boolean\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-analytics-id\n      path: /{Bucket}#analytics&id\n      operations:\n      - name: deletebucketanalyticsconfiguration\n        method: DELETE\n        description: Amazon S3 - DeleteBucketAnalyticsConfiguration\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: The name of the bucket from which an analytics configuration\
  \ is deleted.\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID that identifies the analytics configuration.\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If the bucket is owned by a different account, the request\n            fails with the HTTP status code <code>403 Forbidden</cod\n        - name: analytics\n          in: query\n          type: boolean\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getbucketanalyticsconfiguration\n        method: GET\n        description: Amazon S3 - GetBucketAnalyticsConfiguration\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: The name of the bucket from\
  \ which an analytics configuration is retrieved.\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID that identifies the analytics configuration.\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If the bucket is owned by a different account, the request\n            fails with the HTTP status code <code>403 Forbidden</cod\n        - name: analytics\n          in: query\n          type: boolean\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putbucketanalyticsconfiguration\n        method: PUT\n        description: Amazon S3 - PutBucketAnalyticsConfiguration\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description:\
  \ The name of the bucket to which an analytics configuration is stored.\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID that identifies the analytics configuration.\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If the bucket is owned by a different account, the request\n            fails with the HTTP status code <code>403 Forbidden</cod\n        - name: analytics\n          in: query\n          type: boolean\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-cors\n      path: /{Bucket}#cors\n      operations:\n      - name: deletebucketcors\n        method: DELETE\n        description: Amazon S3 - DeleteBucketCors\n        inputParameters:\n        - name: Bucket\n          in: path\n\
  \          type: string\n          required: true\n          description: Specifies the bucket whose <code>cors</code> configuration is being deleted.\n        - name: x-amz-expected-bucket-owner\n          in: header\n          type: string\n          description: The account ID of the expected bucket owner. If the bucket is owned by a different account, the request\n            fails with the HTTP status code <code>403 Forbidden</cod\n     \n\n# --- truncated at 32 KB (162 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/aws-s3/refs/heads/main/capabilities/aws-s3-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-s3/refs/heads/main/capabilities/aws-s3-capability.yaml
tags:
- Aws
- S3
- API
tools:
- description: Amazon S3 - AbortMultipartUpload
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: abortmultipartupload
- description: Amazon S3 - CompleteMultipartUpload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completemultipartupload
- description: Amazon S3 - ListParts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listparts
- description: Amazon S3 - CopyObject
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: copyobject
- description: Amazon S3 - CreateBucket
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createbucket
- description: Amazon S3 - DeleteBucket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucket
- description: Amazon S3 - ListObjects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listobjects
- description: Amazon S3 - CreateMultipartUpload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmultipartupload
- description: Amazon S3 - DeleteBucketAnalyticsConfiguration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketanalyticsconfiguration
- description: Amazon S3 - GetBucketAnalyticsConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketanalyticsconfiguration
- description: Amazon S3 - PutBucketAnalyticsConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketanalyticsconfiguration
- description: Amazon S3 - DeleteBucketCors
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketcors
- description: Amazon S3 - GetBucketCors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketcors
- description: Amazon S3 - PutBucketCors
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketcors
- description: Amazon S3 - DeleteBucketEncryption
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketencryption
- description: Amazon S3 - GetBucketEncryption
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketencryption
- description: Amazon S3 - PutBucketEncryption
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketencryption
- description: Amazon S3 - DeleteBucketIntelligentTieringConfiguration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketintelligenttieringconfiguration
- description: Amazon S3 - GetBucketIntelligentTieringConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketintelligenttieringconfiguration
- description: Amazon S3 - PutBucketIntelligentTieringConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketintelligenttieringconfiguration
- description: Amazon S3 - DeleteBucketInventoryConfiguration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketinventoryconfiguration
- description: Amazon S3 - GetBucketInventoryConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketinventoryconfiguration
- description: Amazon S3 - PutBucketInventoryConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketinventoryconfiguration
- description: Amazon S3 - DeleteBucketLifecycle
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketlifecycle
- description: Amazon S3 - GetBucketLifecycleConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketlifecycleconfiguration
- description: Amazon S3 - PutBucketLifecycleConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketlifecycleconfiguration
- description: Amazon S3 - DeleteBucketMetricsConfiguration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketmetricsconfiguration
- description: Amazon S3 - GetBucketMetricsConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketmetricsconfiguration
- description: Amazon S3 - PutBucketMetricsConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketmetricsconfiguration
- description: Amazon S3 - DeleteBucketOwnershipControls
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketownershipcontrols
- description: Amazon S3 - GetBucketOwnershipControls
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketownershipcontrols
- description: Amazon S3 - PutBucketOwnershipControls
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketownershipcontrols
- description: Amazon S3 - DeleteBucketPolicy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketpolicy
- description: Amazon S3 - GetBucketPolicy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketpolicy
- description: Amazon S3 - PutBucketPolicy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketpolicy
- description: Amazon S3 - DeleteBucketReplication
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketreplication
- description: Amazon S3 - GetBucketReplication
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketreplication
- description: Amazon S3 - PutBucketReplication
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketreplication
- description: Amazon S3 - DeleteBucketTagging
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebuckettagging
- description: Amazon S3 - GetBucketTagging
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuckettagging
- description: Amazon S3 - PutBucketTagging
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbuckettagging
- description: Amazon S3 - DeleteBucketWebsite
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketwebsite
- description: Amazon S3 - GetBucketWebsite
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketwebsite
- description: Amazon S3 - PutBucketWebsite
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketwebsite
- description: Amazon S3 - DeleteObject
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteobject
- description: Amazon S3 - GetObject
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getobject
- description: Amazon S3 - PutObject
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putobject
- description: Amazon S3 - DeleteObjectTagging
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteobjecttagging
- description: Amazon S3 - GetObjectTagging
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getobjecttagging
- description: Amazon S3 - PutObjectTagging
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putobjecttagging
- description: Amazon S3 - DeleteObjects
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteobjects
- description: Amazon S3 - DeletePublicAccessBlock
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepublicaccessblock
- description: Amazon S3 - GetPublicAccessBlock
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpublicaccessblock
- description: Amazon S3 - PutPublicAccessBlock
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putpublicaccessblock
- description: Amazon S3 - GetBucketAccelerateConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketaccelerateconfiguration
- description: Amazon S3 - PutBucketAccelerateConfiguration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketaccelerateconfiguration
- description: Amazon S3 - GetBucketAcl
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketacl
- description: Amazon S3 - PutBucketAcl
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketacl
- description: Amazon S3 - GetBucketLifecycle
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketlifecycle
- description: Amazon S3 - PutBucketLifecycle
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbucketlifecycle
---
