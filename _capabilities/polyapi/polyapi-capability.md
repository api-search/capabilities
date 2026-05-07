---
categories: []
consumed_apis: []
description: PolyAPI is a modern enterprise middleware platform that provides a unified REST API for managing cloud service resources including functions, variables, webhooks, triggers, jobs, schemas, and environments. Built using AI and Kubernetes-native technology, it accelerates development and simplifies the operation of integrations, orchestrations, and microservices.
layout: capability
name: PolyAPI Platform API
operations:
- description: PolyAPI List API functions
  method: GET
  name: listapifunctions
  path: /functions/api
- description: PolyAPI Create an API function
  method: POST
  name: createapifunction
  path: /functions/api
- description: PolyAPI Get an API function
  method: GET
  name: getapifunction
  path: /functions/api/{functionId}
- description: PolyAPI Update an API function
  method: PATCH
  name: updateapifunction
  path: /functions/api/{functionId}
- description: PolyAPI Delete an API function
  method: DELETE
  name: deleteapifunction
  path: /functions/api/{functionId}
- description: PolyAPI Execute an API function
  method: POST
  name: executeapifunction
  path: /functions/api/{functionId}/execute
- description: PolyAPI List server functions
  method: GET
  name: listserverfunctions
  path: /functions/server
- description: PolyAPI Create a server function
  method: POST
  name: createserverfunction
  path: /functions/server
- description: PolyAPI Get a server function
  method: GET
  name: getserverfunction
  path: /functions/server/{functionId}
- description: PolyAPI Update a server function
  method: PATCH
  name: updateserverfunction
  path: /functions/server/{functionId}
- description: PolyAPI Delete a server function
  method: DELETE
  name: deleteserverfunction
  path: /functions/server/{functionId}
- description: PolyAPI Execute a server function
  method: POST
  name: executeserverfunction
  path: /functions/server/{functionId}/execute
- description: PolyAPI List client functions
  method: GET
  name: listclientfunctions
  path: /functions/client
- description: PolyAPI Create a client function
  method: POST
  name: createclientfunction
  path: /functions/client
- description: PolyAPI Get a client function
  method: GET
  name: getclientfunction
  path: /functions/client/{functionId}
- description: PolyAPI Update a client function
  method: PATCH
  name: updateclientfunction
  path: /functions/client/{functionId}
- description: PolyAPI Delete a client function
  method: DELETE
  name: deleteclientfunction
  path: /functions/client/{functionId}
- description: PolyAPI List webhooks
  method: GET
  name: listwebhooks
  path: /webhooks
- description: PolyAPI Create a webhook
  method: POST
  name: createwebhook
  path: /webhooks
- description: PolyAPI Get a webhook
  method: GET
  name: getwebhook
  path: /webhooks/{webhookId}
- description: PolyAPI Update a webhook
  method: PATCH
  name: updatewebhook
  path: /webhooks/{webhookId}
- description: PolyAPI Delete a webhook
  method: DELETE
  name: deletewebhook
  path: /webhooks/{webhookId}
- description: PolyAPI Trigger a webhook
  method: POST
  name: triggerwebhook
  path: /webhooks/{webhookId}/trigger
- description: PolyAPI List variables
  method: GET
  name: listvariables
  path: /variables
- description: PolyAPI Create a variable
  method: POST
  name: createvariable
  path: /variables
- description: PolyAPI Get a variable
  method: GET
  name: getvariable
  path: /variables/{variableId}
- description: PolyAPI Update a variable
  method: PATCH
  name: updatevariable
  path: /variables/{variableId}
- description: PolyAPI Delete a variable
  method: DELETE
  name: deletevariable
  path: /variables/{variableId}
- description: PolyAPI List triggers
  method: GET
  name: listtriggers
  path: /triggers
- description: PolyAPI Create a trigger
  method: POST
  name: createtrigger
  path: /triggers
- description: PolyAPI Get a trigger
  method: GET
  name: gettrigger
  path: /triggers/{triggerId}
- description: PolyAPI Update a trigger
  method: PATCH
  name: updatetrigger
  path: /triggers/{triggerId}
