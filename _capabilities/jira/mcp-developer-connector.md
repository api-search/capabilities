---
categories:
- developer-experience
- collaboration
consumed_apis:
- jira-cloud-rest
description: In-IDE Jira context for assigned tickets and sprint work via MCP. Lets enterprise developers see their assigned issues, drill into details, transition status, comment, and log work without leaving VS Code or Copilot. Operations metadata is shaped for security-team review so platform teams can govern an MCP-served Jira connector across thousands of engineers.
layout: capability
name: Jira MCP Developer Connector
operations:
- description: Search for issues assigned to the current developer using JQL
  method: GET
  name: list-assigned-issues
  path: /rest/api/3/search
- description: Get full details for a specific Jira issue including fields, status, and comments
  method: GET
  name: get-issue-details
  path: /rest/api/3/issue/{issueIdOrKey}
- description: Transition a Jira issue to a new workflow status from inside the IDE
  method: POST
  name: transition-issue-status
  path: /rest/api/3/issue/{issueIdOrKey}/transitions
- description: Add a comment to a Jira issue from the developer's editor context
  method: POST
  name: add-issue-comment
  path: /rest/api/3/issue/{issueIdOrKey}/comment
- description: Log a worklog entry against an issue to capture time spent in the IDE
  method: POST
  name: log-work
  path: /rest/api/3/issue/{issueIdOrKey}/worklog
- description: List available transitions for an issue so the IDE can offer valid status moves
  method: GET
  name: list-issue-transitions
  path: /rest/api/3/issue/{issueIdOrKey}/transitions
personas:
- Developer
- Engineering Manager
provider_name: Jira
provider_slug: jira
search_terms:
- list jira issues assigned to me
- jql search for assigned tickets
- get jira issue details
- transition issue from in progress to done
- add comment to jira ticket from the ide
- log work against a jira issue
- in-ide jira context for sprint work
- mcp server for jira inside vs code and copilot
- governed jira connector for enterprise developers
- ford-style sprint work from the editor
- list issue transitions
- developer ticket triage
- copilot jira integration
- security-reviewed jira mcp
- enterprise atlassian governance
- Developer
- assigned issues
- update ticket status
- worklog logging
- sprint context in copilot
- jira cloud rest
- mcp connector for project tracking
slug: mcp-developer-connector
tags:
- Jira
- MCP
- Developer Experience
- Project Tracking
- IDE Integration
tools:
- description: Search Jira for issues assigned to the current developer using a JQL query
  hints:
    openWorld: false
    readOnly: true
  name: list-assigned-issues
- description: Get full details for a specific Jira issue including fields, status, and comments
  hints:
    openWorld: false
    readOnly: true
  name: get-issue-details
- description: Transition a Jira issue to a new workflow status from inside the IDE
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: transition-issue-status
- description: Add a comment to a Jira issue from the developer's editor context
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-issue-comment
- description: Log a worklog entry against a Jira issue to capture time spent on the work
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: log-work
- description: List the available workflow transitions for an issue so the IDE can offer valid status moves
  hints:
    openWorld: false
    readOnly: true
  name: list-issue-transitions
---
