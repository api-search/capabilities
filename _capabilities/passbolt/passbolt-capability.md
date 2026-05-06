---
categories: []
consumed_apis: []
description: This is a low-level overview of the API and its endpoints, if you need higher-level guides for interacting with the endpoints, use the Developer guide.
layout: capability
name: Passbolt API
operations:
- description: Check authentication status.
  method: GET
  name: viewauthisauthenticated
  path: /auth/is-authenticated.json
- description: Get the JWKs server information.
  method: GET
  name: viewauthjwtjwks
  path: /auth/jwt/jwks.json
- description: Login.
  method: POST
  name: authjwtlogin
  path: /auth/jwt/login.json
- description: Logout.
  method: POST
  name: authjwtlogout
  path: /auth/jwt/logout.json
- description: Refresh access token.
  method: POST
  name: authjwtrefresh
  path: /auth/jwt/refresh.json
- description: Get the JWT RSA server information.
  method: GET
  name: viewauthjwtrsa
  path: /auth/jwt/rsa.json
- description: Log in.
  method: POST
  name: authlogin
  path: /auth/login.json
- description: Log out.
  method: POST
  name: authlogout
  path: /auth/logout.json
- description: Get the server's public PGP key.
  method: GET
  name: viewauthverify
  path: /auth/verify.json
- description: Verify the server's identity.
  method: POST
  name: checkauthverify
  path: /auth/verify.json
- description: Get an avatar as an image.
  method: GET
  name: viewavatar
  path: /avatars/view/{avatarId}/{avatarFormat}
- description: Update a comment.
  method: PUT
  name: updatecomment
  path: /comments/{commentId}.json
- description: Delete a comment.
  method: DELETE
  name: deletecomment
  path: /comments/{commentId}.json
- description: Get comments for a resource.
  method: GET
  name: indexcomments
  path: /comments/resource/{resourceId}.json
- description: Add a comment.
  method: POST
  name: addcomment
  path: /comments/resource/{resourceId}.json
- description: Simulate directory synchronization without making changes.
  method: GET
  name: simulatesync
  path: /directorysync/synchronize/dry-run.json
- description: Run the directory synchronization.
  method: POST
  name: runsync
  path: /directorysync/synchronize.json
- description: Unset a resource as favorite.
  method: DELETE
  name: deletefavorite
  path: /favorite/{favoriteId}.json
- description: Set a resource as favorite.
  method: POST
  name: addfavorite
  path: /favorite/{foreignModel}/{foreignId}.json
- description: Get multiple folders.
  method: GET
  name: indexfolders
  path: /folders.json
- description: Create a folder.
  method: POST
  name: addfolder
  path: /folders.json
- description: Get a folder.
  method: GET
  name: viewfolder
  path: /folders/{folderId}.json
- description: Update a folder.
  method: PUT
  name: updatefolder
  path: /folders/{folderId}.json
- description: Delete a folder.
  method: DELETE
  name: deletefolder
  path: /folders/{folderId}.json
- description: Get multiple GPG keys.
  method: GET
  name: indexgpgkeys
  path: /gpgkeys.json
- description: Get a GPG key.
  method: GET
  name: viewgpgkey
  path: /gpgkeys/{gpgkeyId}.json
- description: Get multiple groups.
  method: GET
  name: indexgroups
  path: /groups.json
- description: Create a group.
  method: POST
  name: addgroup
  path: /groups.json
- description: Get a group.
  method: GET
  name: viewgroup
  path: /groups/{groupId}.json
- description: Update a group.
  method: PUT
  name: updategroup
  path: /groups/{groupId}.json
- description: Delete a group.
  method: DELETE
  name: deletegroup
  path: /groups/{groupId}.json
- description: Dry run a group update.
  method: PUT
  name: dryrunupdategroup
  path: /groups/{groupId}/dry-run.json
- description: Dry run a group deletion.
  method: DELETE
  name: dryrundeletegroup
  path: /groups/{groupId}/dry-run.json
- description: Get healthcheck information.
  method: GET
  name: viewhealthcheck
  path: /healthcheck.json
- description: Check if passbolt is up.
  method: GET
  name: viewhealthcheckstatus
  path: /healthcheck/status.json
