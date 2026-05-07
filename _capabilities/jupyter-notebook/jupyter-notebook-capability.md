---
categories: []
consumed_apis: []
description: 'REST API for the Jupyter Kernel Gateway, a web server that provides headless access to Jupyter kernels. The Kernel Gateway supports two modes: jupyter-websocket mode (default) which provides a Jupyter Notebook server-compatible API for kernel management, and notebook-http mode which maps notebook cells to HTTP endpoints. This spec covers the jupyter-websocket mode API.'
layout: capability
name: Jupyter Notebook Jupyter Kernel Gateway API
operations:
- description: Jupyter Notebook Get API info
  method: GET
  name: getapiinfo
  path: /api
- description: Jupyter Notebook List running kernels
  method: GET
  name: listkernels
  path: /api/kernels
- description: Jupyter Notebook Start a kernel
  method: POST
  name: startkernel
  path: /api/kernels
- description: Jupyter Notebook Get kernel information
  method: GET
  name: getkernel
  path: /api/kernels/{kernel_id}
- description: Jupyter Notebook Shut down a kernel
  method: DELETE
  name: shutdownkernel
  path: /api/kernels/{kernel_id}
- description: Jupyter Notebook Interrupt a kernel
  method: POST
  name: interruptkernel
  path: /api/kernels/{kernel_id}/interrupt
- description: Jupyter Notebook Restart a kernel
  method: POST
  name: restartkernel
  path: /api/kernels/{kernel_id}/restart
- description: Jupyter Notebook List kernel specifications
  method: GET
  name: listkernelspecs
  path: /api/kernelspecs
- description: Jupyter Notebook Get a kernel specification
  method: GET
  name: getkernelspec
  path: /api/kernelspecs/{kernel_name}