- description: PolyAPI Delete a trigger
  method: DELETE
  name: deletetrigger
  path: /triggers/{triggerId}
- description: PolyAPI List jobs
  method: GET
  name: listjobs
  path: /jobs
- description: PolyAPI Create a job
  method: POST
  name: createjob
  path: /jobs
- description: PolyAPI Get a job
  method: GET
  name: getjob
  path: /jobs/{jobId}
- description: PolyAPI Update a job
  method: PATCH
  name: updatejob
  path: /jobs/{jobId}
- description: PolyAPI Delete a job
  method: DELETE
  name: deletejob
  path: /jobs/{jobId}
- description: PolyAPI List schemas
  method: GET
  name: listschemas
  path: /schemas
- description: PolyAPI Create a schema
  method: POST
  name: createschema
  path: /schemas
- description: PolyAPI Get a schema
  method: GET
  name: getschema
  path: /schemas/{schemaId}
- description: PolyAPI Update a schema
  method: PATCH
  name: updateschema
  path: /schemas/{schemaId}
- description: PolyAPI Delete a schema
  method: DELETE
  name: deleteschema
  path: /schemas/{schemaId}
- description: PolyAPI List environments
  method: GET
  name: listenvironments
  path: /environments
- description: PolyAPI Get an environment
  method: GET
  name: getenvironment
  path: /environments/{environmentId}
- description: PolyAPI List conversations
  method: GET
  name: listconversations
  path: /assistants/{slug}/conversations
- description: PolyAPI Create a conversation
  method: POST
  name: createconversation
  path: /assistants/{slug}/conversations
- description: PolyAPI Get a conversation
  method: GET
  name: getconversation
  path: /assistants/{slug}/conversations/{conversationSlug}
- description: PolyAPI Delete a conversation
  method: DELETE
  name: deleteconversation
  path: /assistants/{slug}/conversations/{conversationSlug}
