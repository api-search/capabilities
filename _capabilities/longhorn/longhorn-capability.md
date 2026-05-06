---
categories: []
consumed_apis: []
description: The Longhorn Manager REST API provides programmatic access to all Longhorn storage management operations. The API follows the Rancher REST API specification and is served by the Longhorn Manager service, typically accessible within a Kubernetes cluster at port 9500 or via the longhorn-backend service. It provides full lifecycle management for volumes, snapshots, backups, nodes, disks, engine images, recurring jobs, and system settings. The API is used by the Longhorn UI and can be accessed directly for automation and integration. The schema is discoverable at /v1/schemas.
layout: capability
name: Longhorn Manager API
operations:
- description: Longhorn List volumes
  method: GET
  name: listvolumes
  path: /v1/volumes
- description: Longhorn Create a volume
  method: POST
  name: createvolume
  path: /v1/volumes
- description: Longhorn Get a volume
  method: GET
  name: getvolume
  path: /v1/volumes/{volumeName}
- description: Longhorn Delete a volume
  method: DELETE
  name: deletevolume
  path: /v1/volumes/{volumeName}
- description: Longhorn Attach a volume to a node
  method: POST
  name: attachvolume
  path: /v1/volumes/{volumeName}?action=attach
- description: Longhorn Detach a volume from its node
  method: POST
  name: detachvolume
  path: /v1/volumes/{volumeName}?action=detach
- description: Longhorn Expand a volume
  method: POST
  name: expandvolume
  path: /v1/volumes/{volumeName}?action=expand
- description: Longhorn Create a snapshot
  method: POST
  name: createsnapshot
  path: /v1/volumes/{volumeName}?action=snapshotCreate
- description: Longhorn List snapshots for a volume
  method: GET
  name: listsnapshots
  path: /v1/volumes/{volumeName}?action=snapshotList
- description: Longhorn Delete a snapshot
  method: POST
  name: deletesnapshot
  path: /v1/volumes/{volumeName}?action=snapshotDelete
- description: Longhorn Revert a volume to a snapshot
  method: POST
  name: revertsnapshot
  path: /v1/volumes/{volumeName}?action=snapshotRevert
- description: Longhorn Back up a snapshot
  method: POST
  name: backupsnapshot
  path: /v1/volumes/{volumeName}?action=snapshotBackup
- description: Longhorn List backup volumes
  method: GET
  name: listbackupvolumes
  path: /v1/backupvolumes
- description: Longhorn Get a backup volume
  method: GET
  name: getbackupvolume
  path: /v1/backupvolumes/{backupVolumeName}
- description: Longhorn List backups for a backup volume
  method: GET
  name: listbackups
  path: /v1/backupvolumes/{backupVolumeName}/backups
- description: Longhorn List nodes
  method: GET
  name: listnodes
  path: /v1/nodes
- description: Longhorn Get a node
  method: GET
  name: getnode
  path: /v1/nodes/{nodeId}
- description: Longhorn Update a node
  method: PUT
  name: updatenode
  path: /v1/nodes/{nodeId}
- description: Longhorn List engine images
  method: GET
  name: listengineimages
  path: /v1/engineimages
- description: Longhorn Create an engine image
  method: POST
  name: createengineimage
  path: /v1/engineimages
- description: Longhorn Get an engine image
  method: GET
  name: getengineimage
  path: /v1/engineimages/{engineImageName}
- description: Longhorn Delete an engine image
  method: DELETE
  name: deleteengineimage
  path: /v1/engineimages/{engineImageName}
- description: Longhorn List recurring jobs
  method: GET
  name: listrecurringjobs
  path: /v1/recurringjobs
- description: Longhorn Create a recurring job
  method: POST
  name: createrecurringjob
  path: /v1/recurringjobs
- description: Longhorn Get a recurring job
  method: GET
  name: getrecurringjob
  path: /v1/recurringjobs/{recurringJobName}
- description: Longhorn Update a recurring job
  method: PUT
  name: updaterecurringjob
  path: /v1/recurringjobs/{recurringJobName}
