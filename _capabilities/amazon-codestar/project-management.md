---
categories:
- ci-cd
consumed_apis:
- codestar
description: Workflow capability for managing AWS CodeStar development projects, team collaboration, and user profiles. Used by development team leads and platform administrators to set up CI/CD toolchains and manage project access.
layout: capability
name: Amazon CodeStar Project Management
operations:
- description: List all AWS CodeStar projects.
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new AWS CodeStar project.
  method: POST
  name: create-project
  path: /v1/projects
- description: Describe a specific CodeStar project.
  method: GET
  name: describe-project
  path: /v1/projects/{project_id}
- description: Delete a CodeStar project.
  method: DELETE
  name: delete-project
  path: /v1/projects/{project_id}
- description: List all team members in a project.
  method: GET
  name: list-team-members
  path: /v1/projects/{project_id}/team-members
- description: Add an IAM user to the project team.
  method: POST
  name: associate-team-member
  path: /v1/projects/{project_id}/team-members
- description: List tags for a CodeStar project.
  method: GET
  name: list-tags
  path: /v1/projects/{project_id}/tags
- description: List all user profiles.
  method: GET
  name: list-user-profiles
  path: /v1/user-profiles
- description: Create a user profile.
  method: POST
  name: create-user-profile
  path: /v1/user-profiles
personas: []
provider_name: Amazon CodeStar
provider_slug: amazon-codestar
search_terms:
- Development Team Lead
- create and manage codestar projects, team members, and user profiles.
- add tags to an aws codestar project for organization.
- list all team members in a project.
- list all aws codestar user profiles.
- list tags
- list projects
- manage codestar projects.
- developer tools
- delete an aws codestar project and its resources.
- disassociate team member
- Platform Administrator
- manage tags on a project.
- get details of a specific aws codestar project.
- list all aws codestar projects.
- list resources
- amazon
- create user profile
- delete a codestar project.
- aws
- team collaboration
- update attributes of an aws codestar project.
- create a user profile.
- describe a specific codestar project.
- add an iam user to an aws codestar project team with a role.
- manage team members for a project.
- associate team member
- creates and manages codestar projects and team membership.
- devops
- list tags for a codestar project.
- list team members
- list all aws codestar projects in the account.
- project management
- delete project
- create a user profile for aws codestar.
- create project
- update project
- describe project
- list user profiles
- get and update individual codestar project.
- remove an iam user from an aws codestar project team.
- list all team members and their roles in a codestar project.
- tag project
- list aws resources associated with a codestar project.
- manages user profiles and project-level access controls.
- add an iam user to the project team.
- list all user profiles.
- manage codestar user profiles.
- create a new aws codestar development project with ci/cd toolchain.
- create a new aws codestar project.
slug: project-management
source_filename: project-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon CodeStar Project Management\"\n  description: \"Workflow capability for managing AWS CodeStar development projects, team collaboration, and user profiles. Used by development team leads and platform administrators to set up CI/CD toolchains and manage project access.\"\n  tags:\n    - Amazon\n    - AWS\n    - Developer Tools\n    - DevOps\n    - Project Management\n    - Team Collaboration\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: codestar\n      location: ./shared/codestar.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: project-management-api\n      description: \"Unified REST API for AWS CodeStar project management and team collaboration.\"\n      resources:\n        - path:\
  \ /v1/projects\n          name: projects\n          description: \"Manage CodeStar projects.\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all AWS CodeStar projects.\"\n              call: \"codestar.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-project\n              description: \"Create a new AWS CodeStar project.\"\n              call: \"codestar.create-project\"\n              with:\n                project_name: \"rest.project_name\"\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{project_id}\n          name: project-detail\n          description: \"Get and update individual CodeStar project.\"\n          operations:\n            - method: GET\n  \
  \            name: describe-project\n              description: \"Describe a specific CodeStar project.\"\n              call: \"codestar.describe-project\"\n              with:\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: DELETE\n              name: delete-project\n              description: \"Delete a CodeStar project.\"\n              call: \"codestar.delete-project\"\n              with:\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{project_id}/team-members\n          name: team-members\n          description: \"Manage team members for a project.\"\n          operations:\n            - method: GET\n              name: list-team-members\n              description: \"List all team members in a project.\"\n              call:\
  \ \"codestar.list-team-members\"\n              with:\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: associate-team-member\n              description: \"Add an IAM user to the project team.\"\n              call: \"codestar.associate-team-member\"\n              with:\n                project_id: \"rest.project_id\"\n                user_arn: \"rest.user_arn\"\n                role: \"rest.role\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{project_id}/tags\n          name: project-tags\n          description: \"Manage tags on a project.\"\n          operations:\n            - method: GET\n              name: list-tags\n              description: \"List tags for a CodeStar project.\"\n              call: \"codestar.list-tags-for-project\"\n        \
  \      with:\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/user-profiles\n          name: user-profiles\n          description: \"Manage CodeStar user profiles.\"\n          operations:\n            - method: GET\n              name: list-user-profiles\n              description: \"List all user profiles.\"\n              call: \"codestar.list-user-profiles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-user-profile\n              description: \"Create a user profile.\"\n              call: \"codestar.create-user-profile\"\n              with:\n                user_arn: \"rest.user_arn\"\n                display_name: \"rest.display_name\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n       \
  \           mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: project-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AWS CodeStar project management and team collaboration.\"\n      tools:\n        - name: list-projects\n          description: \"List all AWS CodeStar projects in the account.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"codestar.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-project\n          description: \"Create a new AWS CodeStar development project with CI/CD toolchain.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"codestar.create-project\"\n          with:\n            project_name: \"tools.project_name\"\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n          \
  \    mapping: \"$.\"\n\n        - name: describe-project\n          description: \"Get details of a specific AWS CodeStar project.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"codestar.describe-project\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-project\n          description: \"Update attributes of an AWS CodeStar project.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"codestar.update-project\"\n          with:\n            project_id: \"tools.project_id\"\n            project_name: \"tools.project_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-project\n          description: \"Delete an AWS CodeStar project and its resources.\"\n          hints:\n\
  \            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"codestar.delete-project\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-resources\n          description: \"List AWS resources associated with a CodeStar project.\"\n          hints:\n            readOnly: true\n          call: \"codestar.list-resources\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-team-members\n          description: \"List all team members and their roles in a CodeStar project.\"\n          hints:\n            readOnly: true\n          call: \"codestar.list-team-members\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n             \
  \ mapping: \"$.\"\n\n        - name: associate-team-member\n          description: \"Add an IAM user to an AWS CodeStar project team with a role.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"codestar.associate-team-member\"\n          with:\n            project_id: \"tools.project_id\"\n            user_arn: \"tools.user_arn\"\n            role: \"tools.role\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: disassociate-team-member\n          description: \"Remove an IAM user from an AWS CodeStar project team.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"codestar.disassociate-team-member\"\n          with:\n            project_id: \"tools.project_id\"\n            user_arn: \"tools.user_arn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-user-profiles\n  \
  \        description: \"List all AWS CodeStar user profiles.\"\n          hints:\n            readOnly: true\n          call: \"codestar.list-user-profiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-user-profile\n          description: \"Create a user profile for AWS CodeStar.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"codestar.create-user-profile\"\n          with:\n            user_arn: \"tools.user_arn\"\n            display_name: \"tools.display_name\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: tag-project\n          description: \"Add tags to an AWS CodeStar project for organization.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"codestar.tag-project\"\n          with:\n            project_id: \"tools.project_id\"\
  \n            tags: \"tools.tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-codestar/refs/heads/main/capabilities/project-management.yaml
