---
categories: []
consumed_apis: []
description: OpenStorage SDK API capability.
layout: capability
name: OpenStorage SDK
operations:
- description: Delete alerts
  method: POST
  name: openstoragealerts-delete
  path: /v1/alerts
- description: Allows querying alerts.
  method: POST
  name: openstoragealerts-enumeratewithfilters
  path: /v1/alerts/filters
- description: POST /v1/bucket
  method: POST
  name: openstoragebucket-create
  path: /v1/bucket
- description: POST /v1/bucket/access/{bucket_id}
  method: POST
  name: openstoragebucket-grantaccess
  path: /v1/bucket/access/{bucket_id}
- description: POST /v1/bucket/revoke/{bucket_id}
  method: POST
  name: openstoragebucket-revokeaccess
  path: /v1/bucket/revoke/{bucket_id}
- description: DELETE /v1/bucket/{bucket_id}
  method: DELETE
  name: openstoragebucket-delete
  path: /v1/bucket/{bucket_id}
- description: Creates a backup request for a specified volume. Use OpenStorageCloudBackup.Status() to get the current status of the backup request.
  method: POST
  name: openstoragecloudbackup-create
  path: /v1/cloudbackups
- description: Deletes a backup stored in the cloud. If the backup is an incremental backup and other backups are dependent on it, it will not be able to be deleted.
  method: DELETE
  name: openstoragecloudbackup-delete
  path: /v1/cloudbackups/backup/{backup_id}
- description: Catalog returns a list of the contents in the backup
  method: POST
  name: openstoragecloudbackup-catalog
  path: /v1/cloudbackups/catalog
- description: DeleteAll deletes all the backups in the cloud for the specified volume.
  method: POST
  name: openstoragecloudbackup-deleteall
  path: /v1/cloudbackups/deleteall
- description: Return a list of backups for the specified volume
  method: POST
  name: openstoragecloudbackup-enumeratewithfilters
  path: /v1/cloudbackups/enumerate/filters
- description: Creates a group backup request for a specified group. Use OpenStorageCloudBackup.Status() to get the current status of the backup request.
  method: POST
  name: openstoragecloudbackup-groupcreate
  path: /v1/cloudbackups/group
- description: History returns a list of backups for a specified volume
  method: GET
  name: openstoragecloudbackup-history
  path: /v1/cloudbackups/history/{src_volume_id}
- description: Restore creates a new volume from a backup id. The newly created volume has an ha_level (number of replicas) of only 1. To increase the number of replicas, use OpenStorageVolume.Set() to change the ha_level.
  method: POST
  name: openstoragecloudbackup-restore
  path: /v1/cloudbackups/restore
- description: Enumerate cloud backup schedules
  method: GET
  name: openstoragecloudbackup-schedenumerate
  path: /v1/cloudbackups/schedules
- description: Create cloud backup schedule
  method: POST
  name: openstoragecloudbackup-schedcreate
  path: /v1/cloudbackups/schedules
- description: Update existing cloud backup schedule
  method: PUT
  name: openstoragecloudbackup-schedupdate
  path: /v1/cloudbackups/schedules
- description: Delete cloud backup schedule
  method: DELETE
  name: openstoragecloudbackup-scheddelete
  path: /v1/cloudbackups/schedules/{backup_schedule_id}
- description: Size returns the size of any cloud backups of a volume
  method: GET
  name: openstoragecloudbackup-size
  path: /v1/cloudbackups/size
- description: StateChange can be used to stop, pause, and restart a backup
  method: POST
  name: openstoragecloudbackup-statechange
  path: /v1/cloudbackups/statechange
- description: Status returns the status of any cloud backups of a volume
  method: POST
  name: openstoragecloudbackup-status
  path: /v1/cloudbackups/status
- description: Enumerate returns names of all the cluster domains in the cluster
  method: GET
  name: openstorageclusterdomains-enumerate
  path: /v1/clusterdomains
- description: Activates a cluster domain in the cluster. All the nodes which are part of an active cluster domain will participate in cluster quorum calculation
  method: POST
  name: openstorageclusterdomains-activate
  path: /v1/clusterdomains/activate/{cluster_domain_name}
- description: Deactivates a cluster domain in the cluster. All the nodes which are part of a deactivated cluster domain. will not participate in cluster quorum calculation
  method: POST
  name: openstorageclusterdomains-deactivate
  path: /v1/clusterdomains/deactivate/{cluster_domain_name}
- description: Inspect returns information about a cluster domain and a status indicating whether the cluster domain is active
  method: GET
  name: openstorageclusterdomains-inspect
  path: /v1/clusterdomains/inspect/{cluster_domain_name}
- description: Enumerate returns list of cluster pairs
  method: GET
  name: openstorageclusterpair-enumerate
  path: /v1/clusterpairs
- description: Creates Pair with a remote cluster and returns details about the remote cluster
  method: POST
  name: openstorageclusterpair-create
  path: /v1/clusterpairs
- description: Inspect information about a cluster pair
  method: GET
  name: openstorageclusterpair-inspect
  path: /v1/clusterpairs/inspect/{id}
- description: GetToken returns a auth token
  method: GET
  name: openstorageclusterpair-gettoken
  path: /v1/clusterpairs/token
- description: ResetToken returns a auth token
  method: POST
  name: openstorageclusterpair-resettoken
  path: /v1/clusterpairs/token
- description: Delete a cluster pair
  method: DELETE
  name: openstorageclusterpair-delete
  path: /v1/clusterpairs/{cluster_id}
