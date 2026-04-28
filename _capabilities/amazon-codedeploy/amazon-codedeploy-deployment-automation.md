---
categories:
- ci-cd
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
- create a deployment group for an application
- get details about a specific deployment
- get deployment information for a target instance
- list deployments for an application and deployment group
- application deployment to ec2, lambda, ecs, and on-premises servers.
- blue/green deployment
- amazon
- release management
- devops
- deployment
- list deployment instances
- ci/cd
- manage deployment groups
- list codedeploy applications
- list instances in a deployment
- create and monitor deployments
- list deployment groups for an application
- stop deployment
- managing software release processes and rollbacks.
- list applications
- DevOps Engineer
- coordinates application releases.
- create a new deployment
- list deployments
- Release Manager
- manage codedeploy applications
- list deployment groups
- automated application deployment to compute targets.
- create deployment group
- manages deployment infrastructure.
- get deployment
- get deployment instance
- create deployment
- stop an in-progress deployment
- create a codedeploy application
- aws
- create application
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
