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
- manage codedeploy applications
- stop deployment
- stop an in-progress deployment
- ci/cd
- application deployment to ec2, lambda, ecs, and on-premises servers.
- list deployment groups
- get deployment information for a target instance
- get deployment
- create a deployment group for an application
- DevOps Engineer
- coordinates application releases.
- get details about a specific deployment
- list deployment instances
- create application
- list deployments for an application and deployment group
- manages deployment infrastructure.
- create and monitor deployments
- create a new deployment
- release management
- aws
- devops
- list deployment groups for an application
- amazon
- create deployment
- automated application deployment to compute targets.
- list deployments
- get deployment instance
- manage deployment groups
- list codedeploy applications
- blue/green deployment
- create a codedeploy application
- deployment
- Release Manager
- create deployment group
- list applications
- managing software release processes and rollbacks.
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