personas: []
provider_name: Jupyter Notebook
provider_slug: jupyter-notebook
search_terms:
- getkernelspec
- jupyter notebook shut down a kernel
- interruptkernel
- jupyter notebook get kernel information
- listkernelspecs
- jupyter notebook get api info
- jupyter notebook list kernel specifications
- api
- getkernel
- startkernel
- jupyter notebook interrupt a kernel
- machine learning
- data science
- notebook
- jupyter notebook get a kernel specification
- python
- listkernels
- notebooks
- shutdownkernel
- jupyter notebook start a kernel
- jupyter notebook list running kernels
- getapiinfo
- interactive computing
- restartkernel
- jupyter notebook restart a kernel
- jupyter
slug: jupyter-notebook-capability
source_filename: jupyter-notebook-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Jupyter Notebook Jupyter Kernel Gateway API\n  description: 'REST API for the Jupyter Kernel Gateway, a web server that provides headless access to Jupyter kernels. The\n    Kernel Gateway supports two modes: jupyter-websocket mode (default) which provides a Jupyter Notebook server-compatible\n    API for kernel management, and notebook-http mode which maps notebook cells to HTTP endpoints. This spec covers the jupyter-websocket\n    mode API.'\n  tags:\n  - Jupyter\n  - Notebook\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jupyter-notebook\n    baseUri: http://localhost:8888/api\n    description: Jupyter Notebook Jupyter Kernel Gateway API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{JUPYTER_NOTEBOOK_TOKEN}}'\n    resources:\n    - name: api\n      path: /api\n      operations:\n      - name: getapiinfo\n\
  \        method: GET\n        description: Jupyter Notebook Get API info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-kernels\n      path: /api/kernels\n      operations:\n      - name: listkernels\n        method: GET\n        description: Jupyter Notebook List running kernels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: startkernel\n        method: POST\n        description: Jupyter Notebook Start a kernel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-kernels-kernel-id\n      path: /api/kernels/{kernel_id}\n      operations:\n      - name: getkernel\n        method: GET\n        description: Jupyter Notebook Get kernel information\n        inputParameters:\n        - name: kernel_id\n          in:\
  \ path\n          type: string\n          required: true\n          description: Unique identifier for the kernel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: shutdownkernel\n        method: DELETE\n        description: Jupyter Notebook Shut down a kernel\n        inputParameters:\n        - name: kernel_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the kernel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-kernels-kernel-id-interrupt\n      path: /api/kernels/{kernel_id}/interrupt\n      operations:\n      - name: interruptkernel\n        method: POST\n        description: Jupyter Notebook Interrupt a kernel\n        inputParameters:\n        - name: kernel_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Unique identifier for the kernel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-kernels-kernel-id-restart\n      path: /api/kernels/{kernel_id}/restart\n      operations:\n      - name: restartkernel\n        method: POST\n        description: Jupyter Notebook Restart a kernel\n        inputParameters:\n        - name: kernel_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the kernel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-kernelspecs\n      path: /api/kernelspecs\n      operations:\n      - name: listkernelspecs\n        method: GET\n        description: Jupyter Notebook List kernel specifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: api-kernelspecs-kernel-name\n      path: /api/kernelspecs/{kernel_name}\n      operations:\n      - name: getkernelspec\n        method: GET\n        description: Jupyter Notebook Get a kernel specification\n        inputParameters:\n        - name: kernel_name\n          in: path\n          type: string\n          required: true\n          description: Name of the kernel specification.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jupyter-notebook-rest\n    description: REST adapter for Jupyter Notebook Jupyter Kernel Gateway API.\n    resources:\n    - path: /api\n      name: getapiinfo\n      operations:\n      - method: GET\n        name: getapiinfo\n        description: Jupyter Notebook Get API info\n        call: jupyter-notebook.getapiinfo\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /api/kernels\n      name: listkernels\n      operations:\n      - method: GET\n        name: listkernels\n        description: Jupyter Notebook List running kernels\n        call: jupyter-notebook.listkernels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/kernels\n      name: startkernel\n      operations:\n      - method: POST\n        name: startkernel\n        description: Jupyter Notebook Start a kernel\n        call: jupyter-notebook.startkernel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/kernels/{kernel_id}\n      name: getkernel\n      operations:\n      - method: GET\n        name: getkernel\n        description: Jupyter Notebook Get kernel information\n        call: jupyter-notebook.getkernel\n        with:\n          kernel_id: rest.kernel_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/kernels/{kernel_id}\n\
  \      name: shutdownkernel\n      operations:\n      - method: DELETE\n        name: shutdownkernel\n        description: Jupyter Notebook Shut down a kernel\n        call: jupyter-notebook.shutdownkernel\n        with:\n          kernel_id: rest.kernel_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/kernels/{kernel_id}/interrupt\n      name: interruptkernel\n      operations:\n      - method: POST\n        name: interruptkernel\n        description: Jupyter Notebook Interrupt a kernel\n        call: jupyter-notebook.interruptkernel\n        with:\n          kernel_id: rest.kernel_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/kernels/{kernel_id}/restart\n      name: restartkernel\n      operations:\n      - method: POST\n        name: restartkernel\n        description: Jupyter Notebook Restart a kernel\n        call: jupyter-notebook.restartkernel\n        with:\n          kernel_id: rest.kernel_id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/kernelspecs\n      name: listkernelspecs\n      operations:\n      - method: GET\n        name: listkernelspecs\n        description: Jupyter Notebook List kernel specifications\n        call: jupyter-notebook.listkernelspecs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/kernelspecs/{kernel_name}\n      name: getkernelspec\n      operations:\n      - method: GET\n        name: getkernelspec\n        description: Jupyter Notebook Get a kernel specification\n        call: jupyter-notebook.getkernelspec\n        with:\n          kernel_name: rest.kernel_name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jupyter-notebook-mcp\n    transport: http\n    description: MCP adapter for Jupyter Notebook Jupyter Kernel Gateway API for AI agent use.\n    tools:\n    - name: getapiinfo\n   \
  \   description: Jupyter Notebook Get API info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebook.getapiinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listkernels\n      description: Jupyter Notebook List running kernels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebook.listkernels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startkernel\n      description: Jupyter Notebook Start a kernel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebook.startkernel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getkernel\n      description: Jupyter Notebook Get kernel information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ jupyter-notebook.getkernel\n      with:\n        kernel_id: tools.kernel_id\n      inputParameters:\n      - name: kernel_id\n        type: string\n        description: Unique identifier for the kernel.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: shutdownkernel\n      description: Jupyter Notebook Shut down a kernel\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-notebook.shutdownkernel\n      with:\n        kernel_id: tools.kernel_id\n      inputParameters:\n      - name: kernel_id\n        type: string\n        description: Unique identifier for the kernel.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: interruptkernel\n      description: Jupyter Notebook Interrupt a kernel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebook.interruptkernel\n\
  \      with:\n        kernel_id: tools.kernel_id\n      inputParameters:\n      - name: kernel_id\n        type: string\n        description: Unique identifier for the kernel.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restartkernel\n      description: Jupyter Notebook Restart a kernel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-notebook.restartkernel\n      with:\n        kernel_id: tools.kernel_id\n      inputParameters:\n      - name: kernel_id\n        type: string\n        description: Unique identifier for the kernel.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listkernelspecs\n      description: Jupyter Notebook List kernel specifications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebook.listkernelspecs\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getkernelspec\n      description: Jupyter Notebook Get a kernel specification\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-notebook.getkernelspec\n      with:\n        kernel_name: tools.kernel_name\n      inputParameters:\n      - name: kernel_name\n        type: string\n        description: Name of the kernel specification.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JUPYTER_NOTEBOOK_TOKEN: JUPYTER_NOTEBOOK_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jupyter-notebook/refs/heads/main/capabilities/jupyter-notebook-capability.yaml
tags:
- Jupyter
- Notebook
- API
tools:
- description: Jupyter Notebook Get API info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapiinfo
- description: Jupyter Notebook List running kernels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkernels
- description: Jupyter Notebook Start a kernel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startkernel
- description: Jupyter Notebook Get kernel information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkernel
- description: Jupyter Notebook Shut down a kernel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: shutdownkernel
- description: Jupyter Notebook Interrupt a kernel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: interruptkernel
- description: Jupyter Notebook Restart a kernel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restartkernel
- description: Jupyter Notebook List kernel specifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkernelspecs
- description: Jupyter Notebook Get a kernel specification
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkernelspec
---
