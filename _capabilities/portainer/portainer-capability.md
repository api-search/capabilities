---
categories: []
consumed_apis: []
description: 'Portainer API is an HTTP API served by Portainer. It is used by the Portainer UI and everything you can do with the UI can be done using the HTTP API. Examples are available at https://documentation.portainer.io/api/api-examples/ You can find out more about Portainer at [http://portainer.io](http://portainer.io) and get some support on [Slack](http://portainer.io/slack/). # Authentication Most of the API environments(endpoints) require to be authenticated as well as some level of authorization to be used. Portainer API uses JSON Web Token to manage authentication and thus requires you to provi'
layout: capability
name: PortainerCE API
operations:
- description: Authenticate
  method: POST
  name: authenticateuser
  path: /auth
- description: Logout
  method: POST
  name: logout
  path: /auth/logout
- description: Authenticate with OAuth
  method: POST
  name: validateoauth
  path: /auth/oauth/validate
- description: Creates an archive with a system data snapshot that could be used to restore the system.
  method: POST
  name: backup
  path: /backup
- description: List available custom templates
  method: GET
  name: customtemplatelist
  path: /custom_templates
- description: Remove a template
  method: DELETE
  name: customtemplatedelete
  path: /custom_templates/{id}
- description: Inspect a custom template
  method: GET
  name: customtemplateinspect
  path: /custom_templates/{id}
- description: Update a template
  method: PUT
  name: customtemplateupdate
  path: /custom_templates/{id}
- description: Get Template stack file content.
  method: GET
  name: customtemplatefile
  path: /custom_templates/{id}/file
- description: Fetch the latest config file content based on custom template's git repository configuration
  method: PUT
  name: customtemplategitfetch
  path: /custom_templates/{id}/git_fetch
- description: Create a custom template
  method: POST
  name: customtemplatecreatefile
  path: /custom_templates/create/file
- description: Create a custom template
  method: POST
  name: customtemplatecreaterepository
  path: /custom_templates/create/repository
- description: Create a custom template
  method: POST
  name: customtemplatecreatestring
  path: /custom_templates/create/string
- description: Fetch container gpus data
  method: GET
  name: dockercontainergpusinspect
  path: /docker/{environmentId}/containers/{containerId}/gpus
- description: Get counters for the dashboard
  method: GET
  name: dockerdashboard
  path: /docker/{environmentId}/dashboard
- description: Fetch images
  method: GET
  name: dockerimageslist
  path: /docker/{environmentId}/images
- description: list EdgeGroups
  method: GET
  name: edgegrouplist
  path: /edge_groups
- description: Create an EdgeGroup
  method: POST
  name: edgegroupcreate
  path: /edge_groups
- description: Deletes an EdgeGroup
  method: DELETE
  name: edgegroupdelete
  path: /edge_groups/{id}
- description: Inspects an EdgeGroup
  method: GET
  name: edgegroupinspect
  path: /edge_groups/{id}
- description: Updates an EdgeGroup
  method: PUT
  name: edgegroupupdate
  path: /edge_groups/{id}
- description: Fetch EdgeJobs list
  method: GET
  name: edgejoblist
  path: /edge_jobs
- description: Delete an EdgeJob
  method: DELETE
  name: edgejobdelete
  path: /edge_jobs/{id}
- description: Inspect an EdgeJob
  method: GET
  name: edgejobinspect
  path: /edge_jobs/{id}
- description: Update an EdgeJob
  method: PUT
  name: edgejobupdate
  path: /edge_jobs/{id}
- description: Fetch a file of an EdgeJob
  method: GET
  name: edgejobfile
  path: /edge_jobs/{id}/file
- description: Fetch the list of tasks on an EdgeJob
  method: GET
  name: edgejobtaskslist
  path: /edge_jobs/{id}/tasks
- description: Clear the log for a specifc task on an EdgeJob
  method: DELETE
  name: edgejobtasksclear
  path: /edge_jobs/{id}/tasks/{taskID}/logs
- description: Fetch the log for a specifc task on an EdgeJob
  method: GET
  name: edgejobtasklogsinspect
  path: /edge_jobs/{id}/tasks/{taskID}/logs
