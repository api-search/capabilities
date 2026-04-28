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
- blue/green deployment
- create a new deployment
- create deployment
- list instances in a deployment
- create deployment group
- release management
- get details about a specific deployment
- get deployment
- deployment
- coordinates application releases.
- stop an in-progress deployment
- ci/cd
- get deployment instance
- DevOps Engineer
- managing software release processes and rollbacks.
- list deployments for an application and deployment group
- application deployment to ec2, lambda, ecs, and on-premises servers.
- list deployment groups
- manages deployment infrastructure.
- list deployment instances
- devops
- list deployments
- automated application deployment to compute targets.
- list deployment groups for an application
- list applications
- manage deployment groups
- list codedeploy applications
- create application
- create and monitor deployments
- get deployment information for a target instance
- create a deployment group for an application
- aws
- Release Manager
- stop deployment
- create a codedeploy application
- manage codedeploy applications
- amazon
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