personas: []
provider_name: PolyAPI
provider_slug: polyapi
search_terms:
- polyapi list conversations
- polyapi update an api function
- polyapi get a server function
- polyapi create a server function
- polyapi list jobs
- api
- getvariable
- polyapi delete a job
- deleteschema
- listvariables
- deleteserverfunction
- polyapi list client functions
- executeapifunction
- getapifunction
- deleteapifunction
- polyapi delete a schema
- executeserverfunction
- polyapi create a variable
- getschema
- updateclientfunction
- listconversations
- integrations
- polyapi get an api function
- deletevariable
- updateschema
- middleware
- polyapi get a job
- getenvironment
- polyapi list webhooks
- deletetrigger
- deleteconversation
- listapifunctions
- updatejob
- polyapi get a conversation
- polyapi delete an api function
- polyapi delete a trigger
- gettrigger
- createvariable
- pro-code api composition
- getconversation
- polyapi create a trigger
- createtrigger
- listenvironments
- getclientfunction
- createconversation
- polyapi delete a webhook
- polyapi list schemas
- listclientfunctions
- polyapi update a schema
- polyapi delete a client function
- createjob
- listserverfunctions
- triggerwebhook
- polyapi delete a conversation
- polyapi update a server function
- polyapi create a webhook
- polyapi get a webhook
- polyapi update a variable
- updatewebhook
- polyapi create a schema
- polyapi get a variable
- createserverfunction
- polyapi get a trigger
- polyapi list environments
- listschemas
- deletejob
- polyapi update a webhook
- getserverfunction
- polyapi create a conversation
- updatetrigger
- microservices
- polyapi delete a server function
- polyapi trigger a webhook
- orchestrations
- getwebhook
- listtriggers
- updateserverfunction
- polyapi list variables
- polyapi update a client function
- polyapi list triggers
- polyapi get a schema
- polyapi execute a server function
- createclientfunction
- updatevariable
- polyapi get an environment
- polyapi execute an api function
- listjobs
- createwebhook
- polyapi update a job
- polyapi
- polyapi get a client function
- polyapi delete a variable
- createschema
- updateapifunction
- polyapi create a client function
- createapifunction
- polyapi create an api function
- polyapi list server functions
- getjob
- polyapi update a trigger
- listwebhooks
- deletewebhook
- deleteclientfunction
- polyapi create a job
- polyapi list api functions
slug: polyapi-capability
source_filename: polyapi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PolyAPI Platform API\n  description: PolyAPI is a modern enterprise middleware platform that provides a unified REST API for managing cloud service\n    resources including functions, variables, webhooks, triggers, jobs, schemas, and environments. Built using AI and Kubernetes-native\n    technology, it accelerates development and simplifies the operation of integrations, orchestrations, and microservices.\n  tags:\n  - Polyapi\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: polyapi\n    baseUri: https://na1.polyapi.io\n    description: PolyAPI Platform API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{POLYAPI_TOKEN}}'\n    resources:\n    - name: functions-api\n      path: /functions/api\n      operations:\n      - name: listapifunctions\n        method: GET\n        description: PolyAPI List API functions\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapifunction\n        method: POST\n        description: PolyAPI Create an API function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-api-functionid\n      path: /functions/api/{functionId}\n      operations:\n      - name: getapifunction\n        method: GET\n        description: PolyAPI Get an API function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapifunction\n        method: PATCH\n        description: PolyAPI Update an API function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapifunction\n        method: DELETE\n        description: PolyAPI Delete an API function\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-api-functionid-execute\n      path: /functions/api/{functionId}/execute\n      operations:\n      - name: executeapifunction\n        method: POST\n        description: PolyAPI Execute an API function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-server\n      path: /functions/server\n      operations:\n      - name: listserverfunctions\n        method: GET\n        description: PolyAPI List server functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createserverfunction\n        method: POST\n        description: PolyAPI Create a server function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: functions-server-functionid\n      path: /functions/server/{functionId}\n      operations:\n      - name: getserverfunction\n        method: GET\n        description: PolyAPI Get a server function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateserverfunction\n        method: PATCH\n        description: PolyAPI Update a server function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteserverfunction\n        method: DELETE\n        description: PolyAPI Delete a server function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-server-functionid-execute\n      path: /functions/server/{functionId}/execute\n      operations:\n      - name: executeserverfunction\n\
  \        method: POST\n        description: PolyAPI Execute a server function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-client\n      path: /functions/client\n      operations:\n      - name: listclientfunctions\n        method: GET\n        description: PolyAPI List client functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createclientfunction\n        method: POST\n        description: PolyAPI Create a client function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions-client-functionid\n      path: /functions/client/{functionId}\n      operations:\n      - name: getclientfunction\n        method: GET\n        description: PolyAPI Get a client function\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateclientfunction\n        method: PATCH\n        description: PolyAPI Update a client function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteclientfunction\n        method: DELETE\n        description: PolyAPI Delete a client function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      operations:\n      - name: listwebhooks\n        method: GET\n        description: PolyAPI List webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createwebhook\n        method: POST\n        description: PolyAPI Create a webhook\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-webhookid\n      path: /webhooks/{webhookId}\n      operations:\n      - name: getwebhook\n        method: GET\n        description: PolyAPI Get a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatewebhook\n        method: PATCH\n        description: PolyAPI Update a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletewebhook\n        method: DELETE\n        description: PolyAPI Delete a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-webhookid-trigger\n      path: /webhooks/{webhookId}/trigger\n      operations:\n      - name: triggerwebhook\n        method: POST\n\
  \        description: PolyAPI Trigger a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variables\n      path: /variables\n      operations:\n      - name: listvariables\n        method: GET\n        description: PolyAPI List variables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvariable\n        method: POST\n        description: PolyAPI Create a variable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variables-variableid\n      path: /variables/{variableId}\n      operations:\n      - name: getvariable\n        method: GET\n        description: PolyAPI Get a variable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: updatevariable\n        method: PATCH\n        description: PolyAPI Update a variable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletevariable\n        method: DELETE\n        description: PolyAPI Delete a variable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: triggers\n      path: /triggers\n      operations:\n      - name: listtriggers\n        method: GET\n        description: PolyAPI List triggers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtrigger\n        method: POST\n        description: PolyAPI Create a trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: triggers-triggerid\n\
  \      path: /triggers/{triggerId}\n      operations:\n      - name: gettrigger\n        method: GET\n        description: PolyAPI Get a trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetrigger\n        method: PATCH\n        description: PolyAPI Update a trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetrigger\n        method: DELETE\n        description: PolyAPI Delete a trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      operations:\n      - name: listjobs\n        method: GET\n        description: PolyAPI List jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n     \
  \ - name: createjob\n        method: POST\n        description: PolyAPI Create a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobid\n      path: /jobs/{jobId}\n      operations:\n      - name: getjob\n        method: GET\n        description: PolyAPI Get a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatejob\n        method: PATCH\n        description: PolyAPI Update a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletejob\n        method: DELETE\n        description: PolyAPI Delete a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schemas\n      path: /schemas\n      operations:\n      -\
  \ name: listschemas\n        method: GET\n        description: PolyAPI List schemas\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createschema\n        method: POST\n        description: PolyAPI Create a schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schemas-schemaid\n      path: /schemas/{schemaId}\n      operations:\n      - name: getschema\n        method: GET\n        description: PolyAPI Get a schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateschema\n        method: PATCH\n        description: PolyAPI Update a schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteschema\n        method:\
  \ DELETE\n        description: PolyAPI Delete a schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments\n      path: /environments\n      operations:\n      - name: listenvironments\n        method: GET\n        description: PolyAPI List environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid\n      path: /environments/{environmentId}\n      operations:\n      - name: getenvironment\n        method: GET\n        description: PolyAPI Get an environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assistants-slug-conversations\n      path: /assistants/{slug}/conversations\n      operations:\n      - name: listconversations\n        method: GET\n        description: PolyAPI\
  \ List conversations\n        inputParameters:\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: The assistant slug identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconversation\n        method: POST\n        description: PolyAPI Create a conversation\n        inputParameters:\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: The assistant slug identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assistants-slug-conversations-conversationslug\n      path: /assistants/{slug}/conversations/{conversationSlug}\n      operations:\n      - name: getconversation\n        method: GET\n        description: PolyAPI Get a conversation\n        inputParameters:\n\
  \        - name: slug\n          in: path\n          type: string\n          required: true\n          description: The assistant slug identifier.\n        - name: conversationSlug\n          in: path\n          type: string\n          required: true\n          description: The conversation slug identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteconversation\n        method: DELETE\n        description: PolyAPI Delete a conversation\n        inputParameters:\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: The assistant slug identifier.\n        - name: conversationSlug\n          in: path\n          type: string\n          required: true\n          description: The conversation slug identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: polyapi-rest\n    description: REST adapter for PolyAPI Platform API.\n    resources:\n    - path: /functions/api\n      name: listapifunctions\n      operations:\n      - method: GET\n        name: listapifunctions\n        description: PolyAPI List API functions\n        call: polyapi.listapifunctions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/api\n      name: createapifunction\n      operations:\n      - method: POST\n        name: createapifunction\n        description: PolyAPI Create an API function\n        call: polyapi.createapifunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/api/{functionId}\n      name: getapifunction\n      operations:\n      - method: GET\n        name: getapifunction\n        description: PolyAPI Get an API function\n        call: polyapi.getapifunction\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /functions/api/{functionId}\n      name: updateapifunction\n      operations:\n      - method: PATCH\n        name: updateapifunction\n        description: PolyAPI Update an API function\n        call: polyapi.updateapifunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/api/{functionId}\n      name: deleteapifunction\n      operations:\n      - method: DELETE\n        name: deleteapifunction\n        description: PolyAPI Delete an API function\n        call: polyapi.deleteapifunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/api/{functionId}/execute\n      name: executeapifunction\n      operations:\n      - method: POST\n        name: executeapifunction\n        description: PolyAPI Execute an API function\n        call: polyapi.executeapifunction\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /functions/server\n      name: listserverfunctions\n      operations:\n      - method: GET\n        name: listserverfunctions\n        description: PolyAPI List server functions\n        call: polyapi.listserverfunctions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/server\n      name: createserverfunction\n      operations:\n      - method: POST\n        name: createserverfunction\n        description: PolyAPI Create a server function\n        call: polyapi.createserverfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/server/{functionId}\n      name: getserverfunction\n      operations:\n      - method: GET\n        name: getserverfunction\n        description: PolyAPI Get a server function\n        call: polyapi.getserverfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/server/{functionId}\n      name:\
  \ updateserverfunction\n      operations:\n      - method: PATCH\n        name: updateserverfunction\n        description: PolyAPI Update a server function\n        call: polyapi.updateserverfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/server/{functionId}\n      name: deleteserverfunction\n      operations:\n      - method: DELETE\n        name: deleteserverfunction\n        description: PolyAPI Delete a server function\n        call: polyapi.deleteserverfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/server/{functionId}/execute\n      name: executeserverfunction\n      operations:\n      - method: POST\n        name: executeserverfunction\n        description: PolyAPI Execute a server function\n        call: polyapi.executeserverfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/client\n      name: listclientfunctions\n\
  \      operations:\n      - method: GET\n        name: listclientfunctions\n        description: PolyAPI List client functions\n        call: polyapi.listclientfunctions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/client\n      name: createclientfunction\n      operations:\n      - method: POST\n        name: createclientfunction\n        description: PolyAPI Create a client function\n        call: polyapi.createclientfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/client/{functionId}\n      name: getclientfunction\n      operations:\n      - method: GET\n        name: getclientfunction\n        description: PolyAPI Get a client function\n        call: polyapi.getclientfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/client/{functionId}\n      name: updateclientfunction\n      operations:\n      - method: PATCH\n    \
  \    name: updateclientfunction\n        description: PolyAPI Update a client function\n        call: polyapi.updateclientfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /functions/client/{functionId}\n      name: deleteclientfunction\n      operations:\n      - method: DELETE\n        name: deleteclientfunction\n        description: PolyAPI Delete a client function\n        call: polyapi.deleteclientfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: listwebhooks\n      operations:\n      - method: GET\n        name: listwebhooks\n        description: PolyAPI List webhooks\n        call: polyapi.listwebhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: createwebhook\n      operations:\n      - method: POST\n        name: createwebhook\n        description: PolyAPI Create a webhook\n        call: polyapi.createwebhook\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{webhookId}\n      name: getwebhook\n      operations:\n      - method: GET\n        name: getwebhook\n        description: PolyAPI Get a webhook\n        call: polyapi.getwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{webhookId}\n      name: updatewebhook\n      operations:\n      - method: PATCH\n        name: updatewebhook\n        description: PolyAPI Update a webhook\n        call: polyapi.updatewebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{webhookId}\n      name: deletewebhook\n      operations:\n      - method: DELETE\n        name: deletewebhook\n        description: PolyAPI Delete a webhook\n        call: polyapi.deletewebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{webhookId}/trigger\n      name: triggerwebhook\n\
  \      operations:\n      - method: POST\n        name: triggerwebhook\n        description: PolyAPI Trigger a webhook\n        call: polyapi.triggerwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /variables\n      name: listvariables\n      operations:\n      - method: GET\n        name: listvariables\n        description: PolyAPI List variables\n        call: polyapi.listvariables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /variables\n      name: createvariable\n      operations:\n      - method: POST\n        name: createvariable\n        description: PolyAPI Create a variable\n        call: polyapi.createvariable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /variables/{variableId}\n      name: getvariable\n      operations:\n      - method: GET\n        name: getvariable\n        description: PolyAPI Get a variable\n        call: polyapi.getvariable\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /variables/{variableId}\n      name: updatevariable\n      operations:\n      - method: PATCH\n        name: updatevariable\n        description: PolyAPI Update a variable\n        call: polyapi.updatevariable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /variables/{variableId}\n      name: deletevariable\n      operations:\n      - method: DELETE\n        name: deletevariable\n        description: PolyAPI Delete a variable\n        call: polyapi.deletevariable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /triggers\n      name: listtriggers\n      operations:\n      - method: GET\n        name: listtriggers\n        description: PolyAPI List triggers\n        call: polyapi.listtriggers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /triggers\n      name: createtrigger\n      operations:\n\
  \      - method: POST\n        name: createtrigger\n        description: PolyAPI Create a trigger\n        call: polyapi.createtrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /triggers/{triggerId}\n      name: gettrigger\n      operations:\n      - method: GET\n        name: gettrigger\n        description: PolyAPI Get a trigger\n        call: polyapi.gettrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /triggers/{triggerId}\n      name: updatetrigger\n      operations:\n      - method: PATCH\n        name: updatetrigger\n        description: PolyAPI Update a trigger\n        call: polyapi.updatetrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /triggers/{triggerId}\n      name: deletetrigger\n      operations:\n      - method: DELETE\n        name: deletetrigger\n        description: PolyAPI Delete a trigger\n        call: polyapi.deletetrigger\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: PolyAPI List jobs\n        call: polyapi.listjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs\n      name: createjob\n      operations:\n      - method: POST\n        name: createjob\n        description: PolyAPI Create a job\n        call: polyapi.createjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobId}\n      name: getjob\n      operations:\n      - method: GET\n        name: getjob\n        description: PolyAPI Get a job\n        call: polyapi.getjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobId}\n      name: updatejob\n      operations:\n      - method: PATCH\n        name: updatejob\n        description: PolyAPI Update a job\n     \
  \   call: polyapi.updatejob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{jobId}\n      name: deletejob\n      operations:\n      - method: DELETE\n        name: deletejob\n        description: PolyAPI Delete a job\n        call: polyapi.deletejob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schemas\n      name: listschemas\n      operations:\n      - method: GET\n        name: listschemas\n        description: PolyAPI List schemas\n        call: polyapi.listschemas\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schemas\n      name: createschema\n      operations:\n      - method: POST\n        name: createschema\n        description: PolyAPI Create a schema\n        call: polyapi.createschema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schemas/{schemaId}\n      name: getschema\n      operations:\n      - method:\
  \ GET\n        name: getschema\n        description: PolyAPI Get a schema\n        call: polyapi.getschema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schemas/{schemaId}\n      name: updateschema\n      operations:\n      - method: PATCH\n        name: updateschema\n        description: PolyAPI Update a schema\n        call: polyapi.updateschema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schemas/{schemaId}\n      name: deleteschema\n      operations:\n      - method: DELETE\n        name: deleteschema\n        description: PolyAPI Delete a schema\n        call: polyapi.deleteschema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments\n      name: listenvironments\n      operations:\n      - method: GET\n        name: listenvironments\n        description: PolyAPI List environments\n        call: polyapi.listenvironments\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /environments/{environmentId}\n      name: getenvironment\n      operations:\n      - method: GET\n        name: getenvironment\n        description: PolyAPI Get an environment\n        call: polyapi.getenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assistants/{slug}/conversations\n      name: listconversations\n      operations:\n      - method: GET\n        name: listconversations\n        description: PolyAPI List conversations\n        call: polyapi.listconversations\n        with:\n          slug: rest.slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assistants/{slug}/conversations\n      name: createconversation\n      operations:\n      - method: POST\n        name: createconversation\n        description: PolyAPI Create a conversation\n        call: polyapi.createconversation\n        with:\n          slug: rest.slug\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assistants/{slug}/conversations/{conversationSlug}\n      name: getconversation\n      operations:\n      - method: GET\n        name: getconversation\n        description: PolyAPI Get a conversation\n        call: polyapi.getconversation\n        with:\n          slug: rest.slug\n          conversationSlug: rest.conversationSlug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assistants/{slug}/conversations/{conversationSlug}\n      name: deleteconversation\n      operations:\n      - method: DELETE\n        name: deleteconversation\n        description: PolyAPI Delete a conversation\n        call: polyapi.deleteconversation\n        with:\n          slug: rest.slug\n          conversationSlug: rest.conversationSlug\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: polyapi-mcp\n    transport: http\n\
  \    description: MCP adapter for PolyAPI Platform API for AI agent use.\n    tools:\n    - name: listapifunctions\n      description: PolyAPI List API functions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: polyapi.listapifunctions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapifunction\n      description: PolyAPI Create an API function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: polyapi.createapifunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapifunction\n      description: PolyAPI Get an API function\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: polyapi.getapifunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapifunction\n      description: PolyAPI Update an API function\n \
  \     hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: polyapi.updateapifunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapifunction\n      description: PolyAPI Delete an API function\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: polyapi.deleteapifunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executeapifunction\n      description: PolyAPI Execute an API function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: polyapi.executeapifunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listserverfunctions\n      description: PolyAPI List server functions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: polyapi.listserverfunctions\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createserverfunction\n      description: PolyAPI Create a server function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: polyapi.createserverfunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getserverfunction\n      description: PolyAPI Get a server function\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: polyapi.getserverfunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateserverfunction\n      description: PolyAPI Update a server function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: polyapi.updateserverfunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteserverfunction\n      description: PolyAPI Delete a server function\n      hints:\n\
  \        readOnly: false\n        destructive: true\n        idempotent: true\n      call: polyapi.deleteserverfunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executeserverfunction\n      description: PolyAPI Execute a server function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: polyapi.executeserverfunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclientfunctions\n      description: PolyAPI List client functions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: polyapi.listclientfunctions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createclientfunction\n      description: PolyAPI Create a client function\n      hints:\n        readOnly: false\n        destruc\n\n# --- truncated at 32 KB (42 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/polyapi/refs/heads/main/capabilities/polyapi-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/polyapi/refs/heads/main/capabilities/polyapi-capability.yaml