- description: Collect the log for a specifc task on an EdgeJob
  method: POST
  name: edgejobtaskscollect
  path: /edge_jobs/{id}/tasks/{taskID}/logs
- description: Create an EdgeJob from a file
  method: POST
  name: edgejobcreatefile
  path: /edge_jobs/create/file
- description: Create an EdgeJob from a text
  method: POST
  name: edgejobcreatestring
  path: /edge_jobs/create/string
- description: Fetches the list of EdgeStacks
  method: GET
  name: edgestacklist
  path: /edge_stacks
- description: Delete an EdgeStack
  method: DELETE
  name: edgestackdelete
  path: /edge_stacks/{id}
- description: Inspect an EdgeStack
  method: GET
  name: edgestackinspect
  path: /edge_stacks/{id}
- description: Update an EdgeStack
  method: PUT
  name: edgestackupdate
  path: /edge_stacks/{id}
- description: Fetches the stack file for an EdgeStack
  method: GET
  name: edgestackfile
  path: /edge_stacks/{id}/file
- description: Update an EdgeStack status
  method: PUT
  name: edgestackstatusupdate
  path: /edge_stacks/{id}/status
- description: Create an EdgeStack from file
  method: POST
  name: edgestackcreatefile
  path: /edge_stacks/create/file
- description: Create an EdgeStack from a git repository
  method: POST
  name: edgestackcreaterepository
  path: /edge_stacks/create/repository
- description: Create an EdgeStack from a text
  method: POST
  name: edgestackcreatestring
  path: /edge_stacks/create/string
- description: List Environment(Endpoint) groups
  method: GET
  name: endpointgrouplist
  path: /endpoint_groups
- description: Create an Environment(Endpoint) Group
  method: POST
  name: post-endpoint-groups
  path: /endpoint_groups
- description: Remove an environment(endpoint) group
  method: DELETE
  name: endpointgroupdelete
  path: /endpoint_groups/{id}
- description: Inspect an Environment(Endpoint) group
  method: GET
  name: get-endpoint-groups-id
  path: /endpoint_groups/{id}
- description: Update an environment(endpoint) group
  method: PUT
  name: endpointgroupupdate
  path: /endpoint_groups/{id}
- description: Removes environment(endpoint) from an environment(endpoint) group
  method: DELETE
  name: endpointgroupdeleteendpoint
  path: /endpoint_groups/{id}/endpoints/{endpointId}
- description: Add an environment(endpoint) to an environment(endpoint) group
  method: PUT
  name: endpointgroupaddendpoint
  path: /endpoint_groups/{id}/endpoints/{endpointId}
- description: Remove multiple environments
  method: DELETE
  name: endpointdeletebatchdeprecated
  path: /endpoints
- description: List environments(endpoints)
  method: GET
  name: endpointlist
  path: /endpoints
- description: Create a new environment(endpoint)
  method: POST
  name: endpointcreate
  path: /endpoints
- description: Remove an environment
  method: DELETE
  name: endpointdelete
  path: /endpoints/{id}
- description: Inspect an environment(endpoint)
  method: GET
  name: endpointinspect
  path: /endpoints/{id}
- description: Update an environment(endpoint)
  method: PUT
  name: endpointupdate
  path: /endpoints/{id}
- description: De-association an edge environment(endpoint)
  method: PUT
  name: endpointassociationdelete
  path: /endpoints/{id}/association
- description: Upload a file under a specific path on the file system of an environment (endpoint)
  method: POST
  name: post-endpoints-id-docker-v2-browse-put
  path: /endpoints/{id}/docker/v2/browse/put
- description: fetch docker pull limits
  method: GET
  name: endpointdockerhubstatus
  path: /endpoints/{id}/dockerhub/{registryId}
- description: Update the logs collected from an Edge Job
  method: POST
  name: post-endpoints-id-edge-jobs-jobid-logs
  path: /endpoints/{id}/edge/jobs/{jobID}/logs
- description: Inspect an Edge Stack for an Environment(Endpoint)
  method: GET
  name: get-endpoints-id-edge-stacks-stackid
  path: /endpoints/{id}/edge/stacks/{stackId}
