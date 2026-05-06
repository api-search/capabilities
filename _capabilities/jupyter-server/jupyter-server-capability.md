---
categories: []
consumed_apis: []
description: Core REST API for Jupyter Server, the backend that powers Jupyter Notebook, JupyterLab, and other Jupyter web applications. Provides endpoints for managing kernels, sessions, contents (notebooks and files), terminals, kernel specifications, configuration, and server status.
layout: capability
name: Jupyter Server REST API
operations:
- description: Jupyter Server Get API info
  method: GET
  name: getapiinfo
  path: /
- description: Jupyter Server Get current user
  method: GET
  name: getcurrentuser
  path: /me
- description: Jupyter Server Get server status
  method: GET
  name: getserverstatus
  path: /status
- description: Jupyter Server Get API specification
  method: GET
  name: getapispec
  path: /spec.yaml
- description: Jupyter Server Get contents
  method: GET
  name: getcontents
  path: /contents/{path}
- description: Jupyter Server Create contents
  method: POST
  name: createcontents
  path: /contents/{path}
- description: Jupyter Server Rename contents
  method: PATCH
  name: renamecontents
  path: /contents/{path}
- description: Jupyter Server Save contents
  method: PUT
  name: savecontents
  path: /contents/{path}
- description: Jupyter Server Delete contents
  method: DELETE
  name: deletecontents
  path: /contents/{path}
- description: Jupyter Server List checkpoints
  method: GET
  name: listcheckpoints
  path: /contents/{path}/checkpoints
- description: Jupyter Server Create checkpoint
  method: POST
  name: createcheckpoint
  path: /contents/{path}/checkpoints
- description: Jupyter Server Restore checkpoint
  method: POST
  name: restorecheckpoint
  path: /contents/{path}/checkpoints/{checkpoint_id}
- description: Jupyter Server Delete checkpoint
  method: DELETE
  name: deletecheckpoint
  path: /contents/{path}/checkpoints/{checkpoint_id}
- description: Jupyter Server List sessions
  method: GET
  name: listsessions
  path: /sessions
- description: Jupyter Server Create session
  method: POST
  name: createsession
  path: /sessions
- description: Jupyter Server Get session
  method: GET
  name: getsession
  path: /sessions/{session}
- description: Jupyter Server Update session
  method: PATCH
  name: updatesession
  path: /sessions/{session}
- description: Jupyter Server Delete session
  method: DELETE
  name: deletesession
  path: /sessions/{session}
- description: Jupyter Server List kernels
  method: GET
  name: listkernels
  path: /kernels
- description: Jupyter Server Start kernel
  method: POST
  name: startkernel
  path: /kernels
- description: Jupyter Server Get kernel
  method: GET
  name: getkernel
  path: /kernels/{kernel_id}
- description: Jupyter Server Shutdown kernel
  method: DELETE
  name: shutdownkernel
  path: /kernels/{kernel_id}
- description: Jupyter Server Interrupt kernel
  method: POST
  name: interruptkernel
  path: /kernels/{kernel_id}/interrupt
- description: Jupyter Server Restart kernel
  method: POST
  name: restartkernel
  path: /kernels/{kernel_id}/restart
- description: Jupyter Server List kernel specifications
  method: GET
  name: listkernelspecs
  path: /kernelspecs
- description: Jupyter Server Get config section
  method: GET
  name: getconfig
  path: /config/{section_name}
- description: Jupyter Server Update config section
  method: PATCH
  name: updateconfig
  path: /config/{section_name}
- description: Jupyter Server List terminals
  method: GET
  name: listterminals
  path: /terminals
- description: Jupyter Server Create terminal
  method: POST
  name: createterminal
  path: /terminals
- description: Jupyter Server Get terminal
  method: GET
  name: getterminal
  path: /terminals/{terminal_id}
- description: Jupyter Server Delete terminal
  method: DELETE
  name: deleteterminal
  path: /terminals/{terminal_id}
