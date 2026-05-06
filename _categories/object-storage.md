---
aliases: []
common_operations:
- put-object
- get-object
- list-objects
- delete-object
- copy-object
description: 'Buckets, blobs, key-addressable opaque object stores. Operations are

  typically PUT/GET/HEAD/DELETE plus listing, ACLs, lifecycle policies.

  Implementations include S3, GCS, Azure Blob, Wasabi, B2.

  '
domain: infrastructure
implementation_count: 6
implementations:
- capability_name: Amazon S3 Storage Management
  capability_slug: storage-management
  capability_url: https://capabilities.apis.io/capabilities/amazon-s3/storage-management/
  consumed_api_count: 0
  operation_count: 16
  provider_name: Amazon S3
  provider_slug: amazon-s3
  tags:
  - Amazon
  - S3
  - Storage Management
  - Cloud Storage
  tool_count: 23
- capability_name: Apache Ozone Object Storage Workflow
  capability_slug: ozone-workflow
  capability_url: https://capabilities.apis.io/capabilities/apache-ozone/ozone-workflow/
  consumed_api_count: 0
  operation_count: 2
  provider_name: Apache Ozone
  provider_slug: apache-ozone
  tags:
  - Apache Ozone
  - Object Storage
  - Distributed Storage
  - S3 Compatible
  tool_count: 8
- capability_name: Backblaze B2 Cloud Storage Management
  capability_slug: cloud-storage-management
  capability_url: https://capabilities.apis.io/capabilities/backblaze/cloud-storage-management/
  consumed_api_count: 0
  operation_count: 23
  provider_name: Backblaze
  provider_slug: backblaze
  tags:
  - Backblaze
  - Cloud Storage
  - Object Storage
  - Storage Management
  tool_count: 24
- capability_name: Cloudflare Data and Storage
  capability_slug: data-and-storage
  capability_url: https://capabilities.apis.io/capabilities/cloudflare/data-and-storage/
  consumed_api_count: 0
  operation_count: 4
  provider_name: Cloudflare
  provider_slug: cloudflare
  tags:
  - Cloudflare
  - Storage
  - Database
  - Data
  tool_count: 18
- capability_name: Google Cloud Storage Management
  capability_slug: cloud-storage
  capability_url: https://capabilities.apis.io/capabilities/gcp-cloud-storage/cloud-storage/
  consumed_api_count: 0
  operation_count: 11
  provider_name: Google Cloud Storage
  provider_slug: gcp-cloud-storage
  tags:
  - Google Cloud
  - Cloud Storage
  - Object Storage
  - Data Management
  tool_count: 11
- capability_name: Azure Data and Security
  capability_slug: data-and-security
  capability_url: https://capabilities.apis.io/capabilities/microsoft-azure/data-and-security/
  consumed_api_count: 0
  operation_count: 4
  provider_name: Microsoft Azure
  provider_slug: microsoft-azure
  tags:
  - Azure
  - Cosmos DB
  - Blob Storage
  - Key Vault
  - Resource Manager
  tool_count: 15
layout: category
name: Object Storage
provider_count: 6
related:
- data-engineering
- document-processing
short: Store and retrieve binary objects in flat key-addressable namespaces.
slug: object-storage
---