- description: Longhorn Delete a recurring job
  method: DELETE
  name: deleterecurringjob
  path: /v1/recurringjobs/{recurringJobName}
- description: Longhorn List all settings
  method: GET
  name: listsettings
  path: /v1/settings
- description: Longhorn Get a setting
  method: GET
  name: getsetting
  path: /v1/settings/{settingName}
- description: Longhorn Update a setting
  method: PUT
  name: updatesetting
  path: /v1/settings/{settingName}
- description: Longhorn List backing images
  method: GET
  name: listbackingimages
  path: /v1/backingimages
- description: Longhorn Create a backing image
  method: POST
  name: createbackingimage
  path: /v1/backingimages
- description: Longhorn List system backups
  method: GET
  name: listsystembackups
  path: /v1/systembackups
- description: Longhorn Create a system backup
  method: POST
  name: createsystembackup
  path: /v1/systembackups
personas: []
provider_name: Longhorn
provider_slug: longhorn
search_terms:
- longhorn create a snapshot
- longhorn create an engine image
- longhorn list system backups
- longhorn expand a volume
- updatesetting
- incubating
- longhorn create a recurring job
- listbackupvolumes
- createengineimage
- listvolumes
- longhorn
- deletevolume
- listsnapshots
- longhorn attach a volume to a node
- revertsnapshot
- longhorn get a volume
- backupsnapshot
- longhorn get a backup volume
- listnodes
- longhorn list recurring jobs
- detachvolume
- updatenode
- deleterecurringjob
- listsettings
- createbackingimage
- longhorn create a backing image
- createsnapshot
- getnode
- longhorn create a system backup
- longhorn get an engine image
- backup
- longhorn list snapshots for a volume
- listbackups
- createsystembackup
- cloud native
- block storage
- kubernetes
- getrecurringjob
- persistent volumes
- longhorn delete an engine image
- getsetting
- longhorn create a volume
- longhorn back up a snapshot
- listsystembackups
- expandvolume
- longhorn detach a volume from its node
- longhorn delete a volume
- longhorn list engine images
- longhorn list nodes
- longhorn get a recurring job
- deleteengineimage
- longhorn update a setting
- api
- longhorn delete a recurring job
- longhorn get a setting
- longhorn update a node
- getengineimage
- longhorn get a node
- attachvolume
- updaterecurringjob
- listbackingimages
- getvolume
- createrecurringjob
- longhorn revert a volume to a snapshot
- deletesnapshot
- longhorn list backups for a backup volume
- longhorn list all settings
- longhorn list backing images
- longhorn delete a snapshot
- longhorn list backup volumes
- longhorn update a recurring job
- getbackupvolume
- createvolume
- listrecurringjobs
- listengineimages
- longhorn list volumes
slug: longhorn-capability
source_filename: longhorn-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Longhorn Manager API\n  description: The Longhorn Manager REST API provides programmatic access to all Longhorn storage management operations. The\n    API follows the Rancher REST API specification and is served by the Longhorn Manager service, typically accessible within\n    a Kubernetes cluster at port 9500 or via the longhorn-backend service. It provides full lifecycle management for volumes,\n    snapshots, backups, nodes, disks, engine images, recurring jobs, and system settings. The API is used by the Longhorn\n    UI and can be accessed directly for automation and integration. The schema is discoverable at /v1/schemas.\n  tags:\n  - Longhorn\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: longhorn\n    baseUri: http://longhorn-backend:9500\n    description: Longhorn Manager API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LONGHORN_TOKEN}}'\n\
  \    resources:\n    - name: v1-volumes\n      path: /v1/volumes\n      operations:\n      - name: listvolumes\n        method: GET\n        description: Longhorn List volumes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvolume\n        method: POST\n        description: Longhorn Create a volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-volumes-volumename\n      path: /v1/volumes/{volumeName}\n      operations:\n      - name: getvolume\n        method: GET\n        description: Longhorn Get a volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletevolume\n        method: DELETE\n        description: Longhorn Delete a volume\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: v1-volumes-volumename-action-attach\n      path: /v1/volumes/{volumeName}?action=attach\n      operations:\n      - name: attachvolume\n        method: POST\n        description: Longhorn Attach a volume to a node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-volumes-volumename-action-detach\n      path: /v1/volumes/{volumeName}?action=detach\n      operations:\n      - name: detachvolume\n        method: POST\n        description: Longhorn Detach a volume from its node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-volumes-volumename-action-expand\n      path: /v1/volumes/{volumeName}?action=expand\n      operations:\n      - name: expandvolume\n        method: POST\n        description: Longhorn Expand a volume\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-volumes-volumename-action-snapshotcreate\n      path: /v1/volumes/{volumeName}?action=snapshotCreate\n      operations:\n      - name: createsnapshot\n        method: POST\n        description: Longhorn Create a snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-volumes-volumename-action-snapshotlist\n      path: /v1/volumes/{volumeName}?action=snapshotList\n      operations:\n      - name: listsnapshots\n        method: GET\n        description: Longhorn List snapshots for a volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-volumes-volumename-action-snapshotdelete\n      path: /v1/volumes/{volumeName}?action=snapshotDelete\n      operations:\n      - name:\
  \ deletesnapshot\n        method: POST\n        description: Longhorn Delete a snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-volumes-volumename-action-snapshotrevert\n      path: /v1/volumes/{volumeName}?action=snapshotRevert\n      operations:\n      - name: revertsnapshot\n        method: POST\n        description: Longhorn Revert a volume to a snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-volumes-volumename-action-snapshotbackup\n      path: /v1/volumes/{volumeName}?action=snapshotBackup\n      operations:\n      - name: backupsnapshot\n        method: POST\n        description: Longhorn Back up a snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-backupvolumes\n      path: /v1/backupvolumes\n\
  \      operations:\n      - name: listbackupvolumes\n        method: GET\n        description: Longhorn List backup volumes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-backupvolumes-backupvolumename\n      path: /v1/backupvolumes/{backupVolumeName}\n      operations:\n      - name: getbackupvolume\n        method: GET\n        description: Longhorn Get a backup volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-backupvolumes-backupvolumename-backups\n      path: /v1/backupvolumes/{backupVolumeName}/backups\n      operations:\n      - name: listbackups\n        method: GET\n        description: Longhorn List backups for a backup volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-nodes\n      path:\
  \ /v1/nodes\n      operations:\n      - name: listnodes\n        method: GET\n        description: Longhorn List nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-nodes-nodeid\n      path: /v1/nodes/{nodeId}\n      operations:\n      - name: getnode\n        method: GET\n        description: Longhorn Get a node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatenode\n        method: PUT\n        description: Longhorn Update a node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-engineimages\n      path: /v1/engineimages\n      operations:\n      - name: listengineimages\n        method: GET\n        description: Longhorn List engine images\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: createengineimage\n        method: POST\n        description: Longhorn Create an engine image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-engineimages-engineimagename\n      path: /v1/engineimages/{engineImageName}\n      operations:\n      - name: getengineimage\n        method: GET\n        description: Longhorn Get an engine image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteengineimage\n        method: DELETE\n        description: Longhorn Delete an engine image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-recurringjobs\n      path: /v1/recurringjobs\n      operations:\n      - name: listrecurringjobs\n  \
  \      method: GET\n        description: Longhorn List recurring jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrecurringjob\n        method: POST\n        description: Longhorn Create a recurring job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-recurringjobs-recurringjobname\n      path: /v1/recurringjobs/{recurringJobName}\n      operations:\n      - name: getrecurringjob\n        method: GET\n        description: Longhorn Get a recurring job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterecurringjob\n        method: PUT\n        description: Longhorn Update a recurring job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n      - name: deleterecurringjob\n        method: DELETE\n        description: Longhorn Delete a recurring job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-settings\n      path: /v1/settings\n      operations:\n      - name: listsettings\n        method: GET\n        description: Longhorn List all settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-settings-settingname\n      path: /v1/settings/{settingName}\n      operations:\n      - name: getsetting\n        method: GET\n        description: Longhorn Get a setting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesetting\n        method: PUT\n        description: Longhorn Update a setting\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-backingimages\n      path: /v1/backingimages\n      operations:\n      - name: listbackingimages\n        method: GET\n        description: Longhorn List backing images\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbackingimage\n        method: POST\n        description: Longhorn Create a backing image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-systembackups\n      path: /v1/systembackups\n      operations:\n      - name: listsystembackups\n        method: GET\n        description: Longhorn List system backups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsystembackup\n        method:\
  \ POST\n        description: Longhorn Create a system backup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: longhorn-rest\n    description: REST adapter for Longhorn Manager API.\n    resources:\n    - path: /v1/volumes\n      name: listvolumes\n      operations:\n      - method: GET\n        name: listvolumes\n        description: Longhorn List volumes\n        call: longhorn.listvolumes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes\n      name: createvolume\n      operations:\n      - method: POST\n        name: createvolume\n        description: Longhorn Create a volume\n        call: longhorn.createvolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{volumeName}\n      name: getvolume\n      operations:\n      - method: GET\n        name:\
  \ getvolume\n        description: Longhorn Get a volume\n        call: longhorn.getvolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{volumeName}\n      name: deletevolume\n      operations:\n      - method: DELETE\n        name: deletevolume\n        description: Longhorn Delete a volume\n        call: longhorn.deletevolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{volumeName}?action=attach\n      name: attachvolume\n      operations:\n      - method: POST\n        name: attachvolume\n        description: Longhorn Attach a volume to a node\n        call: longhorn.attachvolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{volumeName}?action=detach\n      name: detachvolume\n      operations:\n      - method: POST\n        name: detachvolume\n        description: Longhorn Detach a volume from its node\n        call: longhorn.detachvolume\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{volumeName}?action=expand\n      name: expandvolume\n      operations:\n      - method: POST\n        name: expandvolume\n        description: Longhorn Expand a volume\n        call: longhorn.expandvolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{volumeName}?action=snapshotCreate\n      name: createsnapshot\n      operations:\n      - method: POST\n        name: createsnapshot\n        description: Longhorn Create a snapshot\n        call: longhorn.createsnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{volumeName}?action=snapshotList\n      name: listsnapshots\n      operations:\n      - method: GET\n        name: listsnapshots\n        description: Longhorn List snapshots for a volume\n        call: longhorn.listsnapshots\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/volumes/{volumeName}?action=snapshotDelete\n      name: deletesnapshot\n      operations:\n      - method: POST\n        name: deletesnapshot\n        description: Longhorn Delete a snapshot\n        call: longhorn.deletesnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{volumeName}?action=snapshotRevert\n      name: revertsnapshot\n      operations:\n      - method: POST\n        name: revertsnapshot\n        description: Longhorn Revert a volume to a snapshot\n        call: longhorn.revertsnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/volumes/{volumeName}?action=snapshotBackup\n      name: backupsnapshot\n      operations:\n      - method: POST\n        name: backupsnapshot\n        description: Longhorn Back up a snapshot\n        call: longhorn.backupsnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/backupvolumes\n      name: listbackupvolumes\n      operations:\n      - method: GET\n        name: listbackupvolumes\n        description: Longhorn List backup volumes\n        call: longhorn.listbackupvolumes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/backupvolumes/{backupVolumeName}\n      name: getbackupvolume\n      operations:\n      - method: GET\n        name: getbackupvolume\n        description: Longhorn Get a backup volume\n        call: longhorn.getbackupvolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/backupvolumes/{backupVolumeName}/backups\n      name: listbackups\n      operations:\n      - method: GET\n        name: listbackups\n        description: Longhorn List backups for a backup volume\n        call: longhorn.listbackups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes\n      name: listnodes\n      operations:\n\
  \      - method: GET\n        name: listnodes\n        description: Longhorn List nodes\n        call: longhorn.listnodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes/{nodeId}\n      name: getnode\n      operations:\n      - method: GET\n        name: getnode\n        description: Longhorn Get a node\n        call: longhorn.getnode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes/{nodeId}\n      name: updatenode\n      operations:\n      - method: PUT\n        name: updatenode\n        description: Longhorn Update a node\n        call: longhorn.updatenode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engineimages\n      name: listengineimages\n      operations:\n      - method: GET\n        name: listengineimages\n        description: Longhorn List engine images\n        call: longhorn.listengineimages\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/engineimages\n      name: createengineimage\n      operations:\n      - method: POST\n        name: createengineimage\n        description: Longhorn Create an engine image\n        call: longhorn.createengineimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engineimages/{engineImageName}\n      name: getengineimage\n      operations:\n      - method: GET\n        name: getengineimage\n        description: Longhorn Get an engine image\n        call: longhorn.getengineimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engineimages/{engineImageName}\n      name: deleteengineimage\n      operations:\n      - method: DELETE\n        name: deleteengineimage\n        description: Longhorn Delete an engine image\n        call: longhorn.deleteengineimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recurringjobs\n\
  \      name: listrecurringjobs\n      operations:\n      - method: GET\n        name: listrecurringjobs\n        description: Longhorn List recurring jobs\n        call: longhorn.listrecurringjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recurringjobs\n      name: createrecurringjob\n      operations:\n      - method: POST\n        name: createrecurringjob\n        description: Longhorn Create a recurring job\n        call: longhorn.createrecurringjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recurringjobs/{recurringJobName}\n      name: getrecurringjob\n      operations:\n      - method: GET\n        name: getrecurringjob\n        description: Longhorn Get a recurring job\n        call: longhorn.getrecurringjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recurringjobs/{recurringJobName}\n      name: updaterecurringjob\n      operations:\n  \
  \    - method: PUT\n        name: updaterecurringjob\n        description: Longhorn Update a recurring job\n        call: longhorn.updaterecurringjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recurringjobs/{recurringJobName}\n      name: deleterecurringjob\n      operations:\n      - method: DELETE\n        name: deleterecurringjob\n        description: Longhorn Delete a recurring job\n        call: longhorn.deleterecurringjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/settings\n      name: listsettings\n      operations:\n      - method: GET\n        name: listsettings\n        description: Longhorn List all settings\n        call: longhorn.listsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/settings/{settingName}\n      name: getsetting\n      operations:\n      - method: GET\n        name: getsetting\n        description: Longhorn Get a\
  \ setting\n        call: longhorn.getsetting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/settings/{settingName}\n      name: updatesetting\n      operations:\n      - method: PUT\n        name: updatesetting\n        description: Longhorn Update a setting\n        call: longhorn.updatesetting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/backingimages\n      name: listbackingimages\n      operations:\n      - method: GET\n        name: listbackingimages\n        description: Longhorn List backing images\n        call: longhorn.listbackingimages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/backingimages\n      name: createbackingimage\n      operations:\n      - method: POST\n        name: createbackingimage\n        description: Longhorn Create a backing image\n        call: longhorn.createbackingimage\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/systembackups\n      name: listsystembackups\n      operations:\n      - method: GET\n        name: listsystembackups\n        description: Longhorn List system backups\n        call: longhorn.listsystembackups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/systembackups\n      name: createsystembackup\n      operations:\n      - method: POST\n        name: createsystembackup\n        description: Longhorn Create a system backup\n        call: longhorn.createsystembackup\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: longhorn-mcp\n    transport: http\n    description: MCP adapter for Longhorn Manager API for AI agent use.\n    tools:\n    - name: listvolumes\n      description: Longhorn List volumes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.listvolumes\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvolume\n      description: Longhorn Create a volume\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.createvolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvolume\n      description: Longhorn Get a volume\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.getvolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletevolume\n      description: Longhorn Delete a volume\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: longhorn.deletevolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: attachvolume\n      description: Longhorn Attach a volume to a node\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: longhorn.attachvolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detachvolume\n      description: Longhorn Detach a volume from its node\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.detachvolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: expandvolume\n      description: Longhorn Expand a volume\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.expandvolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsnapshot\n      description: Longhorn Create a snapshot\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.createsnapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsnapshots\n      description:\
  \ Longhorn List snapshots for a volume\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.listsnapshots\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesnapshot\n      description: Longhorn Delete a snapshot\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.deletesnapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revertsnapshot\n      description: Longhorn Revert a volume to a snapshot\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.revertsnapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: backupsnapshot\n      description: Longhorn Back up a snapshot\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.backupsnapshot\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbackupvolumes\n      description: Longhorn List backup volumes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.listbackupvolumes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbackupvolume\n      description: Longhorn Get a backup volume\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.getbackupvolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbackups\n      description: Longhorn List backups for a backup volume\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.listbackups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnodes\n      description: Longhorn List nodes\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: longhorn.listnodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnode\n      description: Longhorn Get a node\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.getnode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatenode\n      description: Longhorn Update a node\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: longhorn.updatenode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listengineimages\n      description: Longhorn List engine images\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.listengineimages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createengineimage\n      description:\
  \ Longhorn Create an engine image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.createengineimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getengineimage\n      description: Longhorn Get an engine image\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.getengineimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteengineimage\n      description: Longhorn Delete an engine image\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: longhorn.deleteengineimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecurringjobs\n      description: Longhorn List recurring jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.listrecurringjobs\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrecurringjob\n      description: Longhorn Create a recurring job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.createrecurringjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrecurringjob\n      description: Longhorn Get a recurring job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.getrecurringjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterecurringjob\n      description: Longhorn Update a recurring job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: longhorn.updaterecurringjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterecurringjob\n      description: Longhorn Delete a recurring job\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: longhorn.deleterecurringjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsettings\n      description: Longhorn List all settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.listsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsetting\n      description: Longhorn Get a setting\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.getsetting\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesetting\n      description: Longhorn Update a setting\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: longhorn.updatesetting\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: listbackingimages\n      description: Longhorn List backing images\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.listbackingimages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbackingimage\n      description: Longhorn Create a backing image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: longhorn.createbackingimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsystembackups\n      description: Longhorn List system backups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: longhorn.listsystembackups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsystembackup\n      description: Longhorn Create a system backup\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: longhorn.createsystembackup\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LONGHORN_TOKEN: LONGHORN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/longhorn/refs/heads/main/capabilities/longhorn-capability.yaml