personas: []
provider_name: Jupyter Server
provider_slug: jupyter-server
search_terms:
- jupyter server list kernels
- getcurrentuser
- jupyter server get api info
- jupyter server list sessions
- createcheckpoint
- jupyter server get session
- jupyter server start kernel
- getkernel
- jupyter server list terminals
- getapispec
- jupyter server delete checkpoint
- getsession
- workbooks
- listkernels
- jupyter server restart kernel
- listkernelspecs
- listcheckpoints
- notebooks
- compute
- jupyter server list kernel specifications
- jupyter server restore checkpoint
- jupyter server rename contents
- jupyter server delete session
- jupyter
- jupyter server get api specification
- jupyter server list checkpoints
- restartkernel
- deletecheckpoint
- getterminal
- createcontents
- jupyter server create checkpoint
- renamecontents
- jupyter server delete contents
- jupyter server update config section
- listterminals
- jupyter server delete terminal
- deleteterminal
- getapiinfo
- jupyter server create terminal
- savecontents
- jupyter server get terminal
- jupyter server shutdown kernel
- updatesession
- api
- jupyter server get server status
- interactive computing
- jupyter server save contents
- shutdownkernel
- jupyter server get current user
- deletecontents
- createterminal
- interruptkernel
- getserverstatus
- getcontents
- listsessions
- kernels
- restorecheckpoint
- createsession
- startkernel
- jupyter server create contents
- jupyter server create session
- jupyter server update session
- updateconfig
- jupyter server interrupt kernel
- jupyter server get kernel
- jupyter server get config section
- server
- deletesession
- getconfig
- jupyter server get contents
- portable
slug: jupyter-server-capability
source_filename: jupyter-server-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Jupyter Server REST API\n  description: Core REST API for Jupyter Server, the backend that powers Jupyter Notebook, JupyterLab, and other Jupyter web\n    applications. Provides endpoints for managing kernels, sessions, contents (notebooks and files), terminals, kernel specifications,\n    configuration, and server status.\n  tags:\n  - Jupyter\n  - Server\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jupyter-server\n    baseUri: http://localhost:8888/api\n    description: Jupyter Server REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{JUPYTER_SERVER_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: getapiinfo\n        method: GET\n        description: Jupyter Server Get API info\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: me\n      path: /me\n      operations:\n      - name: getcurrentuser\n        method: GET\n        description: Jupyter Server Get current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status\n      path: /status\n      operations:\n      - name: getserverstatus\n        method: GET\n        description: Jupyter Server Get server status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spec-yaml\n      path: /spec.yaml\n      operations:\n      - name: getapispec\n        method: GET\n        description: Jupyter Server Get API specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contents-path\n      path: /contents/{path}\n    \
  \  operations:\n      - name: getcontents\n        method: GET\n        description: Jupyter Server Get contents\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        - name: type\n          in: query\n          type: string\n        - name: format\n          in: query\n          type: string\n        - name: content\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontents\n        method: POST\n        description: Jupyter Server Create contents\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: renamecontents\n        method: PATCH\n        description: Jupyter Server\
  \ Rename contents\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: savecontents\n        method: PUT\n        description: Jupyter Server Save contents\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontents\n        method: DELETE\n        description: Jupyter Server Delete contents\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contents-path-checkpoints\n\
  \      path: /contents/{path}/checkpoints\n      operations:\n      - name: listcheckpoints\n        method: GET\n        description: Jupyter Server List checkpoints\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcheckpoint\n        method: POST\n        description: Jupyter Server Create checkpoint\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contents-path-checkpoints-checkpoint-id\n      path: /contents/{path}/checkpoints/{checkpoint_id}\n      operations:\n      - name: restorecheckpoint\n        method: POST\n        description: Jupyter Server Restore checkpoint\n\
  \        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        - name: checkpoint_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecheckpoint\n        method: DELETE\n        description: Jupyter Server Delete checkpoint\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        - name: checkpoint_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions\n      path: /sessions\n      operations:\n      - name: listsessions\n        method: GET\n        description: Jupyter Server List sessions\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsession\n        method: POST\n        description: Jupyter Server Create session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions-session\n      path: /sessions/{session}\n      operations:\n      - name: getsession\n        method: GET\n        description: Jupyter Server Get session\n        inputParameters:\n        - name: session\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesession\n        method: PATCH\n        description: Jupyter Server Update session\n        inputParameters:\n        - name: session\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesession\n        method: DELETE\n        description: Jupyter Server Delete session\n        inputParameters:\n        - name: session\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernels\n      path: /kernels\n      operations:\n      - name: listkernels\n        method: GET\n        description: Jupyter Server List kernels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: startkernel\n        method: POST\n        description: Jupyter Server Start kernel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernels-kernel-id\n\
  \      path: /kernels/{kernel_id}\n      operations:\n      - name: getkernel\n        method: GET\n        description: Jupyter Server Get kernel\n        inputParameters:\n        - name: kernel_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: shutdownkernel\n        method: DELETE\n        description: Jupyter Server Shutdown kernel\n        inputParameters:\n        - name: kernel_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernels-kernel-id-interrupt\n      path: /kernels/{kernel_id}/interrupt\n      operations:\n      - name: interruptkernel\n        method: POST\n        description: Jupyter Server Interrupt kernel\n        inputParameters:\n       \
  \ - name: kernel_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernels-kernel-id-restart\n      path: /kernels/{kernel_id}/restart\n      operations:\n      - name: restartkernel\n        method: POST\n        description: Jupyter Server Restart kernel\n        inputParameters:\n        - name: kernel_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernelspecs\n      path: /kernelspecs\n      operations:\n      - name: listkernelspecs\n        method: GET\n        description: Jupyter Server List kernel specifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: config-section-name\n\
  \      path: /config/{section_name}\n      operations:\n      - name: getconfig\n        method: GET\n        description: Jupyter Server Get config section\n        inputParameters:\n        - name: section_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateconfig\n        method: PATCH\n        description: Jupyter Server Update config section\n        inputParameters:\n        - name: section_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: terminals\n      path: /terminals\n      operations:\n      - name: listterminals\n        method: GET\n        description: Jupyter Server List terminals\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createterminal\n        method: POST\n        description: Jupyter Server Create terminal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: terminals-terminal-id\n      path: /terminals/{terminal_id}\n      operations:\n      - name: getterminal\n        method: GET\n        description: Jupyter Server Get terminal\n        inputParameters:\n        - name: terminal_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteterminal\n        method: DELETE\n        description: Jupyter Server Delete terminal\n        inputParameters:\n        - name: terminal_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jupyter-server-rest\n    description: REST adapter for Jupyter Server REST API.\n    resources:\n    - path: /\n      name: getapiinfo\n      operations:\n      - method: GET\n        name: getapiinfo\n        description: Jupyter Server Get API info\n        call: jupyter-server.getapiinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /me\n      name: getcurrentuser\n      operations:\n      - method: GET\n        name: getcurrentuser\n        description: Jupyter Server Get current user\n        call: jupyter-server.getcurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /status\n      name: getserverstatus\n      operations:\n      - method: GET\n        name: getserverstatus\n        description: Jupyter Server Get server status\n     \
  \   call: jupyter-server.getserverstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spec.yaml\n      name: getapispec\n      operations:\n      - method: GET\n        name: getapispec\n        description: Jupyter Server Get API specification\n        call: jupyter-server.getapispec\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}\n      name: getcontents\n      operations:\n      - method: GET\n        name: getcontents\n        description: Jupyter Server Get contents\n        call: jupyter-server.getcontents\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}\n      name: createcontents\n      operations:\n      - method: POST\n        name: createcontents\n        description: Jupyter Server Create contents\n        call: jupyter-server.createcontents\n        with:\n          path: rest.path\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}\n      name: renamecontents\n      operations:\n      - method: PATCH\n        name: renamecontents\n        description: Jupyter Server Rename contents\n        call: jupyter-server.renamecontents\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}\n      name: savecontents\n      operations:\n      - method: PUT\n        name: savecontents\n        description: Jupyter Server Save contents\n        call: jupyter-server.savecontents\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}\n      name: deletecontents\n      operations:\n      - method: DELETE\n        name: deletecontents\n        description: Jupyter Server Delete contents\n        call: jupyter-server.deletecontents\n        with:\n  \
  \        path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}/checkpoints\n      name: listcheckpoints\n      operations:\n      - method: GET\n        name: listcheckpoints\n        description: Jupyter Server List checkpoints\n        call: jupyter-server.listcheckpoints\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}/checkpoints\n      name: createcheckpoint\n      operations:\n      - method: POST\n        name: createcheckpoint\n        description: Jupyter Server Create checkpoint\n        call: jupyter-server.createcheckpoint\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}/checkpoints/{checkpoint_id}\n      name: restorecheckpoint\n      operations:\n      - method: POST\n        name: restorecheckpoint\n        description:\
  \ Jupyter Server Restore checkpoint\n        call: jupyter-server.restorecheckpoint\n        with:\n          path: rest.path\n          checkpoint_id: rest.checkpoint_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}/checkpoints/{checkpoint_id}\n      name: deletecheckpoint\n      operations:\n      - method: DELETE\n        name: deletecheckpoint\n        description: Jupyter Server Delete checkpoint\n        call: jupyter-server.deletecheckpoint\n        with:\n          path: rest.path\n          checkpoint_id: rest.checkpoint_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sessions\n      name: listsessions\n      operations:\n      - method: GET\n        name: listsessions\n        description: Jupyter Server List sessions\n        call: jupyter-server.listsessions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sessions\n      name: createsession\n\
  \      operations:\n      - method: POST\n        name: createsession\n        description: Jupyter Server Create session\n        call: jupyter-server.createsession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sessions/{session}\n      name: getsession\n      operations:\n      - method: GET\n        name: getsession\n        description: Jupyter Server Get session\n        call: jupyter-server.getsession\n        with:\n          session: rest.session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sessions/{session}\n      name: updatesession\n      operations:\n      - method: PATCH\n        name: updatesession\n        description: Jupyter Server Update session\n        call: jupyter-server.updatesession\n        with:\n          session: rest.session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sessions/{session}\n      name: deletesession\n      operations:\n\
  \      - method: DELETE\n        name: deletesession\n        description: Jupyter Server Delete session\n        call: jupyter-server.deletesession\n        with:\n          session: rest.session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels\n      name: listkernels\n      operations:\n      - method: GET\n        name: listkernels\n        description: Jupyter Server List kernels\n        call: jupyter-server.listkernels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels\n      name: startkernel\n      operations:\n      - method: POST\n        name: startkernel\n        description: Jupyter Server Start kernel\n        call: jupyter-server.startkernel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels/{kernel_id}\n      name: getkernel\n      operations:\n      - method: GET\n        name: getkernel\n        description: Jupyter Server Get kernel\n\
  \        call: jupyter-server.getkernel\n        with:\n          kernel_id: rest.kernel_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels/{kernel_id}\n      name: shutdownkernel\n      operations:\n      - method: DELETE\n        name: shutdownkernel\n        description: Jupyter Server Shutdown kernel\n        call: jupyter-server.shutdownkernel\n        with:\n          kernel_id: rest.kernel_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels/{kernel_id}/interrupt\n      name: interruptkernel\n      operations:\n      - method: POST\n        name: interruptkernel\n        description: Jupyter Server Interrupt kernel\n        call: jupyter-server.interruptkernel\n        with:\n          kernel_id: rest.kernel_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels/{kernel_id}/restart\n      name: restartkernel\n      operations:\n      - method:\
  \ POST\n        name: restartkernel\n        description: Jupyter Server Restart kernel\n        call: jupyter-server.restartkernel\n        with:\n          kernel_id: rest.kernel_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernelspecs\n      name: listkernelspecs\n      operations:\n      - method: GET\n        name: listkernelspecs\n        description: Jupyter Server List kernel specifications\n        call: jupyter-server.listkernelspecs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /config/{section_name}\n      name: getconfig\n      operations:\n      - method: GET\n        name: getconfig\n        description: Jupyter Server Get config section\n        call: jupyter-server.getconfig\n        with:\n          section_name: rest.section_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /config/{section_name}\n      name: updateconfig\n      operations:\n\
  \      - method: PATCH\n        name: updateconfig\n        description: Jupyter Server Update config section\n        call: jupyter-server.updateconfig\n        with:\n          section_name: rest.section_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /terminals\n      name: listterminals\n      operations:\n      - method: GET\n        name: listterminals\n        description: Jupyter Server List terminals\n        call: jupyter-server.listterminals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /terminals\n      name: createterminal\n      operations:\n      - method: POST\n        name: createterminal\n        description: Jupyter Server Create terminal\n        call: jupyter-server.createterminal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /terminals/{terminal_id}\n      name: getterminal\n      operations:\n      - method: GET\n        name: getterminal\n\
  \        description: Jupyter Server Get terminal\n        call: jupyter-server.getterminal\n        with:\n          terminal_id: rest.terminal_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /terminals/{terminal_id}\n      name: deleteterminal\n      operations:\n      - method: DELETE\n        name: deleteterminal\n        description: Jupyter Server Delete terminal\n        call: jupyter-server.deleteterminal\n        with:\n          terminal_id: rest.terminal_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jupyter-server-mcp\n    transport: http\n    description: MCP adapter for Jupyter Server REST API for AI agent use.\n    tools:\n    - name: getapiinfo\n      description: Jupyter Server Get API info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.getapiinfo\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: getcurrentuser\n      description: Jupyter Server Get current user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.getcurrentuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getserverstatus\n      description: Jupyter Server Get server status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.getserverstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapispec\n      description: Jupyter Server Get API specification\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.getapispec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontents\n      description: Jupyter Server Get contents\n      hints:\n        readOnly: true\n  \
  \      destructive: false\n        idempotent: true\n      call: jupyter-server.getcontents\n      with:\n        path: tools.path\n        type: tools.type\n        format: tools.format\n        content: tools.content\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      - name: type\n        type: string\n        description: type\n      - name: format\n        type: string\n        description: format\n      - name: content\n        type: integer\n        description: content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontents\n      description: Jupyter Server Create contents\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-server.createcontents\n      with:\n        path: tools.path\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: renamecontents\n      description: Jupyter Server Rename contents\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-server.renamecontents\n      with:\n        path: tools.path\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: savecontents\n      description: Jupyter Server Save contents\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: jupyter-server.savecontents\n      with:\n        path: tools.path\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontents\n      description: Jupyter Server\
  \ Delete contents\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-server.deletecontents\n      with:\n        path: tools.path\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcheckpoints\n      description: Jupyter Server List checkpoints\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.listcheckpoints\n      with:\n        path: tools.path\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcheckpoint\n      description: Jupyter Server Create checkpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n   \
  \   call: jupyter-server.createcheckpoint\n      with:\n        path: tools.path\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restorecheckpoint\n      description: Jupyter Server Restore checkpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-server.restorecheckpoint\n      with:\n        path: tools.path\n        checkpoint_id: tools.checkpoint_id\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      - name: checkpoint_id\n        type: string\n        description: checkpoint_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecheckpoint\n      description: Jupyter Server Delete checkpoint\n      hints:\n        readOnly: false\n      \
  \  destructive: true\n        idempotent: true\n      call: jupyter-server.deletecheckpoint\n      with:\n        path: tools.path\n        checkpoint_id: tools.checkpoint_id\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      - name: checkpoint_id\n        type: string\n        description: checkpoint_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsessions\n      description: Jupyter Server List sessions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.listsessions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsession\n      description: Jupyter Server Create session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-server.createsession\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: getsession\n      description: Jupyter Server Get session\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.getsession\n      with:\n        session: tools.session\n      inputParameters:\n      - name: session\n        type: string\n        description: session\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesession\n      description: Jupyter Server Update session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-server.updatesession\n      with:\n        session: tools.session\n      inputParameters:\n      - name: session\n        type: string\n        description: session\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesession\n      description: Jupyter Server Delete session\n    \
  \  hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-server.deletesession\n      with:\n        session: tools.session\n      inputParameters:\n      - name: session\n        type: string\n        description: session\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listkernels\n      description: Jupyter Server List kernels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.listkernels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startkernel\n      description: Jupyter Server Start kernel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-server.startkernel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getkernel\n      description: Jupyter Server Get kernel\n      hints:\n \
  \       readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.getkernel\n      with:\n        kernel_id: tools.kernel_id\n      inputParameters:\n      - name: kernel_id\n        type: string\n        description: kernel_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: shutdownkernel\n      description: Jupyter Server Shutdown kernel\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-server.shutdownkernel\n      with:\n        kernel_id: tools.kernel_id\n      inputParameters:\n      - name: kernel_id\n        type: string\n        description: kernel_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: interruptkernel\n      description: Jupyter Server Interrupt kernel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ jupyter-server.interruptkernel\n      with:\n        kernel_id: tools.kernel_id\n      inputParameters:\n      - name: kernel_id\n        type: string\n        description: kernel_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restartkernel\n      description: Jupyter Server Restart kernel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-server.restartkernel\n      with:\n        kernel_id: tools.kernel_id\n      inputParameters:\n      - name: kernel_id\n        type: string\n        description: kernel_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listkernelspecs\n      description: Jupyter Server List kernel specifications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.listkernelspecs\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: getconfig\n      description: Jupyter Server Get config section\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-server.getconfig\n      with:\n        section_name: tools.section_name\n      inputParameters:\n      - name: section_name\n        type: string\n        description: section_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateconfig\n      description: Jupyter Server Update config section\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-server.updateconfig\n      with:\n        section_name: tools.section_name\n      inputParameters:\n      - name: section_name\n        type: string\n        description: section_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtermi\n\n# --- truncated\
  \ at 32 KB (33 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/jupyter-server/refs/heads/main/capabilities/jupyter-server-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jupyter-server/refs/heads/main/capabilities/jupyter-server-capability.yaml
tags:
- Jupyter
- Server
- API
tools:
- description: Jupyter Server Get API info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapiinfo
- description: Jupyter Server Get current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentuser
- description: Jupyter Server Get server status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserverstatus
- description: Jupyter Server Get API specification
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapispec
- description: Jupyter Server Get contents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontents
- description: Jupyter Server Create contents
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontents
- description: Jupyter Server Rename contents
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renamecontents
- description: Jupyter Server Save contents
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: savecontents
- description: Jupyter Server Delete contents
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontents
- description: Jupyter Server List checkpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcheckpoints
- description: Jupyter Server Create checkpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcheckpoint
- description: Jupyter Server Restore checkpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restorecheckpoint
- description: Jupyter Server Delete checkpoint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecheckpoint
- description: Jupyter Server List sessions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsessions
- description: Jupyter Server Create session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsession
- description: Jupyter Server Get session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsession
- description: Jupyter Server Update session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesession
- description: Jupyter Server Delete session
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesession
- description: Jupyter Server List kernels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkernels
- description: Jupyter Server Start kernel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startkernel
- description: Jupyter Server Get kernel
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkernel
- description: Jupyter Server Shutdown kernel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: shutdownkernel
- description: Jupyter Server Interrupt kernel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: interruptkernel
- description: Jupyter Server Restart kernel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restartkernel
- description: Jupyter Server List kernel specifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkernelspecs
- description: Jupyter Server Get config section
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfig
- description: Jupyter Server Update config section
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateconfig
- description: Jupyter Server List terminals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listterminals
- description: Jupyter Server Create terminal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createterminal
- description: Jupyter Server Get terminal
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getterminal
- description: Jupyter Server Delete terminal
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteterminal
---
