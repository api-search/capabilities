---
categories: []
consumed_apis: []
description: Unified workflow that combines FlashArray, FlashBlade, and Pure1 APIs to give a storage administrator a single REST and MCP surface for managing block, file, and object storage across the Pure Storage fleet plus cross-array reporting and telemetry from Pure1. Used by storage administrators, platform engineers, and SREs running Pure Storage at scale.
layout: capability
name: Pure Storage Fleet Management
operations:
- description: List FlashArray arrays.
  method: GET
  name: list-flasharray-arrays
  path: /v1/arrays
- description: List FlashBlade arrays.
  method: GET
  name: list-flashblade-arrays
  path: /v1/arrays
- description: List arrays known to Pure1.
  method: GET
  name: list-pure1-arrays
  path: /v1/arrays
- description: List FlashArray volumes.
  method: GET
  name: list-volumes
  path: /v1/volumes
- description: List FlashArray hosts.
  method: GET
  name: list-hosts
  path: /v1/hosts
- description: List FlashBlade file systems.
  method: GET
  name: list-file-systems
  path: /v1/file-systems
- description: List FlashBlade S3 buckets.
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: List Pure1 fleet metrics catalog.
  method: GET
  name: list-metrics
  path: /v1/fleet/metrics
- description: List Pure1 alerts across the fleet.
  method: GET
  name: list-alerts
  path: /v1/fleet/alerts
- description: List sustainability metrics for arrays.
  method: GET
  name: list-sustainability-metrics
  path: /v1/fleet/sustainability
