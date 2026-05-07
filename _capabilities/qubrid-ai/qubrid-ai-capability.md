---
categories: []
consumed_apis: []
description: The Qubrid AI Compute API provides programmatic access to GPU cloud infrastructure including NVIDIA H100, H200, and B200 accelerators. Developers can provision and manage GPU instances for AI and machine learning workloads through API calls. The service supports on-demand compute for training, fine-tuning, and batch inference jobs, with usage-based billing and enterprise features such as team collaboration and usage tracking. Instances can be accessed via SSH, Jupyter notebooks, or Visual Studio Code, and support quick-deploy templates for popular frameworks including PyTorch, TensorFlow, Comf
layout: capability
name: Qubrid AI Compute API
operations:
- description: List compute instances
  method: GET
  name: listinstances
  path: /instances
- description: Create a compute instance
  method: POST
  name: createinstance
  path: /instances
- description: Retrieve a compute instance
  method: GET
  name: getinstance
  path: /instances/{instance_id}
- description: Terminate a compute instance
  method: DELETE
  name: deleteinstance
  path: /instances/{instance_id}
- description: Start a compute instance
  method: POST
  name: startinstance
  path: /instances/{instance_id}/start
- description: Stop a compute instance
  method: POST
  name: stopinstance
  path: /instances/{instance_id}/stop
- description: List available GPU types
  method: GET
  name: listgputypes
  path: /gpus
- description: List available templates
  method: GET
  name: listtemplates
  path: /templates
- description: List SSH keys
  method: GET
  name: listsshkeys
  path: /ssh-keys
- description: Add an SSH key
  method: POST
  name: createsshkey
  path: /ssh-keys
- description: Remove an SSH key
  method: DELETE
  name: deletesshkey
  path: /ssh-keys/{key_id}
