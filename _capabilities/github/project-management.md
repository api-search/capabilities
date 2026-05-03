---
categories: []
consumed_apis:
- github-issues
- github-projects
- github-search
description: Unified workflow for project management combining issues, projects, milestones, labels, and search. Used by project managers and team leads for tracking work, organizing sprints, and managing deliverables.
layout: capability
name: GitHub Project Management
operations:
- description: List issues
  method: GET
  name: listRepositoryIssues
  path: /v1/repositories/{owner}/{repo}/issues
- description: Create an issue
  method: POST
  name: createAnIssue
  path: /v1/repositories/{owner}/{repo}/issues
- description: Get an issue
  method: GET
  name: getAnIssue
  path: /v1/repositories/{owner}/{repo}/issues/{issue_number}
- description: Update an issue
  method: PATCH
  name: updateAnIssue
  path: /v1/repositories/{owner}/{repo}/issues/{issue_number}
- description: List milestones
  method: GET
  name: listMilestones
  path: /v1/repositories/{owner}/{repo}/milestones
- description: Create a milestone
  method: POST
  name: createMilestone
  path: /v1/repositories/{owner}/{repo}/milestones
- description: List labels
  method: GET
  name: listLabelsForRepository
  path: /v1/repositories/{owner}/{repo}/labels
- description: Create a label
  method: POST
  name: createLabel
  path: /v1/repositories/{owner}/{repo}/labels
- description: Get a project
  method: GET
  name: getProject
  path: /v1/projects/{project_id}
- description: Update a project
  method: PATCH
  name: updateProject
  path: /v1/projects/{project_id}
- description: List columns
  method: GET
  name: listProjectColumns
  path: /v1/projects/{project_id}/columns
- description: Create a column
  method: POST
  name: createProjectColumn
  path: /v1/projects/{project_id}/columns
- description: Search issues and pull requests
  method: GET
  name: searchIssuesAndPullRequests
  path: /v1/search/issues
