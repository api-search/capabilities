---
categories: []
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
- snapshots
- volumes
- describeVolumes
- attachVolume
- storage
- detachVolume
- describeSnapshots
- amazon ebs create snapshot
- amazon ebs attach volume
- amazon ebs
- describe snapshots
- createVolume
- create volume
- create snapshot
- amazon ebs describe volumes
- ebs
- createSnapshot
- block storage
- amazon ebs delete volume
- amazon ebs create volume
- engineers managing amazon ebs resources on aws.
- detach volume
- workflow capability for block storage management.
- ec2
- describe volumes
- block storage management business domain for amazon ebs.
- deleteVolume
- amazon web services
- aws
- delete volume
- attach volume
- amazon ebs detach volume
- amazon ebs describe snapshots
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
