---
categories: []
consumed_apis: []
description: 'The Engine API is an HTTP API served by Docker Engine. It is the API the Docker client uses to communicate with the Engine, so everything the Docker client can do can be done with the API. Most of the client''s commands map directly to API endpoints (e.g. `docker ps` is `GET /containers/json`). The notable exception is running containers, which consists of several API calls. # Errors The API uses standard HTTP status codes to indicate the success or failure of the API call. The body of the response will be JSON in the following format: ``` { "message": "page not found" } ``` # Versioning The AP'
layout: capability
name: Docker Engine API
operations:
- description: List containers
  method: GET
  name: containerlist
  path: /containers/json
- description: Create a container
  method: POST
  name: containercreate
  path: /containers/create
- description: Inspect a container
  method: GET
  name: containerinspect
  path: /containers/{id}/json
- description: List processes running inside a container
  method: GET
  name: containertop
  path: /containers/{id}/top
- description: Get container logs
  method: GET
  name: containerlogs
  path: /containers/{id}/logs
- description: Get changes on a container’s filesystem
  method: GET
  name: containerchanges
  path: /containers/{id}/changes
- description: Export a container
  method: GET
  name: containerexport
  path: /containers/{id}/export
- description: Get container stats based on resource usage
  method: GET
  name: containerstats
  path: /containers/{id}/stats
- description: Resize a container TTY
  method: POST
  name: containerresize
  path: /containers/{id}/resize
- description: Start a container
  method: POST
  name: containerstart
  path: /containers/{id}/start
- description: Stop a container
  method: POST
  name: containerstop
  path: /containers/{id}/stop
- description: Restart a container
  method: POST
  name: containerrestart
  path: /containers/{id}/restart
- description: Kill a container
  method: POST
  name: containerkill
  path: /containers/{id}/kill
- description: Update a container
  method: POST
  name: containerupdate
  path: /containers/{id}/update
- description: Rename a container
  method: POST
  name: containerrename
  path: /containers/{id}/rename
- description: Pause a container
  method: POST
  name: containerpause
  path: /containers/{id}/pause
- description: Unpause a container
  method: POST
  name: containerunpause
  path: /containers/{id}/unpause
- description: Attach to a container
  method: POST
  name: containerattach
  path: /containers/{id}/attach
- description: Attach to a container via a websocket
  method: GET
  name: containerattachwebsocket
  path: /containers/{id}/attach/ws
- description: Wait for a container
  method: POST
  name: containerwait
  path: /containers/{id}/wait
- description: Remove a container
  method: DELETE
  name: containerdelete
  path: /containers/{id}
- description: Get an archive of a filesystem resource in a container
  method: GET
  name: containerarchive
  path: /containers/{id}/archive
- description: Extract an archive of files or folders to a directory in a container
  method: PUT
  name: putcontainerarchive
  path: /containers/{id}/archive
- description: Delete stopped containers
  method: POST
  name: containerprune
  path: /containers/prune
- description: List Images
  method: GET
  name: imagelist
  path: /images/json
- description: Build an image
  method: POST
  name: imagebuild
  path: /build
- description: Delete builder cache
  method: POST
  name: buildprune
  path: /build/prune
- description: Create an image
  method: POST
  name: imagecreate
  path: /images/create
- description: Inspect an image
  method: GET
  name: imageinspect
  path: /images/{name}/json
- description: Get the history of an image
  method: GET
  name: imagehistory
  path: /images/{name}/history
- description: Push an image
  method: POST
  name: imagepush
  path: /images/{name}/push
- description: Tag an image
  method: POST
  name: imagetag
  path: /images/{name}/tag
- description: Remove an image
  method: DELETE
  name: imagedelete
  path: /images/{name}
- description: Search images
  method: GET
  name: imagesearch
  path: /images/search
- description: Delete unused images
  method: POST
  name: imageprune
  path: /images/prune
- description: Check auth configuration
  method: POST
  name: systemauth
  path: /auth
- description: Get system information
  method: GET
  name: systeminfo
  path: /info
- description: Get version
  method: GET
  name: systemversion
  path: /version
- description: Ping
  method: GET
  name: systemping
  path: /_ping
- description: Create a new image from a container
  method: POST
  name: imagecommit
  path: /commit
- description: Monitor events
  method: GET
  name: systemevents
  path: /events
- description: Get data usage information
  method: GET
  name: systemdatausage
  path: /system/df
