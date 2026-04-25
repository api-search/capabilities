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
- stop an in-progress deployment
- manages deployment infrastructure.
- list deployments for an application and deployment group
- create a codedeploy application
- list applications
- list instances in a deployment
- get deployment
- application deployment to ec2, lambda, ecs, and on-premises servers.
- create application
- release management
- devops
- get details about a specific deployment
- blue/green deployment
- Release Manager
- manage codedeploy applications
- list deployments
- manage deployment groups
- create a new deployment
- list deployment groups
- get deployment instance
- create deployment group
- stop deployment
- ci/cd
- get deployment information for a target instance
- amazon
- create a deployment group for an application
- create deployment
- coordinates application releases.
- list codedeploy applications
- aws
- list deployment groups for an application
- DevOps Engineer
- automated application deployment to compute targets.
- list deployment instances
- managing software release processes and rollbacks.
- create and monitor deployments
- deployment
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