- description: Get environment(endpoint) status
  method: GET
  name: endpointedgestatusinspect
  path: /endpoints/{id}/edge/status
personas: []
provider_name: Portainer
provider_slug: portainer
search_terms:
- edgestacklist
- customtemplatelist
- update a template
- edgejobfile
- collect the log for a specifc task on an edgejob
- endpointdockerhubstatus
- create an edgegroup
- create a new environment(endpoint)
- fetch a file of an edgejob
- endpointassociationdelete
- get template stack file content.
- create an environment(endpoint) group
- customtemplatecreatestring
- list environment(endpoint) groups
- edgegroupdelete
- edgejoblist
- create an edgestack from file
- endpointgroupdeleteendpoint
- authenticate with oauth
- edgestackfile
- update an environment(endpoint)
- api
- endpointdelete
- inspect an edgestack
- inspect an edgejob
- edgejobtaskscollect
- edgestackcreaterepository
- endpointinspect
- logout
- remove a template
- post endpoint groups
- remove an environment
- edgejobdelete
- list edgegroups
- edgegroupcreate
- create an edgejob from a file
- remove an environment(endpoint) group
- endpointdeletebatchdeprecated
- edgejobtasklogsinspect
- edgestackdelete
- inspects an edgegroup
- remove multiple environments
- edgejobcreatestring
- inspect a custom template
- create a custom template
- edgejobcreatefile
- container management
- edgejobinspect
- fetch the list of tasks on an edgejob
- kubernetes
- updates an edgegroup
- list available custom templates
- dockercontainergpusinspect
- edgestackcreatestring
- endpointcreate
- edgestackupdate
- customtemplatecreaterepository
- update an environment(endpoint) group
- endpointgroupdelete
- customtemplatefile
- fetch images
- get environment(endpoint) status
- inspect an environment(endpoint) group
- get endpoints id edge stacks stackid
- de-association an edge environment(endpoint)
- edgegrouplist
- edgegroupinspect
- edgestackinspect
- authenticateuser
- post endpoints id docker v2 browse put
- create an edgestack from a git repository
- fetch the latest config file content based on custom template's git repository configuration
- backup
- fetches the stack file for an edgestack
- fetches the list of edgestacks
- upload a file under a specific path on the file system of an environment (endpoint)
- fetch the log for a specifc task on an edgejob
- endpointlist
- endpointedgestatusinspect
- fetch container gpus data
- update an edgestack status
- edgejobtaskslist
- create an edgejob from a text
- add an environment(endpoint) to an environment(endpoint) group
- creates an archive with a system data snapshot that could be used to restore the system.
- endpointgrouplist
- portainer
- dockerdashboard
- removes environment(endpoint) from an environment(endpoint) group
- dockerimageslist
- endpointupdate
- customtemplatecreatefile
- update an edgestack
- customtemplateinspect
- edgejobupdate
- update the logs collected from an edge job
- customtemplategitfetch
- delete an edgestack
- deletes an edgegroup
- fetch docker pull limits
- get endpoint groups id
- endpointgroupaddendpoint
- edgejobtasksclear
- containers
- delete an edgejob
- fetch edgejobs list
- edgegroupupdate
- update an edgejob
- customtemplatedelete
- inspect an environment(endpoint)
- docker
- endpointgroupupdate
- edgestackcreatefile
- create an edgestack from a text
- clear the log for a specifc task on an edgejob
- authenticate
- edgestackstatusupdate
- list environments(endpoints)
- inspect an edge stack for an environment(endpoint)
- get counters for the dashboard
- post endpoints id edge jobs jobid logs
- customtemplateupdate
- validateoauth
slug: portainer-capability
source_filename: portainer-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PortainerCE API\n  description: 'Portainer API is an HTTP API served by Portainer. It is used by the Portainer UI and everything you can do\n    with the UI can be done using the HTTP API. Examples are available at https://documentation.portainer.io/api/api-examples/\n    You can find out more about Portainer at [http://portainer.io](http://portainer.io) and get some support on [Slack](http://portainer.io/slack/).\n    # Authentication Most of the API environments(endpoints) require to be authenticated as well as some level of authorization\n    to be used. Portainer API uses JSON Web Token to manage authentication and thus requires you to provi'\n  tags:\n  - Portainer\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: portainer\n    baseUri: https://api.example.com\n    description: PortainerCE API HTTP API.\n    resources:\n    - name: auth\n      path: /auth\n     \
  \ operations:\n      - name: authenticateuser\n        method: POST\n        description: Authenticate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-logout\n      path: /auth/logout\n      operations:\n      - name: logout\n        method: POST\n        description: Logout\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-oauth-validate\n      path: /auth/oauth/validate\n      operations:\n      - name: validateoauth\n        method: POST\n        description: Authenticate with OAuth\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: backup\n      path: /backup\n      operations:\n      - name: backup\n        method: POST\n        description: Creates an archive with a system data snapshot that could be used\
  \ to restore the system.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-templates\n      path: /custom_templates\n      operations:\n      - name: customtemplatelist\n        method: GET\n        description: List available custom templates\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: true\n          description: Template types\n        - name: edge\n          in: query\n          type: string\n          description: Filter by edge templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-templates-id\n      path: /custom_templates/{id}\n      operations:\n      - name: customtemplatedelete\n        method: DELETE\n        description: Remove a template\n        inputParameters:\n        - name: id\n          in: path\n  \
  \        type: string\n          required: true\n          description: Template identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: customtemplateinspect\n        method: GET\n        description: Inspect a custom template\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Template identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: customtemplateupdate\n        method: PUT\n        description: Update a template\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Template identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \  - name: custom-templates-id-file\n      path: /custom_templates/{id}/file\n      operations:\n      - name: customtemplatefile\n        method: GET\n        description: Get Template stack file content.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Template identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-templates-id-git-fetch\n      path: /custom_templates/{id}/git_fetch\n      operations:\n      - name: customtemplategitfetch\n        method: PUT\n        description: Fetch the latest config file content based on custom template's git repository configuration\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Template identifier\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: custom-templates-create-file\n      path: /custom_templates/create/file\n      operations:\n      - name: customtemplatecreatefile\n        method: POST\n        description: Create a custom template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-templates-create-repository\n      path: /custom_templates/create/repository\n      operations:\n      - name: customtemplatecreaterepository\n        method: POST\n        description: Create a custom template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-templates-create-string\n      path: /custom_templates/create/string\n      operations:\n      - name: customtemplatecreatestring\n        method: POST\n        description: Create a custom template\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: docker-environmentid-containers-containerid-gpus\n      path: /docker/{environmentId}/containers/{containerId}/gpus\n      operations:\n      - name: dockercontainergpusinspect\n        method: GET\n        description: Fetch container gpus data\n        inputParameters:\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: containerId\n          in: path\n          type: string\n          required: true\n          description: Container identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: docker-environmentid-dashboard\n      path: /docker/{environmentId}/dashboard\n      operations:\n      - name: dockerdashboard\n        method: GET\n        description: Get counters\
  \ for the dashboard\n        inputParameters:\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: docker-environmentid-images\n      path: /docker/{environmentId}/images\n      operations:\n      - name: dockerimageslist\n        method: GET\n        description: Fetch images\n        inputParameters:\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: withUsage\n          in: query\n          type: string\n          description: Include image usage information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-groups\n      path: /edge_groups\n     \
  \ operations:\n      - name: edgegrouplist\n        method: GET\n        description: list EdgeGroups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edgegroupcreate\n        method: POST\n        description: Create an EdgeGroup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-groups-id\n      path: /edge_groups/{id}\n      operations:\n      - name: edgegroupdelete\n        method: DELETE\n        description: Deletes an EdgeGroup\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeGroup Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edgegroupinspect\n        method: GET\n        description: Inspects an EdgeGroup\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeGroup Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edgegroupupdate\n        method: PUT\n        description: Updates an EdgeGroup\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeGroup Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-jobs\n      path: /edge_jobs\n      operations:\n      - name: edgejoblist\n        method: GET\n        description: Fetch EdgeJobs list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-jobs-id\n      path: /edge_jobs/{id}\n     \
  \ operations:\n      - name: edgejobdelete\n        method: DELETE\n        description: Delete an EdgeJob\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeJob Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edgejobinspect\n        method: GET\n        description: Inspect an EdgeJob\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeJob Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edgejobupdate\n        method: PUT\n        description: Update an EdgeJob\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeJob Id\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-jobs-id-file\n      path: /edge_jobs/{id}/file\n      operations:\n      - name: edgejobfile\n        method: GET\n        description: Fetch a file of an EdgeJob\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeJob Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-jobs-id-tasks\n      path: /edge_jobs/{id}/tasks\n      operations:\n      - name: edgejobtaskslist\n        method: GET\n        description: Fetch the list of tasks on an EdgeJob\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeJob Id\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: edge-jobs-id-tasks-taskid-logs\n      path: /edge_jobs/{id}/tasks/{taskID}/logs\n      operations:\n      - name: edgejobtasksclear\n        method: DELETE\n        description: Clear the log for a specifc task on an EdgeJob\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeJob Id\n        - name: taskID\n          in: path\n          type: string\n          required: true\n          description: Task Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edgejobtasklogsinspect\n        method: GET\n        description: Fetch the log for a specifc task on an EdgeJob\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeJob Id\n        - name:\
  \ taskID\n          in: path\n          type: string\n          required: true\n          description: Task Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edgejobtaskscollect\n        method: POST\n        description: Collect the log for a specifc task on an EdgeJob\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeJob Id\n        - name: taskID\n          in: path\n          type: string\n          required: true\n          description: Task Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-jobs-create-file\n      path: /edge_jobs/create/file\n      operations:\n      - name: edgejobcreatefile\n        method: POST\n        description: Create an EdgeJob from a file\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-jobs-create-string\n      path: /edge_jobs/create/string\n      operations:\n      - name: edgejobcreatestring\n        method: POST\n        description: Create an EdgeJob from a text\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-stacks\n      path: /edge_stacks\n      operations:\n      - name: edgestacklist\n        method: GET\n        description: Fetches the list of EdgeStacks\n        inputParameters:\n        - name: summarizeStatuses\n          in: query\n          type: string\n          description: will summarize the statuses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-stacks-id\n      path: /edge_stacks/{id}\n      operations:\n      - name: edgestackdelete\n     \
  \   method: DELETE\n        description: Delete an EdgeStack\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeStack Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edgestackinspect\n        method: GET\n        description: Inspect an EdgeStack\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeStack Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edgestackupdate\n        method: PUT\n        description: Update an EdgeStack\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeStack Id\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-stacks-id-file\n      path: /edge_stacks/{id}/file\n      operations:\n      - name: edgestackfile\n        method: GET\n        description: Fetches the stack file for an EdgeStack\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeStack Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-stacks-id-status\n      path: /edge_stacks/{id}/status\n      operations:\n      - name: edgestackstatusupdate\n        method: PUT\n        description: Update an EdgeStack status\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EdgeStack Id\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: edge-stacks-create-file\n      path: /edge_stacks/create/file\n      operations:\n      - name: edgestackcreatefile\n        method: POST\n        description: Create an EdgeStack from file\n        inputParameters:\n        - name: dryrun\n          in: query\n          type: string\n          description: if true, will not create an edge stack, but just will check the settings and return a non-persisted\n            edge stack object\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-stacks-create-repository\n      path: /edge_stacks/create/repository\n      operations:\n      - name: edgestackcreaterepository\n        method: POST\n        description: Create an EdgeStack from a git repository\n        inputParameters:\n        - name: dryrun\n          in: query\n          type: string\n          description: if true, will\
  \ not create an edge stack, but just will check the settings and return a non-persisted\n            edge stack object\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edge-stacks-create-string\n      path: /edge_stacks/create/string\n      operations:\n      - name: edgestackcreatestring\n        method: POST\n        description: Create an EdgeStack from a text\n        inputParameters:\n        - name: dryrun\n          in: query\n          type: string\n          description: if true, will not create an edge stack, but just will check the settings and return a non-persisted\n            edge stack object\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-groups\n      path: /endpoint_groups\n      operations:\n      - name: endpointgrouplist\n        method: GET\n        description: List Environment(Endpoint)\
  \ groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-endpoint-groups\n        method: POST\n        description: Create an Environment(Endpoint) Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-groups-id\n      path: /endpoint_groups/{id}\n      operations:\n      - name: endpointgroupdelete\n        method: DELETE\n        description: Remove an environment(endpoint) group\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EndpointGroup identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-endpoint-groups-id\n        method: GET\n        description: Inspect an Environment(Endpoint) group\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Environment(Endpoint) group identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: endpointgroupupdate\n        method: PUT\n        description: Update an environment(endpoint) group\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EndpointGroup identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-groups-id-endpoints-endpointid\n      path: /endpoint_groups/{id}/endpoints/{endpointId}\n      operations:\n      - name: endpointgroupdeleteendpoint\n        method: DELETE\n        description: Removes environment(endpoint) from an environment(endpoint) group\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EndpointGroup identifier\n        - name: endpointId\n          in: path\n          type: string\n          required: true\n          description: Environment(Endpoint) identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: endpointgroupaddendpoint\n        method: PUT\n        description: Add an environment(endpoint) to an environment(endpoint) group\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: EndpointGroup identifier\n        - name: endpointId\n          in: path\n          type: string\n          required: true\n          description: Environment(Endpoint) identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n    - name: endpoints\n      path: /endpoints\n      operations:\n      - name: endpointdeletebatchdeprecated\n        method: DELETE\n        description: Remove multiple environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: endpointlist\n        method: GET\n        description: List environments(endpoints)\n        inputParameters:\n        - name: start\n          in: query\n          type: string\n          description: Start searching from\n        - name: limit\n          in: query\n          type: string\n          description: Limit results to this value\n        - name: sort\n          in: query\n          type: string\n          description: Sort results by this value\n        - name: order\n          in: query\n          type: string\n          description: Order sorted results by desc/asc\n        - name: search\n          in: query\n\
  \          type: string\n          description: Search query\n        - name: groupIds\n          in: query\n          type: string\n          description: List environments(endpoints) of these groups\n        - name: status\n          in: query\n          type: string\n          description: List environments(endpoints) by this status\n        - name: types\n          in: query\n          type: string\n          description: List environments(endpoints) of this type\n        - name: tagIds\n          in: query\n          type: string\n          description: search environments(endpoints) with these tags (depends on tagsPartialMatch)\n        - name: tagsPartialMatch\n          in: query\n          type: string\n          description: If true, will return environment(endpoint) which has one of tagIds, if false (or missing) will return\n            only environments(endpoints) that has all the tags\n        - name: endpointIds\n          in: query\n          type: string\n          description:\
  \ will return only these environments(endpoints)\n        - name: excludeIds\n          in: query\n          type: string\n          description: will exclude these environments(endpoints)\n        - name: excludeGroupIds\n          in: query\n          type: string\n          description: will exclude environments(endpoints) belonging to these endpoint groups\n        - name: provisioned\n          in: query\n          type: string\n          description: If true, will return environment(endpoint) that were provisioned\n        - name: agentVersions\n          in: query\n          type: string\n          description: will return only environments with on of these agent versions\n        - name: edgeAsync\n          in: query\n          type: string\n          description: if exists true show only edge async agents, false show only standard edge agents. if missing, will\n            show both types (relevant only for edge agents)\n        - name: edgeDeviceUntrusted\n          in: query\n\
  \          type: string\n          description: if true, show only untrusted edge agents, if false show only trusted edge agents (relevant only for\n            edge agents)\n        - name: edgeCheckInPassedSeconds\n          in: query\n          type: string\n          description: if bigger then zero, show only edge agents that checked-in in the last provided seconds (relevant only\n            for edge agents)\n        - name: excludeSnapshots\n          in: query\n          type: string\n          description: if true, the snapshot data won't be retrieved\n        - name: name\n          in: query\n          type: string\n          description: will return only environments(endpoints) with this name\n        - name: edgeStackStatus\n          in: query\n          type: string\n          description: only applied when edgeStackId exists. Filter the returned environments based on their deployment status\n            in the stack (not the environment status!)\n        - name: edgeGroupIds\n\
  \          in: query\n          type: string\n          description: List environments(endpoints) of these edge groups\n        - name: excludeEdgeGroupIds\n          in: query\n          type: string\n          description: Exclude environments(endpoints) of these edge groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: endpointcreate\n        method: POST\n        description: Create a new environment(endpoint)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints-id\n      path: /endpoints/{id}\n      operations:\n      - name: endpointdelete\n        method: DELETE\n        description: Remove an environment\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Environment(Endpoint) identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: endpointinspect\n        method: GET\n        description: Inspect an environment(endpoint)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Environment(Endpoint) identifier\n        - name: excludeSnapshot\n          in: query\n          type: string\n          description: if true, the snapshot data won't be retrieved\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: endpointupdate\n        method: PUT\n        description: Update an environment(endpoint)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Environment(Endpoint) identifier\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: endpoints-id-association\n      path: /endpoints/{id}/association\n      operations:\n      - name: endpointassociationdelete\n        method: PUT\n        description: De-association an edge environment(endpoint)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Environment(Endpoint) identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints-id-docker-v2-browse-put\n      path: /endpoints/{id}/docker/v2/browse/put\n      operations:\n      - name: post-endpoints-id-docker-v2-browse-put\n        method: POST\n        description: Upload a file under a specific path on the file system of an environment (endpoint)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Environment(Endpoint) identifier\n        - name: volumeID\n          in: query\n          type: string\n          description: Optional volume identifier to upload the file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints-id-dockerhub-registryid\n      path: /endpoints/{id}/dockerhub/{registryId}\n      operations:\n      - name: endpointdockerhubstatus\n        method: GET\n        description: fetch docker pull limits\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: endpoint ID\n        - name: registryId\n          in: path\n          type: string\n          required: true\n          description: registry ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints-id-edge-jobs-jobid-logs\n\
  \      path: /endpoints/{id}/edge/jobs/{jobID}/logs\n      operations:\n      - name: post-endpoints-id-edge-jobs-jobid-logs\n        method: POST\n        description: Update the logs collected from an Edge Job\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: environment(endpoint) Id\n        - name: jobID\n          in: path\n          type: string\n          required: true\n          description: Job Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints-id-edge-stacks-stackid\n      path: /endpoints/{id}/edge/stacks/{stackId}\n      operations:\n      - name: get-endpoints-id-edge-stacks-stackid\n        method: GET\n        description: Inspect an Edge Stack for an Environment(Endpoint)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required:\
  \ true\n          description: environment(endpoint) Id\n        - name: stackId\n          in: path\n          type: string\n          required: true\n          description: EdgeStack Id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints-id-edge-status\n      path: /endpoints/{id}/edge/status\n      operations:\n      - name: endpointedgestatusinspect\n        method: GET\n        description: Get environment(endpoint) status\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Environment(Endpoint) identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: portainer-rest\n    description: REST adapter for PortainerCE API.\n    resources:\n    - path: /auth\n      name:\
  \ authenticateuser\n      operations:\n      - method: POST\n        name: authenticateuser\n        description: Authenticate\n        call: portainer.authenticateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/logout\n      name: logout\n      operations:\n      - method: POST\n        name: logout\n        description: Logout\n        call: portainer.logout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/oauth/validate\n      name: validateoauth\n      operations:\n      - method: POST\n        name: validateoauth\n        description: Authenticate with OAuth\n        call: portainer.validateoauth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /backup\n      name: backup\n      operations:\n      - method: POST\n        name: backup\n        description: Creates an archive with a system data snapshot that could be used to restore the system.\n      \
  \  call: portainer.backup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /custom_templates\n      name: customtemplatelist\n      operations:\n      - method: GET\n        name: customtemplatelist\n        description: List available custom templates\n        call: portainer.customtemplatelist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /custom_templates/{id}\n      name: customtemplatedelete\n      operations:\n      - method: DELETE\n        name: customtemplatedelete\n        description: Remove a template\n        call: portainer.customtemplatedelete\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /custom_templates/{id}\n      name: customtemplateinspect\n      operations:\n      - me\n\n# --- truncated at 32 KB (79 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/portainer/refs/heads/main/capabilities/portainer-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/portainer/refs/heads/main/capabilities/portainer-capability.yaml