tags:
- Polyapi
- API
tools:
- description: PolyAPI List API functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapifunctions
- description: PolyAPI Create an API function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapifunction
- description: PolyAPI Get an API function
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapifunction
- description: PolyAPI Update an API function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapifunction
- description: PolyAPI Delete an API function
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapifunction
- description: PolyAPI Execute an API function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executeapifunction
- description: PolyAPI List server functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listserverfunctions
- description: PolyAPI Create a server function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createserverfunction
- description: PolyAPI Get a server function
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserverfunction
- description: PolyAPI Update a server function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateserverfunction
- description: PolyAPI Delete a server function
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteserverfunction
- description: PolyAPI Execute a server function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executeserverfunction
- description: PolyAPI List client functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclientfunctions
- description: PolyAPI Create a client function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createclientfunction
- description: PolyAPI Get a client function
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclientfunction
- description: PolyAPI Update a client function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateclientfunction
- description: PolyAPI Delete a client function
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteclientfunction
- description: PolyAPI List webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebhooks
- description: PolyAPI Create a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhook
- description: PolyAPI Get a webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhook
- description: PolyAPI Update a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatewebhook
- description: PolyAPI Delete a webhook
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewebhook
- description: PolyAPI Trigger a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: triggerwebhook
- description: PolyAPI List variables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvariables
- description: PolyAPI Create a variable
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvariable
- description: PolyAPI Get a variable
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvariable
- description: PolyAPI Update a variable
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatevariable
- description: PolyAPI Delete a variable
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletevariable
- description: PolyAPI List triggers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtriggers
- description: PolyAPI Create a trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtrigger
- description: PolyAPI Get a trigger
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettrigger
- description: PolyAPI Update a trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetrigger
- description: PolyAPI Delete a trigger
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetrigger
- description: PolyAPI List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: PolyAPI Create a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createjob
- description: PolyAPI Get a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: PolyAPI Update a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatejob
- description: PolyAPI Delete a job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejob
- description: PolyAPI List schemas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschemas
- description: PolyAPI Create a schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createschema
- description: PolyAPI Get a schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getschema
- description: PolyAPI Update a schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateschema
- description: PolyAPI Delete a schema
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteschema
- description: PolyAPI List environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenvironments
- description: PolyAPI Get an environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: PolyAPI List conversations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconversations
- description: PolyAPI Create a conversation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconversation
- description: PolyAPI Get a conversation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconversation
- description: PolyAPI Delete a conversation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconversation
---