personas: []
provider_name: GitHub
provider_slug: github
search_terms:
- projects
- list project columns
- searchIssuesAndPullRequests
- milestone management
- source control
- github
- create a project card
- issues
- get a project
- createProjectColumn
- create an issue comment
- list timeline events for an issue
- milestones
- label management
- list labels
- list columns
- listLabelsForRepository
- create card
- project operations
- lock issue
- create a column
- platform
- list issue comments
- search
- updateAnIssue
- create issue
- code
- createMilestone
- list cards
- create issue comment
- createLabel
- add labels to an issue
- add labels
- create a project column
- create milestone
- updateProject
- move card
- issue management
- createAnIssue
- get an issue
- project management
- list issues
- create an issue
- individual issue operations
- update an issue
- getProject
- issue and pr search
- getAnIssue
- get project
- t1
- search issues and pull requests
- listRepositoryIssues
- update issue
- create a milestone
- project column management
- lock an issue
- update a project
- listProjectColumns
- update project
- create column
- create a label
- create label
- move a project card
- listMilestones
- list timeline events
- pipelines
- search labels
- add assignees
- add assignees to an issue
- search issues
- get issue
- list project cards
- software development
- list repository issues
- list milestones
slug: project-management
source_filename: project-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"GitHub Project Management\"\n  description: \"Unified workflow for project management combining issues, projects, milestones, labels, and search. Used by project managers and team leads for tracking work, organizing sprints, and managing deliverables.\"\n  tags:\n    - GitHub\n    - Project Management\n    - Issues\n    - Projects\n    - Milestones\n    - Search\n  personas:\n    - project managers\n    - team leads\n    - scrum masters\n    - product owners\n  created: \"2026-04-17\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GITHUB_TOKEN: GITHUB_TOKEN\n\ncapability:\n  consumes:\n    - import: github-issues\n      location: \"./shared/issues.yaml\"\n    - import: github-projects\n      location: \"./shared/projects.yaml\"\n    - import: github-search\n      location: \"./shared/search.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: github-project-management-api\n   \
  \   description: \"Unified REST API for project management workflows combining issues, projects, and search.\"\n      resources:\n        - path: /v1/repositories/{owner}/{repo}/issues\n          name: issues\n          description: \"Issue management\"\n          operations:\n            - method: GET\n              name: listRepositoryIssues\n              description: \"List issues\"\n              call: \"github-issues.listRepositoryIssues\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createAnIssue\n              description: \"Create an issue\"\n              call: \"github-issues.createAnIssue\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/issues/{issue_number}\n          name: issue\n          description: \"Individual issue operations\"\n          operations:\n           \
  \ - method: GET\n              name: getAnIssue\n              description: \"Get an issue\"\n              call: \"github-issues.getAnIssue\"\n              with:\n                issue_number: \"rest.issue_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: updateAnIssue\n              description: \"Update an issue\"\n              call: \"github-issues.updateAnIssue\"\n              with:\n                issue_number: \"rest.issue_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/milestones\n          name: milestones\n          description: \"Milestone management\"\n          operations:\n            - method: GET\n              name: listMilestones\n              description: \"List milestones\"\n              call: \"github-issues.listMilestones\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createMilestone\n              description: \"Create a milestone\"\n              call: \"github-issues.createMilestone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/labels\n          name: labels\n          description: \"Label management\"\n          operations:\n            - method: GET\n              name: listLabelsForRepository\n              description: \"List labels\"\n              call: \"github-issues.listLabelsForRepository\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createLabel\n              description: \"Create a label\"\n              call: \"github-issues.createLabel\"\n              outputParameters:\n                - type: object\n         \
  \         mapping: \"$.\"\n        - path: /v1/projects/{project_id}\n          name: project\n          description: \"Project operations\"\n          operations:\n            - method: GET\n              name: getProject\n              description: \"Get a project\"\n              call: \"github-projects.getProject\"\n              with:\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: updateProject\n              description: \"Update a project\"\n              call: \"github-projects.updateProject\"\n              with:\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{project_id}/columns\n          name: columns\n          description: \"Project column management\"\n          operations:\n            - method:\
  \ GET\n              name: listProjectColumns\n              description: \"List columns\"\n              call: \"github-projects.listProjectColumns\"\n              with:\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createProjectColumn\n              description: \"Create a column\"\n              call: \"github-projects.createProjectColumn\"\n              with:\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search/issues\n          name: issue-search\n          description: \"Issue and PR search\"\n          operations:\n            - method: GET\n              name: searchIssuesAndPullRequests\n              description: \"Search issues and pull requests\"\n              call: \"github-search.searchIssuesAndPullRequests\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: github-project-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted project management workflows.\"\n      tools:\n        - name: list-issues\n          description: \"List repository issues\"\n          call: \"github-issues.listRepositoryIssues\"\n          hints:\n            readOnly: true\n        - name: create-issue\n          description: \"Create an issue\"\n          call: \"github-issues.createAnIssue\"\n        - name: get-issue\n          description: \"Get an issue\"\n          call: \"github-issues.getAnIssue\"\n          hints:\n            readOnly: true\n        - name: update-issue\n          description: \"Update an issue\"\n          call: \"github-issues.updateAnIssue\"\n          hints:\n            idempotent: true\n        - name: lock-issue\n          description: \"Lock an\
  \ issue\"\n          call: \"github-issues.lockAnIssue\"\n        - name: list-issue-comments\n          description: \"List issue comments\"\n          call: \"github-issues.listIssueComments\"\n          hints:\n            readOnly: true\n        - name: create-issue-comment\n          description: \"Create an issue comment\"\n          call: \"github-issues.createAnIssueComment\"\n        - name: add-assignees\n          description: \"Add assignees to an issue\"\n          call: \"github-issues.addAssigneesToAnIssue\"\n        - name: add-labels\n          description: \"Add labels to an issue\"\n          call: \"github-issues.addLabelsToAnIssue\"\n        - name: list-milestones\n          description: \"List milestones\"\n          call: \"github-issues.listMilestones\"\n          hints:\n            readOnly: true\n        - name: create-milestone\n          description: \"Create a milestone\"\n          call: \"github-issues.createMilestone\"\n        - name: list-labels\n  \
  \        description: \"List labels\"\n          call: \"github-issues.listLabelsForRepository\"\n          hints:\n            readOnly: true\n        - name: create-label\n          description: \"Create a label\"\n          call: \"github-issues.createLabel\"\n        - name: get-project\n          description: \"Get a project\"\n          call: \"github-projects.getProject\"\n          hints:\n            readOnly: true\n        - name: update-project\n          description: \"Update a project\"\n          call: \"github-projects.updateProject\"\n          hints:\n            idempotent: true\n        - name: list-columns\n          description: \"List project columns\"\n          call: \"github-projects.listProjectColumns\"\n          hints:\n            readOnly: true\n        - name: create-column\n          description: \"Create a project column\"\n          call: \"github-projects.createProjectColumn\"\n        - name: list-cards\n          description: \"List project cards\"\n\
  \          call: \"github-projects.listProjectCards\"\n          hints:\n            readOnly: true\n        - name: create-card\n          description: \"Create a project card\"\n          call: \"github-projects.createProjectCard\"\n        - name: move-card\n          description: \"Move a project card\"\n          call: \"github-projects.moveProjectCard\"\n        - name: search-issues\n          description: \"Search issues and pull requests\"\n          call: \"github-search.searchIssuesAndPullRequests\"\n          hints:\n            readOnly: true\n        - name: search-labels\n          description: \"Search labels\"\n          call: \"github-search.searchLabels\"\n          hints:\n            readOnly: true\n        - name: list-timeline-events\n          description: \"List timeline events for an issue\"\n          call: \"github-issues.listTimelineEventsForAnIssue\"\n          hints:\n            readOnly: true\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/project-management.yaml
tags:
- GitHub
- Project Management
- Issues
- Projects
- Milestones
- Search
tools:
- description: List repository issues
  hints:
    readOnly: true
  name: list-issues
- description: Create an issue
  hints: {}
  name: create-issue
- description: Get an issue
  hints:
    readOnly: true
  name: get-issue
- description: Update an issue
  hints:
    idempotent: true
  name: update-issue
- description: Lock an issue
  hints: {}
  name: lock-issue
- description: List issue comments
  hints:
    readOnly: true
  name: list-issue-comments
- description: Create an issue comment
  hints: {}
  name: create-issue-comment
- description: Add assignees to an issue
  hints: {}
  name: add-assignees
- description: Add labels to an issue
  hints: {}
  name: add-labels
- description: List milestones
  hints:
    readOnly: true
  name: list-milestones
- description: Create a milestone
  hints: {}
  name: create-milestone
- description: List labels
  hints:
    readOnly: true
  name: list-labels
- description: Create a label
  hints: {}
  name: create-label
- description: Get a project
  hints:
    readOnly: true
  name: get-project
- description: Update a project
  hints:
    idempotent: true
  name: update-project
- description: List project columns
  hints:
    readOnly: true
  name: list-columns
- description: Create a project column
  hints: {}
  name: create-column
- description: List project cards
  hints:
    readOnly: true
  name: list-cards
- description: Create a project card
  hints: {}
  name: create-card
- description: Move a project card
  hints: {}
  name: move-card
- description: Search issues and pull requests
  hints:
    readOnly: true
  name: search-issues
- description: Search labels
  hints:
    readOnly: true
  name: search-labels
- description: List timeline events for an issue
  hints:
    readOnly: true
  name: list-timeline-events
---