tags:
- Portainer
- API
tools:
- description: Authenticate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authenticateuser
- description: Logout
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: logout
- description: Authenticate with OAuth
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: validateoauth
- description: Creates an archive with a system data snapshot that could be used to restore the system.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: backup
- description: List available custom templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: customtemplatelist
- description: Remove a template
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: customtemplatedelete
- description: Inspect a custom template
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: customtemplateinspect
- description: Update a template
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: customtemplateupdate
- description: Get Template stack file content.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: customtemplatefile
- description: Fetch the latest config file content based on custom template's git repository configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: customtemplategitfetch
- description: Create a custom template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: customtemplatecreatefile
- description: Create a custom template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: customtemplatecreaterepository
- description: Create a custom template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: customtemplatecreatestring
- description: Fetch container gpus data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: dockercontainergpusinspect
- description: Get counters for the dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: dockerdashboard
- description: Fetch images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: dockerimageslist
- description: list EdgeGroups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgegrouplist
- description: Create an EdgeGroup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edgegroupcreate
- description: Deletes an EdgeGroup
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: edgegroupdelete
- description: Inspects an EdgeGroup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgegroupinspect
- description: Updates an EdgeGroup
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: edgegroupupdate
- description: Fetch EdgeJobs list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgejoblist
- description: Delete an EdgeJob
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: edgejobdelete
- description: Inspect an EdgeJob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgejobinspect
- description: Update an EdgeJob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: edgejobupdate
- description: Fetch a file of an EdgeJob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgejobfile
- description: Fetch the list of tasks on an EdgeJob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgejobtaskslist
- description: Clear the log for a specifc task on an EdgeJob
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: edgejobtasksclear
- description: Fetch the log for a specifc task on an EdgeJob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgejobtasklogsinspect
- description: Collect the log for a specifc task on an EdgeJob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edgejobtaskscollect
- description: Create an EdgeJob from a file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edgejobcreatefile
- description: Create an EdgeJob from a text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edgejobcreatestring
- description: Fetches the list of EdgeStacks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgestacklist
- description: Delete an EdgeStack
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: edgestackdelete
- description: Inspect an EdgeStack
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgestackinspect
- description: Update an EdgeStack
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: edgestackupdate
- description: Fetches the stack file for an EdgeStack
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: edgestackfile
- description: Update an EdgeStack status
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: edgestackstatusupdate
- description: Create an EdgeStack from file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edgestackcreatefile
- description: Create an EdgeStack from a git repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edgestackcreaterepository
- description: Create an EdgeStack from a text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edgestackcreatestring
- description: List Environment(Endpoint) groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: endpointgrouplist
- description: Create an Environment(Endpoint) Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-endpoint-groups
- description: Remove an environment(endpoint) group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: endpointgroupdelete
- description: Inspect an Environment(Endpoint) group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-endpoint-groups-id
- description: Update an environment(endpoint) group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: endpointgroupupdate
- description: Removes environment(endpoint) from an environment(endpoint) group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: endpointgroupdeleteendpoint
- description: Add an environment(endpoint) to an environment(endpoint) group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: endpointgroupaddendpoint
- description: Remove multiple environments
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: endpointdeletebatchdeprecated
- description: List environments(endpoints)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: endpointlist
- description: Create a new environment(endpoint)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: endpointcreate
- description: Remove an environment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: endpointdelete
- description: Inspect an environment(endpoint)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: endpointinspect
- description: Update an environment(endpoint)
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: endpointupdate
- description: De-association an edge environment(endpoint)
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: endpointassociationdelete
- description: Upload a file under a specific path on the file system of an environment (endpoint)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-endpoints-id-docker-v2-browse-put
- description: fetch docker pull limits
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: endpointdockerhubstatus
- description: Update the logs collected from an Edge Job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-endpoints-id-edge-jobs-jobid-logs
- description: Inspect an Edge Stack for an Environment(Endpoint)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-endpoints-id-edge-stacks-stackid
- description: Get environment(endpoint) status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: endpointedgestatusinspect
---
