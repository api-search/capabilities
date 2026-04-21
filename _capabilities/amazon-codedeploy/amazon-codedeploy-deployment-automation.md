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
- DevOps Engineer
- managing software release processes and rollbacks.
- list deployment groups
- aws
- create a new deployment
- application deployment to ec2, lambda, ecs, and on-premises servers.
- get deployment information for a target instance
- list codedeploy applications
- create and monitor deployments
- automated application deployment to compute targets.
- list deployments for an application and deployment group
- stop an in-progress deployment
- get details about a specific deployment
- list instances in a deployment
- stop deployment
- coordinates application releases.
- blue/green deployment
- deployment
- list applications
- list deployment groups for an application
- list deployments
- create application
- list deployment instances
- create a deployment group for an application
- manage codedeploy applications
- devops
- create deployment
- create deployment group
- ci/cd
- get deployment instance
- amazon
- manage deployment groups
- manages deployment infrastructure.
- release management
- create a codedeploy application
- Release Manager
- get deployment
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
