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
- manages deployment infrastructure.
- create deployment
- deployment
- create and monitor deployments
- create a deployment group for an application
- list applications
- release management
- get deployment
- amazon
- blue/green deployment
- get deployment instance
- automated application deployment to compute targets.
- coordinates application releases.
- manage codedeploy applications
- devops
- stop deployment
- create deployment group
- list deployment groups for an application
- Release Manager
- list deployment groups
- list instances in a deployment
- ci/cd
- stop an in-progress deployment
- list deployments for an application and deployment group
- managing software release processes and rollbacks.
- create a codedeploy application
- list deployment instances
- list deployments
- get deployment information for a target instance
- manage deployment groups
- create application
- DevOps Engineer
- create a new deployment
- list codedeploy applications
- aws
- get details about a specific deployment
- application deployment to ec2, lambda, ecs, and on-premises servers.
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
