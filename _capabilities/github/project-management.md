---
categories: []
consumed_apis: []
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
- github
- issues
- list issues
- list columns
- getProject
- update issue
- list cards
- createMilestone
- create issue
- add labels to an issue
- add labels
- list milestones
- pipelines
- updateAnIssue
- create card
- platform
- create a project column
- move card
- listRepositoryIssues
- list issue comments
- create a project card
- add assignees to an issue
- get a project
- update an issue
- list timeline events
- createLabel
- searchIssuesAndPullRequests
- lock issue
- create an issue
- create milestone
- project management
- list project cards
- get issue
- listMilestones
- add assignees
- listLabelsForRepository
- search issues
- create issue comment
- create a column
- createAnIssue
- create a milestone
- search labels
- list repository issues
- software development
- milestone management
- t1
- list labels
- milestones
- create an issue comment
- source control
- list project columns
- update a project
- getAnIssue
- issue management
- projects
- project column management
- get project
- issue and pr search
- updateProject
- project operations
- get an issue
- listProjectColumns
- search
- lock an issue
- create label
- createProjectColumn
- code
- search issues and pull requests
- label management
- list timeline events for an issue
- create a label
- individual issue operations
- update project
- move a project card
- create column
slug: project-management
source_filename: project-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GitHub Project Management\n  description: Unified workflow for project management combining issues, projects, milestones, labels, and search. Used by\n    project managers and team leads for tracking work, organizing sprints, and managing deliverables.\n  tags:\n  - GitHub\n  - Project Management\n  - Issues\n  - Projects\n  - Milestones\n  - Search\n  personas:\n  - project managers\n  - team leads\n  - scrum masters\n  - product owners\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GITHUB_TOKEN: GITHUB_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: github-issues\n    baseUri: https://api.github.com\n    description: GitHub REST API for issues, labels, milestones, assignees, comments, and reactions.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: issues\n      path: /repos/{owner}/{repo}/issues\n      description: Issue\
  \ CRUD and listing operations.\n      operations:\n      - name: listRepositoryIssues\n        method: GET\n        description: List repository issues.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createAnIssue\n        method: POST\n        description: Create an issue.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnIssue\n        method: GET\n        path: /repos/{owner}/{repo}/issues/{issue_number}\n        description: Get an issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateAnIssue\n        method: PATCH\n        path: /repos/{owner}/{repo}/issues/{issue_number}\n        description: Update an issue.\n        body:\n          type: json\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: lockAnIssue\n        method: PUT\n        path: /repos/{owner}/{repo}/issues/{issue_number}/lock\n        description: Lock an issue.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unlockAnIssue\n        method: DELETE\n        path: /repos/{owner}/{repo}/issues/{issue_number}/lock\n        description: Unlock an issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issue-comments\n      path: /repos/{owner}/{repo}/issues\n      description: Issue comment management.\n      operations:\n      - name: listIssueComments\n        method: GET\n        path: /repos/{owner}/{repo}/issues/{issue_number}/comments\n        description: List issue comments.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createAnIssueComment\n        method: POST\n        path: /repos/{owner}/{repo}/issues/{issue_number}/comments\n        description: Create an issue comment.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnIssueComment\n        method: GET\n        path: /repos/{owner}/{repo}/issues/comments/{comment_id}\n        description: Get an issue comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateAnIssueComment\n        method: PATCH\n        path: /repos/{owner}/{repo}/issues/comments/{comment_id}\n        description: Update an issue comment.\n        body:\n          type: json\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnIssueComment\n        method: DELETE\n        path: /repos/{owner}/{repo}/issues/comments/{comment_id}\n        description: Delete an issue comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listIssueCommentsForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/issues/comments\n        description: List issue comments for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assignees\n      path: /repos/{owner}/{repo}\n      description: Issue assignee management.\n      operations:\n      - name: listAssignees\n        method: GET\n        path: /repos/{owner}/{repo}/assignees\n        description: List assignees.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: checkIfUserCanBeAssigned\n        method: GET\n        path: /repos/{owner}/{repo}/assignees/{assignee}\n        description: Check if a user can be assigned.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addAssigneesToAnIssue\n        method: POST\n        path: /repos/{owner}/{repo}/issues/{issue_number}/assignees\n        description: Add assignees to an issue.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeAssigneesFromAnIssue\n        method: DELETE\n        path: /repos/{owner}/{repo}/issues/{issue_number}/assignees\n        description: Remove assignees from an issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: labels\n      path: /repos/{owner}/{repo}/labels\n      description: Label management for repositories and issues.\n      operations:\n      - name: listLabelsForRepository\n        method: GET\n        description: List labels for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createLabel\n        method: POST\n        description: Create a label.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getLabel\n        method: GET\n        path: /repos/{owner}/{repo}/labels/{name}\n        description: Get a label.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateLabel\n        method: PATCH\n        path: /repos/{owner}/{repo}/labels/{name}\n\
  \        description: Update a label.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteLabel\n        method: DELETE\n        path: /repos/{owner}/{repo}/labels/{name}\n        description: Delete a label.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listLabelsForAnIssue\n        method: GET\n        path: /repos/{owner}/{repo}/issues/{issue_number}/labels\n        description: List labels for an issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addLabelsToAnIssue\n        method: POST\n        path: /repos/{owner}/{repo}/issues/{issue_number}/labels\n        description: Add labels to an issue.\n        body:\n          type: json\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeAllLabelsFromAnIssue\n        method: DELETE\n        path: /repos/{owner}/{repo}/issues/{issue_number}/labels\n        description: Remove all labels from an issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeLabelFromAnIssue\n        method: DELETE\n        path: /repos/{owner}/{repo}/issues/{issue_number}/labels/{name}\n        description: Remove a label from an issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: milestones\n      path: /repos/{owner}/{repo}/milestones\n      description: Milestone management.\n      operations:\n      - name: listMilestones\n        method: GET\n        description: List milestones.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createMilestone\n        method: POST\n        description: Create a milestone.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getMilestone\n        method: GET\n        path: /repos/{owner}/{repo}/milestones/{milestone_number}\n        description: Get a milestone.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateMilestone\n        method: PATCH\n        path: /repos/{owner}/{repo}/milestones/{milestone_number}\n        description: Update a milestone.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteMilestone\n        method: DELETE\n      \
  \  path: /repos/{owner}/{repo}/milestones/{milestone_number}\n        description: Delete a milestone.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reactions\n      path: /repos/{owner}/{repo}/issues\n      description: Issue and comment reaction management.\n      operations:\n      - name: listReactionsForAnIssue\n        method: GET\n        path: /repos/{owner}/{repo}/issues/{issue_number}/reactions\n        description: List reactions for an issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createReactionForAnIssue\n        method: POST\n        path: /repos/{owner}/{repo}/issues/{issue_number}/reactions\n        description: Create reaction for an issue.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deleteAnIssueReaction\n        method: DELETE\n        path: /repos/{owner}/{repo}/issues/{issue_number}/reactions/{reaction_id}\n        description: Delete an issue reaction.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listReactionsForAnIssueComment\n        method: GET\n        path: /repos/{owner}/{repo}/issues/comments/{comment_id}/reactions\n        description: List reactions for an issue comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createReactionForAnIssueComment\n        method: POST\n        path: /repos/{owner}/{repo}/issues/comments/{comment_id}/reactions\n        description: Create reaction for an issue comment.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n      - name: deleteAnIssueCommentReaction\n        method: DELETE\n        path: /repos/{owner}/{repo}/issues/comments/{comment_id}/reactions/{reaction_id}\n        description: Delete an issue comment reaction.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timeline\n      path: /repos/{owner}/{repo}/issues/{issue_number}/timeline\n      description: Issue timeline events.\n      operations:\n      - name: listTimelineEventsForAnIssue\n        method: GET\n        description: List timeline events for an issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issue-events\n      path: /repos/{owner}/{repo}/issues/events\n      description: Issue event listing.\n      operations:\n      - name: listIssueEventsForRepository\n        method: GET\n        description:\
  \ List issue events for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnIssueEvent\n        method: GET\n        path: /repos/{owner}/{repo}/issues/events/{event_id}\n        description: Get an issue event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listIssueEvents\n        method: GET\n        path: /repos/{owner}/{repo}/issues/{issue_number}/events\n        description: List events for an issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: github-projects\n    baseUri: https://api.github.com\n    description: GitHub REST API for projects, columns, cards, and collaborators.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n\
  \    - name: projects\n      path: /projects\n      description: Project CRUD operations.\n      operations:\n      - name: getProject\n        method: GET\n        path: /projects/{project_id}\n        description: Get a project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateProject\n        method: PATCH\n        path: /projects/{project_id}\n        description: Update a project.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteProject\n        method: DELETE\n        path: /projects/{project_id}\n        description: Delete a project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listOrganizationProjects\n        method: GET\n        path: /orgs/{org}/projects\n\
  \        description: List organization projects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createAnOrganizationProject\n        method: POST\n        path: /orgs/{org}/projects\n        description: Create an organization project.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoryProjects\n        method: GET\n        path: /repos/{owner}/{repo}/projects\n        description: List repository projects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createRepositoryProject\n        method: POST\n        path: /repos/{owner}/{repo}/projects\n        description: Create a repository project.\n        body:\n          type: json\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createUserProject\n        method: POST\n        path: /user/projects\n        description: Create a user project.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listUserProjects\n        method: GET\n        path: /users/{username}/projects\n        description: List user projects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: columns\n      path: /projects/{project_id}/columns\n      description: Project column management.\n      operations:\n      - name: listProjectColumns\n        method: GET\n        description: List project columns.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n      - name: createProjectColumn\n        method: POST\n        description: Create a project column.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getProjectColumn\n        method: GET\n        path: /projects/columns/{column_id}\n        description: Get a project column.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateAnExistingProjectColumn\n        method: PATCH\n        path: /projects/columns/{column_id}\n        description: Update a project column.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteProjectColumn\n        method: DELETE\n        path: /projects/columns/{column_id}\n        description:\
  \ Delete a project column.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: moveProjectColumn\n        method: POST\n        path: /projects/columns/{column_id}/moves\n        description: Move a project column.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cards\n      path: /projects/columns/{column_id}/cards\n      description: Project card management.\n      operations:\n      - name: listProjectCards\n        method: GET\n        description: List project cards.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createProjectCard\n        method: POST\n        description: Create a project card.\n        body:\n          type: json\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getProjectCard\n        method: GET\n        path: /projects/columns/cards/{card_id}\n        description: Get a project card.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateAnExistingProjectCard\n        method: PATCH\n        path: /projects/columns/cards/{card_id}\n        description: Update a project card.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteProjectCard\n        method: DELETE\n        path: /projects/columns/cards/{card_id}\n        description: Delete a project card.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: moveProjectCard\n       \
  \ method: POST\n        path: /projects/columns/cards/{card_id}/moves\n        description: Move a project card.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collaborators\n      path: /projects/{project_id}/collaborators\n      description: Project collaborator management.\n      operations:\n      - name: listProjectCollaborators\n        method: GET\n        description: List project collaborators.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addProjectCollaborator\n        method: PUT\n        path: /projects/{project_id}/collaborators/{username}\n        description: Add a project collaborator.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: removeUserAsCollaborator\n        method: DELETE\n        path: /projects/{project_id}/collaborators/{username}\n        description: Remove a user as collaborator.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getProjectPermissionForUser\n        method: GET\n        path: /projects/{project_id}/collaborators/{username}/permission\n        description: Get project permission for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: github-search\n    baseUri: https://api.github.com\n    description: GitHub REST API for searching code, commits, issues, labels, repositories, topics, and users.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: search\n      path: /search\n      description: Search operations across\
  \ GitHub.\n      operations:\n      - name: searchCode\n        method: GET\n        path: /search/code\n        description: Search code.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchCommits\n        method: GET\n        path: /search/commits\n        description: Search commits.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchIssuesAndPullRequests\n        method: GET\n        path: /search/issues\n        description: Search issues and pull requests.\n        inputParameters:\n     \
  \   - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchLabels\n        method: GET\n        path: /search/labels\n        description: Search labels.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: repository_id\n          in: query\n          type: integer\n          required: true\n          description: Repository ID to search labels in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchRepositories\n        method: GET\n        path: /search/repositories\n        description: Search repositories.\n        inputParameters:\n        - name: q\n          in:\
  \ query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchTopics\n        method: GET\n        path: /search/topics\n        description: Search topics.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchUsers\n        method: GET\n        path: /search/users\n        description: Search users.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: github-project-management-api\n    description: Unified REST API for project management workflows combining issues, projects, and search.\n    resources:\n    - path: /v1/repositories/{owner}/{repo}/issues\n      name: issues\n      description: Issue management\n      operations:\n      - method: GET\n        name: listRepositoryIssues\n        description: List issues\n        call: github-issues.listRepositoryIssues\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: createAnIssue\n        description: Create an issue\n        call: github-issues.createAnIssue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{owner}/{repo}/issues/{issue_number}\n      name: issue\n      description: Individual issue operations\n      operations:\n      - method: GET\n        name: getAnIssue\n        description: Get\
  \ an issue\n        call: github-issues.getAnIssue\n        with:\n          issue_number: rest.issue_number\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: updateAnIssue\n        description: Update an issue\n        call: github-issues.updateAnIssue\n        with:\n          issue_number: rest.issue_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{owner}/{repo}/milestones\n      name: milestones\n      description: Milestone management\n      operations:\n      - method: GET\n        name: listMilestones\n        description: List milestones\n        call: github-issues.listMilestones\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: createMilestone\n        description: Create a milestone\n        call: github-issues.createMilestone\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/repositories/{owner}/{repo}/labels\n      name: labels\n      description: Label management\n      operations:\n      - method: GET\n        name: listLabelsForRepository\n        description: List labels\n        call: github-issues.listLabelsForRepository\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: createLabel\n        description: Create a label\n        call: github-issues.createLabel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project_id}\n      name: project\n      description: Project operations\n      operations:\n      - method: GET\n        name: getProject\n        description: Get a project\n        call: github-projects.getProject\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: updateProject\n        description:\
  \ Update a project\n        call: github-projects.updateProject\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project_id}/columns\n      name: columns\n      description: Project column management\n      operations:\n      - method: GET\n        name: listProjectColumns\n        description: List columns\n        call: github-projects.listProjectColumns\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: createProjectColumn\n        description: Create a column\n        call: github-projects.createProjectColumn\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search/issues\n      name: issue-search\n      description: Issue and PR search\n      operations:\n      - method:\
  \ GET\n        name: searchIssuesAndPullRequests\n        description: Search issues and pull requests\n        call: github-search.searchIssuesAndPullRequests\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: github-project-management-mcp\n    transport: http\n    description: MCP server for AI-assisted project management workflows.\n    tools:\n    - name: list-issues\n      description: List repository issues\n      call: github-issues.listRepositoryIssues\n      hints:\n        readOnly: true\n    - name: create-issue\n      description: Create an issue\n      call: github-issues.createAnIssue\n    - name: get-issue\n      description: Get an issue\n      call: github-issues.getAnIssue\n      hints:\n        readOnly: true\n    - name: update-issue\n      description: Update an issue\n      call: github-issues.updateAnIssue\n      hints:\n        idempotent: true\n    - name: lock-issue\n      description: Lock\
  \ an issue\n      call: github-issues.lockAnIssue\n    - name: list-issue-comments\n      description: List issue comments\n      call: github-issues.listIssueComments\n      hints:\n        readOnly: true\n    - name: create-issue-comment\n      description: Create an issue comment\n      call: github-issues.createAnIssueComment\n    - name: add-assignees\n      description: Add assignees to an issue\n      call: github-issues.addAssigneesToAnIssue\n    - name: add-labels\n      description: Add labels to an issue\n      call: github-issues.addLabelsToAnIssue\n    - name: list-milestones\n      description: List milestones\n      call: github-issues.listMilestones\n      hints:\n        readOnly: true\n    - name: create-milestone\n      description: Create a milestone\n      call: github-issues.createMilestone\n    - name: list-labels\n      description: List labels\n      call: github-issues.listLabelsForRepository\n      hints:\n        readOnly: true\n    - name: create-label\n  \
  \    description: Create a label\n      call: github-issues.createLabel\n    - name: get-project\n      description: Get a project\n      call: github-projects.getProject\n      hints:\n        readOnly: true\n    - name: update-project\n      description: Update a project\n      call: github-projects.updateProject\n      hints:\n        idempotent: true\n    - name: list-columns\n      description: List project columns\n      call: github-projects.listProjectColumns\n      hints:\n        readOnly: true\n    - name: create-column\n      description: Create a project column\n      call: github-projects.createProjectColumn\n    - name: list-cards\n      description: List project cards\n      call: github-projects.listProjectCards\n      hints:\n        readOnly: true\n    - name: create-card\n      description: Create a project card\n      call: github-projects.createProjectCard\n    - name: move-card\n      description: Move a project card\n      call: github-projects.moveProjectCard\n\
  \    - name: search-issues\n      description: Search issues and pull requests\n      call: github-search.searchIssuesAndPullRequests\n      hints:\n        readOnly: true\n    - name: search-labels\n      description: Search labels\n      call: github-search.searchLabels\n      hints:\n        readOnly: true\n    - name: list-timeline-events\n      description: List timeline events for an issue\n      call: github-issues.listTimelineEventsForAnIssue\n      hints:\n        readOnly: true\n"
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