- description: Export an image
  method: GET
  name: imageget
  path: /images/{name}/get
- description: Export several images
  method: GET
  name: imagegetall
  path: /images/get
- description: Import images
  method: POST
  name: imageload
  path: /images/load
- description: Create an exec instance
  method: POST
  name: containerexec
  path: /containers/{id}/exec
- description: Start an exec instance
  method: POST
  name: execstart
  path: /exec/{id}/start
- description: Resize an exec instance
  method: POST
  name: execresize
  path: /exec/{id}/resize
- description: Inspect an exec instance
  method: GET
  name: execinspect
  path: /exec/{id}/json
- description: List volumes
  method: GET
  name: volumelist
  path: /volumes
- description: Create a volume
  method: POST
  name: volumecreate
  path: /volumes/create
- description: Inspect a volume
  method: GET
  name: volumeinspect
  path: /volumes/{name}
- description: '"Update a volume. Valid only for Swarm cluster volumes"'
  method: PUT
  name: volumeupdate
  path: /volumes/{name}
- description: Remove a volume
  method: DELETE
  name: volumedelete
  path: /volumes/{name}
- description: Delete unused volumes
  method: POST
  name: volumeprune
  path: /volumes/prune
- description: List networks
  method: GET
  name: networklist
  path: /networks
- description: Inspect a network
  method: GET
  name: networkinspect
  path: /networks/{id}
- description: Remove a network
  method: DELETE
  name: networkdelete
  path: /networks/{id}
- description: Create a network
  method: POST
  name: networkcreate
  path: /networks/create
- description: Connect a container to a network
  method: POST
  name: networkconnect
  path: /networks/{id}/connect
