---
categories: []
consumed_apis: []
description: REST API for the Jupyter Notebook server, providing access to notebook contents, kernels, kernel specs, sessions, and terminals. Used by clients to drive interactive computing workflows.
layout: capability
name: Jupyter Notebook Server REST API
operations:
- description: Get contents at a path
  method: GET
  name: getcontents
  path: /contents/{path}
- description: Save or upload contents at a path
  method: PUT
  name: savecontents
  path: /contents/{path}
- description: Rename or move contents
  method: PATCH
  name: renamecontents
  path: /contents/{path}
- description: Create a new file or directory
  method: POST
  name: createcontents
  path: /contents/{path}
- description: Delete contents at a path
  method: DELETE
  name: deletecontents
  path: /contents/{path}
- description: List checkpoints for a file
  method: GET
  name: listcheckpoints
  path: /contents/{path}/checkpoints
- description: Create a new checkpoint
  method: POST
  name: createcheckpoint
  path: /contents/{path}/checkpoints
- description: Restore a file to a checkpoint
  method: POST
  name: restorecheckpoint
  path: /contents/{path}/checkpoints/{checkpoint_id}
- description: Delete a checkpoint
  method: DELETE
  name: deletecheckpoint
  path: /contents/{path}/checkpoints/{checkpoint_id}
- description: List running kernels
  method: GET
  name: listkernels
  path: /kernels
- description: Start a new kernel
  method: POST
  name: startkernel
  path: /kernels
- description: Get kernel info
  method: GET
  name: getkernel
  path: /kernels/{kernel_id}
- description: Shut down a kernel
  method: DELETE
  name: shutdownkernel
  path: /kernels/{kernel_id}
- description: Interrupt a kernel
  method: POST
  name: interruptkernel
  path: /kernels/{kernel_id}/interrupt
- description: Restart a kernel
  method: POST
  name: restartkernel
  path: /kernels/{kernel_id}/restart
- description: List installed kernel specs
  method: GET
  name: listkernelspecs
  path: /kernelspecs
- description: List active sessions
  method: GET
  name: listsessions
  path: /sessions
- description: Create a new session
  method: POST
  name: createsession
  path: /sessions
- description: Get a session
  method: GET
  name: getsession
  path: /sessions/{session_id}
- description: Update a session
  method: PATCH
  name: updatesession
  path: /sessions/{session_id}
- description: Delete a session
  method: DELETE
  name: deletesession
  path: /sessions/{session_id}
- description: List active terminals
  method: GET
  name: listterminals
  path: /terminals
- description: Start a new terminal
  method: POST
  name: startterminal
  path: /terminals
- description: Get a terminal
  method: GET
  name: getterminal
  path: /terminals/{terminal_id}
- description: Stop a terminal
  method: DELETE
  name: stopterminal
  path: /terminals/{terminal_id}
