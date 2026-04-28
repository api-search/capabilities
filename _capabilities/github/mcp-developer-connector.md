---
categories:
- developer-experience
- collaboration
consumed_apis:
- github-rest
description: Governed in-IDE GitHub access via MCP for enterprise developers. Surfaces assigned issues, pull requests, branches, file content, and CI workflow runs directly inside VS Code and Copilot, with security-team-ready operations metadata so platform teams can roll out an MCP-served GitHub connector across thousands of engineers without exposing raw PATs or unscoped repo access.
layout: capability
name: GitHub MCP Developer Connector
operations:
- description: List issues assigned to the authenticated developer across the enterprise
  method: GET
  name: list-assigned-issues
  path: /issues
- description: List pull requests for a repository, filtered to the developer's open work
  method: GET
  name: list-pull-requests
  path: /repos/{owner}/{repo}/pulls
- description: Create a new branch reference in a repository for in-IDE feature work
  method: POST
  name: create-branch
  path: /repos/{owner}/{repo}/git/refs
- description: Get the contents of a file at a specific path and ref for code context
  method: GET
  name: get-repo-file-content
  path: /repos/{owner}/{repo}/contents/{path}
- description: List recent GitHub Actions workflow runs for a repository to triage CI failures
  method: GET
  name: list-workflow-runs
  path: /repos/{owner}/{repo}/actions/runs
- description: Add a review comment to an open pull request from inside the IDE
  method: POST
  name: comment-on-pull-request
  path: /repos/{owner}/{repo}/pulls/{pull_number}/comments
personas:
- Developer
- Engineering Manager
provider_name: GitHub
provider_slug: github
search_terms:
- list issues assigned to me
- list pull requests for a repo
- create a feature branch from inside the ide
- mcp server for github inside vs code and copilot
- enterprise developer connector
- governed github access
- in-ide github context
- read repo file contents at a specific ref
- list workflow runs to triage ci failures
- comment on a pull request
- pull request review from the editor
- assigned issues across the enterprise
- security-reviewed github mcp connector
- ford-style enterprise developer rollout
- github inside copilot
- developer experience
- platform engineering
- Developer
- governed scopes for github personal access tokens
- list github actions runs
- create branch ref
- mcp connector for source control
- ci/cd triage
- list my open prs
slug: mcp-developer-connector
tags:
- GitHub
- MCP
- Developer Experience
- Source Control
- IDE Integration
tools:
- description: List issues assigned to the authenticated developer across all enterprise repositories
  hints:
    openWorld: false
    readOnly: true
  name: list-assigned-issues
- description: List pull requests for a given repository, scoped to the developer's open work
  hints:
    openWorld: false
    readOnly: true
  name: list-pull-requests
- description: Create a new branch reference in a repository so the developer can start feature work without leaving the IDE
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-branch
- description: Read the contents of a file at a specific path and ref to give Copilot live repo context
  hints:
    openWorld: false
    readOnly: true
  name: get-repo-file-content
- description: List recent GitHub Actions workflow runs for a repository to help triage CI failures inline
  hints:
    openWorld: false
    readOnly: true
  name: list-workflow-runs
- description: Add a review comment to an open pull request from inside the IDE
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: comment-on-pull-request
---