tags:
- Longhorn
- API
tools:
- description: Longhorn List volumes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvolumes
- description: Longhorn Create a volume
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvolume
- description: Longhorn Get a volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvolume
- description: Longhorn Delete a volume
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletevolume
- description: Longhorn Attach a volume to a node
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: attachvolume
- description: Longhorn Detach a volume from its node
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: detachvolume
- description: Longhorn Expand a volume
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: expandvolume
- description: Longhorn Create a snapshot
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsnapshot
- description: Longhorn List snapshots for a volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsnapshots
- description: Longhorn Delete a snapshot
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletesnapshot
- description: Longhorn Revert a volume to a snapshot
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revertsnapshot
- description: Longhorn Back up a snapshot
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: backupsnapshot
- description: Longhorn List backup volumes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackupvolumes
- description: Longhorn Get a backup volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbackupvolume
- description: Longhorn List backups for a backup volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackups
- description: Longhorn List nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodes
- description: Longhorn Get a node
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnode
- description: Longhorn Update a node
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatenode
- description: Longhorn List engine images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listengineimages
- description: Longhorn Create an engine image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createengineimage
- description: Longhorn Get an engine image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getengineimage
- description: Longhorn Delete an engine image
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteengineimage
- description: Longhorn List recurring jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecurringjobs
- description: Longhorn Create a recurring job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrecurringjob
- description: Longhorn Get a recurring job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecurringjob
- description: Longhorn Update a recurring job
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterecurringjob
- description: Longhorn Delete a recurring job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterecurringjob
- description: Longhorn List all settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsettings
- description: Longhorn Get a setting
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsetting
- description: Longhorn Update a setting
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesetting
- description: Longhorn List backing images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackingimages
- description: Longhorn Create a backing image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbackingimage
- description: Longhorn List system backups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsystembackups
- description: Longhorn Create a system backup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsystembackup
---