- description: Get metadata keys.
  method: GET
  name: indexmetadatakeys
  path: /metadata/keys.json
- description: Create a metadata key.
  method: POST
  name: addmetadatakey
  path: /metadata/keys.json
- description: Mark a metadata key as expired.
  method: PUT
  name: updatemetadatakey
  path: /metadata/keys/{metadataKeyId}.json
- description: Delete a metadata key.
  method: DELETE
  name: deletemetadatakey
  path: /metadata/keys/{metadataKeyId}.json
- description: Create a metadata private key.
  method: POST
  name: addmetadataprivatekey
  path: /metadata/keys/privates.json
- description: Update a metadata private key.
  method: PUT
  name: updatemetadataprivatekey
  path: /metadata/keys/private/{metadataPrivateKeyId}.json
- description: Get metadata keys settings.
  method: GET
  name: indexmetadatakeyssettings
  path: /metadata/keys/settings.json
- description: Update metadata keys settings.
  method: POST
  name: updatemetadatakeyssettings
  path: /metadata/keys/settings.json
- description: Get metadata types settings
  method: GET
  name: viewmetadatatypessettings
  path: /metadata/types/settings.json
- description: Upgrade a resource types settings
  method: POST
  name: upgrademetadatatypessettings
  path: /metadata/types/settings.json
- description: Get folders with expired keys
  method: GET
  name: viewmetadatarotatekeyfolders
  path: /metadata/rotate-key/folders.json
- description: Rotate expired metadata keys for folders
  method: POST
  name: rotatemetadataexpiredkeysfolders
  path: /metadata/rotate-key/folders.json
- description: Get resources with expired keys
  method: GET
  name: viewmetadatarotatekeyresources
  path: /metadata/rotate-key/resources.json
- description: Rotate expired metadata keys for resources
  method: POST
  name: rotatemetadataexpiredkeys
  path: /metadata/rotate-key/resources.json
- description: Get session keys.
  method: GET
  name: viewmetadatasessionkeys
  path: /metadata/session-keys.json
- description: Add a session key.
  method: POST
  name: addmetadatasessionkey
  path: /metadata/session-keys.json
- description: Update a given session-key entry.
  method: POST
  name: updatemetadatasessionkey
  path: /metadata/session-key/{sessionKeyId}.json
- description: Delete a given session-key entry.
  method: DELETE
  name: deletesessionkey
  path: /metadata/session-key/{sessionKeyId}.json
- description: Get tags with expired keys
  method: GET
  name: viewmetadatarotatekeytags
  path: /metadata/rotate-key/tags.json
- description: Rotate expired metadata keys for tags
  method: POST
  name: rotatemetadatakeystags
  path: /metadata/rotate-key/tags.json
- description: Get Upgradable Folders
  method: GET
  name: viewmetadataupgradefolders
  path: /metadata/upgrade/folders.json
- description: Upgrade a folder
  method: POST
  name: upgrademetadatafolders
  path: /metadata/upgrade/folders.json
- description: Get Upgradable Resources
  method: GET
  name: viewmetadataupgraderesources
  path: /metadata/upgrade/resources.json
- description: Upgrade a Resource
  method: POST
  name: upgrademetadataresources
  path: /metadata/upgrade/resources.json
- description: Get Upgradable Tags
  method: GET
  name: viewmetadataupgradetags
  path: /metadata/upgrade/tags.json
