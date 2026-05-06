---
categories:
- machine-learning
consumed_apis: []
description: Unified workflow capability for AI and HPC workloads on AMD Instinct GPUs — provision instances, deploy LLMs, monitor performance, and manage cloud credits. Designed for AI researchers, ML engineers, and HPC developers.
layout: capability
name: AMD AI GPU Computing
operations:
- description: List GPU instances.
  method: GET
  name: list-instances
  path: /v1/instances
- description: Create a GPU instance.
  method: POST
  name: create-instance
  path: /v1/instances
- description: List deployed AI models.
  method: GET
  name: list-models
  path: /v1/models
- description: Deploy an AI model.
  method: POST
  name: deploy-model
  path: /v1/models
personas: []
provider_name: Advanced Micro Devices
provider_slug: advanced-micro-devices
search_terms:
- deploy llm
- deploy model
- semiconductor
- list all amd instinct gpu compute instances in the developer cloud.
- amd
- terminate an amd gpu compute instance to stop billing and release resources.
- list gpu instances
- list deployed ai models.
- ai researcher
- check available amd developer cloud gpu credit balance and usage history.
- deploy a large language model on amd instinct gpus using vllm for high-throughput inference.
- engineer deploying and optimizing ml inference workloads on amd hardware
- ai
- unified workflow for ai and hpc workloads on amd instinct gpus
- cloud computing
- ai model deployment.
- terminate instance
- create gpu instance
- check the current status and configuration of an amd gpu compute instance.
- hpc
- list instances
- get real-time gpu utilization, memory usage, temperature, and power draw for an amd instance.
- machine learning
- list deployed models
- ml engineer
- gpu instance management.
- hpc developer
- launch an amd instinct gpu instance (mi300x, mi250, mi210) for ai training or hpc.
- list models
- developer running scientific simulations and hpc workloads with rocm
- check credit balance
- create a gpu instance.
- monitor gpu performance
- create instance
- gpu
- get gpu instance status
- deploy an ai model.
- list gpu instances.
- list ai models deployed and serving on amd instinct gpus.
- researcher training and evaluating large language models on amd gpu clusters
slug: ai-gpu-computing
source_filename: ai-gpu-computing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AMD AI GPU Computing\n  description: Unified workflow capability for AI and HPC workloads on AMD Instinct GPUs — provision instances, deploy LLMs,\n    monitor performance, and manage cloud credits. Designed for AI researchers, ML engineers, and HPC developers.\n  tags:\n  - AMD\n  - AI\n  - Cloud Computing\n  - GPU\n  - HPC\n  - Machine Learning\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMD_API_KEY: AMD_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amd-cloud\n    baseUri: https://api.developer.amd.com/v1\n    description: AMD Developer Cloud REST API.\n    authentication:\n      type: apiKey\n      header: X-API-Key\n      token: '{{AMD_API_KEY}}'\n    resources:\n    - name: instances\n      path: /instances\n      description: GPU compute instance management.\n      operations:\n      - name: list-instances\n        method: GET\n        description: List all GPU instances.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-instance\n        method: POST\n        description: Launch a new GPU instance.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance\n      path: /instances/{instanceId}\n      description: Individual GPU instance operations.\n      operations:\n      - name: get-instance\n        method: GET\n        description: Get GPU instance details.\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: Instance ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminate-instance\n        method: DELETE\n        description: Terminate a GPU instance.\n        inputParameters:\n\
  \        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: Instance ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance-metrics\n      path: /instances/{instanceId}/metrics\n      description: GPU instance performance metrics.\n      operations:\n      - name: get-instance-metrics\n        method: GET\n        description: Get GPU utilization and performance metrics.\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: Instance ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /models\n      description: AI model deployment and management.\n      operations:\n      - name: list-models\n        method: GET\n        description:\
  \ List deployed AI models.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-model\n        method: POST\n        description: Deploy an AI model for inference.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credits\n      path: /credits\n      description: Cloud credit balance.\n      operations:\n      - name: get-credits\n        method: GET\n        description: Get credit balance and usage.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amd-gpu-api\n    description: Unified REST API for AMD GPU compute management, AI model deployment, and monitoring.\n    resources:\n    - path: /v1/instances\n      name: instances\n      description: GPU instance management.\n\
  \      operations:\n      - method: GET\n        name: list-instances\n        description: List GPU instances.\n        call: amd-cloud.list-instances\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-instance\n        description: Create a GPU instance.\n        call: amd-cloud.create-instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description: AI model deployment.\n      operations:\n      - method: GET\n        name: list-models\n        description: List deployed AI models.\n        call: amd-cloud.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: deploy-model\n        description: Deploy an AI model.\n        call: amd-cloud.deploy-model\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace:\
  \ amd-gpu-mcp\n    transport: http\n    description: MCP server for AI-assisted AMD GPU computing — provision hardware, deploy models, and monitor performance.\n    tools:\n    - name: list-gpu-instances\n      description: List all AMD Instinct GPU compute instances in the developer cloud.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amd-cloud.list-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-gpu-instance\n      description: Launch an AMD Instinct GPU instance (MI300X, MI250, MI210) for AI training or HPC.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amd-cloud.create-instance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gpu-instance-status\n      description: Check the current status and configuration of an AMD GPU compute instance.\n      hints:\n        readOnly: true\n        openWorld: false\n    \
  \  call: amd-cloud.get-instance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: monitor-gpu-performance\n      description: Get real-time GPU utilization, memory usage, temperature, and power draw for an AMD instance.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: amd-cloud.get-instance-metrics\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-llm\n      description: Deploy a large language model on AMD Instinct GPUs using vLLM for high-throughput inference.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amd-cloud.deploy-model\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deployed-models\n      description: List AI models deployed and serving on AMD Instinct GPUs.\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: amd-cloud.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-credit-balance\n      description: Check available AMD Developer Cloud GPU credit balance and usage history.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: amd-cloud.get-credits\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminate-instance\n      description: Terminate an AMD GPU compute instance to stop billing and release resources.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amd-cloud.terminate-instance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/advanced-micro-devices/refs/heads/main/capabilities/ai-gpu-computing.yaml
tags:
- AMD
- AI
- Cloud Computing
- GPU
- HPC
- Machine Learning
tools:
- description: List all AMD Instinct GPU compute instances in the developer cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-gpu-instances
- description: Launch an AMD Instinct GPU instance (MI300X, MI250, MI210) for AI training or HPC.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-gpu-instance
- description: Check the current status and configuration of an AMD GPU compute instance.
  hints:
    openWorld: false
    readOnly: true
  name: get-gpu-instance-status
- description: Get real-time GPU utilization, memory usage, temperature, and power draw for an AMD instance.
  hints:
    openWorld: false
    readOnly: true
  name: monitor-gpu-performance
- description: Deploy a large language model on AMD Instinct GPUs using vLLM for high-throughput inference.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-llm
- description: List AI models deployed and serving on AMD Instinct GPUs.
  hints:
    openWorld: true
    readOnly: true
  name: list-deployed-models
- description: Check available AMD Developer Cloud GPU credit balance and usage history.
  hints:
    openWorld: false
    readOnly: true
  name: check-credit-balance
- description: Terminate an AMD GPU compute instance to stop billing and release resources.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminate-instance
---
