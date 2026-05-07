---
categories: []
consumed_apis: []
description: 'This documentation describes the Podman v2.x+ RESTful API. It consists of a Docker-compatible API and a Libpod API providing support for Podman’s unique features such as pods. To start the service and keep it running for 5,000 seconds (-t 0 runs forever): podman system service -t 5000 & You can then use cURL on the socket using requests documented below. NOTE: if you install the package podman-docker, it will create a symbolic link for /run/docker.sock to /run/podman/podman.sock NOTE: Some fields in the API response JSON are encoded as omitempty, which means that if said field has a zero value'
layout: capability
name: supports a RESTful API for the Libpod library
operations:
- description: Check auth configuration
  method: POST
  name: systemauth
  path: /auth
- description: Build image
  method: POST
  name: imagebuild
  path: /build
- description: New Image
  method: POST
  name: imagecommit
  path: /commit
- description: Remove a container
  method: DELETE
  name: containerdelete
  path: /containers/{name}
- description: Get files from a container
  method: GET
  name: containerarchive
  path: /containers/{name}/archive
- description: Put files into a container
  method: PUT
  name: putcontainerarchive
  path: /containers/{name}/archive
- description: Attach to a container
  method: POST
  name: containerattach
  path: /containers/{name}/attach
- description: Report on changes to container's filesystem; adds, deletes or modifications.
  method: GET
  name: containerchanges
  path: /containers/{name}/changes
- description: Create an exec instance
  method: POST
  name: containerexec
  path: /containers/{name}/exec
- description: Export a container
  method: GET
  name: containerexport
  path: /containers/{name}/export
- description: Inspect container
  method: GET
  name: containerinspect
  path: /containers/{name}/json
- description: Kill container
  method: POST
  name: containerkill
  path: /containers/{name}/kill
- description: Get container logs
  method: GET
  name: containerlogs
  path: /containers/{name}/logs
- description: Pause container
  method: POST
  name: containerpause
  path: /containers/{name}/pause
- description: Rename an existing container
  method: POST
  name: containerrename
  path: /containers/{name}/rename
- description: Resize a container's TTY
  method: POST
  name: containerresize
  path: /containers/{name}/resize
- description: Restart container
  method: POST
  name: containerrestart
  path: /containers/{name}/restart
- description: Start a container
  method: POST
  name: containerstart
  path: /containers/{name}/start
- description: Get stats for a container
  method: GET
  name: containerstats
  path: /containers/{name}/stats
- description: Stop a container
  method: POST
  name: containerstop
  path: /containers/{name}/stop
- description: List processes running inside a container
  method: GET
  name: containertop
  path: /containers/{name}/top
- description: Unpause container
  method: POST
  name: containerunpause
  path: /containers/{name}/unpause
- description: Update configuration of an existing container, allowing changes to resource limits
  method: POST
  name: containerupdate
  path: /containers/{name}/update
- description: Wait on a container
  method: POST
  name: containerwait
  path: /containers/{name}/wait
- description: Create a container
  method: POST
  name: containercreate
  path: /containers/create
- description: List containers
  method: GET
  name: containerlist
  path: /containers/json
- description: Delete stopped containers
  method: POST
  name: containerprune
  path: /containers/prune
- description: Get events
  method: GET
  name: systemevents
  path: /events
- description: Inspect an exec instance
  method: GET
  name: execinspect
  path: /exec/{id}/json
- description: Resize an exec instance
  method: POST
  name: execresize
  path: /exec/{id}/resize
- description: Start an exec instance
  method: POST
  name: execstart
  path: /exec/{id}/start
- description: Remove Image
  method: DELETE
  name: imagedelete
  path: /images/{name}
- description: Export an image
  method: GET
  name: imageget
  path: /images/{name}/get
- description: History of an image
  method: GET
  name: imagehistory
  path: /images/{name}/history
- description: Inspect an image
  method: GET
  name: imageinspect
  path: /images/{name}/json
- description: Push Image
  method: POST
  name: imagepush
  path: /images/{name}/push
- description: Tag an image
  method: POST
  name: imagetag
  path: /images/{name}/tag
- description: Create an image
  method: POST
  name: imagecreate
  path: /images/create
- description: Export several images
  method: GET
  name: imagegetall
  path: /images/get
