---
categories: []
consumed_apis: []
description: Workflow capability for identity engineers and cloud architects to manage AWS Managed Microsoft Active Directory, including directory provisioning, trust relationships, domain controllers, snapshots, IP routing, and certificate management for hybrid identity workloads.
layout: capability
name: Amazon Directory Service Active Directory Management
operations:
- description: List all managed directories
  method: GET
  name: describe-directories
  path: /v1/directories
- description: Create an AWS Managed Microsoft AD directory
  method: POST
  name: create-microsoft-ad
  path: /v1/directories
- description: List trust relationships
  method: GET
  name: describe-trusts
  path: /v1/trusts
- description: Create a trust relationship
  method: POST
  name: create-trust
  path: /v1/trusts
- description: List directory snapshots
  method: GET
  name: describe-snapshots
  path: /v1/snapshots
- description: Create a manual directory snapshot
  method: POST
  name: create-snapshot
  path: /v1/snapshots
- description: List registered certificates
  method: GET
  name: list-certificates
  path: /v1/certificates
- description: List shared directories
  method: GET
  name: describe-shared-directories
  path: /v1/shared-directories
personas: []
provider_name: Amazon Directory Service
provider_slug: amazon-directory-service
search_terms:
- amazon directory service
- create trust
- managed active directory instances
- aws
- get the directory service limits for the current aws account and region
- get directory limits
- describe shared directories
- Cloud Architect
- identity engineer provisioning and managing active directory in aws
- share a directory with another aws account for multi-account access
- Identity Engineer
- list shared directories
- restore from snapshot
- create an aws managed microsoft ad directory
- describe trusts
- certificates for directory authentication
- create directory
- hybrid cloud
- describe domain controllers
- directory snapshots for backup and restore
- list directory snapshots
- list domain controllers provisioned for an aws managed microsoft ad directory
- certificate management, ldaps, and audit logging
- list certificates registered for ldaps or client certificate authentication
- cloud architect designing hybrid identity solutions with aws directory service
- provisioning and managing microsoft ad and simple ad directories
- list all managed directories
- create a manual directory snapshot
- identity management
- delete directory
- active directory
- list directories shared from your account or shared with your account
- create an aws managed microsoft active directory in the aws cloud
- create snapshot
- list all aws managed microsoft ad and simple ad directories in the account
- list certificates
- create microsoft ad
- end-to-end active directory lifecycle management using amazon directory service
- list trust relationships
- authentication
- directories shared with other aws accounts
- describe directories
- restore a directory to a previous state using a snapshot
- create a trust relationship
- list trust relationships established for aws managed microsoft ad directories
- trust relationships between directories
- share directory
- list registered certificates
- create a manual snapshot of a directory for backup
- describe snapshots
- create a simple ad directory powered by samba 4
- delete an aws directory service directory
- trust relationships and shared directory access across accounts
- create a trust relationship between aws managed microsoft ad and an on-premises directory
- directory services
- list manual snapshots of a directory for backup and restore purposes
slug: active-directory-management
source_filename: active-directory-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Directory Service Active Directory Management\n  description: Workflow capability for identity engineers and cloud architects to manage AWS Managed Microsoft Active Directory,\n    including directory provisioning, trust relationships, domain controllers, snapshots, IP routing, and certificate management\n    for hybrid identity workloads.\n  tags:\n  - Amazon Directory Service\n  - Active Directory\n  - Identity Management\n  - Hybrid Cloud\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: directory-service\n    baseUri: https://ds.amazonaws.com\n    description: Amazon Directory Service REST API for managing Active Directory.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n\
  \      placement: header\n    resources:\n    - name: directories\n      path: /\n      description: Managed directories\n      operations:\n      - name: describe-directories\n        method: POST\n        description: List all directories in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-directory\n        method: POST\n        description: Create a Simple AD directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-microsoft-ad\n        method: POST\n        description: Create an AWS Managed Microsoft AD directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-directory\n        method: POST\n        description: Delete a directory\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domain-controllers\n      path: /\n      description: Domain controllers for directories\n      operations:\n      - name: describe-domain-controllers\n        method: POST\n        description: List domain controllers for a directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trusts\n      path: /\n      description: Trust relationships between directories\n      operations:\n      - name: describe-trusts\n        method: POST\n        description: List trust relationships\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-trust\n        method: POST\n        description: Create a trust relationship\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: delete-trust\n        method: POST\n        description: Delete a trust relationship\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: snapshots\n      path: /\n      description: Directory snapshots\n      operations:\n      - name: describe-snapshots\n        method: POST\n        description: List directory snapshots\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-snapshot\n        method: POST\n        description: Create a manual snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restore-from-snapshot\n        method: POST\n        description: Restore a directory from a snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: delete-snapshot\n        method: POST\n        description: Delete a snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ip-routes\n      path: /\n      description: IP routes for Microsoft AD\n      operations:\n      - name: list-ip-routes\n        method: POST\n        description: List IP routes for a directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-ip-routes\n        method: POST\n        description: Add IP routes to a directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates\n      path: /\n      description: Certificates registered for directories\n      operations:\n      - name: list-certificates\n      \
  \  method: POST\n        description: List certificates for a directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: register-certificate\n        method: POST\n        description: Register a certificate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deregister-certificate\n        method: POST\n        description: Deregister a certificate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: log-subscriptions\n      path: /\n      description: Log subscriptions for directories\n      operations:\n      - name: list-log-subscriptions\n        method: POST\n        description: List log subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n      - name: create-log-subscription\n        method: POST\n        description: Create a log subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-log-subscription\n        method: POST\n        description: Delete a log subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shared-directories\n      path: /\n      description: Directories shared with other accounts\n      operations:\n      - name: share-directory\n        method: POST\n        description: Share a directory with another account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-shared-directories\n        method: POST\n        description: List shared directories\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unshare-directory\n        method: POST\n        description: Unshare a directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: limits\n      path: /\n      description: Directory service limits\n      operations:\n      - name: get-directory-limits\n        method: POST\n        description: Get directory limits for the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: directory-management-api\n    description: Unified REST API for Amazon Directory Service Active Directory management workflows.\n    resources:\n    - path: /v1/directories\n      name: directories\n      description: Managed Active Directory instances\n      operations:\n     \
  \ - method: GET\n        name: describe-directories\n        description: List all managed directories\n        call: directory-service.describe-directories\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-microsoft-ad\n        description: Create an AWS Managed Microsoft AD directory\n        call: directory-service.create-microsoft-ad\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trusts\n      name: trusts\n      description: Trust relationships between directories\n      operations:\n      - method: GET\n        name: describe-trusts\n        description: List trust relationships\n        call: directory-service.describe-trusts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-trust\n        description: Create a trust relationship\n        call: directory-service.create-trust\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/snapshots\n      name: snapshots\n      description: Directory snapshots for backup and restore\n      operations:\n      - method: GET\n        name: describe-snapshots\n        description: List directory snapshots\n        call: directory-service.describe-snapshots\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-snapshot\n        description: Create a manual directory snapshot\n        call: directory-service.create-snapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/certificates\n      name: certificates\n      description: Certificates for directory authentication\n      operations:\n      - method: GET\n        name: list-certificates\n        description: List registered certificates\n        call: directory-service.list-certificates\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/shared-directories\n      name: shared-directories\n      description: Directories shared with other AWS accounts\n      operations:\n      - method: GET\n        name: describe-shared-directories\n        description: List shared directories\n        call: directory-service.describe-shared-directories\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: directory-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Active Directory management.\n    tools:\n    - name: describe-directories\n      description: List all AWS Managed Microsoft AD and Simple AD directories in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: directory-service.describe-directories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-microsoft-ad\n      description: Create an AWS Managed Microsoft Active Directory in the\
  \ AWS Cloud\n      hints:\n        readOnly: false\n        destructive: false\n      call: directory-service.create-microsoft-ad\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-directory\n      description: Create a Simple AD directory powered by Samba 4\n      hints:\n        readOnly: false\n        destructive: false\n      call: directory-service.create-directory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-directory\n      description: Delete an AWS Directory Service directory\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: directory-service.delete-directory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-trusts\n      description: List trust relationships established for AWS Managed Microsoft AD directories\n      hints:\n        readOnly: true\n        openWorld: true\n      call: directory-service.describe-trusts\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-trust\n      description: Create a trust relationship between AWS Managed Microsoft AD and an on-premises directory\n      hints:\n        readOnly: false\n        destructive: false\n      call: directory-service.create-trust\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-snapshots\n      description: List manual snapshots of a directory for backup and restore purposes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: directory-service.describe-snapshots\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-snapshot\n      description: Create a manual snapshot of a directory for backup\n      hints:\n        readOnly: false\n        destructive: false\n      call: directory-service.create-snapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restore-from-snapshot\n\
  \      description: Restore a directory to a previous state using a snapshot\n      hints:\n        readOnly: false\n        destructive: false\n      call: directory-service.restore-from-snapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-domain-controllers\n      description: List domain controllers provisioned for an AWS Managed Microsoft AD directory\n      hints:\n        readOnly: true\n        openWorld: true\n      call: directory-service.describe-domain-controllers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-certificates\n      description: List certificates registered for LDAPS or client certificate authentication\n      hints:\n        readOnly: true\n        openWorld: true\n      call: directory-service.list-certificates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: share-directory\n      description: Share a directory with another AWS account for multi-account\
  \ access\n      hints:\n        readOnly: false\n        destructive: false\n      call: directory-service.share-directory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-shared-directories\n      description: List directories shared from your account or shared with your account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: directory-service.describe-shared-directories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-directory-limits\n      description: Get the directory service limits for the current AWS account and region\n      hints:\n        readOnly: true\n        openWorld: true\n      call: directory-service.get-directory-limits\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-directory-service/refs/heads/main/capabilities/active-directory-management.yaml
