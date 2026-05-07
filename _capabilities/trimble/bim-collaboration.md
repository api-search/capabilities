---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Bim Collaboration
operations: []
personas: []
provider_name: Trimble
provider_slug: trimble
search_terms:
- fleet management
- transportation
- bim
- agriculture
- collaboration
- geospatial
- mapping
- gps
- construction
slug: bim-collaboration
source_filename: bim-collaboration.yaml
source_heading: Capability Spec
source_yaml: "name: BIM Collaboration\ndescription: >-\n  Workflow capability for BIM coordination and construction collaboration using\n  Trimble Connect. Supports project setup, model file management, BCF issue tracking,\n  and team member coordination for AEC project workflows.\nversion: \"1.0\"\n\nimports:\n  - capabilities/shared/trimble-connect.yaml\n\ntools:\n  - name: list-projects\n    description: List all accessible Trimble Connect construction projects\n    operationRef: trimble-connect/listProjects\n    inputs:\n      - name: page\n        description: Page number for paginated results\n        required: false\n      - name: pageSize\n        description: Number of projects per page (max 100)\n        required: false\n\n  - name: create-project\n    description: Create a new Trimble Connect project for BIM coordination\n    operationRef: trimble-connect/createProject\n    inputs:\n      - name: name\n        description: Project name\n        required: true\n      - name: description\n\
  \        description: Project description\n        required: false\n      - name: type\n        description: \"Project type: CONSTRUCTION, INFRASTRUCTURE, ENGINEERING\"\n        required: false\n      - name: location\n        description: Physical project location\n        required: false\n\n  - name: get-project\n    description: Retrieve full details for a specific Trimble Connect project\n    operationRef: trimble-connect/getProject\n    inputs:\n      - name: projectId\n        description: Unique project identifier\n        required: true\n\n  - name: upload-model-file\n    description: Upload a BIM model or document to a project folder (IFC, RVT, SKP, NWD, PDF, DWG)\n    operationRef: trimble-connect/uploadFile\n    inputs:\n      - name: projectId\n        description: Target project identifier\n        required: true\n      - name: file\n        description: Binary file content\n        required: true\n      - name: path\n        description: Target folder path (e.g., /Models/Structural)\n\
  \        required: false\n\n  - name: list-project-files\n    description: Browse files and folders in a project directory\n    operationRef: trimble-connect/listProjectFiles\n    inputs:\n      - name: projectId\n        description: Project identifier\n        required: true\n      - name: path\n        description: Folder path to list (default is root)\n        required: false\n\n  - name: create-clash-issue\n    description: Create a BCF topic to record a clash or coordination issue in a BIM model\n    operationRef: trimble-connect/createBCFTopic\n    inputs:\n      - name: projectId\n        description: Project identifier\n        required: true\n      - name: topicType\n        description: \"Issue type: ISSUE, CLASH, REQUEST_FOR_INFORMATION, TASK\"\n        required: true\n      - name: title\n        description: Short descriptive title for the clash or issue\n        required: true\n      - name: description\n        description: Detailed description of the clash or coordination\
  \ issue\n        required: false\n      - name: priority\n        description: \"Priority level: LOW, MEDIUM, HIGH, CRITICAL\"\n        required: false\n      - name: assignedTo\n        description: Email or user ID of the person responsible for resolution\n        required: false\n      - name: dueDate\n        description: Target resolution date (ISO 8601)\n        required: false\n\n  - name: list-bcf-topics\n    description: List BCF issues and clash records for a project with optional filters\n    operationRef: trimble-connect/listBCFTopics\n    inputs:\n      - name: projectId\n        description: Project identifier\n        required: true\n      - name: topicType\n        description: Filter by issue type\n        required: false\n      - name: topicStatus\n        description: Filter by status (OPEN, IN_PROGRESS, RESOLVED, CLOSED)\n        required: false\n      - name: assignedTo\n        description: Filter by assignee\n        required: false\n\n  - name: update-issue-status\n\
  \    description: Update the status or assignee of a BCF topic to track resolution progress\n    operationRef: trimble-connect/updateBCFTopic\n    inputs:\n      - name: projectId\n        description: Project identifier\n        required: true\n      - name: topicGuid\n        description: BCF topic GUID\n        required: true\n      - name: topicStatus\n        description: \"New status: OPEN, IN_PROGRESS, RESOLVED, CLOSED\"\n        required: false\n      - name: assignedTo\n        description: New assignee email or user ID\n        required: false\n\n  - name: list-team-members\n    description: List all team members and their roles on a Trimble Connect project\n    operationRef: trimble-connect/listProjectMembers\n    inputs:\n      - name: projectId\n        description: Project identifier\n        required: true\n\n  - name: invite-team-member\n    description: Add a new member to a Trimble Connect project with a specified role\n    operationRef: trimble-connect/addProjectMember\n\
  \    inputs:\n      - name: projectId\n        description: Project identifier\n        required: true\n      - name: email\n        description: Email address of the user to invite\n        required: true\n      - name: role\n        description: \"Project role: VIEWER, CONTRIBUTOR, MANAGER, ADMIN\"\n        required: true\n\nadapters:\n  rest:\n    port: 8080\n    basePath: /bim-collaboration\n\n  mcp:\n    port: 9090\n    serverName: bim-collaboration\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trimble/refs/heads/main/capabilities/bim-collaboration.yaml
tags: []
tools: []
---
