---
categories:
- machine-learning
consumed_apis:
- amd-cloud
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
- launch an amd instinct gpu instance (mi300x, mi250, mi210) for ai training or hpc.
- check available amd developer cloud gpu credit balance and usage history.
- list models
- engineer deploying and optimizing ml inference workloads on amd hardware
- get real-time gpu utilization, memory usage, temperature, and power draw for an amd instance.
- researcher training and evaluating large language models on amd gpu clusters
- ml engineer
- create a gpu instance.
- check the current status and configuration of an amd gpu compute instance.
- list ai models deployed and serving on amd instinct gpus.
- list deployed models
- deploy a large language model on amd instinct gpus using vllm for high-throughput inference.
- terminate instance
- gpu instance management.
- ai
- get gpu instance status
- amd
- monitor gpu performance
- machine learning
- ai researcher
- list instances
- check credit balance
- list all amd instinct gpu compute instances in the developer cloud.
- semiconductor
- hpc developer
- gpu
- list gpu instances.
- deploy model
- developer running scientific simulations and hpc workloads with rocm
- unified workflow for ai and hpc workloads on amd instinct gpus
- hpc
- ai model deployment.
- terminate an amd gpu compute instance to stop billing and release resources.
- list deployed ai models.
- cloud computing
- create instance
- deploy an ai model.
- list gpu instances
- deploy llm
- create gpu instance
slug: ai-gpu-computing
source_filename: ai-gpu-computing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AMD AI GPU Computing\"\n  description: \"Unified workflow capability for AI and HPC workloads on AMD Instinct GPUs — provision instances, deploy LLMs, monitor performance, and manage cloud credits. Designed for AI researchers, ML engineers, and HPC developers.\"\n  tags:\n    - AMD\n    - AI\n    - Cloud Computing\n    - GPU\n    - HPC\n    - Machine Learning\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMD_API_KEY: AMD_API_KEY\n\ncapability:\n  consumes:\n    - import: amd-cloud\n      location: ./shared/developer-cloud-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: amd-gpu-api\n      description: \"Unified REST API for AMD GPU compute management, AI model deployment, and monitoring.\"\n      resources:\n        - path: /v1/instances\n          name: instances\n          description: \"GPU instance management.\"\n          operations:\n   \
  \         - method: GET\n              name: list-instances\n              description: \"List GPU instances.\"\n              call: \"amd-cloud.list-instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-instance\n              description: \"Create a GPU instance.\"\n              call: \"amd-cloud.create-instance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models\n          name: models\n          description: \"AI model deployment.\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List deployed AI models.\"\n              call: \"amd-cloud.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: deploy-model\n              description:\
  \ \"Deploy an AI model.\"\n              call: \"amd-cloud.deploy-model\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: amd-gpu-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AMD GPU computing — provision hardware, deploy models, and monitor performance.\"\n      tools:\n        - name: list-gpu-instances\n          description: \"List all AMD Instinct GPU compute instances in the developer cloud.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amd-cloud.list-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-gpu-instance\n          description: \"Launch an AMD Instinct GPU instance (MI300X, MI250, MI210) for AI training or HPC.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ false\n          call: \"amd-cloud.create-instance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-gpu-instance-status\n          description: \"Check the current status and configuration of an AMD GPU compute instance.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"amd-cloud.get-instance\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: monitor-gpu-performance\n          description: \"Get real-time GPU utilization, memory usage, temperature, and power draw for an AMD instance.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"amd-cloud.get-instance-metrics\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: deploy-llm\n          description: \"Deploy a large language model on AMD Instinct GPUs using vLLM for high-throughput inference.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"amd-cloud.deploy-model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-deployed-models\n          description: \"List AI models deployed and serving on AMD Instinct GPUs.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amd-cloud.list-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-credit-balance\n          description: \"Check available AMD Developer Cloud GPU credit balance and usage history.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"amd-cloud.get-credits\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: terminate-instance\n          description: \"Terminate an AMD GPU compute instance to stop billing and release resources.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"amd-cloud.terminate-instance\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
