---
consumed_apis:
- amazon-amplify
description: Workflow capability for managing full-stack Amplify applications including app creation, branch management, and deployment workflows.
layout: capability
name: Amazon Amplify App Management
operations:
- description: List all Amplify apps.
  method: GET
  name: list-apps
  path: /v1/apps
personas: []
provider_name: Amazon Amplify
provider_slug: amazon-amplify
search_terms:
- frontend
- list apps
- hosting
- developer building and deploying web and mobile frontends on aws amplify.
- DevOps Engineer
- amplify
- aws
- Frontend Developer
- amplify application management.
- amazon
- create amplify app
- manage amplify apps, branches, and deployments.
- list all amazon amplify applications in the aws account.
- full stack
- mobile development
- engineer managing ci/cd pipelines and deployments for amplify applications.
- list all amplify apps.
- web applications
- deployment
- create a new amplify full-stack application connected to a code repository.
- list amplify apps
slug: amplify-app-management
tags:
- Amazon
- Amplify
- AWS
- Deployment
- Frontend
tools:
- description: List all Amazon Amplify applications in the AWS account.
  hints:
    openWorld: false
    readOnly: true
  name: list-amplify-apps
- description: Create a new Amplify full-stack application connected to a code repository.
  hints:
    openWorld: false
    readOnly: false
  name: create-amplify-app
---