- description: List Images
  method: GET
  name: imagelist
  path: /images/json
- description: Import image
  method: POST
  name: imageload
  path: /images/load
- description: Prune unused images
  method: POST
  name: imageprune
  path: /images/prune
- description: Search images
  method: GET
  name: imagesearch
  path: /images/search
- description: Get info
  method: GET
  name: systeminfo
  path: /info
- description: Ping service
  method: GET
  name: systemping
  path: /libpod/_ping
- description: Remove an artifact
  method: DELETE
  name: artifactdeletelibpod
  path: /libpod/artifacts/{name}
- description: Extract an artifacts contents
  method: GET
  name: artifactextractlibpod
  path: /libpod/artifacts/{name}/extract
- description: Inspect an artifact
  method: GET
  name: artifactinspectlibpod
  path: /libpod/artifacts/{name}/json
- description: Push an artifact
  method: POST
  name: artifactpushlibpod
  path: /libpod/artifacts/{name}/push
- description: Add a file as an artifact
  method: POST
  name: artifactaddlibpod
  path: /libpod/artifacts/add
- description: List artifacts
  method: GET
  name: artifactlistlibpod
  path: /libpod/artifacts/json
- description: Add a local file as an artifact
  method: POST
  name: artifactlocallibpod
  path: /libpod/artifacts/local/add
- description: Pull an artifact
  method: POST
  name: artifactpulllibpod
  path: /libpod/artifacts/pull
- description: Remove one or more artifacts
  method: DELETE
  name: artifactdeletealllibpod
  path: /libpod/artifacts/remove
- description: Build image
  method: POST
  name: imagebuildlibpod
  path: /libpod/build
- description: Commit
  method: POST
  name: imagecommitlibpod
  path: /libpod/commit
- description: Delete container
  method: DELETE
  name: containerdeletelibpod
  path: /libpod/containers/{name}
- description: Copy files from a container
  method: GET
  name: containerarchivelibpod
  path: /libpod/containers/{name}/archive
- description: Copy files into a container
  method: PUT
  name: putcontainerarchivelibpod
  path: /libpod/containers/{name}/archive
- description: Attach to a container
  method: POST
  name: containerattachlibpod
  path: /libpod/containers/{name}/attach
