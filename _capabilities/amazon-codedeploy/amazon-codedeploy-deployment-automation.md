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
- Release Manager
- manage codedeploy applications
- stop an in-progress deployment
- create a new deployment
- get deployment
- list deployments for an application and deployment group
- managing software release processes and rollbacks.
- list deployments
- application deployment to ec2, lambda, ecs, and on-premises servers.
- coordinates application releases.
- list instances in a deployment
- aws
- release management
- get details about a specific deployment
- get deployment instance
- get deployment information for a target instance
- list codedeploy applications
- manage deployment groups
- list deployment groups
- create a codedeploy application
- stop deployment
- create application
- create deployment group
- list deployment groups for an application
- list deployment instances
- blue/green deployment
- create and monitor deployments
- devops
- create deployment
- create a deployment group for an application
- list applications
- amazon
- manages deployment infrastructure.
- DevOps Engineer
- automated application deployment to compute targets.
- deployment
- ci/cd
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