personas: []
provider_name: Passbolt
provider_slug: passbolt
search_terms:
- upgrade a folder
- get comments for a resource.
- indexcomments
- addgroup
- viewmetadatasessionkeys
- updatemetadatakey
- viewmetadatatypessettings
- viewauthisauthenticated
- viewauthjwtjwks
- get multiple folders.
- updatefolder
- security
- update a folder.
- delete a group.
- add a comment.
- get folders with expired keys
- api
- addmetadatakey
- updatemetadatasessionkey
- upgrade a resource
- get upgradable resources
- addmetadataprivatekey
- get metadata types settings
- simulatesync
- authjwtlogin
- unset a resource as favorite.
- viewgroup
- create a folder.
- update metadata keys settings.
- get upgradable folders
- passbolt
- create a metadata private key.
- identity
- rotatemetadataexpiredkeysfolders
- rotatemetadataexpiredkeys
- addmetadatasessionkey
- viewhealthcheck
- get session keys.
- get a group.
- indexfolders
- viewhealthcheckstatus
- get multiple groups.
- dry run a group deletion.
- viewmetadatarotatekeyfolders
- dryrunupdategroup
- get the server's public pgp key.
- addcomment
- create a metadata key.
- rotatemetadatakeystags
- delete a folder.
- rotate expired metadata keys for tags
- upgrademetadatafolders
- viewmetadataupgraderesources
- authlogout
- get the jwks server information.
- viewmetadataupgradetags
- mark a metadata key as expired.
- runsync
- viewgpgkey
- updatecomment
- authjwtrefresh
- indexgpgkeys
- logout.
- rotate expired metadata keys for folders
- password manager
- viewauthverify
- delete a given session-key entry.
- updategroup
- update a given session-key entry.
- set a resource as favorite.
- indexmetadatakeys
- run the directory synchronization.
- get metadata keys settings.
- addfolder
- login.
- upgrademetadatatypessettings
- get multiple gpg keys.
- verify the server's identity.
- upgrade a resource types settings
- deletemetadatakey
- get a folder.
- update a group.
- authlogin
- log in.
- add a session key.
- log out.
- addfavorite
- get upgradable tags
- refresh access token.
- delete a metadata key.
- get metadata keys.
- check if passbolt is up.
- secrets
- get a gpg key.
- delete a comment.
- viewauthjwtrsa
- viewmetadatarotatekeytags
- check authentication status.
- indexgroups
- authjwtlogout
- update a comment.
- deletegroup
- viewfolder
- viewmetadatarotatekeyresources
- simulate directory synchronization without making changes.
- deletesessionkey
- update a metadata private key.
- updatemetadatakeyssettings
- rotate expired metadata keys for resources
- indexmetadatakeyssettings
- deletecomment
- deletefolder
- dryrundeletegroup
- deletefavorite
- get resources with expired keys
- get tags with expired keys
- get the jwt rsa server information.
- checkauthverify
- get healthcheck information.
- create a group.
- updatemetadataprivatekey
- viewmetadataupgradefolders
- upgrademetadataresources
- dry run a group update.
- viewavatar
- get an avatar as an image.
slug: passbolt-capability
source_filename: passbolt-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Passbolt API\n  description: This is a low-level overview of the API and its endpoints, if you need higher-level guides for interacting\n    with the endpoints, use the Developer guide.\n  tags:\n  - Passbolt\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: passbolt\n    baseUri: https://passbolt.local\n    description: Passbolt API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PASSBOLT_TOKEN}}'\n    resources:\n    - name: auth-is-authenticated-json\n      path: /auth/is-authenticated.json\n      operations:\n      - name: viewauthisauthenticated\n        method: GET\n        description: Check authentication status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-jwt-jwks-json\n      path: /auth/jwt/jwks.json\n      operations:\n      - name: viewauthjwtjwks\n\
  \        method: GET\n        description: Get the JWKs server information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-jwt-login-json\n      path: /auth/jwt/login.json\n      operations:\n      - name: authjwtlogin\n        method: POST\n        description: Login.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-jwt-logout-json\n      path: /auth/jwt/logout.json\n      operations:\n      - name: authjwtlogout\n        method: POST\n        description: Logout.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-jwt-refresh-json\n      path: /auth/jwt/refresh.json\n      operations:\n      - name: authjwtrefresh\n        method: POST\n        description: Refresh access token.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-jwt-rsa-json\n      path: /auth/jwt/rsa.json\n      operations:\n      - name: viewauthjwtrsa\n        method: GET\n        description: Get the JWT RSA server information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-login-json\n      path: /auth/login.json\n      operations:\n      - name: authlogin\n        method: POST\n        description: Log in.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-logout-json\n      path: /auth/logout.json\n      operations:\n      - name: authlogout\n        method: POST\n        description: Log out.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ auth-verify-json\n      path: /auth/verify.json\n      operations:\n      - name: viewauthverify\n        method: GET\n        description: Get the server's public PGP key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: checkauthverify\n        method: POST\n        description: Verify the server's identity.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: avatars-view-avatarid-avatarformat\n      path: /avatars/view/{avatarId}/{avatarFormat}\n      operations:\n      - name: viewavatar\n        method: GET\n        description: Get an avatar as an image.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments-commentid-json\n      path: /comments/{commentId}.json\n      operations:\n      - name: updatecomment\n\
  \        method: PUT\n        description: Update a comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecomment\n        method: DELETE\n        description: Delete a comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments-resource-resourceid-json\n      path: /comments/resource/{resourceId}.json\n      operations:\n      - name: indexcomments\n        method: GET\n        description: Get comments for a resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addcomment\n        method: POST\n        description: Add a comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: directorysync-synchronize-dry-run-json\n\
  \      path: /directorysync/synchronize/dry-run.json\n      operations:\n      - name: simulatesync\n        method: GET\n        description: Simulate directory synchronization without making changes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: directorysync-synchronize-json\n      path: /directorysync/synchronize.json\n      operations:\n      - name: runsync\n        method: POST\n        description: Run the directory synchronization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: favorite-favoriteid-json\n      path: /favorite/{favoriteId}.json\n      operations:\n      - name: deletefavorite\n        method: DELETE\n        description: Unset a resource as favorite.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: favorite-foreignmodel-foreignid-json\n      path: /favorite/{foreignModel}/{foreignId}.json\n      operations:\n      - name: addfavorite\n        method: POST\n        description: Set a resource as favorite.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: folders-json\n      path: /folders.json\n      operations:\n      - name: indexfolders\n        method: GET\n        description: Get multiple folders.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addfolder\n        method: POST\n        description: Create a folder.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: folders-folderid-json\n      path: /folders/{folderId}.json\n      operations:\n      - name: viewfolder\n        method: GET\n     \
  \   description: Get a folder.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefolder\n        method: PUT\n        description: Update a folder.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefolder\n        method: DELETE\n        description: Delete a folder.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gpgkeys-json\n      path: /gpgkeys.json\n      operations:\n      - name: indexgpgkeys\n        method: GET\n        description: Get multiple GPG keys.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gpgkeys-gpgkeyid-json\n      path: /gpgkeys/{gpgkeyId}.json\n      operations:\n      - name: viewgpgkey\n\
  \        method: GET\n        description: Get a GPG key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-json\n      path: /groups.json\n      operations:\n      - name: indexgroups\n        method: GET\n        description: Get multiple groups.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addgroup\n        method: POST\n        description: Create a group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-groupid-json\n      path: /groups/{groupId}.json\n      operations:\n      - name: viewgroup\n        method: GET\n        description: Get a group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n\
  \        method: PUT\n        description: Update a group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: Delete a group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-groupid-dry-run-json\n      path: /groups/{groupId}/dry-run.json\n      operations:\n      - name: dryrunupdategroup\n        method: PUT\n        description: Dry run a group update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dryrundeletegroup\n        method: DELETE\n        description: Dry run a group deletion.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: healthcheck-json\n   \
  \   path: /healthcheck.json\n      operations:\n      - name: viewhealthcheck\n        method: GET\n        description: Get healthcheck information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: healthcheck-status-json\n      path: /healthcheck/status.json\n      operations:\n      - name: viewhealthcheckstatus\n        method: GET\n        description: Check if passbolt is up.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-keys-json\n      path: /metadata/keys.json\n      operations:\n      - name: indexmetadatakeys\n        method: GET\n        description: Get metadata keys.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addmetadatakey\n        method: POST\n        description: Create a metadata\
  \ key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-keys-metadatakeyid-json\n      path: /metadata/keys/{metadataKeyId}.json\n      operations:\n      - name: updatemetadatakey\n        method: PUT\n        description: Mark a metadata key as expired.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemetadatakey\n        method: DELETE\n        description: Delete a metadata key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-keys-privates-json\n      path: /metadata/keys/privates.json\n      operations:\n      - name: addmetadataprivatekey\n        method: POST\n        description: Create a metadata private key.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: metadata-keys-private-metadataprivatekeyid-json\n      path: /metadata/keys/private/{metadataPrivateKeyId}.json\n      operations:\n      - name: updatemetadataprivatekey\n        method: PUT\n        description: Update a metadata private key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-keys-settings-json\n      path: /metadata/keys/settings.json\n      operations:\n      - name: indexmetadatakeyssettings\n        method: GET\n        description: Get metadata keys settings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemetadatakeyssettings\n        method: POST\n        description: Update metadata keys settings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: metadata-types-settings-json\n      path: /metadata/types/settings.json\n      operations:\n      - name: viewmetadatatypessettings\n        method: GET\n        description: Get metadata types settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upgrademetadatatypessettings\n        method: POST\n        description: Upgrade a resource types settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-rotate-key-folders-json\n      path: /metadata/rotate-key/folders.json\n      operations:\n      - name: viewmetadatarotatekeyfolders\n        method: GET\n        description: Get folders with expired keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rotatemetadataexpiredkeysfolders\n\
  \        method: POST\n        description: Rotate expired metadata keys for folders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-rotate-key-resources-json\n      path: /metadata/rotate-key/resources.json\n      operations:\n      - name: viewmetadatarotatekeyresources\n        method: GET\n        description: Get resources with expired keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rotatemetadataexpiredkeys\n        method: POST\n        description: Rotate expired metadata keys for resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-session-keys-json\n      path: /metadata/session-keys.json\n      operations:\n      - name: viewmetadatasessionkeys\n        method: GET\n       \
  \ description: Get session keys.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addmetadatasessionkey\n        method: POST\n        description: Add a session key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-session-key-sessionkeyid-json\n      path: /metadata/session-key/{sessionKeyId}.json\n      operations:\n      - name: updatemetadatasessionkey\n        method: POST\n        description: Update a given session-key entry.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesessionkey\n        method: DELETE\n        description: Delete a given session-key entry.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: metadata-rotate-key-tags-json\n      path: /metadata/rotate-key/tags.json\n      operations:\n      - name: viewmetadatarotatekeytags\n        method: GET\n        description: Get tags with expired keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rotatemetadatakeystags\n        method: POST\n        description: Rotate expired metadata keys for tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-upgrade-folders-json\n      path: /metadata/upgrade/folders.json\n      operations:\n      - name: viewmetadataupgradefolders\n        method: GET\n        description: Get Upgradable Folders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upgrademetadatafolders\n        method: POST\n       \
  \ description: Upgrade a folder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-upgrade-resources-json\n      path: /metadata/upgrade/resources.json\n      operations:\n      - name: viewmetadataupgraderesources\n        method: GET\n        description: Get Upgradable Resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upgrademetadataresources\n        method: POST\n        description: Upgrade a Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-upgrade-tags-json\n      path: /metadata/upgrade/tags.json\n      operations:\n      - name: viewmetadataupgradetags\n        method: GET\n        description: Get Upgradable Tags\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: passbolt-rest\n    description: REST adapter for Passbolt API.\n    resources:\n    - path: /auth/is-authenticated.json\n      name: viewauthisauthenticated\n      operations:\n      - method: GET\n        name: viewauthisauthenticated\n        description: Check authentication status.\n        call: passbolt.viewauthisauthenticated\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/jwt/jwks.json\n      name: viewauthjwtjwks\n      operations:\n      - method: GET\n        name: viewauthjwtjwks\n        description: Get the JWKs server information.\n        call: passbolt.viewauthjwtjwks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/jwt/login.json\n      name: authjwtlogin\n      operations:\n      - method: POST\n        name: authjwtlogin\n        description: Login.\n\
  \        call: passbolt.authjwtlogin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/jwt/logout.json\n      name: authjwtlogout\n      operations:\n      - method: POST\n        name: authjwtlogout\n        description: Logout.\n        call: passbolt.authjwtlogout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/jwt/refresh.json\n      name: authjwtrefresh\n      operations:\n      - method: POST\n        name: authjwtrefresh\n        description: Refresh access token.\n        call: passbolt.authjwtrefresh\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/jwt/rsa.json\n      name: viewauthjwtrsa\n      operations:\n      - method: GET\n        name: viewauthjwtrsa\n        description: Get the JWT RSA server information.\n        call: passbolt.viewauthjwtrsa\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/login.json\n\
  \      name: authlogin\n      operations:\n      - method: POST\n        name: authlogin\n        description: Log in.\n        call: passbolt.authlogin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/logout.json\n      name: authlogout\n      operations:\n      - method: POST\n        name: authlogout\n        description: Log out.\n        call: passbolt.authlogout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/verify.json\n      name: viewauthverify\n      operations:\n      - method: GET\n        name: viewauthverify\n        description: Get the server's public PGP key.\n        call: passbolt.viewauthverify\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/verify.json\n      name: checkauthverify\n      operations:\n      - method: POST\n        name: checkauthverify\n        description: Verify the server's identity.\n        call: passbolt.checkauthverify\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /avatars/view/{avatarId}/{avatarFormat}\n      name: viewavatar\n      operations:\n      - method: GET\n        name: viewavatar\n        description: Get an avatar as an image.\n        call: passbolt.viewavatar\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments/{commentId}.json\n      name: updatecomment\n      operations:\n      - method: PUT\n        name: updatecomment\n        description: Update a comment.\n        call: passbolt.updatecomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments/{commentId}.json\n      name: deletecomment\n      operations:\n      - method: DELETE\n        name: deletecomment\n        description: Delete a comment.\n        call: passbolt.deletecomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments/resource/{resourceId}.json\n\
  \      name: indexcomments\n      operations:\n      - method: GET\n        name: indexcomments\n        description: Get comments for a resource.\n        call: passbolt.indexcomments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments/resource/{resourceId}.json\n      name: addcomment\n      operations:\n      - method: POST\n        name: addcomment\n        description: Add a comment.\n        call: passbolt.addcomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /directorysync/synchronize/dry-run.json\n      name: simulatesync\n      operations:\n      - method: GET\n        name: simulatesync\n        description: Simulate directory synchronization without making changes.\n        call: passbolt.simulatesync\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /directorysync/synchronize.json\n      name: runsync\n      operations:\n      - method: POST\n      \
  \  name: runsync\n        description: Run the directory synchronization.\n        call: passbolt.runsync\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /favorite/{favoriteId}.json\n      name: deletefavorite\n      operations:\n      - method: DELETE\n        name: deletefavorite\n        description: Unset a resource as favorite.\n        call: passbolt.deletefavorite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /favorite/{foreignModel}/{foreignId}.json\n      name: addfavorite\n      operations:\n      - method: POST\n        name: addfavorite\n        description: Set a resource as favorite.\n        call: passbolt.addfavorite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders.json\n      name: indexfolders\n      operations:\n      - method: GET\n        name: indexfolders\n        description: Get multiple folders.\n        call: passbolt.indexfolders\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders.json\n      name: addfolder\n      operations:\n      - method: POST\n        name: addfolder\n        description: Create a folder.\n        call: passbolt.addfolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders/{folderId}.json\n      name: viewfolder\n      operations:\n      - method: GET\n        name: viewfolder\n        description: Get a folder.\n        call: passbolt.viewfolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders/{folderId}.json\n      name: updatefolder\n      operations:\n      - method: PUT\n        name: updatefolder\n        description: Update a folder.\n        call: passbolt.updatefolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders/{folderId}.json\n      name: deletefolder\n      operations:\n      - method: DELETE\n\
  \        name: deletefolder\n        description: Delete a folder.\n        call: passbolt.deletefolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gpgkeys.json\n      name: indexgpgkeys\n      operations:\n      - method: GET\n        name: indexgpgkeys\n        description: Get multiple GPG keys.\n        call: passbolt.indexgpgkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gpgkeys/{gpgkeyId}.json\n      name: viewgpgkey\n      operations:\n      - method: GET\n        name: viewgpgkey\n        description: Get a GPG key.\n        call: passbolt.viewgpgkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups.json\n      name: indexgroups\n      operations:\n      - method: GET\n        name: indexgroups\n        description: Get multiple groups.\n        call: passbolt.indexgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /groups.json\n      name: addgroup\n      operations:\n      - method: POST\n        name: addgroup\n        description: Create a group.\n        call: passbolt.addgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{groupId}.json\n      name: viewgroup\n      operations:\n      - method: GET\n        name: viewgroup\n        description: Get a group.\n        call: passbolt.viewgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{groupId}.json\n      name: updategroup\n      operations:\n      - method: PUT\n        name: updategroup\n        description: Update a group.\n        call: passbolt.updategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{groupId}.json\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: Delete a group.\n        call: passbolt.deletegroup\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{groupId}/dry-run.json\n      name: dryrunupdategroup\n      operations:\n      - method: PUT\n        name: dryrunupdategroup\n        description: Dry run a group update.\n        call: passbolt.dryrunupdategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{groupId}/dry-run.json\n      name: dryrundeletegroup\n      operations:\n      - method: DELETE\n        name: dryrundeletegroup\n        description: Dry run a group deletion.\n        call: passbolt.dryrundeletegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /healthcheck.json\n      name: viewhealthcheck\n      operations:\n      - method: GET\n        name: viewhealthcheck\n        description: Get healthcheck information.\n        call: passbolt.viewhealthcheck\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /healthcheck/status.json\n      name: viewhealthcheckstatus\n      operations:\n      - method: GET\n        name: viewhealthcheckstatus\n        description: Check if passbolt is up.\n        call: passbolt.viewhealthcheckstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/keys.json\n      name: indexmetadatakeys\n      operations:\n      - method: GET\n        name: indexmetadatakeys\n        description: Get metadata keys.\n        call: passbolt.indexmetadatakeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/keys.json\n      name: addmetadatakey\n      operations:\n      - method: POST\n        name: addmetadatakey\n        description: Create a metadata key.\n        call: passbolt.addmetadatakey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/keys/{metadataKeyId}.json\n      name: updatemetadatakey\n      operations:\n \
  \     - method: PUT\n        name: updatemetadatakey\n        description: Mark a metadata key as expired.\n        call: passbolt.updatemetadatakey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/keys/{metadataKeyId}.json\n      name: deletemetadatakey\n      operations:\n      - method: DELETE\n        name: deletemetadatakey\n        description: Delete a metadata key.\n        call: passbolt.deletemetadatakey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/keys/privates.json\n      name: addmetadataprivatekey\n      operations:\n      - method: POST\n        name: addmetadataprivatekey\n        description: Create a metadata private key.\n        call: passbolt.addmetadataprivatekey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/keys/private/{metadataPrivateKeyId}.json\n      name: updatemetadataprivatekey\n      operations:\n      - method:\
  \ PUT\n        name: updatemetadataprivatekey\n        description: Update a metadata private key.\n        call: passbolt.updatemetadataprivatekey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/keys/settings.json\n      name: indexmetadatakeyssettings\n      operations:\n      - method: GET\n        name: indexmetadatakeyssettings\n        description: Get metadata keys settings.\n        call: passbolt.indexmetadatakeyssettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/keys/settings.json\n      name: updatemetadatakeyssettings\n      operations:\n      - method: POST\n        name: updatemetadatakeyssettings\n        description: Update metadata keys settings.\n        call: passbolt.updatemetadatakeyssettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/types/settings.json\n      name: viewmetadatatypessettings\n      operations:\n\
  \      - method: GET\n        name: viewmetadatatypessettings\n        description: Get metadata types settings\n        call: passbolt.viewmetadatatypessettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/types/settings.json\n      name: upgrademetadatatypessettings\n      operations:\n      - method: POST\n        name: upgrademetadatatypessettings\n        description: Upgrade a resource types settings\n        call: passbolt.upgrademetadatatypessettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/rotate-key/folders.json\n      name: viewmetadatarotatekeyfolders\n      operations:\n      - method: GET\n        name: viewmetadatarotatekeyfolders\n        description: Get folders with expired keys\n        call: passbolt.viewmetadatarotatekeyfolders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/rotate-key/folders.json\n      name:\
  \ rotatemetadataexpiredkeysfolders\n      operations:\n      - method: POST\n        name: rotatemetadataexpiredkeysfolders\n        description: Rotate expired metadata keys for folders\n        call: passbolt.rotatemetadataexpiredkeysfolders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/rotate-key/resources.json\n      name: viewmetadatarotatekeyresources\n      operations:\n      - method: GET\n        name: viewmetadatarotatekeyresources\n        description: Get resources with expired keys\n        call: passbolt.viewmetadatarotatekeyresources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/rotate-key/resources.json\n      name: rotatemetadataexpiredkeys\n      operations:\n      - method: POST\n        name: rotatemetadataexpiredkeys\n        description: Rotate expired metadata keys for resources\n        call: passbolt.rotatemetadataexpiredkeys\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /metadata/session-keys.json\n      name: viewmetadatasessionkeys\n      operations:\n      - method: GET\n        name: viewmetadatasessionkeys\n        description: Get session keys.\n        call: passbolt.viewmetadatasessionkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/session-keys.json\n      name: addmetadatasessionkey\n      operations:\n      - method: POST\n        name: addmetadatasessionkey\n        description: Add a session key.\n        call: passbolt.addmetadatasessionkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/session-key/{sessionKeyId}.json\n      name: updatemetadatasessionkey\n      operations:\n      - method: POST\n        name: updatemetadatasessionkey\n       \n\n# --- truncated at 32 KB (50 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/passbolt/refs/heads/main/capabilities/passbolt-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/passbolt/refs/heads/main/capabilities/passbolt-capability.yaml