tags:
- Amazon Directory Service
- Active Directory
- Identity Management
- Hybrid Cloud
tools:
- description: List all AWS Managed Microsoft AD and Simple AD directories in the account
  hints:
    openWorld: true
    readOnly: true
  name: describe-directories
- description: Create an AWS Managed Microsoft Active Directory in the AWS Cloud
  hints:
    destructive: false
    readOnly: false
  name: create-microsoft-ad
- description: Create a Simple AD directory powered by Samba 4
  hints:
    destructive: false
    readOnly: false
  name: create-directory
- description: Delete an AWS Directory Service directory
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-directory
- description: List trust relationships established for AWS Managed Microsoft AD directories
  hints:
    openWorld: true
    readOnly: true
  name: describe-trusts
- description: Create a trust relationship between AWS Managed Microsoft AD and an on-premises directory
  hints:
    destructive: false
    readOnly: false
  name: create-trust
- description: List manual snapshots of a directory for backup and restore purposes
  hints:
    openWorld: true
    readOnly: true
  name: describe-snapshots
- description: Create a manual snapshot of a directory for backup
  hints:
    destructive: false
    readOnly: false
  name: create-snapshot
- description: Restore a directory to a previous state using a snapshot
  hints:
    destructive: false
    readOnly: false
  name: restore-from-snapshot
- description: List domain controllers provisioned for an AWS Managed Microsoft AD directory
  hints:
    openWorld: true
    readOnly: true
  name: describe-domain-controllers
- description: List certificates registered for LDAPS or client certificate authentication
  hints:
    openWorld: true
    readOnly: true
  name: list-certificates
- description: Share a directory with another AWS account for multi-account access
  hints:
    destructive: false
    readOnly: false
  name: share-directory
- description: List directories shared from your account or shared with your account
  hints:
    openWorld: true
    readOnly: true
  name: describe-shared-directories
- description: Get the directory service limits for the current AWS account and region
  hints:
    openWorld: true
    readOnly: true
  name: get-directory-limits
---
