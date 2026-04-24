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
- manage codedeploy applications
- get deployment information for a target instance
- manages deployment infrastructure.
- manage deployment groups
- list deployment instances
- create a deployment group for an application
- list codedeploy applications
- get deployment
- get details about a specific deployment
- devops
- create application
- list applications
- application deployment to ec2, lambda, ecs, and on-premises servers.
- create deployment
- stop deployment
- create and monitor deployments
- create a codedeploy application
- DevOps Engineer
- deployment
- managing software release processes and rollbacks.
- get deployment instance
- list instances in a deployment
- list deployments
- automated application deployment to compute targets.
- list deployments for an application and deployment group
- blue/green deployment
- release management
- stop an in-progress deployment
- aws
- list deployment groups
- amazon
- Release Manager
- coordinates application releases.
- ci/cd
- create a new deployment
- list deployment groups for an application
- create deployment group
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
