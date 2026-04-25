---
consumed_apis:
- codedeploy
description: Unified workflow for DevOps teams to create deployment groups, deploy revisions to EC2, Lambda, and ECS targets, and monitor deployment status.
layout: capability
name: Amazon CodeDeploy Deployment Automation
operations: []
personas: []
provider_name: Amazon CodeDeploy
provider_slug: amazon-codedeploy
search_terms:
- list instances in a deployment
- DevOps Engineer
- list deployment groups
- list applications
- release management
- manages deployment infrastructure.
- blue/green deployment
- list deployment groups for an application
- automated application deployment to compute targets.
- create and monitor deployments
- application deployment to ec2, lambda, ecs, and on-premises servers.
- stop an in-progress deployment
- stop deployment
- manage codedeploy applications
- create deployment group
- aws
- devops
- list codedeploy applications
- coordinates application releases.
- create deployment
- create a deployment group for an application
- list deployments
- list deployment instances
- deployment
- Release Manager
- amazon
- get deployment information for a target instance
- manage deployment groups
- managing software release processes and rollbacks.
- create a new deployment
- create application
- get deployment
- get deployment instance
- ci/cd
- list deployments for an application and deployment group
- get details about a specific deployment
- create a codedeploy application
slug: amazon-codedeploy-deployment-automation
tags:
- Amazon
- AWS
- Deployment
- DevOps
- CI/CD
- Release Management
tools:
- description: List CodeDeploy applications
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Create a CodeDeploy application
  hints:
    openWorld: false
    readOnly: false
  name: create-application
- description: List deployment groups for an application
  hints:
    openWorld: true
    readOnly: true
  name: list-deployment-groups
- description: Create a new deployment
  hints:
    openWorld: false
    readOnly: false
  name: create-deployment
- description: Get details about a specific deployment
  hints:
    openWorld: true
    readOnly: true
  name: get-deployment
- description: List deployments for an application and deployment group
  hints:
    openWorld: true
    readOnly: true
  name: list-deployments
- description: Stop an in-progress deployment
  hints:
    destructive: false
    openWorld: false
    readOnly: false
  name: stop-deployment
- description: Get deployment information for a target instance
  hints:
    openWorld: true
    readOnly: true
  name: get-deployment-instance
- description: List instances in a deployment
  hints:
    openWorld: true
    readOnly: true
  name: list-deployment-instances
- description: Create a deployment group for an application
  hints:
    openWorld: false
    readOnly: false
  name: create-deployment-group
---