- description: InspectCurrent returns information about the current cluster
  method: GET
  name: openstoragecluster-inspectcurrent
  path: /v1/clusters/inspectcurrent
- description: Enumerate returns a list of credential ids
  method: GET
  name: openstoragecredentials-enumerate
  path: /v1/credentials
- description: Create is used to submit cloud credentials. It will return an id of the credentials once they are verified to work.
  method: POST
  name: openstoragecredentials-create
  path: /v1/credentials
- description: Inspect returns the information about a credential, but does not return the secret key.
  method: GET
  name: openstoragecredentials-inspect
  path: /v1/credentials/inspect/{credential_id}
- description: DeleteReferences is used to remove references to credentials
  method: DELETE
  name: openstoragecredentials-deletereferences
  path: /v1/credentials/references/{credential_id}
- description: Validate is used to validate credentials
  method: GET
  name: openstoragecredentials-validate
  path: /v1/credentials/validate/{credential_id}
- description: Delete a specified credential
  method: DELETE
  name: openstoragecredentials-delete
  path: /v1/credentials/{credential_id}
- description: input is very same as credential create
  method: PUT
  name: openstoragecredentials-update
  path: /v1/credentials/{credential_id}
- description: Collect starts a job to collect diagnostics from set of nodes that are selected based on the selectors provided in the SdkDiagsCollectRequest. See SdkDiagsCollectRequest for more details on how to select the nodes Returns SdkDiagsCollectRes
  method: POST
  name: openstoragediags-collect
  path: /v1/diags
- description: Delete all fsck created snapshots on volume
  method: POST
  name: openstoragefilesystemcheck-deletesnapshots
  path: /v1/filesystem-check/delete-snapshots
- description: List all fsck created snapshots on volume
  method: GET
  name: openstoragefilesystemcheck-listsnapshots
  path: /v1/filesystem-check/list-snapshots
- description: List of all volumes which require fsck check/fix to be run
  method: GET
  name: openstoragefilesystemcheck-listvolumes
  path: /v1/filesystem-check/list-volumes
- description: Start a filesystem-check background operation on a unmounted volume.
  method: POST
  name: openstoragefilesystemcheck-start
  path: /v1/filesystem-check/start
- description: Get Status of a filesystem-check background operation on an unmounted volume, if any
  method: GET
  name: openstoragefilesystemcheck-status
  path: /v1/filesystem-check/status
- description: Stop a filesystem check background operation on an unmounted volume, if any
  method: POST
  name: openstoragefilesystemcheck-stop
  path: /v1/filesystem-check/stop
- description: Create a schedule to run defragmentation tasks periodically
  method: POST
  name: openstoragefilesystemdefrag-createschedule
  path: /v1/filesystem-defrag/schedule
- description: Clean up all defrag schedules and stop all operations
  method: DELETE
  name: openstoragefilesystemdefrag-cleanupschedules
  path: /v1/filesystem-defrag/schedules
- description: Enumerate all nodes, returning defrag status of the entire cluster
  method: GET
  name: openstoragefilesystemdefrag-enumeratenodestatus
  path: /v1/filesystem-defrag/status
- description: Get defrag status of a node
  method: GET
  name: openstoragefilesystemdefrag-getnodestatus
  path: /v1/filesystem-defrag/status/{node_id}
- description: Pop a auto filesystem Trim job from the queue
  method: POST
  name: openstoragefilesystemtrim-autofstrimpop
  path: /v1/filesystem-trim/auto-fstrim-pop
- description: Push a auto filesystem Trim job into the queue
  method: POST
  name: openstoragefilesystemtrim-autofstrimpush
  path: /v1/filesystem-trim/auto-fstrim-push
- description: GET /v1/filesystem-trim/auto-fstrim-status
  method: GET
  name: openstoragefilesystemtrim-autofstrimstatus
  path: /v1/filesystem-trim/auto-fstrim-status
- description: Usage of a filesystem Trim background operation on all locally mounted volume
  method: GET
  name: openstoragefilesystemtrim-autofstrimusage
  path: /v1/filesystem-trim/auto-fstrim-usage
- description: Start a filesystem Trim background operation on a mounted volume
  method: POST
  name: openstoragefilesystemtrim-start
  path: /v1/filesystem-trim/start
- description: Status of a filesystem Trim background operation on a mounted volume, if any
  method: GET
  name: openstoragefilesystemtrim-status
  path: /v1/filesystem-trim/status
- description: Stop a filesystem Trim background operation on a mounted volume, if any
  method: POST
  name: openstoragefilesystemtrim-stop
  path: /v1/filesystem-trim/stop
- description: Capabilities returns the supported services by the cluster. This allows SDK implementations to advertise their supported services as the API matures. With this information, clients can determine supported services from storage clusters at d
  method: GET
  name: openstorageidentity-capabilities
  path: /v1/identities/capabilities
- description: Version returns version information about the system.
  method: GET
  name: openstorageidentity-version
  path: /v1/identities/version
- description: Enumerate returns all the jobs currently known to the system
  method: GET
  name: openstoragejob-enumerate
  path: /v1/jobs
