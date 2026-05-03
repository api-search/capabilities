---
categories: []
consumed_apis: []
description: Manage fully managed Amazon FSx file systems including Lustre, Windows File Server, NetApp ONTAP, and OpenZFS.
layout: capability
name: Amazon FSx File System Management
operations: []
personas: []
provider_name: Amazon FSx
provider_slug: amazon-fsx
search_terms:
- lustre
- file systems
- netapp
- high performance computing
- storage
- aws
- windows
- netapp ontap
- openzfs
slug: amazon-fsx-file-system-management
source_filename: amazon-fsx-file-system-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon FSx File System Management\n  description: Manage fully managed Amazon FSx file systems including Lustre, Windows File Server, NetApp ONTAP, and OpenZFS.\n  tags:\n  - Storage\n  - File Systems\n  - High Performance Computing\n  - NetApp ONTAP\n  - Lustre\n  - AWS\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - namespace: fsx\n    ref: capabilities/shared/fsx.yaml\n  exposes:\n  - type: rest\n    port: 8080\n  - type: mcp\n    port: 9090\n  tools:\n  - name: createFileSystem\n    description: Create an Amazon FSx file system\n    inputSchema:\n      type: object\n      properties:\n        FileSystemType:\n          type: string\n        StorageCapacity:\n          type: integer\n        SubnetIds:\n          type: array\n        StorageType:\n          type: string\n        KmsKeyId:\n      \
  \    type: string\n        Tags:\n          type: array\n      required:\n      - FileSystemType\n      - StorageCapacity\n      - SubnetIds\n  - name: describeFileSystems\n    description: Describe file systems\n    inputSchema:\n      type: object\n      properties:\n        FileSystemIds:\n          type: array\n        MaxResults:\n          type: integer\n        NextToken:\n          type: string\n  - name: updateFileSystem\n    description: Update a file system configuration\n    inputSchema:\n      type: object\n      properties:\n        FileSystemId:\n          type: string\n        StorageCapacity:\n          type: integer\n      required:\n      - FileSystemId\n  - name: deleteFileSystem\n    description: Delete an Amazon FSx file system\n    inputSchema:\n      type: object\n      properties:\n        FileSystemId:\n          type: string\n        FinalBackup:\n          type: object\n      required:\n      - FileSystemId\n  - name: createBackup\n    description: Create a\
  \ backup of an Amazon FSx file system\n    inputSchema:\n      type: object\n      properties:\n        FileSystemId:\n          type: string\n        Tags:\n          type: array\n      required:\n      - FileSystemId\n  - name: describeBackups\n    description: Describe backups\n    inputSchema:\n      type: object\n      properties:\n        BackupIds:\n          type: array\n        MaxResults:\n          type: integer\n        NextToken:\n          type: string\n  - name: deleteBackup\n    description: Delete a backup\n    inputSchema:\n      type: object\n      properties:\n        BackupId:\n          type: string\n      required:\n      - BackupId\n  - name: createSnapshot\n    description: Create a snapshot of an OpenZFS volume\n    inputSchema:\n      type: object\n      properties:\n        Name:\n          type: string\n        VolumeId:\n          type: string\n        Tags:\n          type: array\n      required:\n      - Name\n      - VolumeId\n  - name: describeSnapshots\n\
  \    description: Describe snapshots\n    inputSchema:\n      type: object\n      properties:\n        SnapshotIds:\n          type: array\n        MaxResults:\n          type: integer\n        NextToken:\n          type: string\n  - name: createStorageVirtualMachine\n    description: Create a storage virtual machine in an ONTAP file system\n    inputSchema:\n      type: object\n      properties:\n        FileSystemId:\n          type: string\n        Name:\n          type: string\n        RootVolumeSecurityStyle:\n          type: string\n      required:\n      - FileSystemId\n      - Name\n  - name: describeStorageVirtualMachines\n    description: Describe storage virtual machines\n    inputSchema:\n      type: object\n      properties:\n        StorageVirtualMachineIds:\n          type: array\n        MaxResults:\n          type: integer\n  - name: listTagsForResource\n    description: List tags for an FSx resource\n    inputSchema:\n      type: object\n      properties:\n        ResourceARN:\n\
  \          type: string\n      required:\n      - ResourceARN\n  - name: tagResource\n    description: Tag an FSx resource\n    inputSchema:\n      type: object\n      properties:\n        ResourceARN:\n          type: string\n        Tags:\n          type: array\n      required:\n      - ResourceARN\n      - Tags\n  - name: restoreVolumeFromSnapshot\n    description: Restore an OpenZFS volume from a snapshot\n    inputSchema:\n      type: object\n      properties:\n        VolumeId:\n          type: string\n        SnapshotId:\n          type: string\n      required:\n      - VolumeId\n      - SnapshotId\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-fsx/refs/heads/main/capabilities/amazon-fsx-file-system-management.yaml
tags:
- Storage
- File Systems
- High Performance Computing
- NetApp ONTAP
- Lustre
tools: []
---