personas: []
provider_name: Jupyter Notebooks
provider_slug: jupyter-notebooks
search_terms:
- interrupt a kernel
- get a session
- get contents at a path
- start a new terminal
- getkernel
- createcheckpoint
- rename or move contents
- getsession
- notebooks
- listkernels
- listkernelspecs
- listcheckpoints
- stop a terminal
- start a new kernel
- list running kernels
- get a terminal
- jupyter
- list active terminals
- save or upload contents at a path
- restartkernel
- list installed kernel specs
- deletecheckpoint
- getterminal
- stopterminal
- createcontents
- renamecontents
- listterminals
- list active sessions
- savecontents
- delete a checkpoint
- delete a session
- updatesession
- startterminal
- api
- interactive computing
- shutdownkernel
- deletecontents
- update a session
- interruptkernel
- python
- restore a file to a checkpoint
- getcontents
- listsessions
- restorecheckpoint
- createsession
- startkernel
- delete contents at a path
- create a new session
- create a new checkpoint
- create a new file or directory
- list checkpoints for a file
- shut down a kernel
- get kernel info
- deletesession
- data science
- restart a kernel
slug: jupyter-notebooks-capability
source_filename: jupyter-notebooks-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Jupyter Notebook Server REST API\n  description: REST API for the Jupyter Notebook server, providing access to notebook contents, kernels, kernel specs, sessions,\n    and terminals. Used by clients to drive interactive computing workflows.\n  tags:\n  - Jupyter\n  - Notebooks\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jupyter-notebooks\n    baseUri: http://localhost:8888/api\n    description: Jupyter Notebook Server REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{JUPYTER_NOTEBOOKS_TOKEN}}'\n    resources:\n    - name: contents-path\n      path: /contents/{path}\n      operations:\n      - name: getcontents\n        method: GET\n        description: Get contents at a path\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n        - name: format\n          in: query\n          type: string\n\
  \        - name: content\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: savecontents\n        method: PUT\n        description: Save or upload contents at a path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: renamecontents\n        method: PATCH\n        description: Rename or move contents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontents\n        method: POST\n        description: Create a new file or directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontents\n        method: DELETE\n        description: Delete contents at a path\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contents-path-checkpoints\n      path: /contents/{path}/checkpoints\n      operations:\n      - name: listcheckpoints\n        method: GET\n        description: List checkpoints for a file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcheckpoint\n        method: POST\n        description: Create a new checkpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contents-path-checkpoints-checkpoint-id\n      path: /contents/{path}/checkpoints/{checkpoint_id}\n      operations:\n      - name: restorecheckpoint\n        method: POST\n        description: Restore a file to a checkpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deletecheckpoint\n        method: DELETE\n        description: Delete a checkpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernels\n      path: /kernels\n      operations:\n      - name: listkernels\n        method: GET\n        description: List running kernels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: startkernel\n        method: POST\n        description: Start a new kernel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernels-kernel-id\n      path: /kernels/{kernel_id}\n      operations:\n      - name: getkernel\n        method: GET\n        description: Get kernel info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n      - name: shutdownkernel\n        method: DELETE\n        description: Shut down a kernel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernels-kernel-id-interrupt\n      path: /kernels/{kernel_id}/interrupt\n      operations:\n      - name: interruptkernel\n        method: POST\n        description: Interrupt a kernel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernels-kernel-id-restart\n      path: /kernels/{kernel_id}/restart\n      operations:\n      - name: restartkernel\n        method: POST\n        description: Restart a kernel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kernelspecs\n      path: /kernelspecs\n      operations:\n      - name: listkernelspecs\n\
  \        method: GET\n        description: List installed kernel specs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions\n      path: /sessions\n      operations:\n      - name: listsessions\n        method: GET\n        description: List active sessions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsession\n        method: POST\n        description: Create a new session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions-session-id\n      path: /sessions/{session_id}\n      operations:\n      - name: getsession\n        method: GET\n        description: Get a session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: updatesession\n        method: PATCH\n        description: Update a session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesession\n        method: DELETE\n        description: Delete a session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: terminals\n      path: /terminals\n      operations:\n      - name: listterminals\n        method: GET\n        description: List active terminals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: startterminal\n        method: POST\n        description: Start a new terminal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: terminals-terminal-id\n      path: /terminals/{terminal_id}\n\
  \      operations:\n      - name: getterminal\n        method: GET\n        description: Get a terminal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stopterminal\n        method: DELETE\n        description: Stop a terminal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jupyter-notebooks-rest\n    description: REST adapter for Jupyter Notebook Server REST API.\n    resources:\n    - path: /contents/{path}\n      name: getcontents\n      operations:\n      - method: GET\n        name: getcontents\n        description: Get contents at a path\n        call: jupyter-notebooks.getcontents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}\n      name: savecontents\n      operations:\n      - method: PUT\n\
  \        name: savecontents\n        description: Save or upload contents at a path\n        call: jupyter-notebooks.savecontents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}\n      name: renamecontents\n      operations:\n      - method: PATCH\n        name: renamecontents\n        description: Rename or move contents\n        call: jupyter-notebooks.renamecontents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}\n      name: createcontents\n      operations:\n      - method: POST\n        name: createcontents\n        description: Create a new file or directory\n        call: jupyter-notebooks.createcontents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}\n      name: deletecontents\n      operations:\n      - method: DELETE\n        name: deletecontents\n        description: Delete contents at a path\n        call:\
  \ jupyter-notebooks.deletecontents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}/checkpoints\n      name: listcheckpoints\n      operations:\n      - method: GET\n        name: listcheckpoints\n        description: List checkpoints for a file\n        call: jupyter-notebooks.listcheckpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}/checkpoints\n      name: createcheckpoint\n      operations:\n      - method: POST\n        name: createcheckpoint\n        description: Create a new checkpoint\n        call: jupyter-notebooks.createcheckpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}/checkpoints/{checkpoint_id}\n      name: restorecheckpoint\n      operations:\n      - method: POST\n        name: restorecheckpoint\n        description: Restore a file to a checkpoint\n        call: jupyter-notebooks.restorecheckpoint\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contents/{path}/checkpoints/{checkpoint_id}\n      name: deletecheckpoint\n      operations:\n      - method: DELETE\n        name: deletecheckpoint\n        description: Delete a checkpoint\n        call: jupyter-notebooks.deletecheckpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels\n      name: listkernels\n      operations:\n      - method: GET\n        name: listkernels\n        description: List running kernels\n        call: jupyter-notebooks.listkernels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels\n      name: startkernel\n      operations:\n      - method: POST\n        name: startkernel\n        description: Start a new kernel\n        call: jupyter-notebooks.startkernel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels/{kernel_id}\n      name:\
  \ getkernel\n      operations:\n      - method: GET\n        name: getkernel\n        description: Get kernel info\n        call: jupyter-notebooks.getkernel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels/{kernel_id}\n      name: shutdownkernel\n      operations:\n      - method: DELETE\n        name: shutdownkernel\n        description: Shut down a kernel\n        call: jupyter-notebooks.shutdownkernel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels/{kernel_id}/interrupt\n      name: interruptkernel\n      operations:\n      - method: POST\n        name: interruptkernel\n        description: Interrupt a kernel\n        call: jupyter-notebooks.interruptkernel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernels/{kernel_id}/restart\n      name: restartkernel\n      operations:\n      - method: POST\n        name: restartkernel\n        description:\
  \ Restart a kernel\n        call: jupyter-notebooks.restartkernel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kernelspecs\n      name: listkernelspecs\n      operations:\n      - method: GET\n        name: listkernelspecs\n        description: List installed kernel specs\n        call: jupyter-notebooks.listkernelspecs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sessions\n      name: listsessions\n      operations:\n      - method: GET\n        name: listsessions\n        description: List active sessions\n        call: jupyter-notebooks.listsessions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sessions\n      name: createsession\n      operations:\n      - method: POST\n        name: createsession\n        description: Create a new session\n        call: jupyter-notebooks.createsession\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /sessions/{session_id}\n      name: getsession\n      operations:\n      - method: GET\n        name: getsession\n        description: Get a session\n        call: jupyter-notebooks.getsession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sessions/{session_id}\n      name: updatesession\n      operations:\n      - method: PATCH\n        name: updatesession\n        description: Update a session\n        call: jupyter-notebooks.updatesession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sessions/{session_id}\n      name: deletesession\n      operations:\n      - method: DELETE\n        name: deletesession\n        description: Delete a session\n        call: jupyter-notebooks.deletesession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /terminals\n      name: listterminals\n      operations:\n      - method: GET\n        name: listterminals\n    \
  \    description: List active terminals\n        call: jupyter-notebooks.listterminals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /terminals\n      name: startterminal\n      operations:\n      - method: POST\n        name: startterminal\n        description: Start a new terminal\n        call: jupyter-notebooks.startterminal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /terminals/{terminal_id}\n      name: getterminal\n      operations:\n      - method: GET\n        name: getterminal\n        description: Get a terminal\n        call: jupyter-notebooks.getterminal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /terminals/{terminal_id}\n      name: stopterminal\n      operations:\n      - method: DELETE\n        name: stopterminal\n        description: Stop a terminal\n        call: jupyter-notebooks.stopterminal\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jupyter-notebooks-mcp\n    transport: http\n    description: MCP adapter for Jupyter Notebook Server REST API for AI agent use.\n    tools:\n    - name: getcontents\n      description: Get contents at a path\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebooks.getcontents\n      with:\n        type: tools.type\n        format: tools.format\n        content: tools.content\n      inputParameters:\n      - name: type\n        type: string\n        description: type\n      - name: format\n        type: string\n        description: format\n      - name: content\n        type: integer\n        description: content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: savecontents\n      description: Save or upload contents at a path\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n \
  \     call: jupyter-notebooks.savecontents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renamecontents\n      description: Rename or move contents\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.renamecontents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontents\n      description: Create a new file or directory\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.createcontents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontents\n      description: Delete contents at a path\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-notebooks.deletecontents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcheckpoints\n      description:\
  \ List checkpoints for a file\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebooks.listcheckpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcheckpoint\n      description: Create a new checkpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.createcheckpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restorecheckpoint\n      description: Restore a file to a checkpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.restorecheckpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecheckpoint\n      description: Delete a checkpoint\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-notebooks.deletecheckpoint\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listkernels\n      description: List running kernels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebooks.listkernels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startkernel\n      description: Start a new kernel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.startkernel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getkernel\n      description: Get kernel info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebooks.getkernel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: shutdownkernel\n      description: Shut down a kernel\n      hints:\n        readOnly: false\n        destructive: true\n\
  \        idempotent: true\n      call: jupyter-notebooks.shutdownkernel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: interruptkernel\n      description: Interrupt a kernel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.interruptkernel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restartkernel\n      description: Restart a kernel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.restartkernel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listkernelspecs\n      description: List installed kernel specs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebooks.listkernelspecs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsessions\n\
  \      description: List active sessions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebooks.listsessions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsession\n      description: Create a new session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.createsession\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsession\n      description: Get a session\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebooks.getsession\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesession\n      description: Update a session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.updatesession\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: deletesession\n      description: Delete a session\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-notebooks.deletesession\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listterminals\n      description: List active terminals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebooks.listterminals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startterminal\n      description: Start a new terminal\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebooks.startterminal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getterminal\n      description: Get a terminal\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: jupyter-notebooks.getterminal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopterminal\n      description: Stop a terminal\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-notebooks.stopterminal\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JUPYTER_NOTEBOOKS_TOKEN: JUPYTER_NOTEBOOKS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jupyter-notebooks/refs/heads/main/capabilities/jupyter-notebooks-capability.yaml
tags:
- Jupyter
- Notebooks
- API
tools:
- description: Get contents at a path
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontents
- description: Save or upload contents at a path
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: savecontents
- description: Rename or move contents
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renamecontents
- description: Create a new file or directory
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontents
- description: Delete contents at a path
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontents
- description: List checkpoints for a file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcheckpoints
- description: Create a new checkpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcheckpoint
- description: Restore a file to a checkpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restorecheckpoint
- description: Delete a checkpoint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecheckpoint
- description: List running kernels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkernels
- description: Start a new kernel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startkernel
- description: Get kernel info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkernel
- description: Shut down a kernel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: shutdownkernel
- description: Interrupt a kernel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: interruptkernel
- description: Restart a kernel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restartkernel
- description: List installed kernel specs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkernelspecs
- description: List active sessions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsessions
- description: Create a new session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsession
- description: Get a session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsession
- description: Update a session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesession
- description: Delete a session
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesession
- description: List active terminals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listterminals
- description: Start a new terminal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startterminal
- description: Get a terminal
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getterminal
- description: Stop a terminal
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stopterminal
---
