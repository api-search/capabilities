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
- amazon ebs detach volume
- delete volume
- attach volume
- block storage
- amazon ebs delete volume
- volumes
- createVolume
- block storage management business domain for amazon ebs.
- amazon ebs describe volumes
- describeVolumes
- create snapshot
- amazon ebs
- ebs
- describe snapshots
- createSnapshot
- describeSnapshots
- snapshots
- create volume
- amazon web services
- detach volume
- workflow capability for block storage management.
- engineers managing amazon ebs resources on aws.
- aws
- amazon ebs create snapshot
- amazon ebs create volume
- detachVolume
- amazon ebs describe snapshots
- attachVolume
- describe volumes
- amazon ebs attach volume
- ec2
- storage
- deleteVolume
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