personas: []
provider_name: Podman
provider_slug: podman
search_terms:
- containers
- inspect an artifact
- api
- imagepush
- imagebuild
- resize a container's tty
- containerrestart
- artifactpushlibpod
- containerlogs
- tag an image
- pull an artifact
- oci
- inspect container
- containerresize
- export an image
- import image
- imagegetall
- imageget
- putcontainerarchivelibpod
- artifactextractlibpod
- containerarchive
- containertop
- containerinspect
- search images
- execinspect
- create a container
- artifactaddlibpod
- resize an exec instance
- containerpause
- build image
- execresize
- list images
- containerdelete
- kill container
- containerlist
- containerunpause
- containerarchivelibpod
- artifactlocallibpod
- cloud native
- push an artifact
- get files from a container
- imagelist
- containerattach
- update configuration of an existing container, allowing changes to resource limits
- imagetag
- imageload
- systeminfo
- inspect an image
- containerrename
- putcontainerarchive
- remove an artifact
- export several images
- artifactdeletealllibpod
- imagecreate
- containerchanges
- containerkill
- imagesearch
- imageinspect
- imagecommit
- remove image
- copy files into a container
- pause container
- list processes running inside a container
- containerstats
- create an image
- artifactpulllibpod
- copy files from a container
- push image
- artifactdeletelibpod
- imagecommitlibpod
- containerstop
- delete stopped containers
- containerexport
- check auth configuration
- systemevents
- containerexec
- containercreate
- containerupdate
- get events
- inspect an exec instance
- add a file as an artifact
- delete container
- add a local file as an artifact
- containerdeletelibpod
- stop a container
- new image
- export a container
- containerwait
- containerprune
- devops
- get container logs
- containerstart
- rename an existing container
- systemping
- list artifacts
- remove a container
- get info
- open source
- execstart
- unpause container
- podman
- extract an artifacts contents
- commit
- start a container
- imagebuildlibpod
- imagehistory
- history of an image
- prune unused images
- systemauth
- restart container
- artifactlistlibpod
- create an exec instance
- get stats for a container
- report on changes to container's filesystem; adds, deletes or modifications.
- remove one or more artifacts
- containerattachlibpod
- ping service
- put files into a container
- artifactinspectlibpod
- start an exec instance
- attach to a container
- imagedelete
- list containers
- wait on a container
- imageprune
slug: podman-capability
source_filename: podman-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: supports a RESTful API for the Libpod library\n  description: 'This documentation describes the Podman v2.x+ RESTful API. It consists of a Docker-compatible API and a Libpod\n    API providing support for Podman’s unique features such as pods. To start the service and keep it running for 5,000 seconds\n    (-t 0 runs forever): podman system service -t 5000 & You can then use cURL on the socket using requests documented below.\n    NOTE: if you install the package podman-docker, it will create a symbolic link for /run/docker.sock to /run/podman/podman.sock\n    NOTE: Some fields in the API response JSON are encoded as omitempty, which means that if said field has a zero value'\n  tags:\n  - Podman\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: podman\n    baseUri: https://api.example.com\n    description: supports a RESTful API for the Libpod library HTTP API.\n    resources:\n\
  \    - name: auth\n      path: /auth\n      operations:\n      - name: systemauth\n        method: POST\n        description: Check auth configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: build\n      path: /build\n      operations:\n      - name: imagebuild\n        method: POST\n        description: Build image\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n        - name: X-Registry-Config\n          in: header\n          type: string\n        - name: dockerfile\n          in: query\n          type: string\n          description: Path within the build context to the `Dockerfile`. This is ignored if remote is specified and points\n            to an external `Dockerfile`.\n        - name: t\n          in: query\n          type: string\n          description: A name and optional tag to apply to the image in the `name:tag` format.\
  \ If you omit the tag, the default\n            latest value is assumed. You can provide several t para\n        - name: extrahosts\n          in: query\n          type: string\n          description: TBD Extra hosts to add to /etc/hosts (As of version 1.xx)\n        - name: nohosts\n          in: query\n          type: string\n          description: Not to create /etc/hosts when building the image\n        - name: remote\n          in: query\n          type: string\n          description: A Git repository URI or HTTP/HTTPS context URI. If the URI points to a single text file, the file’s\n            contents are placed into a file called Dockerfile and the im\n        - name: retry\n          in: query\n          type: string\n          description: Number of times to retry in case of failure when performing push/pull.\n        - name: retry-delay\n          in: query\n          type: string\n          description: Delay between retries in case of push/pull failures.\n        - name:\
  \ q\n          in: query\n          type: string\n          description: Suppress verbose build output\n        - name: nocache\n          in: query\n          type: string\n          description: Do not use the cache when building the image (As of version 1.xx)\n        - name: cachefrom\n          in: query\n          type: string\n          description: JSON array of images used to build cache resolution (As of version 1.xx)\n        - name: pull\n          in: query\n          type: string\n          description: Attempt to pull the image even if an older image exists locally (As of version 1.xx)\n        - name: rm\n          in: query\n          type: string\n          description: Remove intermediate containers after a successful build (As of version 1.xx)\n        - name: forcerm\n          in: query\n          type: string\n          description: Always remove intermediate containers, even upon failure (As of version 1.xx)\n        - name: memory\n          in: query\n       \
  \   type: string\n          description: Memory is the upper limit (in bytes) on how much memory running containers can use (As of version 1.xx)\n        - name: memswap\n          in: query\n          type: string\n          description: MemorySwap limits the amount of memory and swap together (As of version 1.xx)\n        - name: cpushares\n          in: query\n          type: string\n          description: CPUShares (relative weight (As of version 1.xx)\n        - name: cpusetcpus\n          in: query\n          type: string\n          description: CPUSetCPUs in which to allow execution (0-3, 0,1) (As of version 1.xx)\n        - name: cpuperiod\n          in: query\n          type: string\n          description: CPUPeriod limits the CPU CFS (Completely Fair Scheduler) period (As of version 1.xx)\n        - name: cpuquota\n          in: query\n          type: string\n          description: CPUQuota limits the CPU CFS (Completely Fair Scheduler) quota (As of version 1.xx)\n        - name:\
  \ buildargs\n          in: query\n          type: string\n          description: JSON map of string pairs denoting build-time variables. For example, the build argument `Foo` with\n            the value of `bar` would be encoded in JSON as `[\"Foo\":\"bar\"]\n        - name: shmsize\n          in: query\n          type: string\n          description: ShmSize is the \"size\" value to use when mounting an shmfs on the container's /dev/shm directory. Default\n            is 64MB (As of version 1.xx)\n        - name: squash\n          in: query\n          type: string\n          description: Silently ignored. Squash the resulting images layers into a single layer (As of version 1.xx)\n        - name: save-stages\n          in: query\n          type: string\n          description: Preserve intermediate stage images instead of removing them after the build completes. By default,\n            they are removed to save space. However, they can be useful f\n        - name: stage-labels\n       \
  \   in: query\n          type: string\n          description: 'Add metadata labels to all intermediate stage images of a multistage build, including the final image.\n            If set to true, save-stages must also be set to true. If '\n        - name: labels\n          in: query\n          type: string\n          description: JSON map of key, value pairs to set as labels on the new image (As of version 1.xx)\n        - name: networkmode\n          in: query\n          type: string\n          description: 'Sets the networking mode for the run commands during build. Supported standard values are: * `bridge`\n            limited to containers within a single host, port mapping r'\n        - name: platform\n          in: query\n          type: string\n          description: Platform format os[/arch[/variant]] Can be comma separated list for multi arch builds. (As of version\n            1.xx)\n        - name: target\n          in: query\n          type: string\n          description: Target\
  \ build stage (As of version 1.xx)\n        - name: outputs\n          in: query\n          type: string\n          description: output configuration TBD (As of version 1.xx)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commit\n      path: /commit\n      operations:\n      - name: imagecommit\n        method: POST\n        description: New Image\n        inputParameters:\n        - name: container\n          in: query\n          type: string\n          description: the name or ID of a container\n        - name: repo\n          in: query\n          type: string\n          description: the repository name for the created image\n        - name: tag\n          in: query\n          type: string\n          description: tag name for the created image\n        - name: comment\n          in: query\n          type: string\n          description: commit message\n        - name: author\n          in: query\n\
  \          type: string\n          description: author of the image\n        - name: pause\n          in: query\n          type: string\n          description: pause the container before committing it\n        - name: changes\n          in: query\n          type: string\n          description: instructions to apply while committing in Dockerfile format\n        - name: squash\n          in: query\n          type: string\n          description: squash newly built layers into a single new layer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name\n      path: /containers/{name}\n      operations:\n      - name: containerdelete\n        method: DELETE\n        description: Remove a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: force\n\
  \          in: query\n          type: string\n          description: If the container is running, kill it before removing it.\n        - name: v\n          in: query\n          type: string\n          description: Remove the volumes associated with the container.\n        - name: link\n          in: query\n          type: string\n          description: not supported\n        - name: ignore\n          in: query\n          type: string\n          description: Ignore if a specified container does not exist.\n        - name: depend\n          in: query\n          type: string\n          description: Remove container dependencies.\n        - name: timeout\n          in: query\n          type: string\n          description: Number of seconds to wait before forcibly stopping the container.\n        - name: volumes\n          in: query\n          type: string\n          description: Remove anonymous volumes associated with the container.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: containers-name-archive\n      path: /containers/{name}/archive\n      operations:\n      - name: containerarchive\n        method: GET\n        description: Get files from a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: container name or id\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: Path to a directory in the container to extract\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putcontainerarchive\n        method: PUT\n        description: Put files into a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: container name or id\n        -\
  \ name: path\n          in: query\n          type: string\n          required: true\n          description: Path to a directory in the container to extract\n        - name: noOverwriteDirNonDir\n          in: query\n          type: string\n          description: if unpacking the given content would cause an existing directory to be replaced with a non-directory\n            and vice versa (1 or true)\n        - name: copyUIDGID\n          in: query\n          type: string\n          description: copy UID/GID maps to the dest file or di (1 or true)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-attach\n      path: /containers/{name}/attach\n      operations:\n      - name: containerattach\n        method: POST\n        description: Attach to a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        \
  \  description: the name or ID of the container\n        - name: detachKeys\n          in: query\n          type: string\n          description: keys to use for detaching from the container\n        - name: logs\n          in: query\n          type: string\n          description: Stream all logs from the container across the connection. Happens before streaming attach (if requested).\n            At least one of logs or stream must be set\n        - name: stream\n          in: query\n          type: string\n          description: Attach to the container. If unset, and logs is set, only the container's logs will be sent. At least\n            one of stream or logs must be set\n        - name: stdout\n          in: query\n          type: string\n          description: Attach to container STDOUT\n        - name: stderr\n          in: query\n          type: string\n          description: Attach to container STDERR\n        - name: stdin\n          in: query\n          type: string\n      \
  \    description: Attach to container STDIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-changes\n      path: /containers/{name}/changes\n      operations:\n      - name: containerchanges\n        method: GET\n        description: Report on changes to container's filesystem; adds, deletes or modifications.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or id of the container\n        - name: parent\n          in: query\n          type: string\n          description: specify a second layer which is used to compare against it instead of the parent layer\n        - name: diffType\n          in: query\n          type: string\n          description: select what you want to match, default is all\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: containers-name-exec\n      path: /containers/{name}/exec\n      operations:\n      - name: containerexec\n        method: POST\n        description: Create an exec instance\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-export\n      path: /containers/{name}/export\n      operations:\n      - name: containerexport\n        method: GET\n        description: Export a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: containers-name-json\n      path: /containers/{name}/json\n      operations:\n      - name: containerinspect\n        method: GET\n        description: Inspect container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or id of the container\n        - name: size\n          in: query\n          type: string\n          description: include the size of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-kill\n      path: /containers/{name}/kill\n      operations:\n      - name: containerkill\n        method: POST\n        description: Kill container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: all\n          in:\
  \ query\n          type: string\n          description: Send kill signal to all containers\n        - name: signal\n          in: query\n          type: string\n          description: signal to be sent to container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-logs\n      path: /containers/{name}/logs\n      operations:\n      - name: containerlogs\n        method: GET\n        description: Get container logs\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: follow\n          in: query\n          type: string\n          description: Keep connection after returning logs.\n        - name: stdout\n          in: query\n          type: string\n          description: Return logs from stdout\n        - name: stderr\n          in: query\n        \
  \  type: string\n          description: Return logs from stderr\n        - name: since\n          in: query\n          type: string\n          description: Only return logs since this time, as a UNIX timestamp\n        - name: until\n          in: query\n          type: string\n          description: Only return logs before this time, as a UNIX timestamp\n        - name: timestamps\n          in: query\n          type: string\n          description: Add timestamps to every log line\n        - name: tail\n          in: query\n          type: string\n          description: Only return this number of log lines from the end of the logs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-pause\n      path: /containers/{name}/pause\n      operations:\n      - name: containerpause\n        method: POST\n        description: Pause container\n        inputParameters:\n        - name: name\n \
  \         in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-rename\n      path: /containers/{name}/rename\n      operations:\n      - name: containerrename\n        method: POST\n        description: Rename an existing container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Full or partial ID or full name of the container to rename\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: New name for the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-resize\n      path: /containers/{name}/resize\n \
  \     operations:\n      - name: containerresize\n        method: POST\n        description: Resize a container's TTY\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: h\n          in: query\n          type: string\n          description: Height to set for the terminal, in characters\n        - name: w\n          in: query\n          type: string\n          description: Width to set for the terminal, in characters\n        - name: running\n          in: query\n          type: string\n          description: Ignore containers not running errors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-restart\n      path: /containers/{name}/restart\n      operations:\n      - name: containerrestart\n        method: POST\n        description: Restart container\n\
  \        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: t\n          in: query\n          type: string\n          description: timeout before sending kill signal to container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-start\n      path: /containers/{name}/start\n      operations:\n      - name: containerstart\n        method: POST\n        description: Start a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: detachKeys\n          in: query\n          type: string\n          description: 'Override the key sequence for detaching a container. Format is a single character [a-Z] or ctrl-<value>\n \
  \           where <value> is one of: a-z, @, ^, [, , or _.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-stats\n      path: /containers/{name}/stats\n      operations:\n      - name: containerstats\n        method: GET\n        description: Get stats for a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: stream\n          in: query\n          type: string\n          description: Stream the output\n        - name: one-shot\n          in: query\n          type: string\n          description: Provide a one-shot response in which preCPU stats are blank, resulting in a single cycle return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-stop\n\
  \      path: /containers/{name}/stop\n      operations:\n      - name: containerstop\n        method: POST\n        description: Stop a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: t\n          in: query\n          type: string\n          description: number of seconds to wait before killing container\n        - name: timeout\n          in: query\n          type: string\n          description: Number of seconds to wait before killing the container (libpod alias for `t`).\n        - name: ignore\n          in: query\n          type: string\n          description: Do not return an error if the container is already stopped.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-top\n      path: /containers/{name}/top\n      operations:\n\
  \      - name: containertop\n        method: GET\n        description: List processes running inside a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: ps_args\n          in: query\n          type: string\n          description: arguments to pass to ps such as aux.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-unpause\n      path: /containers/{name}/unpause\n      operations:\n      - name: containerunpause\n        method: POST\n        description: Unpause container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: containers-name-update\n      path: /containers/{name}/update\n      operations:\n      - name: containerupdate\n        method: POST\n        description: Update configuration of an existing container, allowing changes to resource limits\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Full or partial ID or full name of the container to rename\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-name-wait\n      path: /containers/{name}/wait\n      operations:\n      - name: containerwait\n        method: POST\n        description: Wait on a container\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        - name: condition\n\
  \          in: query\n          type: string\n          description: 'Wait condition. Valid values are: - not-running (default) - return when the container is not running\n            (stopped, exited, or was never started). - next-exit - wait'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-create\n      path: /containers/create\n      operations:\n      - name: containercreate\n        method: POST\n        description: Create a container\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: container name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-json\n      path: /containers/json\n      operations:\n      - name: containerlist\n        method: GET\n        description: List containers\n        inputParameters:\n\
  \        - name: all\n          in: query\n          type: string\n          description: Return all containers. By default, only running containers are shown\n        - name: external\n          in: query\n          type: string\n          description: Return containers in storage not controlled by Podman\n        - name: limit\n          in: query\n          type: string\n          description: Return this number of most recently created containers, including non-running ones.\n        - name: size\n          in: query\n          type: string\n          description: Return the size of container as fields SizeRw and SizeRootFs.\n        - name: filters\n          in: query\n          type: string\n          description: 'A JSON encoded value of the filters (a `map[string][]string`) to process on the containers list. Available\n            filters: - `ancestor`=(`<image-name>[:<tag>]`, `<imag'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: containers-prune\n      path: /containers/prune\n      operations:\n      - name: containerprune\n        method: POST\n        description: Delete stopped containers\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n          description: 'Filters to process on the prune list, encoded as JSON (a `map[string][]string`). Available filters:\n            - `until=<timestamp>` Prune containers created before this t'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: systemevents\n        method: GET\n        description: Get events\n        inputParameters:\n        - name: since\n          in: query\n          type: string\n          description: start streaming events from this time\n        - name: until\n          in: query\n          type: string\n\
  \          description: stop streaming events later than this\n        - name: filters\n          in: query\n          type: string\n          description: JSON encoded map[string][]string of constraints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exec-id-json\n      path: /exec/{id}/json\n      operations:\n      - name: execinspect\n        method: GET\n        description: Inspect an exec instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Exec instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exec-id-resize\n      path: /exec/{id}/resize\n      operations:\n      - name: execresize\n        method: POST\n        description: Resize an exec instance\n        inputParameters:\n        - name: id\n\
  \          in: path\n          type: string\n          required: true\n          description: Exec instance ID\n        - name: h\n          in: query\n          type: string\n          description: Height of the TTY session in characters\n        - name: w\n          in: query\n          type: string\n          description: Width of the TTY session in characters\n        - name: running\n          in: query\n          type: string\n          description: Ignore containers not running errors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exec-id-start\n      path: /exec/{id}/start\n      operations:\n      - name: execstart\n        method: POST\n        description: Start an exec instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Exec instance ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: images-name\n      path: /images/{name}\n      operations:\n      - name: imagedelete\n        method: DELETE\n        description: Remove Image\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name or ID of image to delete\n        - name: force\n          in: query\n          type: string\n          description: Remove the image even if it is being used by stopped containers or has other tags\n        - name: noprune\n          in: query\n          type: string\n          description: do not remove dangling parent images\n        - name: ignore\n          in: query\n          type: string\n          description: Ignore if a specified image does not exist and do not throw an error.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: images-name-get\n      path: /images/{name}/get\n      operations:\n      - name: imageget\n        method: GET\n        description: Export an image\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-name-history\n      path: /images/{name}/history\n      operations:\n      - name: imagehistory\n        method: GET\n        description: History of an image\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-name-json\n      path: /images/{name}/json\n\
  \      operations:\n      - name: imageinspect\n        method: GET\n        description: Inspect an image\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: the name or ID of the container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-name-push\n      path: /images/{name}/push\n      operations:\n      - name: imagepush\n        method: POST\n        description: Push Image\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of image to push.\n        - name: tag\n          in: query\n          type: string\n          description: The tag to associate with the image on the registry.\n        - name: all\n          in: query\n          type: string\n          description: All indicates whether to push all\
  \ images related to the image list\n        - name: compress\n          in: query\n          type: string\n          description: Use compression on image.\n        - name: destination\n          in: query\n          type: string\n          description: Allows for pushing the image to a different destination than the image refers to.\n        - name: format\n          in: query\n          type: string\n          description: Manifest type (oci, v2s1, or v2s2) to use when pushing an image. Default is manifest type of source,\n            with fallbacks.\n        - name: tlsVerify\n          in: query\n          type: string\n          description: Require TLS verification.\n        - name: X-Registry-Auth\n          in: header\n          type: string\n          \n\n# --- truncated at 32 KB (136 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/podman/refs/heads/main/capabilities/podman-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/podman/refs/heads/main/capabilities/podman-capability.yaml
tags:
- Podman
- API
tools:
- description: Check auth configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: systemauth
- description: Build image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagebuild
- description: New Image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagecommit
- description: Remove a container
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: containerdelete
- description: Get files from a container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerarchive
- description: Put files into a container
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putcontainerarchive
- description: Attach to a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerattach
- description: Report on changes to container's filesystem; adds, deletes or modifications.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerchanges
- description: Create an exec instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerexec
- description: Export a container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerexport
- description: Inspect container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerinspect
- description: Kill container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerkill
- description: Get container logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerlogs
- description: Pause container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerpause
- description: Rename an existing container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerrename
- description: Resize a container's TTY
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerresize
- description: Restart container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerrestart
- description: Start a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerstart
- description: Get stats for a container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerstats
- description: Stop a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerstop
- description: List processes running inside a container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containertop
- description: Unpause container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerunpause
- description: Update configuration of an existing container, allowing changes to resource limits
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerupdate
- description: Wait on a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerwait
- description: Create a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containercreate
- description: List containers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerlist
- description: Delete stopped containers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerprune
- description: Get events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systemevents
- description: Inspect an exec instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: execinspect
- description: Resize an exec instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execresize
- description: Start an exec instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execstart
- description: Remove Image
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: imagedelete
- description: Export an image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imageget
- description: History of an image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imagehistory
- description: Inspect an image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imageinspect
- description: Push Image
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
- description: Create an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagecreate
- description: Export several images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imagegetall
- description: List Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imagelist
- description: Import image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imageload
- description: Prune unused images
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imageprune
- description: Search images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: imagesearch
- description: Get info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systeminfo
- description: Ping service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systemping
- description: Remove an artifact
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: artifactdeletelibpod
- description: Extract an artifacts contents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: artifactextractlibpod
- description: Inspect an artifact
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: artifactinspectlibpod
- description: Push an artifact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: artifactpushlibpod
- description: Add a file as an artifact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: artifactaddlibpod
- description: List artifacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: artifactlistlibpod
- description: Add a local file as an artifact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: artifactlocallibpod
- description: Pull an artifact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: artifactpulllibpod
- description: Remove one or more artifacts
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: artifactdeletealllibpod
- description: Build image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagebuildlibpod
- description: Commit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagecommitlibpod
- description: Delete container
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: containerdeletelibpod
- description: Copy files from a container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: containerarchivelibpod
- description: Copy files into a container
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putcontainerarchivelibpod
- description: Attach to a container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: containerattachlibpod
---
