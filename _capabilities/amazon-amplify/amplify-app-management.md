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
- list all amazon amplify applications in the aws account.
- create amplify app
- developer building and deploying web and mobile frontends on aws amplify.
- Frontend Developer
- hosting
- list apps
- create a new amplify full-stack application connected to a code repository.
- full stack
- list amplify apps
- frontend
- mobile development
- amazon
- aws
- amplify application management.
- list all amplify apps.
- engineer managing ci/cd pipelines and deployments for amplify applications.
- web applications
- DevOps Engineer
- amplify
- manage amplify apps, branches, and deployments.
- deployment
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