personas: []
provider_name: Pure Storage
provider_slug: pure-storage
search_terms:
- pure1 sustainability and energy telemetry.
- list file systems
- flash storage
- list pure1 sustainability metrics for arrays.
- pure1 list alerts
- list buckets
- list flashblade arrays
- flashblade s3 bucket operations.
- enterprise storage
- flashblade
- fb list buckets
- storage administration
- list pure1 fleet-wide alerts.
- pure storage
- list flasharray arrays
- cloud storage
- list sustainability metrics for arrays.
- pure1 fleet-wide alert stream.
- list and inspect flasharray, flashblade, and pure1-tracked arrays.
- flasharray host operations.
- fb list arrays
- list pure1 subscription information.
- infrastructure
- list arrays known to pure1.
- fa list arrays
- flasharray volume operations.
- fa list protection groups
- list pure1 fleet metrics catalog.
- data storage
- kubernetes storage
- pure1 list arrays
- fa list hosts
- pure1
- pure1 list metrics
- pure1 list sustainability
- list flashblade s3 buckets.
- pure1 list subscriptions
- object storage
- file storage
- list flasharray hosts.
- list alerts
- list hosts
- cross-fleet telemetry from pure1.
- fleet management
- storage
- list sustainability metrics
- fb list file systems
- list pure1 alerts across the fleet.
- list metrics
- list flasharray volumes.
- flashblade file system operations.
- list flasharray protection groups for replication and snapshots.
- flasharray
- list flashblade file systems.
- list flasharray arrays.
- fa list volumes
- list flashblade arrays.
- block storage
- list volumes
- list pure1 arrays
slug: storage-fleet-management
source_filename: storage-fleet-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pure Storage Fleet Management\n  description: Unified workflow that combines FlashArray, FlashBlade, and Pure1 APIs to give a storage administrator a single\n    REST and MCP surface for managing block, file, and object storage across the Pure Storage fleet plus cross-array reporting\n    and telemetry from Pure1. Used by storage administrators, platform engineers, and SREs running Pure Storage at scale.\n  tags:\n  - Pure Storage\n  - Fleet Management\n  - Storage Administration\n  - FlashArray\n  - FlashBlade\n  - Pure1\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PURE_FA_API_TOKEN: PURE_FA_API_TOKEN\n    PURE_FB_API_TOKEN: PURE_FB_API_TOKEN\n    PURE1_API_TOKEN: PURE1_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: flasharray-rest-api\n    baseUri: https://[array]/api/2.52\n    description: Pure Storage FlashArray REST API for managing all-flash storage arrays, volumes,\
  \ hosts, snapshots, replication,\n      and other FlashArray resources.\n    authentication:\n      type: apikey\n      key: x-auth-token\n      value: '{{PURE_FA_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: policies\n      description: Policies resources on FlashArray REST API\n      operations:\n      - name: get-api-policies\n        method: GET\n        path: /api/2.52/policies\n        description: Pure Storage List Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-policies-management-access\n        method: GET\n        path: /api/2.52/policies/management-access\n        description: Pure Storage List Management Access Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-policies-management-access\n        method: POST\n        path: /api/2.52/policies/management-access\n\
  \        description: Pure Storage Create Management Access Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-policies-management-access\n        method: DELETE\n        path: /api/2.52/policies/management-access\n        description: Pure Storage Delete Management Access Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-policies-management-access\n        method: PATCH\n        path: /api/2.52/policies/management-access\n        description: Pure Storage Modify Management Access Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-management-access-members\n   \
  \     method: GET\n        path: /api/2.52/policies/management-access/members\n        description: Pure Storage List Management Access Policy Members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: directories\n      description: Directories resources on FlashArray REST API\n      operations:\n      - name: get-api-directories\n        method: GET\n        path: /api/2.52/directories\n        description: Pure Storage List Directories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-directories\n        method: POST\n        path: /api/2.52/directories\n        description: Pure Storage Create or Copy Directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n\
  \      - name: delete-api-directories\n        method: DELETE\n        path: /api/2.52/directories\n        description: Pure Storage Delete Managed Directories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-directories\n        method: PATCH\n        path: /api/2.52/directories\n        description: Pure Storage Modify a Managed Directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-directories-groups\n        method: GET\n        path: /api/2.52/directories/groups\n        description: Pure Storage List Group with Content in Directories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-locks-nlm-reclamations\n        method: POST\n\
  \        path: /api/2.52/directories/locks/nlm-reclamations\n        description: Pure Storage Create NLM Reclamation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: directory-services\n      description: Directory Services resources on FlashArray REST API\n      operations:\n      - name: get-api-directory-services\n        method: GET\n        path: /api/2.52/directory-services\n        description: Pure Storage List Directory Services Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-directory-services\n        method: POST\n        path: /api/2.52/directory-services\n        description: Pure Storage Create Directory Services Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-api-directory-services\n        method: DELETE\n        path: /api/2.52/directory-services\n        description: Pure Storage Delete Directory Services Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-directory-services\n        method: PATCH\n        path: /api/2.52/directory-services\n        description: Pure Storage Modify Directory Services Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-directory-services-roles\n        method: GET\n        path: /api/2.52/directory-services/roles\n        description: Pure Storage List Group to Management Access Policy Mappings\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-directory-services-roles\n        method: POST\n        path: /api/2.52/directory-services/roles\n        description: Pure Storage Create a Group in Management Access Policy Mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: arrays\n      description: Arrays resources on FlashArray REST API\n      operations:\n      - name: get-api-arrays\n        method: GET\n        path: /api/2.52/arrays\n        description: Pure Storage List Arrays\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-arrays\n        method: DELETE\n        path: /api/2.52/arrays\n        description: Pure Storage Delete an Array\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-arrays\n        method: PATCH\n        path: /api/2.52/arrays\n        description: Pure Storage Modify an Array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-arrays-cache\n        method: GET\n        path: /api/2.52/arrays/cache\n        description: Pure Storage DIMM Cache Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-arrays-cloud-config\n        method: GET\n        path: /api/2.52/arrays/cloud-config\n        description: Pure Storage List CBS Array Configuration Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: patch-arrays-cloud-config\n        method: PATCH\n        path: /api/2.52/arrays/cloud-config\n        description: Pure Storage Modify CBS Array Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: protection-groups\n      description: Protection Groups resources on FlashArray REST API\n      operations:\n      - name: get-api-protection-groups\n        method: GET\n        path: /api/2.52/protection-groups\n        description: Pure Storage List Protection Groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-protection-groups\n        method: POST\n        path: /api/2.52/protection-groups\n        description: Pure Storage Create a Protection Group and Upsert Tags\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-api-protection-groups\n        method: DELETE\n        path: /api/2.52/protection-groups\n        description: Pure Storage Delete a Protection Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-protection-groups\n        method: PATCH\n        path: /api/2.52/protection-groups\n        description: Pure Storage Modify a Protection Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-protection-groups-hosts\n        method: GET\n        path: /api/2.52/protection-groups/hosts\n        description: Pure Storage List Protection Groups with Host Members\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-protection-groups-hosts\n        method: POST\n        path: /api/2.52/protection-groups/hosts\n        description: Pure Storage Create an Action to Add a Host to a Protection Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: pods\n      description: Pods resources on FlashArray REST API\n      operations:\n      - name: get-api-pods\n        method: GET\n        path: /api/2.52/pods\n        description: Pure Storage List Pods\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-pods\n        method: POST\n        path: /api/2.52/pods\n        description: Pure Storage Create a Pod\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-api-pods\n        method: DELETE\n        path: /api/2.52/pods\n        description: Pure Storage Delete a Pod\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-pods\n        method: PATCH\n        path: /api/2.52/pods\n        description: Pure Storage Modify a Pod\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-pods-arrays\n        method: GET\n        path: /api/2.52/pods/arrays\n        description: Pure Storage List Pods and Their the Array Members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ post-pods-arrays\n        method: POST\n        path: /api/2.52/pods/arrays\n        description: Pure Storage Creates a Pod to Be Stretched to an Array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: volumes\n      description: Volumes resources on FlashArray REST API\n      operations:\n      - name: get-api-volumes\n        method: GET\n        path: /api/2.52/volumes\n        description: Pure Storage List Volumes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-volumes\n        method: POST\n        path: /api/2.52/volumes\n        description: Pure Storage Create or Copy a Volume and Upsert Tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data: {}\n      - name: delete-api-volumes\n        method: DELETE\n        path: /api/2.52/volumes\n        description: Pure Storage Delete a Volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-volumes\n        method: PATCH\n        path: /api/2.52/volumes\n        description: Pure Storage Modify a Volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: post-volumes-batch\n        method: POST\n        path: /api/2.52/volumes/batch\n        description: Pure Storage Create or Copy Volumes and Upsert Tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name:\
  \ get-volumes-diff\n        method: GET\n        path: /api/2.52/volumes/diff\n        description: Pure Storage List Volume Diffs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hosts\n      description: Hosts resources on FlashArray REST API\n      operations:\n      - name: get-api-hosts\n        method: GET\n        path: /api/2.52/hosts\n        description: Pure Storage List Hosts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-hosts\n        method: POST\n        path: /api/2.52/hosts\n        description: Pure Storage Create a Host and Upsert Tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-api-hosts\n        method: DELETE\n \
  \       path: /api/2.52/hosts\n        description: Pure Storage Delete a Host\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-hosts\n        method: PATCH\n        path: /api/2.52/hosts\n        description: Pure Storage Modify a Host\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-hosts-host-groups\n        method: GET\n        path: /api/2.52/hosts/host-groups\n        description: Pure Storage List Hosts That Are Associated with Host Groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-hosts-host-groups\n        method: POST\n        path: /api/2.52/hosts/host-groups\n        description: Pure Storage Create a Membership to a Host\
  \ Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: host-groups\n      description: Host Groups resources on FlashArray REST API\n      operations:\n      - name: get-api-host-groups\n        method: GET\n        path: /api/2.52/host-groups\n        description: Pure Storage List Host Groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-host-groups\n        method: POST\n        path: /api/2.52/host-groups\n        description: Pure Storage Create a Host Group and Upsert Tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-api-host-groups\n        method: DELETE\n        path:\
  \ /api/2.52/host-groups\n        description: Pure Storage Delete a Host Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-host-groups\n        method: PATCH\n        path: /api/2.52/host-groups\n        description: Pure Storage Modify a Host Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-host-groups-hosts\n        method: GET\n        path: /api/2.52/host-groups/hosts\n        description: Pure Storage List Host Groups That Are Associated with Hosts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-host-groups-hosts\n        method: POST\n        path: /api/2.52/host-groups/hosts\n        description: Pure Storage Create a\
  \ Membership to a Host Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: software\n      description: Software resources on FlashArray REST API\n      operations:\n      - name: get-api-software\n        method: GET\n        path: /api/2.52/software\n        description: Pure Storage List Software Packages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-software\n        method: POST\n        path: /api/2.52/software\n        description: Pure Storage Create a Software Package\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-api-software\n        method: DELETE\n        path: /api/2.52/software\n\
  \        description: Pure Storage Delete a Software Package\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-api-software-bundle\n        method: GET\n        path: /api/2.52/software-bundle\n        description: Pure Storage List Software-bundle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-software-bundle\n        method: POST\n        path: /api/2.52/software-bundle\n        description: Pure Storage Create Software-bundle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-api-software-check\n        method: GET\n        path: /api/2.52/software-check\n        description: Pure Storage List Software Check Tasks\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: administrators\n      description: Administrators resources on FlashArray REST API\n      operations:\n      - name: get-api-admins\n        method: GET\n        path: /api/2.52/admins\n        description: Pure Storage List Administrators\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-admins\n        method: POST\n        path: /api/2.52/admins\n        description: Pure Storage Create an Administrator\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-api-admins\n        method: DELETE\n        path: /api/2.52/admins\n        description: Pure Storage Delete an Administrator\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: patch-api-admins\n        method: PATCH\n        path: /api/2.52/admins\n        description: Pure Storage Modify an Administrator\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-policies-management-access-get\n        method: GET\n        path: /api/2.52/admins/policies/management-access\n        description: Pure Storage List Management Access Policies Attached to Administrators\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-policies-management-access-post\n        method: POST\n        path: /api/2.52/admins/policies/management-access\n        description: Pure Storage Create a Membership Between an Administrator with One or More Management Access Policies.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: log-targets\n      description: Log Targets resources on FlashArray REST API\n      operations:\n      - name: get-api-log-targets\n        method: GET\n        path: /api/2.52/log-targets\n        description: Pure Storage List Log Targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-log-targets-file\n        method: GET\n        path: /api/2.52/log-targets/file\n        description: Pure Storage List File Log Targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-log-targets-file\n        method: POST\n        path: /api/2.52/log-targets/file\n        description: Pure Storage Create File Log\
  \ Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-log-targets-file\n        method: DELETE\n        path: /api/2.52/log-targets/file\n        description: Pure Storage Delete File Log Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-log-targets-file\n        method: PATCH\n        path: /api/2.52/log-targets/file\n        description: Pure Storage Modify File Log Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-log-targets-syslog\n        method: GET\n        path: /api/2.52/log-targets/syslog\n        description: Pure Storage List Syslog Servers\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: flashblade-rest-api\n    baseUri: https://[blade]/api/2.26\n    description: Pure Storage FlashBlade REST API for managing unified fast file and object storage including file systems,\n      buckets, network configuration, and platform management.\n    authentication:\n      type: apikey\n      key: x-auth-token\n      value: '{{PURE_FB_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: file-systems\n      description: File Systems resources on FlashBlade REST API\n      operations:\n      - name: get-api-file-systems\n        method: GET\n        path: /api/2.26/file-systems\n        description: Pure Storage GET File-systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-file-systems\n        method: POST\n        path: /api/2.26/file-systems\n\
  \        description: Pure Storage POST File-systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-api-file-systems\n        method: DELETE\n        path: /api/2.26/file-systems\n        description: Pure Storage DELETE File-systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-file-systems\n        method: PATCH\n        path: /api/2.26/file-systems\n        description: Pure Storage PATCH File-systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-file-systems-data-eviction-policies\n        method: GET\n        path: /api/2.26/file-systems/data-eviction-policies\n    \
  \    description: Pure Storage GET File-systems/data-eviction-policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-file-systems-data-eviction-policies\n        method: POST\n        path: /api/2.26/file-systems/data-eviction-policies\n        description: Pure Storage POST File-systems/data-eviction-policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: policies-management-access\n      description: Policies - Management Access resources on FlashBlade REST API\n      operations:\n      - name: get-admins-management-access-policies\n        method: GET\n        path: /api/2.26/admins/management-access-policies\n        description: Pure Storage GET Admins/management-access-policies\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: post-admins-management-access-policies\n        method: POST\n        path: /api/2.26/admins/management-access-policies\n        description: Pure Storage POST Admins/management-access-policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-admins-management-access-policies\n        method: DELETE\n        path: /api/2.26/admins/management-access-policies\n        description: Pure Storage DELETE Admins/management-access-policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-roles-management-access-policies\n        method: GET\n        path: /api/2.26/directory-services/roles/management-access-policies\n        description: Pure Storage GET Directory-services/roles/management-access-policies\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-roles-management-access-policies\n        method: POST\n        path: /api/2.26/directory-services/roles/management-access-policies\n        description: Pure Storage POST Directory-services/roles/management-access-policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-roles-management-access-policies\n        method: DELETE\n        path: /api/2.26/directory-services/roles/management-access-policies\n        description: Pure Storage DELETE Directory-services/roles/management-access-policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: directory-services\n      description: Directory Services\
  \ resources on FlashBlade REST API\n      operations:\n      - name: get-api-directory-services\n        method: GET\n        path: /api/2.26/directory-services\n        description: Pure Storage GET Directory-services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-directory-services\n        method: PATCH\n        path: /api/2.26/directory-services\n        description: Pure Storage PATCH Directory-services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-directory-services-roles\n        method: GET\n        path: /api/2.26/directory-services/roles\n        description: Pure Storage GET Directory-service/roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: post-directory-services-roles\n        method: POST\n        path: /api/2.26/directory-services/roles\n        description: Pure Storage POST Directory-service/roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-directory-services-roles\n        method: DELETE\n        path: /api/2.26/directory-services/roles\n        description: Pure Storage DELETE Directory-service/roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-directory-services-roles\n        method: PATCH\n        path: /api/2.26/directory-services/roles\n        description: Pure Storage PATCH Directory-service/roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \     body:\n          type: json\n          data: {}\n    - name: buckets\n      description: Buckets resources on FlashBlade REST API\n      operations:\n      - name: get-api-bucket-audit-filter-actions\n        method: GET\n        path: /api/2.26/bucket-audit-filter-actions\n        description: Pure Storage GET Bucket-audit-filter-actions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-api-buckets\n        method: GET\n        path: /api/2.26/buckets\n        description: Pure Storage GET Buckets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-buckets\n        method: POST\n        path: /api/2.26/buckets\n        description: Pure Storage POST Buckets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \     body:\n          type: json\n          data: {}\n      - name: delete-api-buckets\n        method: DELETE\n        path: /api/2.26/buckets\n        description: Pure Storage DELETE Buckets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-api-buckets\n        method: PATCH\n        path: /api/2.26/buckets\n        description: Pure Storage PATCH Buckets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-buckets-audit-filters\n      \n\n# --- truncated at 32 KB (65 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/pure-storage/refs/heads/main/capabilities/storage-fleet-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pure-storage/refs/heads/main/capabilities/storage-fleet-management.yaml
tags:
- Pure Storage
- Fleet Management
- Storage Administration
- FlashArray
- FlashBlade
- Pure1
tools:
- description: List FlashArray arrays.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: fa-list-arrays
- description: List FlashArray volumes.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: fa-list-volumes
- description: List FlashArray hosts.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: fa-list-hosts
- description: List FlashArray protection groups for replication and snapshots.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: fa-list-protection-groups
- description: List FlashBlade arrays.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: fb-list-arrays
- description: List FlashBlade file systems.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: fb-list-file-systems
- description: List FlashBlade S3 buckets.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: fb-list-buckets
- description: List arrays known to Pure1.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: pure1-list-arrays
- description: List Pure1 fleet-wide alerts.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: pure1-list-alerts
- description: List Pure1 fleet metrics catalog.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: pure1-list-metrics
- description: List Pure1 sustainability metrics for arrays.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: pure1-list-sustainability
- description: List Pure1 subscription information.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: pure1-list-subscriptions
---
