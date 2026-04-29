---
categories: []
consumed_apis:
- jira-cloud
description: Unified project management workflow combining issue tracking, workflow transitions, JQL search, and project management. Used by project managers, developers, and team leads to manage agile software delivery.
layout: capability
name: Jira Project Management
operations:
- description: Create a new issue.
  method: POST
  name: create-issue
  path: /v1/issues
- description: Get issue details.
  method: GET
  name: get-issue
  path: /v1/issues/{issueIdOrKey}
- description: Edit an issue.
  method: PUT
  name: edit-issue
  path: /v1/issues/{issueIdOrKey}
- description: Delete an issue.
  method: DELETE
  name: delete-issue
  path: /v1/issues/{issueIdOrKey}
- description: Get available transitions.
  method: GET
  name: get-transitions
  path: /v1/issues/{issueIdOrKey}/transitions
- description: Perform a transition.
  method: POST
  name: do-transition
  path: /v1/issues/{issueIdOrKey}/transitions
- description: Get issue comments.
  method: GET
  name: get-comments
  path: /v1/issues/{issueIdOrKey}/comments
- description: Add a comment.
  method: POST
  name: add-comment
  path: /v1/issues/{issueIdOrKey}/comments
- description: Search with JQL.
  method: GET
  name: search-issues
  path: /v1/search
- description: List all projects.
  method: GET
  name: list-projects
  path: /v1/projects
- description: Get project details.
  method: GET
  name: get-project
  path: /v1/projects/{projectIdOrKey}
personas: []
provider_name: Jira
provider_slug: jira
search_terms:
- transition an issue through its workflow.
- get all jira issue types.
- get all jira priorities.
- service management
- search issues
- create a new issue.
- edit an issue.
- jira
- list all projects.
- search jira issues using jql.
- single project.
- edit issue
- get available transitions.
- search with jql.
- get project details.
- get comments
- itsm
- get transitions
- get issue
- single issue operations.
- get jira project details.
- list all jira projects.
- delete an issue.
- issue lifecycle management.
- jql issue search.
- project management.
- edit an existing jira issue.
- get jira issue details.
- delete a jira issue.
- add a comment to a jira issue.
- issue comments.
- get available workflow transitions.
- perform a transition.
- agile
- delete issue
- issue tracking
- add a comment.
- get priorities
- create issue
- list projects
- create a new jira issue.
- workflow transitions.
- do transition
- get issue details.
- get issue comments.
- get comments on a jira issue.
- get issue types
- project management
- add comment
- get statuses
- get all jira issue statuses.
- get project
slug: project-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Jira Project Management\"\n  description: \"Unified project management workflow combining issue tracking, workflow transitions, JQL search, and project management. Used by project managers, developers, and team leads to manage agile software delivery.\"\n  tags:\n    - Jira\n    - Project Management\n    - Issue Tracking\n    - Agile\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      JIRA_API_TOKEN: JIRA_API_TOKEN\n      JIRA_EMAIL: JIRA_EMAIL\n\ncapability:\n  consumes:\n    - import: jira-cloud\n      location: ./shared/jira-cloud-platform.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: jira-pm-api\n      description: \"Unified REST API for Jira project management workflows.\"\n      resources:\n        - path: /v1/issues\n          name: issues\n          description: \"Issue lifecycle management.\"\n          operations:\n            - method: POST\n\
  \              name: create-issue\n              description: \"Create a new issue.\"\n              call: \"jira-cloud.create-issue\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/issues/{issueIdOrKey}\n          name: issue-detail\n          description: \"Single issue operations.\"\n          operations:\n            - method: GET\n              name: get-issue\n              description: \"Get issue details.\"\n              call: \"jira-cloud.get-issue\"\n              with:\n                issueIdOrKey: \"rest.issueIdOrKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: edit-issue\n              description: \"Edit an issue.\"\n              call: \"jira-cloud.edit-issue\"\n              with:\n                issueIdOrKey: \"rest.issueIdOrKey\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-issue\n              description: \"Delete an issue.\"\n              call: \"jira-cloud.delete-issue\"\n              with:\n                issueIdOrKey: \"rest.issueIdOrKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/issues/{issueIdOrKey}/transitions\n          name: transitions\n          description: \"Workflow transitions.\"\n          operations:\n            - method: GET\n              name: get-transitions\n              description: \"Get available transitions.\"\n              call: \"jira-cloud.get-transitions\"\n              with:\n                issueIdOrKey: \"rest.issueIdOrKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: do-transition\n              description: \"Perform a transition.\"\n    \
  \          call: \"jira-cloud.do-transition\"\n              with:\n                issueIdOrKey: \"rest.issueIdOrKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/issues/{issueIdOrKey}/comments\n          name: comments\n          description: \"Issue comments.\"\n          operations:\n            - method: GET\n              name: get-comments\n              description: \"Get issue comments.\"\n              call: \"jira-cloud.get-comments\"\n              with:\n                issueIdOrKey: \"rest.issueIdOrKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-comment\n              description: \"Add a comment.\"\n              call: \"jira-cloud.add-comment\"\n              with:\n                issueIdOrKey: \"rest.issueIdOrKey\"\n              outputParameters:\n                - type: object\n  \
  \                mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"JQL issue search.\"\n          operations:\n            - method: GET\n              name: search-issues\n              description: \"Search with JQL.\"\n              call: \"jira-cloud.search-issues-jql\"\n              with:\n                jql: \"rest.jql\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects\n          name: projects\n          description: \"Project management.\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all projects.\"\n              call: \"jira-cloud.get-all-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{projectIdOrKey}\n          name: project-detail\n          description: \"Single project.\"\n       \
  \   operations:\n            - method: GET\n              name: get-project\n              description: \"Get project details.\"\n              call: \"jira-cloud.get-project\"\n              with:\n                projectIdOrKey: \"rest.projectIdOrKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: jira-pm-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Jira project management.\"\n      tools:\n        - name: create-issue\n          description: \"Create a new Jira issue.\"\n          hints:\n            readOnly: false\n          call: \"jira-cloud.create-issue\"\n          with:\n            project_key: \"tools.project_key\"\n            summary: \"tools.summary\"\n            issue_type: \"tools.issue_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-issue\n          description:\
  \ \"Get Jira issue details.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"jira-cloud.get-issue\"\n          with:\n            issueIdOrKey: \"tools.issueIdOrKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edit-issue\n          description: \"Edit an existing Jira issue.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"jira-cloud.edit-issue\"\n          with:\n            issueIdOrKey: \"tools.issueIdOrKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-issue\n          description: \"Delete a Jira issue.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"jira-cloud.delete-issue\"\n          with:\n            issueIdOrKey: \"tools.issueIdOrKey\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n        - name: get-transitions\n          description: \"Get available workflow transitions.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"jira-cloud.get-transitions\"\n          with:\n            issueIdOrKey: \"tools.issueIdOrKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: do-transition\n          description: \"Transition an issue through its workflow.\"\n          hints:\n            readOnly: false\n          call: \"jira-cloud.do-transition\"\n          with:\n            issueIdOrKey: \"tools.issueIdOrKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-comments\n          description: \"Get comments on a Jira issue.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"jira-cloud.get-comments\"\n          with:\n            issueIdOrKey:\
  \ \"tools.issueIdOrKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-comment\n          description: \"Add a comment to a Jira issue.\"\n          hints:\n            readOnly: false\n          call: \"jira-cloud.add-comment\"\n          with:\n            issueIdOrKey: \"tools.issueIdOrKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-issues\n          description: \"Search Jira issues using JQL.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"jira-cloud.search-issues-jql\"\n          with:\n            jql: \"tools.jql\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: \"List all Jira projects.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call:\
  \ \"jira-cloud.get-all-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project\n          description: \"Get Jira project details.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"jira-cloud.get-project\"\n          with:\n            projectIdOrKey: \"tools.projectIdOrKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-statuses\n          description: \"Get all Jira issue statuses.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"jira-cloud.get-all-statuses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-issue-types\n          description: \"Get all Jira issue types.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"jira-cloud.get-all-issue-types\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-priorities\n          description: \"Get all Jira priorities.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"jira-cloud.get-priorities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jira/refs/heads/main/capabilities/project-management.yaml