personas: []
provider_name: Qubrid AI
provider_slug: qubrid-ai
search_terms:
- createinstance
- stop a compute instance
- ai
- api
- remove an ssh key
- qubrid
- deleteinstance
- artificial intelligence
- list available gpu types
- list available templates
- cloud computing
- getinstance
- list ssh keys
- machine learning
- serverless
- nvidia
- listsshkeys
- start a compute instance
- inference
- listgputypes
- stopinstance
- terminate a compute instance
- large language models
- createsshkey
- deletesshkey
- list compute instances
- listtemplates
- retrieve a compute instance
- create a compute instance
- listinstances
- gpu
- startinstance
- add an ssh key
slug: qubrid-ai-capability
source_filename: qubrid-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Qubrid AI Compute API\n  description: The Qubrid AI Compute API provides programmatic access to GPU cloud infrastructure including NVIDIA H100, H200,\n    and B200 accelerators. Developers can provision and manage GPU instances for AI and machine learning workloads through\n    API calls. The service supports on-demand compute for training, fine-tuning, and batch inference jobs, with usage-based\n    billing and enterprise features such as team collaboration and usage tracking. Instances can be accessed via SSH, Jupyter\n    notebooks, or Visual Studio Code, and support quick-deploy templates for popular frameworks including PyTorch, TensorFlow,\n    Comf\n  tags:\n  - Qubrid\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: qubrid-ai\n    baseUri: https://platform.qubrid.com/api/v1\n    description: Qubrid AI Compute API HTTP API.\n    authentication:\n      type:\
  \ bearer\n      token: '{{QUBRID_AI_TOKEN}}'\n    resources:\n    - name: instances\n      path: /instances\n      operations:\n      - name: listinstances\n        method: GET\n        description: List compute instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinstance\n        method: POST\n        description: Create a compute instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instance-id\n      path: /instances/{instance_id}\n      operations:\n      - name: getinstance\n        method: GET\n        description: Retrieve a compute instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstance\n        method: DELETE\n        description: Terminate a compute instance\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instance-id-start\n      path: /instances/{instance_id}/start\n      operations:\n      - name: startinstance\n        method: POST\n        description: Start a compute instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instance-id-stop\n      path: /instances/{instance_id}/stop\n      operations:\n      - name: stopinstance\n        method: POST\n        description: Stop a compute instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gpus\n      path: /gpus\n      operations:\n      - name: listgputypes\n        method: GET\n        description: List available GPU types\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: templates\n      path: /templates\n      operations:\n      - name: listtemplates\n        method: GET\n        description: List available templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ssh-keys\n      path: /ssh-keys\n      operations:\n      - name: listsshkeys\n        method: GET\n        description: List SSH keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsshkey\n        method: POST\n        description: Add an SSH key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ssh-keys-key-id\n      path: /ssh-keys/{key_id}\n      operations:\n      - name: deletesshkey\n        method: DELETE\n        description: Remove\
  \ an SSH key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: qubrid-ai-rest\n    description: REST adapter for Qubrid AI Compute API.\n    resources:\n    - path: /instances\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n        description: List compute instances\n        call: qubrid-ai.listinstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances\n      name: createinstance\n      operations:\n      - method: POST\n        name: createinstance\n        description: Create a compute instance\n        call: qubrid-ai.createinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instance_id}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description:\
  \ Retrieve a compute instance\n        call: qubrid-ai.getinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instance_id}\n      name: deleteinstance\n      operations:\n      - method: DELETE\n        name: deleteinstance\n        description: Terminate a compute instance\n        call: qubrid-ai.deleteinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instance_id}/start\n      name: startinstance\n      operations:\n      - method: POST\n        name: startinstance\n        description: Start a compute instance\n        call: qubrid-ai.startinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instance_id}/stop\n      name: stopinstance\n      operations:\n      - method: POST\n        name: stopinstance\n        description: Stop a compute instance\n        call: qubrid-ai.stopinstance\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /gpus\n      name: listgputypes\n      operations:\n      - method: GET\n        name: listgputypes\n        description: List available GPU types\n        call: qubrid-ai.listgputypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates\n      name: listtemplates\n      operations:\n      - method: GET\n        name: listtemplates\n        description: List available templates\n        call: qubrid-ai.listtemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ssh-keys\n      name: listsshkeys\n      operations:\n      - method: GET\n        name: listsshkeys\n        description: List SSH keys\n        call: qubrid-ai.listsshkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ssh-keys\n      name: createsshkey\n      operations:\n      - method: POST\n        name: createsshkey\n        description: Add\
  \ an SSH key\n        call: qubrid-ai.createsshkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ssh-keys/{key_id}\n      name: deletesshkey\n      operations:\n      - method: DELETE\n        name: deletesshkey\n        description: Remove an SSH key\n        call: qubrid-ai.deletesshkey\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: qubrid-ai-mcp\n    transport: http\n    description: MCP adapter for Qubrid AI Compute API for AI agent use.\n    tools:\n    - name: listinstances\n      description: List compute instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qubrid-ai.listinstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinstance\n      description: Create a compute instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: qubrid-ai.createinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstance\n      description: Retrieve a compute instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qubrid-ai.getinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinstance\n      description: Terminate a compute instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: qubrid-ai.deleteinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startinstance\n      description: Start a compute instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qubrid-ai.startinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopinstance\n      description: Stop a compute instance\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qubrid-ai.stopinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgputypes\n      description: List available GPU types\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qubrid-ai.listgputypes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtemplates\n      description: List available templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qubrid-ai.listtemplates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsshkeys\n      description: List SSH keys\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qubrid-ai.listsshkeys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ createsshkey\n      description: Add an SSH key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qubrid-ai.createsshkey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesshkey\n      description: Remove an SSH key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: qubrid-ai.deletesshkey\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    QUBRID_AI_TOKEN: QUBRID_AI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/qubrid-ai/refs/heads/main/capabilities/qubrid-ai-capability.yaml
tags:
- Qubrid
- Ai
- API
tools:
- description: List compute instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Create a compute instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinstance
- description: Retrieve a compute instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Terminate a compute instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstance
- description: Start a compute instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startinstance
- description: Stop a compute instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopinstance
- description: List available GPU types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgputypes
- description: List available templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtemplates
- description: List SSH keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsshkeys
- description: Add an SSH key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsshkey
- description: Remove an SSH key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesshkey
---
