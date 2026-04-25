---
consumed_apis:
- ebs
description: Unified capability for managing EBS volumes, snapshots, and encryption for cloud storage administrators.
layout: capability
name: Amazon EBS Block Storage Management
operations:
- description: Amazon EBS Describe Volumes
  method: GET
  name: describeVolumes
  path: /v1/resource
- description: Amazon EBS Create Volume
  method: POST
  name: createVolume
  path: /v1/resource
- description: Amazon EBS Delete Volume
  method: POST
  name: deleteVolume
  path: /v1/#DeleteVolume
- description: Amazon EBS Attach Volume
  method: POST
  name: attachVolume
  path: /v1/#AttachVolume
- description: Amazon EBS Detach Volume
  method: POST
  name: detachVolume
  path: /v1/#DetachVolume
- description: Amazon EBS Create Snapshot
  method: POST
  name: createSnapshot
  path: /v1/#CreateSnapshot
- description: Amazon EBS Describe Snapshots
  method: GET
  name: describeSnapshots
  path: /v1/#DescribeSnapshots
personas: []
provider_name: Amazon EBS
provider_slug: amazon-ebs
search_terms:
- ec2
- describe snapshots
- engineers managing amazon ebs resources on aws.
- amazon ebs describe snapshots
- detach volume
- deleteVolume
- amazon web services
- createVolume
- snapshots
- amazon ebs
- aws
- amazon ebs describe volumes
- volumes
- block storage management business domain for amazon ebs.
- describeVolumes
- describeSnapshots
- createSnapshot
- attach volume
- create volume
- workflow capability for block storage management.
- detachVolume
- ebs
- create snapshot
- amazon ebs create volume
- attachVolume
- delete volume
- storage
- describe volumes
- amazon ebs detach volume
- amazon ebs attach volume
- block storage
- amazon ebs delete volume
- amazon ebs create snapshot
slug: ebs-management
tags:
- Amazon EBS
- AWS
- Storage
- Block Storage
tools:
- description: Amazon EBS Describe Volumes
  hints:
    destructive: false
    readOnly: true
  name: describe-volumes
- description: Amazon EBS Create Volume
  hints:
    destructive: false
    readOnly: false
  name: create-volume
- description: Amazon EBS Delete Volume
  hints:
    destructive: false
    readOnly: false
  name: delete-volume
- description: Amazon EBS Attach Volume
  hints:
    destructive: false
    readOnly: false
  name: attach-volume
- description: Amazon EBS Detach Volume
  hints:
    destructive: false
    readOnly: false
  name: detach-volume
- description: Amazon EBS Create Snapshot
  hints:
    destructive: false
    readOnly: false
  name: create-snapshot
- description: Amazon EBS Describe Snapshots
  hints:
    destructive: false
    readOnly: true
  name: describe-snapshots
---