tags:
- Passbolt
- API
tools:
- description: Check authentication status.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewauthisauthenticated
- description: Get the JWKs server information.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewauthjwtjwks
- description: Login.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authjwtlogin
- description: Logout.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authjwtlogout
- description: Refresh access token.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authjwtrefresh
- description: Get the JWT RSA server information.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewauthjwtrsa
- description: Log in.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authlogin
- description: Log out.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authlogout
- description: Get the server's public PGP key.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewauthverify
- description: Verify the server's identity.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checkauthverify
- description: Get an avatar as an image.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewavatar
- description: Update a comment.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecomment
- description: Delete a comment.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecomment
- description: Get comments for a resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: indexcomments
- description: Add a comment.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addcomment
- description: Simulate directory synchronization without making changes.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: simulatesync
- description: Run the directory synchronization.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runsync
- description: Unset a resource as favorite.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefavorite
- description: Set a resource as favorite.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addfavorite
- description: Get multiple folders.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: indexfolders
- description: Create a folder.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addfolder
- description: Get a folder.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewfolder
- description: Update a folder.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefolder
- description: Delete a folder.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefolder
- description: Get multiple GPG keys.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: indexgpgkeys
- description: Get a GPG key.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewgpgkey
- description: Get multiple groups.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: indexgroups
- description: Create a group.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addgroup
- description: Get a group.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewgroup
- description: Update a group.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroup
- description: Delete a group.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: Dry run a group update.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: dryrunupdategroup
- description: Dry run a group deletion.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: dryrundeletegroup
- description: Get healthcheck information.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewhealthcheck
- description: Check if passbolt is up.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewhealthcheckstatus
- description: Get metadata keys.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: indexmetadatakeys
- description: Create a metadata key.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addmetadatakey
- description: Mark a metadata key as expired.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemetadatakey
- description: Delete a metadata key.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemetadatakey
- description: Create a metadata private key.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addmetadataprivatekey
- description: Update a metadata private key.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemetadataprivatekey
- description: Get metadata keys settings.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: indexmetadatakeyssettings
- description: Update metadata keys settings.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatemetadatakeyssettings
- description: Get metadata types settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewmetadatatypessettings
- description: Upgrade a resource types settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upgrademetadatatypessettings
- description: Get folders with expired keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewmetadatarotatekeyfolders
- description: Rotate expired metadata keys for folders
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rotatemetadataexpiredkeysfolders
- description: Get resources with expired keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewmetadatarotatekeyresources
- description: Rotate expired metadata keys for resources
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rotatemetadataexpiredkeys
- description: Get session keys.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewmetadatasessionkeys
- description: Add a session key.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addmetadatasessionkey
- description: Update a given session-key entry.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatemetadatasessionkey
- description: Delete a given session-key entry.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesessionkey
- description: Get tags with expired keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewmetadatarotatekeytags
- description: Rotate expired metadata keys for tags
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rotatemetadatakeystags
- description: Get Upgradable Folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewmetadataupgradefolders
- description: Upgrade a folder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upgrademetadatafolders
- description: Get Upgradable Resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewmetadataupgraderesources
- description: Upgrade a Resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upgrademetadataresources
- description: Get Upgradable Tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewmetadataupgradetags
---
