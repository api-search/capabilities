---
aliases: []
common_operations:
- list-clusters
- list-pods
- deploy-container
- scale-deployment
description: 'Kubernetes-style or proprietary orchestrators that schedule containers

  onto a fleet of nodes — pods, deployments, services, ingress, autoscaling.

  '
domain: infrastructure
implementation_count: 14
implementations:
- capability_name: Amazon ECR Container Registry Management
  capability_slug: ecr-management
  capability_url: https://capabilities.apis.io/capabilities/amazon-ecr/ecr-management/
  consumed_api_count: 0
  operation_count: 6
  provider_name: Amazon ECR
  provider_slug: amazon-ecr
  tags:
  - Amazon ECR
  - Containers
  - Container Registry
  tool_count: 6
- capability_name: Amazon ECS Container Orchestration
  capability_slug: container-orchestration
  capability_url: https://capabilities.apis.io/capabilities/amazon-ecs/container-orchestration/
  consumed_api_count: 0
  operation_count: 8
  provider_name: Amazon ECS
  provider_slug: amazon-ecs
  tags:
  - Amazon
  - Containers
  - Orchestration
  tool_count: 18
- capability_name: Amazon Fargate Container Orchestration
  capability_slug: amazon-fargate-container-orchestration
  capability_url: https://capabilities.apis.io/capabilities/amazon-fargate/amazon-fargate-container-orchestration/
  consumed_api_count: 0
  operation_count: 10
  provider_name: Amazon Fargate
  provider_slug: amazon-fargate
  tags:
  - Amazon Fargate
  - Containers
  - Serverless
  - ECS
  - DevOps
  tool_count: 17
- capability_name: Apptainer HPC Container Management
  capability_slug: hpc-container-management
  capability_url: https://capabilities.apis.io/capabilities/apptainer/hpc-container-management/
  consumed_api_count: 0
  operation_count: 0
  provider_name: Apptainer
  provider_slug: apptainer
  tags:
  - Apptainer
  - HPC
  - Scientific Computing
  - Containers
  - Research
  tool_count: 4
- capability_name: Argo Platform
  capability_slug: argo-platform
  capability_url: https://capabilities.apis.io/capabilities/argo/argo-platform/
  consumed_api_count: 0
  operation_count: 4
  provider_name: Argo
  provider_slug: argo
  tags:
  - Argo
  - GitOps
  - Kubernetes
  - Workflow Engine
  - CNCF
  - Platform Engineering
  tool_count: 4
- capability_name: Argo CD GitOps Delivery
  capability_slug: gitops-delivery
  capability_url: https://capabilities.apis.io/capabilities/argo-cd/gitops-delivery/
  consumed_api_count: 0
  operation_count: 8
  provider_name: Argo CD
  provider_slug: argo-cd
  tags:
  - Argo CD
  - GitOps
  - Kubernetes
  - Continuous Delivery
  - Platform Engineering
  tool_count: 9
- capability_name: Argo Workflows Orchestration
  capability_slug: workflow-orchestration
  capability_url: https://capabilities.apis.io/capabilities/argo-workflows/workflow-orchestration/
  consumed_api_count: 0
  operation_count: 5
  provider_name: Argo Workflows
  provider_slug: argo-workflows
  tags:
  - Argo Workflows
  - Kubernetes
  - Workflow Engine
  - CNCF
  - Data Engineering
  tool_count: 5
- capability_name: Azure Container Apps Management
  capability_slug: container-apps-management
  capability_url: https://capabilities.apis.io/capabilities/azure-container-apps/container-apps-management/
  consumed_api_count: 0
  operation_count: 3
  provider_name: Azure Container Apps
  provider_slug: azure-container-apps
  tags:
  - Azure
  - Containers
  - Microservices
  - Serverless
  - DevOps
  tool_count: 5
- capability_name: Azure Kubernetes Service Cluster Management
  capability_slug: cluster-management
  capability_url: https://capabilities.apis.io/capabilities/azure-kubernetes-service/cluster-management/
  consumed_api_count: 0
  operation_count: 5
  provider_name: Azure Kubernetes Service
  provider_slug: azure-kubernetes-service
  tags:
  - Azure
  - Kubernetes
  - Cluster Management
  - DevOps
  tool_count: 11
- capability_name: Azure Container Platform
  capability_slug: container-platform
  capability_url: https://capabilities.apis.io/capabilities/microsoft-azure/container-platform/
  consumed_api_count: 0
  operation_count: 2
  provider_name: Microsoft Azure
  provider_slug: microsoft-azure
  tags:
  - Azure
  - Kubernetes
  - Containers
  - Container Registry
  tool_count: 9
- capability_name: OpenShift Platform Management
  capability_slug: platform-management
  capability_url: https://capabilities.apis.io/capabilities/openshift/platform-management/
  consumed_api_count: 0
  operation_count: 1
  provider_name: OpenShift
  provider_slug: openshift
  tags:
  - OpenShift
  - Kubernetes
  - Platform
  - DevOps
  tool_count: 13
- capability_name: Snowflake Compute and Services
  capability_slug: compute-and-services
  capability_url: https://capabilities.apis.io/capabilities/snowflake/compute-and-services/
  consumed_api_count: 0
  operation_count: 8
  provider_name: Snowflake
  provider_slug: snowflake
  tags:
  - Snowflake
  - Compute
  - Containers
  - Infrastructure
  tool_count: 34
- capability_name: Spot Compute Optimization
  capability_slug: compute-optimization
  capability_url: https://capabilities.apis.io/capabilities/spot/compute-optimization/
  consumed_api_count: 0
  operation_count: 3
  provider_name: Spot
  provider_slug: spot
  tags:
  - Spot
  - Compute
  - Autoscaling
  - Kubernetes
  tool_count: 16
- capability_name: Spot Compute Optimization
  capability_slug: compute-optimization
  capability_url: https://capabilities.apis.io/capabilities/spot/compute-optimization/
  consumed_api_count: 0
  operation_count: 3
  provider_name: Spot
  provider_slug: spot
  tags:
  - Spot
  - Compute
  - Autoscaling
  - Kubernetes
  tool_count: 16
layout: category
name: Container Orchestration
provider_count: 13
related:
- serverless
- ci-cd
short: Schedule, scale, and operate containerized workloads.
slug: container-orchestration
---