personas: []
provider_name: Docker
provider_slug: docker
search_terms:
- containerunpause
- volumeupdate
- volumeprune
- create a container
- putcontainerarchive
- start a container
- networkconnect
- rename a container
- list networks
- inspect a container
- wait for a container
- containerdelete
- cloud
- unpause a container
- inspect an image
- volumecreate
- imagegetall
- build an image
- get version
- networkinspect
- containertop
- api
- containerrestart
- imagedelete
- attach to a container
- pause a container
- export several images
- imagepush
- resize a container tty
- systemversion
- imagehistory
- delete unused images
- search images
- systemping
- start an exec instance
- connect a container to a network
- list volumes
- imagecreate
- containerchanges
- systemdatausage
- infrastructure
- containerkill
- get changes on a container’s filesystem
- '"update a volume. valid only for swarm cluster volumes"'
- networklist
- create a new image from a container
- containerstop
- inspect an exec instance
- networkcreate
- resize an exec instance
- containerwait
- imagecommit
- networkdelete
- create an image
- containerexec
- volumeinspect
- containerstats
- containerresize
- get container stats based on resource usage
- containerattachwebsocket
- systeminfo
- remove a volume
- imagelist
- delete stopped containers
- delete builder cache
- containerupdate
- containerrename
- systemevents
- containerlist
- imageprune
- get the history of an image
- containerattach
- devops
- imagesearch
- imageget
- monitor events
- get data usage information
- create an exec instance
- volumedelete
- remove an image
- execinspect
- push an image
- kill a container
- containerstart
- remove a container
- restart a container
- containerlogs
- list processes running inside a container
- export a container
- stop a container
- update a container
- list images
- imageload
- microservices
- check auth configuration
- delete unused volumes
- extract an archive of files or folders to a directory in a container
- get container logs
- containerarchive
- export an image
- imagetag
- attach to a container via a websocket
- create a volume
- import images
- create a network
- get system information
- containers
- docker
- list containers
- tag an image
- imageinspect
- volumelist
- inspect a network
- inspect a volume
- execresize
- containerexport
- imagebuild
- containerpause
- ping
- remove a network
- systemauth
- containerinspect
- containerprune
- containercreate
- get an archive of a filesystem resource in a container
- execstart
- buildprune
slug: docker-capability
source_filename: docker-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Docker Engine API\n  description: 'The Engine API is an HTTP API served by Docker Engine. It is the API the Docker client uses to communicate\n    with the Engine, so everything the Docker client can do can be done with the API. Most of the client''s commands map directly\n    to API endpoints (e.g. `docker ps` is `GET /containers/json`). The notable exception is running containers, which consists\n    of several API calls. # Errors The API uses standard HTTP status codes to indicate the success or failure of the API call.\n    The body of the response will be JSON in the following format: ``` { \"message\": \"page not found\" } ``` # Versioning The\n    AP'\n  tags:\n  - Docker\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: docker\n    baseUri: https://api.example.com\n    description: Docker Engine API HTTP API.\n    resources:\n    - name: containers-json\n     \
  \ path: /containers/json\n      operations:\n      - name: containerlist\n        method: GET\n        description: List containers\n        inputParameters:\n        - name: all\n          in: query\n          type: string\n          description: Return all containers. By default, only running containers are shown.\n        - name: limit\n          in: query\n          type: string\n          description: Return this number of most recently created containers, including non-running ones.\n        - name: size\n          in: query\n          type: string\n          description: Return the size of container as fields `SizeRw` and `SizeRootFs`.\n        - name: filters\n          in: query\n          type: string\n          description: 'Filters to process on the container list, encoded as JSON (a `map[string][]string`). For example,\n            `{\"status\": [\"paused\"]}` will only return paused containers. A'\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: containers-create\n      path: /containers/create\n      operations:\n      - name: containercreate\n        method: POST\n        description: Create a container\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Assign the specified name to the container. Must match `/?[a-zA-Z0-9][a-zA-Z0-9_.-]+`.\n        - name: platform\n          in: query\n          type: string\n          description: Platform in the format `os[/arch[/variant]]` used for image lookup. When specified, the daemon checks\n            if the requested image is present in the local image cache\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-json\n      path: /containers/{id}/json\n      operations:\n      - name: containerinspect\n        method: GET\n        description: Inspect a\
  \ container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: size\n          in: query\n          type: string\n          description: Return the size of container as fields `SizeRw` and `SizeRootFs`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-top\n      path: /containers/{id}/top\n      operations:\n      - name: containertop\n        method: GET\n        description: List processes running inside a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: ps_args\n          in: query\n          type: string\n          description: The arguments to pass to `ps`. For example, `aux`\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-logs\n      path: /containers/{id}/logs\n      operations:\n      - name: containerlogs\n        method: GET\n        description: Get container logs\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: follow\n          in: query\n          type: string\n          description: Keep connection after returning logs.\n        - name: stdout\n          in: query\n          type: string\n          description: Return logs from `stdout`\n        - name: stderr\n          in: query\n          type: string\n          description: Return logs from `stderr`\n        - name: since\n          in: query\n          type: string\n          description: Only return logs since this time, as a UNIX timestamp\n        - name: until\n          in: query\n\
  \          type: string\n          description: Only return logs before this time, as a UNIX timestamp\n        - name: timestamps\n          in: query\n          type: string\n          description: Add timestamps to every log line\n        - name: tail\n          in: query\n          type: string\n          description: Only return this number of log lines from the end of the logs. Specify as an integer or `all` to output\n            all log lines.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-changes\n      path: /containers/{id}/changes\n      operations:\n      - name: containerchanges\n        method: GET\n        description: Get changes on a container’s filesystem\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: containers-id-export\n      path: /containers/{id}/export\n      operations:\n      - name: containerexport\n        method: GET\n        description: Export a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-stats\n      path: /containers/{id}/stats\n      operations:\n      - name: containerstats\n        method: GET\n        description: Get container stats based on resource usage\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: stream\n          in: query\n          type: string\n         \
  \ description: Stream the output. If false, the stats will be output once and then it will disconnect.\n        - name: one-shot\n          in: query\n          type: string\n          description: Only get a single stat instead of waiting for 2 cycles. Must be used with `stream=false`.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-resize\n      path: /containers/{id}/resize\n      operations:\n      - name: containerresize\n        method: POST\n        description: Resize a container TTY\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: h\n          in: query\n          type: string\n          required: true\n          description: Height of the TTY session in characters\n        - name: w\n          in: query\n          type: string\n         \
  \ required: true\n          description: Width of the TTY session in characters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-start\n      path: /containers/{id}/start\n      operations:\n      - name: containerstart\n        method: POST\n        description: Start a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: detachKeys\n          in: query\n          type: string\n          description: 'Override the key sequence for detaching a container. Format is a single character `[a-Z]` or `ctrl-<value>`\n            where `<value>` is one of: `a-z`, `@`, `^`, `[`, `,`'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-stop\n      path:\
  \ /containers/{id}/stop\n      operations:\n      - name: containerstop\n        method: POST\n        description: Stop a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: signal\n          in: query\n          type: string\n          description: Signal to send to the container as an integer or string (e.g. `SIGINT`).\n        - name: t\n          in: query\n          type: string\n          description: Number of seconds to wait before killing the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-restart\n      path: /containers/{id}/restart\n      operations:\n      - name: containerrestart\n        method: POST\n        description: Restart a container\n        inputParameters:\n        - name: id\n          in: path\n       \
  \   type: string\n          required: true\n          description: ID or name of the container\n        - name: signal\n          in: query\n          type: string\n          description: Signal to send to the container as an integer or string (e.g. `SIGINT`).\n        - name: t\n          in: query\n          type: string\n          description: Number of seconds to wait before killing the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-kill\n      path: /containers/{id}/kill\n      operations:\n      - name: containerkill\n        method: POST\n        description: Kill a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: signal\n          in: query\n          type: string\n          description: Signal to send to the container\
  \ as an integer or string (e.g. `SIGINT`).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-update\n      path: /containers/{id}/update\n      operations:\n      - name: containerupdate\n        method: POST\n        description: Update a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-rename\n      path: /containers/{id}/rename\n      operations:\n      - name: containerrename\n        method: POST\n        description: Rename a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n\
  \        - name: name\n          in: query\n          type: string\n          required: true\n          description: New name for the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-pause\n      path: /containers/{id}/pause\n      operations:\n      - name: containerpause\n        method: POST\n        description: Pause a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-unpause\n      path: /containers/{id}/unpause\n      operations:\n      - name: containerunpause\n        method: POST\n        description: Unpause a container\n        inputParameters:\n        - name: id\n          in: path\n\
  \          type: string\n          required: true\n          description: ID or name of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-attach\n      path: /containers/{id}/attach\n      operations:\n      - name: containerattach\n        method: POST\n        description: Attach to a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: detachKeys\n          in: query\n          type: string\n          description: 'Override the key sequence for detaching a container.Format is a single character `[a-Z]` or `ctrl-<value>`\n            where `<value>` is one of: `a-z`, `@`, `^`, `[`, `,` '\n        - name: logs\n          in: query\n          type: string\n          description: Replay previous logs from the container. This is useful\
  \ for attaching to a container that has started\n            and you want to output everything since the container star\n        - name: stream\n          in: query\n          type: string\n          description: Stream attached streams from the time the request was made onwards.\n        - name: stdin\n          in: query\n          type: string\n          description: Attach to `stdin`\n        - name: stdout\n          in: query\n          type: string\n          description: Attach to `stdout`\n        - name: stderr\n          in: query\n          type: string\n          description: Attach to `stderr`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-attach-ws\n      path: /containers/{id}/attach/ws\n      operations:\n      - name: containerattachwebsocket\n        method: GET\n        description: Attach to a container via a websocket\n        inputParameters:\n        - name:\
  \ id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: detachKeys\n          in: query\n          type: string\n          description: 'Override the key sequence for detaching a container.Format is a single character `[a-Z]` or `ctrl-<value>`\n            where `<value>` is one of: `a-z`, `@`, `^`, `[`, `,`,'\n        - name: logs\n          in: query\n          type: string\n          description: Return logs\n        - name: stream\n          in: query\n          type: string\n          description: Return stream\n        - name: stdin\n          in: query\n          type: string\n          description: Attach to `stdin`\n        - name: stdout\n          in: query\n          type: string\n          description: Attach to `stdout`\n        - name: stderr\n          in: query\n          type: string\n          description: Attach to `stderr`\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: containers-id-wait\n      path: /containers/{id}/wait\n      operations:\n      - name: containerwait\n        method: POST\n        description: Wait for a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: condition\n          in: query\n          type: string\n          description: Wait until a container state reaches the given condition. Defaults to `not-running` if omitted or empty.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id\n      path: /containers/{id}\n      operations:\n      - name: containerdelete\n        method: DELETE\n        description: Remove a container\n        inputParameters:\n        - name: id\n          in: path\n          type:\
  \ string\n          required: true\n          description: ID or name of the container\n        - name: v\n          in: query\n          type: string\n          description: Remove anonymous volumes associated with the container.\n        - name: force\n          in: query\n          type: string\n          description: If the container is running, kill it before removing it.\n        - name: link\n          in: query\n          type: string\n          description: Remove the specified link associated with the container.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-id-archive\n      path: /containers/{id}/archive\n      operations:\n      - name: containerarchive\n        method: GET\n        description: Get an archive of a filesystem resource in a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n     \
  \     description: ID or name of the container\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: Resource in the container’s filesystem to archive.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putcontainerarchive\n        method: PUT\n        description: Extract an archive of files or folders to a directory in a container\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: ID or name of the container\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: Path to a directory in the container to extract the archive’s contents into.\n        - name: noOverwriteDirNonDir\n          in: query\n          type: string\n          description: If `1`, `true`, or `True` then it will be\
  \ an error if unpacking the given content would cause an existing\n            directory to be replaced with a non-directory and vice\n        - name: copyUIDGID\n          in: query\n          type: string\n          description: If `1`, `true`, then it will copy UID/GID maps to the dest file or dir\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-prune\n      path: /containers/prune\n      operations:\n      - name: containerprune\n        method: POST\n        description: Delete stopped containers\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n          description: 'Filters to process on the prune list, encoded as JSON (a `map[string][]string`). Available filters:\n            - `until=<timestamp>` Prune containers created before this t'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: images-json\n      path: /images/json\n      operations:\n      - name: imagelist\n        method: GET\n        description: List Images\n        inputParameters:\n        - name: all\n          in: query\n          type: string\n          description: Show all images. Only images from a final layer (no children) are shown by default.\n        - name: filters\n          in: query\n          type: string\n          description: 'A JSON encoded value of the filters (a `map[string][]string`) to process on the images list. Available\n            filters: - `before`=(`<image-name>[:<tag>]`, `<image id>`'\n        - name: shared-size\n          in: query\n          type: string\n          description: Compute and show shared size as a `SharedSize` field on each image.\n        - name: digests\n          in: query\n          type: string\n          description: Show digest information as a `RepoDigests` field on each image.\n        - name: manifests\n\
  \          in: query\n          type: string\n          description: Include `Manifests` in the image summary.\n        - name: identity\n          in: query\n          type: string\n          description: Include `Identity` in each manifest summary. Requires `manifests=1`.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: build\n      path: /build\n      operations:\n      - name: imagebuild\n        method: POST\n        description: Build an image\n        inputParameters:\n        - name: dockerfile\n          in: query\n          type: string\n          description: Path within the build context to the `Dockerfile`. This is ignored if `remote` is specified and points\n            to an external `Dockerfile`.\n        - name: t\n          in: query\n          type: string\n          description: A name and optional tag to apply to the image in the `name:tag` format. If you omit the tag the default\n\
  \            `latest` value is assumed. You can provide several `t` p\n        - name: extrahosts\n          in: query\n          type: string\n          description: Extra hosts to add to /etc/hosts\n        - name: remote\n          in: query\n          type: string\n          description: 'A Git repository URI or HTTP/HTTPS context URI. If the URI points to a single text file, the file’s\n            contents are placed into a file called `Dockerfile` and the '\n        - name: q\n          in: query\n          type: string\n          description: Suppress verbose build output.\n        - name: nocache\n          in: query\n          type: string\n          description: Do not use the cache when building the image.\n        - name: cachefrom\n          in: query\n          type: string\n          description: JSON array of images used for build cache resolution.\n        - name: pull\n          in: query\n          type: string\n          description: Attempt to pull the image even\
  \ if an older image exists locally.\n        - name: rm\n          in: query\n          type: string\n          description: Remove intermediate containers after a successful build.\n        - name: forcerm\n          in: query\n          type: string\n          description: Always remove intermediate containers, even upon failure.\n        - name: memory\n          in: query\n          type: string\n          description: Set memory limit for build.\n        - name: memswap\n          in: query\n          type: string\n          description: Total memory (memory + swap). Set as `-1` to disable swap.\n        - name: cpushares\n          in: query\n          type: string\n          description: CPU shares (relative weight).\n        - name: cpusetcpus\n          in: query\n          type: string\n          description: CPUs in which to allow execution (e.g., `0-3`, `0,1`).\n        - name: cpuperiod\n          in: query\n          type: string\n          description: The length of a CPU\
  \ period in microseconds.\n        - name: cpuquota\n          in: query\n          type: string\n          description: Microseconds of CPU time that the container can get in a CPU period.\n        - name: buildargs\n          in: query\n          type: string\n          description: 'JSON map of string pairs for build-time variables. Users pass these values at build-time. Docker uses\n            the buildargs as the environment context for commands run '\n        - name: shmsize\n          in: query\n          type: string\n          description: Size of `/dev/shm` in bytes. The size must be greater than 0. If omitted the system uses 64MB.\n        - name: squash\n          in: query\n          type: string\n          description: Squash the resulting images layers into a single layer. *(Experimental release only.)*\n        - name: labels\n          in: query\n          type: string\n          description: Arbitrary key/value labels to set on the image, as a JSON map of string pairs.\n\
  \        - name: networkmode\n          in: query\n          type: string\n          description: 'Sets the networking mode for the run commands during build. Supported standard values are: `bridge`,\n            `host`, `none`, and `container:<name|id>`. Any other value '\n        - name: Content-type\n          in: header\n          type: string\n        - name: X-Registry-Config\n          in: header\n          type: string\n          description: 'This is a base64-encoded JSON object with auth configurations for multiple registries that a build\n            may refer to. The key is a registry URL, and the value is an '\n        - name: platform\n          in: query\n          type: string\n          description: Platform in the format os[/arch[/variant]]\n        - name: target\n          in: query\n          type: string\n          description: Target build stage\n        - name: outputs\n          in: query\n          type: string\n          description: 'BuildKit output configuration\
  \ in the format of a stringified JSON array of objects. Each object must\n            have two top-level properties: `Type` and `Attrs`. The `Typ'\n        - name: version\n          in: query\n          type: string\n          description: Version of the builder backend to use. - `1` is the first generation classic (deprecated) builder in\n            the Docker daemon (default) - `2` is [BuildKit](https://git\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: build-prune\n      path: /build/prune\n      operations:\n      - name: buildprune\n        method: POST\n        description: Delete builder cache\n        inputParameters:\n        - name: reserved-space\n          in: query\n          type: string\n          description: Amount of disk space in bytes to keep for cache\n        - name: max-used-space\n          in: query\n          type: string\n          description: Maximum amount of disk\
  \ space allowed to keep for cache\n        - name: min-free-space\n          in: query\n          type: string\n          description: Target amount of free disk space after pruning\n        - name: all\n          in: query\n          type: string\n          description: Remove all types of build cache\n        - name: filters\n          in: query\n          type: string\n          description: 'A JSON encoded value of the filters (a `map[string][]string`) to process on the list of build cache\n            objects. Available filters: - `until=<timestamp>` remove cac'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-create\n      path: /images/create\n      operations:\n      - name: imagecreate\n        method: POST\n        description: Create an image\n        inputParameters:\n        - name: fromImage\n          in: query\n          type: string\n          description: 'Name of the image\
  \ to pull. If the name includes a tag or digest, specific behavior applies: - If only\n            `fromImage` includes a tag, that tag is used. - If both `f'\n        - name: fromSrc\n          in: query\n          type: string\n          description: Source to import. The value may be a URL from which the image can be retrieved or `-` to read the image\n            from the request body. This parameter may only be used w\n        - name: repo\n          in: query\n          type: string\n          description: Repository name given to an image when it is imported. The repo may include a tag. This parameter may\n            only be used when importing an image.\n        - name: tag\n          in: query\n          type: string\n          description: Tag or digest. If empty when pulling an image, this causes all tags for the given image to be pulled.\n        - name: message\n          in: query\n          type: string\n          description: Set commit message for imported image.\n  \
  \      - name: X-Registry-Auth\n          in: header\n          type: string\n          description: A base64url-encoded auth configuration. Refer to the [authentication section](#section/Authentication)\n            for details.\n        - name: changes\n          in: query\n          type: string\n          description: 'Apply `Dockerfile` instructions to the image that is created, for example: `changes=ENV DEBUG=true`.\n            Note that `ENV DEBUG=true` should be URI component encoded.'\n        - name: platform\n          in: query\n          type: string\n          description: Platform in the format os[/arch[/variant]]. When used in combination with the `fromImage` option, the\n            daemon checks if the given image is present in the local i\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-name-json\n      path: /images/{name}/json\n      operations:\n      - name: imageinspect\n\
  \        method: GET\n        description: Inspect an image\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Image name or id\n        - name: manifests\n          in: query\n          type: string\n          description: Include Manifests in the image summary. The `manifests` and `platform` options are mutually exclusive,\n            and an error is produced if both are set.\n        - name: platform\n          in: query\n          type: string\n          description: JSON-encoded OCI platform to select the platform-variant. If omitted, it defaults to any locally available\n            platform, prioritizing the daemon's host platform. If\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-name-history\n      path: /images/{name}/history\n      operations:\n      - name: imagehistory\n        method:\
  \ GET\n        description: Get the history of an image\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Image name or ID\n        - name: platform\n          in: query\n          type: string\n          description: JSON-encoded OCI platform to select the platform-variant. If omitted, it defaults to any locally available\n            platform, prioritizing the daemon's host platform. If\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-name-push\n      path: /images/{name}/push\n      operations:\n      - name: imagepush\n        method: POST\n        description: Push an image\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the image to push. For example, `registry.example.com/myimage`. The image\
  \ must be present in\n            the local image store with the same name. The name should b\n        - name: tag\n          in: query\n          type: string\n          description: Tag of the image to push. For example, `latest`. If no tag is provided, all tags of the given image\n            that are present in the local image store are pushed.\n        - name: platform\n          in: query\n          type: string\n          description: JSON-encoded OCI platform to select the platform-variant to push. If not provided, all available variants\n            will attempt to be pushed. If the daemon provides a mu\n        - name: X-Registry-Auth\n          in: header\n          type: string\n          required: true\n          description: A base64url-encoded auth configuration. Refer to the [authentication section](#section/Authentication)\n            for details.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: images-name-tag\n      path: /images/{name}/tag\n      operations:\n      - name: imagetag\n        method: POST\n        description: Tag an image\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Image name or ID to tag.\n        - name: repo\n          in: query\n          type: string\n          description: The repository to tag in. For example, `someuser/someimage`.\n        - name: tag\n          in: query\n          type: string\n          description: The name of the new tag.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \n\n# --- truncated at 32 KB (109 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/docker/refs/heads/main/capabilities/docker-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/docker/refs/heads/main/capabilities/docker-capability.yaml
tags:
- Docker
- API
tools:
- description: List containers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerlist
- description: Create a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containercreate
- description: Inspect a container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerinspect
- description: List processes running inside a container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containertop
- description: Get container logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerlogs
- description: Get changes on a container’s filesystem
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerchanges
- description: Export a container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerexport
- description: Get container stats based on resource usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerstats
- description: Resize a container TTY
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerresize
- description: Start a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerstart
- description: Stop a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerstop
- description: Restart a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerrestart
- description: Kill a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerkill
- description: Update a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerupdate
- description: Rename a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerrename
- description: Pause a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerpause
- description: Unpause a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerunpause
- description: Attach to a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerattach
- description: Attach to a container via a websocket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerattachwebsocket
- description: Wait for a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerwait
- description: Remove a container
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: containerdelete
- description: Get an archive of a filesystem resource in a container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerarchive
- description: Extract an archive of files or folders to a directory in a container
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putcontainerarchive
- description: Delete stopped containers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerprune
- description: List Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imagelist
- description: Build an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagebuild
- description: Delete builder cache
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: buildprune
- description: Create an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagecreate
- description: Inspect an image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imageinspect
- description: Get the history of an image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imagehistory
- description: Push an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagepush
- description: Tag an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagetag
- description: Remove an image
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: imagedelete
- description: Search images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imagesearch
- description: Delete unused images
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imageprune
- description: Check auth configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: systemauth
- description: Get system information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systeminfo
- description: Get version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systemversion
- description: Ping
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systemping
- description: Create a new image from a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagecommit
- description: Monitor events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systemevents
- description: Get data usage information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systemdatausage
- description: Export an image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imageget
- description: Export several images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imagegetall
- description: Import images
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imageload
- description: Create an exec instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerexec
- description: Start an exec instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execstart
- description: Resize an exec instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execresize
- description: Inspect an exec instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: execinspect
- description: List volumes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: volumelist
- description: Create a volume
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: volumecreate
- description: Inspect a volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: volumeinspect
- description: '"Update a volume. Valid only for Swarm cluster volumes"'
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: volumeupdate
- description: Remove a volume
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: volumedelete
- description: Delete unused volumes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: volumeprune
- description: List networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: networklist
- description: Inspect a network
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: networkinspect
- description: Remove a network
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: networkdelete
- description: Create a network
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: networkcreate
- description: Connect a container to a network
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: networkconnect
---