tags:
- Jira
- Project Management
- Issue Tracking
- Agile
tools:
- description: Create a new Jira issue.
  hints:
    readOnly: false
  name: create-issue
- description: Get Jira issue details.
  hints:
    idempotent: true
    readOnly: true
  name: get-issue
- description: Edit an existing Jira issue.
  hints:
    idempotent: true
    readOnly: false
  name: edit-issue
- description: Delete a Jira issue.
  hints:
    destructive: true
    readOnly: false
  name: delete-issue
- description: Get available workflow transitions.
  hints:
    idempotent: true
    readOnly: true
  name: get-transitions
- description: Transition an issue through its workflow.
  hints:
    readOnly: false
  name: do-transition
- description: Get comments on a Jira issue.
  hints:
    idempotent: true
    readOnly: true
  name: get-comments
- description: Add a comment to a Jira issue.
  hints:
    readOnly: false
  name: add-comment
- description: Search Jira issues using JQL.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-issues
- description: List all Jira projects.
  hints:
    idempotent: true
    readOnly: true
  name: list-projects
- description: Get Jira project details.
  hints:
    idempotent: true
    readOnly: true
  name: get-project
- description: Get all Jira issue statuses.
  hints:
    idempotent: true
    readOnly: true
  name: get-statuses
- description: Get all Jira issue types.
  hints:
    idempotent: true
    readOnly: true
  name: get-issue-types
- description: Get all Jira priorities.
  hints:
    idempotent: true
    readOnly: true
  name: get-priorities
---
