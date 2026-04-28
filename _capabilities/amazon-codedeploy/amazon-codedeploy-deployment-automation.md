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
- list deployment groups
- devops
- list deployments for an application and deployment group
- get deployment information for a target instance
- DevOps Engineer
- get deployment instance
- blue/green deployment
- Release Manager
- amazon
- coordinates application releases.
- stop an in-progress deployment
- create and monitor deployments
- release management
- list deployment groups for an application
- aws
- get details about a specific deployment
- list deployment instances
- create a new deployment
- create a codedeploy application
- manages deployment infrastructure.
- create a deployment group for an application
- list instances in a deployment
- manage codedeploy applications
- deployment
- automated application deployment to compute targets.
- ci/cd
- list codedeploy applications
- create application
- list deployments
- application deployment to ec2, lambda, ecs, and on-premises servers.
- create deployment
- managing software release processes and rollbacks.
- stop deployment
- list applications
- get deployment
- create deployment group
- manage deployment groups
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