personas: []
provider_name: Portworx
provider_slug: portworx
search_terms:
- openstoragecloudbackup status
- containers
- openstoragebucket create
- api
- openstoragefilesystemtrim autofstrimstatus
- update existing cloud backup schedule
- gettoken returns a auth token
- openstoragejob enumerate
- size returns the size of any cloud backups of a volume
- openstorageclusterpair resettoken
- openstoragefilesystemcheck start
- openstorageidentity version
- get status of a filesystem-check background operation on an unmounted volume, if any
- push a auto filesystem trim job into the queue
- openstoragealerts delete
- statechange can be used to stop, pause, and restart a backup
- version returns version information about the system.
- enumerate cloud backup schedules
- input is very same as credential create
- openstoragecloudbackup scheddelete
- stop a filesystem check background operation on an unmounted volume, if any
- openstoragealerts enumeratewithfilters
- openstorageidentity capabilities
- openstoragefilesystemtrim status
- stop a filesystem trim background operation on a mounted volume, if any
- create a schedule to run defragmentation tasks periodically
- openstoragefilesystemdefrag cleanupschedules
- create cloud backup schedule
- allows querying alerts.
- get defrag status of a node
- history returns a list of backups for a specified volume
- openstoragebucket revokeaccess
- return a list of backups for the specified volume
- openstoragefilesystemcheck status
- openstorageclusterdomains inspect
- cloud native
- delete a cluster pair
- create is used to submit cloud credentials. it will return an id of the credentials once they are verified to work.
- openstoragefilesystemtrim stop
- deleteall deletes all the backups in the cloud for the specified volume.
- data management
- openstoragefilesystemtrim autofstrimpush
- openstorageclusterpair delete
- deactivates a cluster domain in the cluster. all the nodes which are part of a deactivated cluster domain. will not participate in cluster quorum calculation
- openstoragefilesystemdefrag createschedule
- openstoragecredentials inspect
- catalog returns a list of the contents in the backup
- openstoragefilesystemcheck listsnapshots
- openstoragecloudbackup deleteall
- openstoragecredentials update
- openstorageclusterdomains deactivate
- openstoragefilesystemtrim start
- openstorageclusterdomains enumerate
- storage
- openstoragecredentials create
- openstoragecloudbackup schedcreate
- activates a cluster domain in the cluster. all the nodes which are part of an active cluster domain will participate in cluster quorum calculation
- openstoragecloudbackup catalog
- enumerate all nodes, returning defrag status of the entire cluster
- status returns the status of any cloud backups of a volume
- deletes a backup stored in the cloud. if the backup is an incremental backup and other backups are dependent on it, it will not be able to be deleted.
- openstoragecloudbackup restore
- post /v1/bucket/access/{bucket_id}
- delete cloud backup schedule
- enumerate returns a list of credential ids
- resettoken returns a auth token
- openstoragefilesystemcheck listvolumes
- collect starts a job to collect diagnostics from set of nodes that are selected based on the selectors provided in the sdkdiagscollectrequest. see sdkdiagscollectrequest for more details on how to select the nodes returns sdkdiagscollectres
- delete alerts
- get /v1/filesystem-trim/auto-fstrim-status
- start a filesystem trim background operation on a mounted volume
- enumerate returns list of cluster pairs
- delete /v1/bucket/{bucket_id}
- openstoragefilesystemtrim autofstrimpop
- openstoragecloudbackup enumeratewithfilters
- creates a backup request for a specified volume. use openstoragecloudbackup.status() to get the current status of the backup request.
- openstoragecloudbackup schedupdate
- openstoragecredentials enumerate
- inspect returns the information about a credential, but does not return the secret key.
- kubernetes
- openstoragecloudbackup schedenumerate
- portworx
- post /v1/bucket
- post /v1/bucket/revoke/{bucket_id}
- creates a group backup request for a specified group. use openstoragecloudbackup.status() to get the current status of the backup request.
- inspect information about a cluster pair
- clean up all defrag schedules and stop all operations
- capabilities returns the supported services by the cluster. this allows sdk implementations to advertise their supported services as the api matures. with this information, clients can determine supported services from storage clusters at d
- openstoragefilesystemtrim autofstrimusage
- delete a specified credential
- openstoragecredentials delete
- status of a filesystem trim background operation on a mounted volume, if any
- openstorageclusterpair gettoken
- openstoragecredentials validate
- openstoragecluster inspectcurrent
- openstoragecloudbackup groupcreate
- openstoragediags collect
- restore creates a new volume from a backup id. the newly created volume has an ha_level (number of replicas) of only 1. to increase the number of replicas, use openstoragevolume.set() to change the ha_level.
- openstoragebucket delete
- openstorageclusterpair inspect
- openstoragecloudbackup create
- openstoragecloudbackup history
- inspectcurrent returns information about the current cluster
- openstoragefilesystemdefrag getnodestatus
- openstoragecloudbackup size
- openstoragefilesystemcheck deletesnapshots
- pop a auto filesystem trim job from the queue
- usage of a filesystem trim background operation on all locally mounted volume
- validate is used to validate credentials
- openstoragefilesystemdefrag enumeratenodestatus
- deletereferences is used to remove references to credentials
- list of all volumes which require fsck check/fix to be run
- openstoragecloudbackup delete
- start a filesystem-check background operation on a unmounted volume.
- openstorageclusterpair enumerate
- openstoragecredentials deletereferences
- enumerate returns names of all the cluster domains in the cluster
- creates pair with a remote cluster and returns details about the remote cluster
- openstoragefilesystemcheck stop
- openstorageclusterpair create
- enumerate returns all the jobs currently known to the system
- openstorageclusterdomains activate
- openstoragecloudbackup statechange
- openstoragebucket grantaccess
- inspect returns information about a cluster domain and a status indicating whether the cluster domain is active
- delete all fsck created snapshots on volume
- list all fsck created snapshots on volume
slug: portworx-capability
source_filename: portworx-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenStorage SDK\n  description: OpenStorage SDK API capability.\n  tags:\n  - Portworx\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: portworx\n    baseUri: https://api.example.com\n    description: OpenStorage SDK HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PORTWORX_TOKEN}}'\n    resources:\n    - name: v1-alerts\n      path: /v1/alerts\n      operations:\n      - name: openstoragealerts-delete\n        method: POST\n        description: Delete alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-alerts-filters\n      path: /v1/alerts/filters\n      operations:\n      - name: openstoragealerts-enumeratewithfilters\n        method: POST\n        description: Allows querying alerts.\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: v1-bucket\n      path: /v1/bucket\n      operations:\n      - name: openstoragebucket-create\n        method: POST\n        description: POST /v1/bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-bucket-access-bucket-id\n      path: /v1/bucket/access/{bucket_id}\n      operations:\n      - name: openstoragebucket-grantaccess\n        method: POST\n        description: POST /v1/bucket/access/{bucket_id}\n        inputParameters:\n        - name: bucket_id\n          in: path\n          type: string\n          required: true\n          description: Id of the bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-bucket-revoke-bucket-id\n      path: /v1/bucket/revoke/{bucket_id}\n      operations:\n      - name: openstoragebucket-revokeaccess\n\
  \        method: POST\n        description: POST /v1/bucket/revoke/{bucket_id}\n        inputParameters:\n        - name: bucket_id\n          in: path\n          type: string\n          required: true\n          description: Id of bucket to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-bucket-bucket-id\n      path: /v1/bucket/{bucket_id}\n      operations:\n      - name: openstoragebucket-delete\n        method: DELETE\n        description: DELETE /v1/bucket/{bucket_id}\n        inputParameters:\n        - name: bucket_id\n          in: path\n          type: string\n          required: true\n          description: Id of bucket to delete\n        - name: region\n          in: query\n          type: string\n          description: Region in which bucket will be created.\n        - name: endpoint\n          in: query\n          type: string\n          description: Endpoint to use when deleting\
  \ the bucket.\n        - name: clear_bucket\n          in: query\n          type: boolean\n          description: Flag to allow non empty bucket deletion.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups\n      path: /v1/cloudbackups\n      operations:\n      - name: openstoragecloudbackup-create\n        method: POST\n        description: Creates a backup request for a specified volume. Use OpenStorageCloudBackup.Status() to get the current\n          status of the backup request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-backup-backup-id\n      path: /v1/cloudbackups/backup/{backup_id}\n      operations:\n      - name: openstoragecloudbackup-delete\n        method: DELETE\n        description: Deletes a backup stored in the cloud. If the backup is an incremental backup\
  \ and other backups are dependent\n          on it, it will not be able to be deleted.\n        inputParameters:\n        - name: backup_id\n          in: path\n          type: string\n          required: true\n          description: ID is the ID of the cloud backup\n        - name: credential_id\n          in: query\n          type: string\n          description: Credential id is the credential for cloud to be used for the request.\n        - name: force\n          in: query\n          type: boolean\n          description: 'Force Delete cloudbackup even if there are dependencies. This may be needed if the backup is an incremental\n            backup and subsequent backups depend on this backup '\n        - name: bucket\n          in: query\n          type: string\n          description: Bucket name to which cloud backup belongs to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-catalog\n\
  \      path: /v1/cloudbackups/catalog\n      operations:\n      - name: openstoragecloudbackup-catalog\n        method: POST\n        description: Catalog returns a list of the contents in the backup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-deleteall\n      path: /v1/cloudbackups/deleteall\n      operations:\n      - name: openstoragecloudbackup-deleteall\n        method: POST\n        description: DeleteAll deletes all the backups in the cloud for the specified volume.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-enumerate-filters\n      path: /v1/cloudbackups/enumerate/filters\n      operations:\n      - name: openstoragecloudbackup-enumeratewithfilters\n        method: POST\n        description: Return a list of backups for the specified volume\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-group\n      path: /v1/cloudbackups/group\n      operations:\n      - name: openstoragecloudbackup-groupcreate\n        method: POST\n        description: Creates a group backup request for a specified group. Use OpenStorageCloudBackup.Status() to get the\n          current status of the backup request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-history-src-volume-id\n      path: /v1/cloudbackups/history/{src_volume_id}\n      operations:\n      - name: openstoragecloudbackup-history\n        method: GET\n        description: History returns a list of backups for a specified volume\n        inputParameters:\n        - name: src_volume_id\n          in: path\n          type: string\n          required: true\n          description: This optional value\
  \ defines which history of backups is being requested. If not provided, it will return\n            the history for all volumes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-restore\n      path: /v1/cloudbackups/restore\n      operations:\n      - name: openstoragecloudbackup-restore\n        method: POST\n        description: Restore creates a new volume from a backup id. The newly created volume has an ha_level (number of replicas)\n          of only 1. To increase the number of replicas, use OpenStorageVolume.Set() to change the ha_level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-schedules\n      path: /v1/cloudbackups/schedules\n      operations:\n      - name: openstoragecloudbackup-schedenumerate\n        method: GET\n        description: Enumerate cloud backup\
  \ schedules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: openstoragecloudbackup-schedcreate\n        method: POST\n        description: Create cloud backup schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: openstoragecloudbackup-schedupdate\n        method: PUT\n        description: Update existing cloud backup schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-schedules-backup-schedule-id\n      path: /v1/cloudbackups/schedules/{backup_schedule_id}\n      operations:\n      - name: openstoragecloudbackup-scheddelete\n        method: DELETE\n        description: Delete cloud backup schedule\n        inputParameters:\n        - name: backup_schedule_id\n          in: path\n      \
  \    type: string\n          required: true\n          description: Id of cloud backup to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-size\n      path: /v1/cloudbackups/size\n      operations:\n      - name: openstoragecloudbackup-size\n        method: GET\n        description: Size returns the size of any cloud backups of a volume\n        inputParameters:\n        - name: backup_id\n          in: query\n          type: string\n          description: BackupId is a value which is used to get information on the size of the specified backup.\n        - name: credential_id\n          in: query\n          type: string\n          description: Credential id describe the credentials for the cloud.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-statechange\n      path:\
  \ /v1/cloudbackups/statechange\n      operations:\n      - name: openstoragecloudbackup-statechange\n        method: POST\n        description: StateChange can be used to stop, pause, and restart a backup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cloudbackups-status\n      path: /v1/cloudbackups/status\n      operations:\n      - name: openstoragecloudbackup-status\n        method: POST\n        description: Status returns the status of any cloud backups of a volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-clusterdomains\n      path: /v1/clusterdomains\n      operations:\n      - name: openstorageclusterdomains-enumerate\n        method: GET\n        description: Enumerate returns names of all the cluster domains in the cluster\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-clusterdomains-activate-cluster-domain-name\n      path: /v1/clusterdomains/activate/{cluster_domain_name}\n      operations:\n      - name: openstorageclusterdomains-activate\n        method: POST\n        description: Activates a cluster domain in the cluster. All the nodes which are part of an active cluster domain will\n          participate in cluster quorum calculation\n        inputParameters:\n        - name: cluster_domain_name\n          in: path\n          type: string\n          required: true\n          description: Name of the cluster domain to activate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-clusterdomains-deactivate-cluster-domain-name\n      path: /v1/clusterdomains/deactivate/{cluster_domain_name}\n      operations:\n      - name: openstorageclusterdomains-deactivate\n        method:\
  \ POST\n        description: Deactivates a cluster domain in the cluster. All the nodes which are part of a deactivated cluster domain.\n          will not participate in cluster quorum calculation\n        inputParameters:\n        - name: cluster_domain_name\n          in: path\n          type: string\n          required: true\n          description: Name of the cluster domain to deactivate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-clusterdomains-inspect-cluster-domain-name\n      path: /v1/clusterdomains/inspect/{cluster_domain_name}\n      operations:\n      - name: openstorageclusterdomains-inspect\n        method: GET\n        description: Inspect returns information about a cluster domain and a status indicating whether the cluster domain\n          is active\n        inputParameters:\n        - name: cluster_domain_name\n          in: path\n          type: string\n          required:\
  \ true\n          description: Name of the cluster domain to inspect\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-clusterpairs\n      path: /v1/clusterpairs\n      operations:\n      - name: openstorageclusterpair-enumerate\n        method: GET\n        description: Enumerate returns list of cluster pairs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: openstorageclusterpair-create\n        method: POST\n        description: Creates Pair with a remote cluster and returns details about the remote cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-clusterpairs-inspect-id\n      path: /v1/clusterpairs/inspect/{id}\n      operations:\n      - name: openstorageclusterpair-inspect\n        method: GET\n \
  \       description: Inspect information about a cluster pair\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID of the cluster, if empty gets the default pair\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-clusterpairs-token\n      path: /v1/clusterpairs/token\n      operations:\n      - name: openstorageclusterpair-gettoken\n        method: GET\n        description: GetToken returns a auth token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: openstorageclusterpair-resettoken\n        method: POST\n        description: ResetToken returns a auth token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-clusterpairs-cluster-id\n\
  \      path: /v1/clusterpairs/{cluster_id}\n      operations:\n      - name: openstorageclusterpair-delete\n        method: DELETE\n        description: Delete a cluster pair\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: ID of the cluster pair to be deleted\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-clusters-inspectcurrent\n      path: /v1/clusters/inspectcurrent\n      operations:\n      - name: openstoragecluster-inspectcurrent\n        method: GET\n        description: InspectCurrent returns information about the current cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-credentials\n      path: /v1/credentials\n      operations:\n      - name: openstoragecredentials-enumerate\n       \
  \ method: GET\n        description: Enumerate returns a list of credential ids\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: openstoragecredentials-create\n        method: POST\n        description: Create is used to submit cloud credentials. It will return an id of the credentials once they are verified\n          to work.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-credentials-inspect-credential-id\n      path: /v1/credentials/inspect/{credential_id}\n      operations:\n      - name: openstoragecredentials-inspect\n        method: GET\n        description: Inspect returns the information about a credential, but does not return the secret key.\n        inputParameters:\n        - name: credential_id\n          in: path\n          type: string\n          required: true\n          description: Id\
  \ of the credential\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-credentials-references-credential-id\n      path: /v1/credentials/references/{credential_id}\n      operations:\n      - name: openstoragecredentials-deletereferences\n        method: DELETE\n        description: DeleteReferences is used to remove references to credentials\n        inputParameters:\n        - name: credential_id\n          in: path\n          type: string\n          required: true\n          description: Id of the credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-credentials-validate-credential-id\n      path: /v1/credentials/validate/{credential_id}\n      operations:\n      - name: openstoragecredentials-validate\n        method: GET\n        description: Validate is used to validate credentials\n      \
  \  inputParameters:\n        - name: credential_id\n          in: path\n          type: string\n          required: true\n          description: Id of the credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-credentials-credential-id\n      path: /v1/credentials/{credential_id}\n      operations:\n      - name: openstoragecredentials-delete\n        method: DELETE\n        description: Delete a specified credential\n        inputParameters:\n        - name: credential_id\n          in: path\n          type: string\n          required: true\n          description: Id for credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: openstoragecredentials-update\n        method: PUT\n        description: input is very same as credential create\n        inputParameters:\n        - name: credential_id\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-diags\n      path: /v1/diags\n      operations:\n      - name: openstoragediags-collect\n        method: POST\n        description: Collect starts a job to collect diagnostics from set of nodes that are selected based on the selectors\n          provided in the SdkDiagsCollectRequest. See SdkDiagsCollectRequest for more details on how to select the nodes Returns\n          SdkDiagsCollectRes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-check-delete-snapshots\n      path: /v1/filesystem-check/delete-snapshots\n      operations:\n      - name: openstoragefilesystemcheck-deletesnapshots\n        method: POST\n        description: Delete all fsck created snapshots on volume\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-check-list-snapshots\n      path: /v1/filesystem-check/list-snapshots\n      operations:\n      - name: openstoragefilesystemcheck-listsnapshots\n        method: GET\n        description: List all fsck created snapshots on volume\n        inputParameters:\n        - name: volume_id\n          in: query\n          type: string\n          description: Id of the volume.\n        - name: node_id\n          in: query\n          type: string\n          description: Node Id of the volume.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-check-list-volumes\n      path: /v1/filesystem-check/list-volumes\n      operations:\n      - name: openstoragefilesystemcheck-listvolumes\n        method: GET\n        description: List of all volumes which\
  \ require fsck check/fix to be run\n        inputParameters:\n        - name: node_id\n          in: query\n          type: string\n          description: Node Id filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-check-start\n      path: /v1/filesystem-check/start\n      operations:\n      - name: openstoragefilesystemcheck-start\n        method: POST\n        description: Start a filesystem-check background operation on a unmounted volume.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-check-status\n      path: /v1/filesystem-check/status\n      operations:\n      - name: openstoragefilesystemcheck-status\n        method: GET\n        description: Get Status of a filesystem-check background operation on an unmounted volume, if any\n        inputParameters:\n        - name:\
  \ volume_id\n          in: query\n          type: string\n          description: Id of the volume.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-check-stop\n      path: /v1/filesystem-check/stop\n      operations:\n      - name: openstoragefilesystemcheck-stop\n        method: POST\n        description: Stop a filesystem check background operation on an unmounted volume, if any\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-defrag-schedule\n      path: /v1/filesystem-defrag/schedule\n      operations:\n      - name: openstoragefilesystemdefrag-createschedule\n        method: POST\n        description: Create a schedule to run defragmentation tasks periodically\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: v1-filesystem-defrag-schedules\n      path: /v1/filesystem-defrag/schedules\n      operations:\n      - name: openstoragefilesystemdefrag-cleanupschedules\n        method: DELETE\n        description: Clean up all defrag schedules and stop all operations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-defrag-status\n      path: /v1/filesystem-defrag/status\n      operations:\n      - name: openstoragefilesystemdefrag-enumeratenodestatus\n        method: GET\n        description: Enumerate all nodes, returning defrag status of the entire cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-defrag-status-node-id\n      path: /v1/filesystem-defrag/status/{node_id}\n      operations:\n      - name: openstoragefilesystemdefrag-getnodestatus\n        method:\
  \ GET\n        description: Get defrag status of a node\n        inputParameters:\n        - name: node_id\n          in: path\n          type: string\n          required: true\n          description: NodeId is uuid of the node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-trim-auto-fstrim-pop\n      path: /v1/filesystem-trim/auto-fstrim-pop\n      operations:\n      - name: openstoragefilesystemtrim-autofstrimpop\n        method: POST\n        description: Pop a auto filesystem Trim job from the queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-trim-auto-fstrim-push\n      path: /v1/filesystem-trim/auto-fstrim-push\n      operations:\n      - name: openstoragefilesystemtrim-autofstrimpush\n        method: POST\n        description: Push a auto filesystem Trim job into the\
  \ queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-trim-auto-fstrim-status\n      path: /v1/filesystem-trim/auto-fstrim-status\n      operations:\n      - name: openstoragefilesystemtrim-autofstrimstatus\n        method: GET\n        description: GET /v1/filesystem-trim/auto-fstrim-status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-trim-auto-fstrim-usage\n      path: /v1/filesystem-trim/auto-fstrim-usage\n      operations:\n      - name: openstoragefilesystemtrim-autofstrimusage\n        method: GET\n        description: Usage of a filesystem Trim background operation on all locally mounted volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-trim-start\n      path:\
  \ /v1/filesystem-trim/start\n      operations:\n      - name: openstoragefilesystemtrim-start\n        method: POST\n        description: Start a filesystem Trim background operation on a mounted volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-filesystem-trim-status\n      path: /v1/filesystem-trim/status\n      operations:\n      - name: openstoragefilesystemtrim-status\n        method: GET\n        description: Status of a filesystem Trim background operation on a mounted volume, if any\n        inputParameters:\n        - name: volume_id\n          in: query\n          type: string\n          description: Id of the volume.\n        - name: mount_path\n          in: query\n          type: string\n          description: Path where the volume is mounted.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: v1-filesystem-trim-stop\n      path: /v1/filesystem-trim/stop\n      operations:\n      - name: openstoragefilesystemtrim-stop\n        method: POST\n        description: Stop a filesystem Trim background operation on a mounted volume, if any\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-identities-capabilities\n      path: /v1/identities/capabilities\n      operations:\n      - name: openstorageidentity-capabilities\n        method: GET\n        description: Capabilities returns the supported services by the cluster. This allows SDK implementations to advertise\n          their supported services as the API matures. With this information, clients can determine supported services from\n          storage clusters at d\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-identities-version\n    \
  \  path: /v1/identities/version\n      operations:\n      - name: openstorageidentity-version\n        method: GET\n        description: Version returns version information about the system.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-jobs\n      path: /v1/jobs\n      operations:\n      - name: openstoragejob-enumerate\n        method: GET\n        description: Enumerate returns all the jobs currently known to the system\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          description: 'Type if specified will list the jobs of the provided type. - UNSPECIFIED_TYPE: Unspecified - NONE:\n            None - DRAIN_ATTACHMENTS: Job for draining volume attachments'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ portworx-rest\n    description: REST adapter for OpenStorage SDK.\n    resources:\n    - path: /v1/alerts\n      name: openstoragealerts-delete\n      operations:\n      - method: POST\n        name: openstoragealerts-delete\n        description: Delete alerts\n        call: portworx.openstoragealerts-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts/filters\n      name: openstoragealerts-enumeratewithfilters\n      operations:\n      - method: POST\n        name: openstoragealerts-enumeratewithfilters\n        description: Allows querying alerts.\n        call: portworx.openstoragealerts-enumeratewithfilters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bucket\n      name: openstoragebucket-create\n      operations:\n      - method: POST\n        name: openstoragebucket-create\n        description: POST /v1/bucket\n        call: portworx.openstoragebucket-create\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/bucket/access/{bucket_id}\n      name: openstoragebucket-grantaccess\n      operations:\n      - method: POST\n        name: openstoragebucket-grantaccess\n        description: POST /v1/bucket/access/{bucket_id}\n        call: portworx.openstoragebucket-grantaccess\n        with:\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bucket/revoke/{bucket_id}\n      name: openstoragebucket-revokeaccess\n      operations:\n      - method: POST\n        name: openstoragebucket-revokeaccess\n        description: POST /v1/bucket/revoke/{bucket_id}\n        call: portworx.openstoragebucket-revokeaccess\n        with:\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bucket/{bucket_id}\n      name: openstoragebucket-delete\n      operations:\n      - method: DELETE\n        name:\
  \ openstoragebucket-delete\n        description: DELETE /v1/bucket/{bucket_id}\n        call: portworx.openstoragebucket-delete\n        with:\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cloudbackups\n      name: openstoragecloudbackup-create\n      operations:\n      - method: POST\n        name: openstoragecloudbackup-create\n        description: Creates a backup request for a specified volume. Use OpenStorageCloudBackup.Status() to get the current\n          status of the backup request.\n        call: portworx.openstoragecloudbackup-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cloudbackups/backup/{backup_id}\n      name: openstoragecloudbackup-delete\n      operations:\n      - method: DELETE\n        name: openstoragecloudbackup-delete\n        description: Deletes a backup stored in the cloud. If the backup is an incremental backup and other backups\
  \ are dependent\n          on it, it will not be able to be deleted.\n        call: portworx.openstoragecloudbackup-delete\n        with:\n          backup_id: rest.backup_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cloudbackups/catalog\n      name: openstoragecloudbackup-catalog\n      operations:\n      - method: POST\n        name: openstoragecloudbackup-catalog\n        description: Catalog returns a list of the contents in the backup\n        call: portworx.openstoragecloudbackup-catalog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cloudbackups/deleteall\n      name: openstoragecloudbackup-deleteall\n      operations:\n      - method: POST\n        name: openstoragecloudbackup-deleteall\n        description: DeleteAll deletes all the backups in the cloud for the specified volume.\n        call: portworx.openstoragecloudbackup-deleteall\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/cloudbackups/enumerate/filters\n      name: openstoragecloudbackup-enumeratewithfilters\n      operations:\n      - method: POST\n        name: openstoragecloudbackup-enumeratewithfilters\n        description: Return a list of backups for the specified volume\n        call: portworx.openstoragecloudbackup-enumeratewithfilters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cloudbackups/group\n      name: openstoragecloudbackup-groupcreate\n      operations:\n      - method: POST\n        name: openstoragecloudbackup-groupcreate\n        description: Creates a group backup request for a specified group. \n\n# --- truncated at 32 KB (77 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/portworx/refs/heads/main/capabilities/portworx-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/portworx/refs/heads/main/capabilities/portworx-capability.yaml