tags:
- Amazon
- AWS
- Developer Tools
- DevOps
- Project Management
- Team Collaboration
tools:
- description: List all AWS CodeStar projects in the account.
  hints:
    openWorld: false
    readOnly: true
  name: list-projects
- description: Create a new AWS CodeStar development project with CI/CD toolchain.
  hints:
    destructive: false
    readOnly: false
  name: create-project
- description: Get details of a specific AWS CodeStar project.
  hints:
    openWorld: false
    readOnly: true
  name: describe-project
- description: Update attributes of an AWS CodeStar project.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-project
- description: Delete an AWS CodeStar project and its resources.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
- description: List AWS resources associated with a CodeStar project.
  hints:
    readOnly: true
  name: list-resources
- description: List all team members and their roles in a CodeStar project.
  hints:
    readOnly: true
  name: list-team-members
- description: Add an IAM user to an AWS CodeStar project team with a role.
  hints:
    destructive: false
    readOnly: false
  name: associate-team-member
- description: Remove an IAM user from an AWS CodeStar project team.
  hints:
    destructive: true
    readOnly: false
  name: disassociate-team-member
- description: List all AWS CodeStar user profiles.
  hints:
    readOnly: true
  name: list-user-profiles
- description: Create a user profile for AWS CodeStar.
  hints:
    destructive: false
    readOnly: false
  name: create-user-profile
- description: Add tags to an AWS CodeStar project for organization.
  hints:
    destructive: false
    readOnly: false
  name: tag-project
---
