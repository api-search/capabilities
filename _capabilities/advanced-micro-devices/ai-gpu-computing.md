---
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
- ai researcher
- ml engineer
- deploy a large language model on amd instinct gpus using vllm for high-throughput inference.
- terminate an amd gpu compute instance to stop billing and release resources.
- list ai models deployed and serving on amd instinct gpus.
- machine learning
- ai model deployment.
- list gpu instances.
- list instances
- launch an amd instinct gpu instance (mi300x, mi250, mi210) for ai training or hpc.
- amd
- check available amd developer cloud gpu credit balance and usage history.
- list deployed ai models.
- list deployed models
- hpc
- create a gpu instance.
- deploy an ai model.
- check credit balance
- monitor gpu performance
- developer running scientific simulations and hpc workloads with rocm
- check the current status and configuration of an amd gpu compute instance.
- get real-time gpu utilization, memory usage, temperature, and power draw for an amd instance.
- unified workflow for ai and hpc workloads on amd instinct gpus
- list gpu instances
- deploy llm
- engineer deploying and optimizing ml inference workloads on amd hardware
- deploy model
- create instance
- list models
- ai
- list all amd instinct gpu compute instances in the developer cloud.
- gpu
- hpc developer
- gpu instance management.
- semiconductor
- create gpu instance
- get gpu instance status
- cloud computing
- researcher training and evaluating large language models on amd gpu clusters
- terminate instance
slug: ai-gpu-computing
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