tags:
- Portworx
- API
tools:
- description: Delete alerts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragealerts-delete
- description: Allows querying alerts.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragealerts-enumeratewithfilters
- description: POST /v1/bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragebucket-create
- description: POST /v1/bucket/access/{bucket_id}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragebucket-grantaccess
- description: POST /v1/bucket/revoke/{bucket_id}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragebucket-revokeaccess
- description: DELETE /v1/bucket/{bucket_id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: openstoragebucket-delete
- description: Creates a backup request for a specified volume. Use OpenStorageCloudBackup.Status() to get the current status of the backup request.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecloudbackup-create
- description: Deletes a backup stored in the cloud. If the backup is an incremental backup and other backups are dependent on it, it will not be able to be deleted.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: openstoragecloudbackup-delete
- description: Catalog returns a list of the contents in the backup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecloudbackup-catalog
- description: DeleteAll deletes all the backups in the cloud for the specified volume.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecloudbackup-deleteall
- description: Return a list of backups for the specified volume
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecloudbackup-enumeratewithfilters
- description: Creates a group backup request for a specified group. Use OpenStorageCloudBackup.Status() to get the current status of the backup request.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecloudbackup-groupcreate
- description: History returns a list of backups for a specified volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragecloudbackup-history
- description: Restore creates a new volume from a backup id. The newly created volume has an ha_level (number of replicas) of only 1. To increase the number of replicas, use OpenStorageVolume.Set() to change the ha_level.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecloudbackup-restore
- description: Enumerate cloud backup schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragecloudbackup-schedenumerate
- description: Create cloud backup schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecloudbackup-schedcreate
- description: Update existing cloud backup schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: openstoragecloudbackup-schedupdate
- description: Delete cloud backup schedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: openstoragecloudbackup-scheddelete
- description: Size returns the size of any cloud backups of a volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragecloudbackup-size
- description: StateChange can be used to stop, pause, and restart a backup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecloudbackup-statechange
- description: Status returns the status of any cloud backups of a volume
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecloudbackup-status
- description: Enumerate returns names of all the cluster domains in the cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstorageclusterdomains-enumerate
- description: Activates a cluster domain in the cluster. All the nodes which are part of an active cluster domain will participate in cluster quorum calculation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstorageclusterdomains-activate
- description: Deactivates a cluster domain in the cluster. All the nodes which are part of a deactivated cluster domain. will not participate in cluster quorum calculation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstorageclusterdomains-deactivate
- description: Inspect returns information about a cluster domain and a status indicating whether the cluster domain is active
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstorageclusterdomains-inspect
- description: Enumerate returns list of cluster pairs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstorageclusterpair-enumerate
- description: Creates Pair with a remote cluster and returns details about the remote cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstorageclusterpair-create
- description: Inspect information about a cluster pair
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstorageclusterpair-inspect
- description: GetToken returns a auth token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstorageclusterpair-gettoken
- description: ResetToken returns a auth token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstorageclusterpair-resettoken
- description: Delete a cluster pair
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: openstorageclusterpair-delete
- description: InspectCurrent returns information about the current cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragecluster-inspectcurrent
- description: Enumerate returns a list of credential ids
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragecredentials-enumerate
- description: Create is used to submit cloud credentials. It will return an id of the credentials once they are verified to work.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragecredentials-create
- description: Inspect returns the information about a credential, but does not return the secret key.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragecredentials-inspect
- description: DeleteReferences is used to remove references to credentials
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: openstoragecredentials-deletereferences
- description: Validate is used to validate credentials
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragecredentials-validate
- description: Delete a specified credential
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: openstoragecredentials-delete
- description: input is very same as credential create
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: openstoragecredentials-update
- description: Collect starts a job to collect diagnostics from set of nodes that are selected based on the selectors provided in the SdkDiagsCollectRequest. See SdkDiagsCollectRequest for more details on how to select the nodes Returns SdkDiagsCollectRes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragediags-collect
- description: Delete all fsck created snapshots on volume
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragefilesystemcheck-deletesnapshots
- description: List all fsck created snapshots on volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragefilesystemcheck-listsnapshots
- description: List of all volumes which require fsck check/fix to be run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragefilesystemcheck-listvolumes
- description: Start a filesystem-check background operation on a unmounted volume.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragefilesystemcheck-start
- description: Get Status of a filesystem-check background operation on an unmounted volume, if any
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragefilesystemcheck-status
- description: Stop a filesystem check background operation on an unmounted volume, if any
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragefilesystemcheck-stop
- description: Create a schedule to run defragmentation tasks periodically
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragefilesystemdefrag-createschedule
- description: Clean up all defrag schedules and stop all operations
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: openstoragefilesystemdefrag-cleanupschedules
- description: Enumerate all nodes, returning defrag status of the entire cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragefilesystemdefrag-enumeratenodestatus
- description: Get defrag status of a node
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragefilesystemdefrag-getnodestatus
- description: Pop a auto filesystem Trim job from the queue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragefilesystemtrim-autofstrimpop
- description: Push a auto filesystem Trim job into the queue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragefilesystemtrim-autofstrimpush
- description: GET /v1/filesystem-trim/auto-fstrim-status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragefilesystemtrim-autofstrimstatus
- description: Usage of a filesystem Trim background operation on all locally mounted volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragefilesystemtrim-autofstrimusage
- description: Start a filesystem Trim background operation on a mounted volume
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragefilesystemtrim-start
- description: Status of a filesystem Trim background operation on a mounted volume, if any
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragefilesystemtrim-status
- description: Stop a filesystem Trim background operation on a mounted volume, if any
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: openstoragefilesystemtrim-stop
- description: Capabilities returns the supported services by the cluster. This allows SDK implementations to advertise their supported services as the API matures. With this information, clients can determine supported services from storage clusters at d
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstorageidentity-capabilities
- description: Version returns version information about the system.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstorageidentity-version
- description: Enumerate returns all the jobs currently known to the system
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: openstoragejob-enumerate
---
