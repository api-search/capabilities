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
- devops
- deployment
- release management
- list deployments for an application and deployment group
- create a deployment group for an application
- list deployments
- application deployment to ec2, lambda, ecs, and on-premises servers.
- create a new deployment
- list applications
- create and monitor deployments
- list codedeploy applications
- Release Manager
- get deployment
- DevOps Engineer
- manages deployment infrastructure.
- list deployment groups
- list deployment groups for an application
- list instances in a deployment
- create deployment
- manage deployment groups
- stop an in-progress deployment
- amazon
- get details about a specific deployment
- blue/green deployment
- manage codedeploy applications
- get deployment information for a target instance
- create deployment group
- coordinates application releases.
- managing software release processes and rollbacks.
- aws
- list deployment instances
- automated application deployment to compute targets.
- get deployment instance
- create a codedeploy application
- create application
- ci/cd
- stop deployment
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
