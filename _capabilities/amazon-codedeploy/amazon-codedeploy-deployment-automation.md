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
- list deployment groups for an application
- aws
- amazon
- create a codedeploy application
- create a new deployment
- DevOps Engineer
- list instances in a deployment
- application deployment to ec2, lambda, ecs, and on-premises servers.
- get details about a specific deployment
- create application
- managing software release processes and rollbacks.
- create a deployment group for an application
- deployment
- list codedeploy applications
- Release Manager
- automated application deployment to compute targets.
- stop an in-progress deployment
- create deployment
- list deployment instances
- create and monitor deployments
- ci/cd
- manage deployment groups
- stop deployment
- get deployment instance
- devops
- create deployment group
- blue/green deployment
- list deployment groups
- manages deployment infrastructure.
- list applications
- manage codedeploy applications
- get deployment information for a target instance
- release management
- list deployments
- coordinates application releases.
- list deployments for an application and deployment group
- get deployment
slug: amazon-codedeploy-deployment-automation
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon CodeDeploy Deployment Automation\n  description: Unified workflow for DevOps teams to create deployment groups, deploy revisions to EC2, Lambda, and ECS targets, and monitor deployment status.\n  tags:\n  - Amazon\n  - AWS\n  - Deployment\n  - DevOps\n  - CI/CD\n  - Release Management\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: codedeploy\n    location: ./shared/codedeploy.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: codedeploy-deployment-api\n    description: Unified REST API for CodeDeploy deployment automation.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: Manage CodeDeploy applications\n    - path: /v1/deployments\n      name: deployments\n      description: Create\
  \ and monitor deployments\n    - path: /v1/deployment-groups\n      name: deployment-groups\n      description: Manage deployment groups\n  - type: mcp\n    port: 9090\n    namespace: codedeploy-deployment-mcp\n    transport: http\n    description: MCP server for AI-assisted deployment management.\n    tools:\n    - name: list-applications\n      description: List CodeDeploy applications\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codedeploy.listApplications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application\n      description: Create a CodeDeploy application\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codedeploy.createApplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deployment-groups\n      description: List deployment groups for an application\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codedeploy.listDeploymentGroups\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-deployment\n      description: Create a new deployment\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codedeploy.createDeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment\n      description: Get details about a specific deployment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codedeploy.getDeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deployments\n      description: List deployments for an application and deployment group\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codedeploy.listDeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-deployment\n      description: Stop an in-progress deployment\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        openWorld: false\n      call: codedeploy.stopDeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment-instance\n      description: Get deployment information for a target instance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codedeploy.getDeploymentInstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deployment-instances\n      description: List instances in a deployment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codedeploy.listDeploymentInstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-deployment-group\n      description: Create a deployment group for an application\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codedeploy.createDeploymentGroup\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-codedeploy/refs/heads/main/capabilities/amazon-codedeploy-deployment-automation.yaml
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
