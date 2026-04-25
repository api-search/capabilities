---
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
- software development
- update an issue
- list issues
- create an issue comment
- create milestone
- createAnIssue
- create label
- create column
- list labels
- milestones
- create a label
- listMilestones
- issue management
- add labels
- list repository issues
- get issue
- lock an issue
- add assignees to an issue
- platform
- move a project card
- list timeline events
- update project
- source control
- getProject
- updateProject
- create a column
- issue and pr search
- searchIssuesAndPullRequests
- project management
- list project columns
- issues
- move card
- update issue
- get project
- code
- list columns
- search issues
- pipelines
- milestone management
- createProjectColumn
- createLabel
- create an issue
- projects
- search
- listProjectColumns
- individual issue operations
- project column management
- create card
- github
- list milestones
- update a project
- create issue
- lock issue
- add assignees
- getAnIssue
- listLabelsForRepository
- add labels to an issue
- create a project column
- search issues and pull requests
- create issue comment
- create a project card
- project operations
- list project cards
- listRepositoryIssues
- get an issue
- get a project
- search labels
- list timeline events for an issue
- createMilestone
- list issue comments
- list cards
- create a milestone
- t1
- updateAnIssue
- label management
slug: project-management
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
