---
api_specs:
- filename: sourceforge-allura-openapi.yml
  format: yaml
  label: sourceforge-api
  slug: sourceforge-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sourceforge/refs/heads/main/openapi/sourceforge-allura-openapi.yml
categories: []
consumed_apis:
- sourceforge-api
description: Unified capability for managing open source projects on SourceForge. Enables project maintainers, contributors, and community managers to programmatically manage issues, wikis, discussions, blogs, and repository webhooks through the SourceForge Allura REST API.
layout: capability
name: SourceForge Project Management
operations:
- description: Get details for a SourceForge project
  method: GET
  name: get-project
  path: /v1/projects/{project}
- description: List all tickets in the project tracker
  method: GET
  name: list-tickets
  path: /v1/projects/{project}/tickets
- description: Create a new issue or bug report
  method: POST
  name: create-ticket
  path: /v1/projects/{project}/tickets
- description: Search tickets with query filtering
  method: GET
  name: search-tickets
  path: /v1/projects/{project}/tickets/search
- description: List all wiki pages for a project
  method: GET
  name: list-wiki-pages
  path: /v1/projects/{project}/wiki
- description: Get a specific wiki page by title
  method: GET
  name: get-wiki-page
  path: /v1/projects/{project}/wiki/{title}
- description: List webhooks for a project tool
  method: GET
  name: list-webhooks
  path: /v1/projects/{project}/webhooks
personas: []
provider_name: SourceForge
provider_slug: sourceforge
search_terms:
- list webhooks for a project tool
- get details about a sourceforge project including its description, tools, and metadata. use to understand a project before performing operations.
- issue tracking
- repository webhook management
- search tickets with query filtering
- wiki
- list project issues
- list all wiki pages for a project. use to discover available documentation and project resources.
- open source
- create a new bug report or feature request in a project tracker. use for automated issue filing from monitoring systems or ci/cd pipelines.
- list wiki pages
- retrieve a specific wiki page from a project. use to read project documentation, installation guides, or release notes.
- get details for a sourceforge project
- search issues in a project tracker with text queries. use to find specific bugs, features, or tickets by keyword.
- create ticket
- ticket search
- get wiki page
- developer tools
- create a new issue or bug report
- create project issue
- get project info
- sourceforge
- list all wiki pages for a project
- wiki page access
- search tickets
- get a specific wiki page by title
- list all tickets in the project tracker
- search project issues
- project management
- individual wiki page
- list tickets
- code hosting
- issue and bug tracking
- project information and management
- get project
- list webhooks
- list all issues and bug reports in a project tracker. use for project health assessment and triage workflows.
- collaboration
- list project webhooks
- list webhooks configured for a project tool. use to audit repository integrations and ci/cd pipeline connections.
slug: project-management
source_filename: project-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SourceForge Project Management\"\n  description: >-\n    Unified capability for managing open source projects on SourceForge. Enables\n    project maintainers, contributors, and community managers to programmatically\n    manage issues, wikis, discussions, blogs, and repository webhooks through the\n    SourceForge Allura REST API.\n  tags:\n    - SourceForge\n    - Open Source\n    - Project Management\n    - Issue Tracking\n    - Wiki\n    - Collaboration\n    - Developer Tools\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SOURCEFORGE_BEARER_TOKEN: SOURCEFORGE_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: sourceforge-api\n      location: ./shared/sourceforge-allura.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sourceforge-project-mgmt-api\n      description: \"Unified REST API for SourceForge open source project management.\"\n     \
  \ resources:\n        - path: /v1/projects/{project}\n          name: projects\n          description: Project information and management\n          operations:\n            - method: GET\n              name: get-project\n              description: Get details for a SourceForge project\n              call: \"sourceforge-api.get-project\"\n              with:\n                project: \"rest.project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{project}/tickets\n          name: tickets\n          description: Issue and bug tracking\n          operations:\n            - method: GET\n              name: list-tickets\n              description: List all tickets in the project tracker\n              call: \"sourceforge-api.list-tickets\"\n              with:\n                project: \"rest.project\"\n                tracker: \"rest.tracker\"\n                page: \"rest.page\"\n                limit:\
  \ \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-ticket\n              description: Create a new issue or bug report\n              call: \"sourceforge-api.create-ticket\"\n              with:\n                project: \"rest.project\"\n                tracker: \"rest.tracker\"\n                summary: \"rest.summary\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{project}/tickets/search\n          name: ticket-search\n          description: Ticket search\n          operations:\n            - method: GET\n              name: search-tickets\n              description: Search tickets with query filtering\n              call: \"sourceforge-api.search-tickets\"\n              with:\n                project: \"rest.project\"\n   \
  \             tracker: \"rest.tracker\"\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{project}/wiki\n          name: wiki\n          description: Wiki page access\n          operations:\n            - method: GET\n              name: list-wiki-pages\n              description: List all wiki pages for a project\n              call: \"sourceforge-api.list-wiki-pages\"\n              with:\n                project: \"rest.project\"\n                wiki: \"rest.wiki\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{project}/wiki/{title}\n          name: wiki-page\n          description: Individual wiki page\n          operations:\n            - method: GET\n              name: get-wiki-page\n              description: Get a specific wiki page by title\n              call: \"sourceforge-api.get-wiki-page\"\
  \n              with:\n                project: \"rest.project\"\n                wiki: \"rest.wiki\"\n                title: \"rest.title\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{project}/webhooks\n          name: webhooks\n          description: Repository webhook management\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: List webhooks for a project tool\n              call: \"sourceforge-api.list-webhooks\"\n              with:\n                project: \"rest.project\"\n                tool: \"rest.tool\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sourceforge-project-mgmt-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SourceForge open source project management.\"\n      tools:\n        -\
  \ name: get-project-info\n          description: >-\n            Get details about a SourceForge project including its description, tools,\n            and metadata. Use to understand a project before performing operations.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sourceforge-api.get-project\"\n          with:\n            project: \"tools.project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-project-issues\n          description: >-\n            List all issues and bug reports in a project tracker. Use for project\n            health assessment and triage workflows.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sourceforge-api.list-tickets\"\n          with:\n            project: \"tools.project\"\n            tracker: \"tools.tracker\"\n            page: \"tools.page\"\n            limit: \"tools.limit\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: search-project-issues\n          description: >-\n            Search issues in a project tracker with text queries. Use to find\n            specific bugs, features, or tickets by keyword.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sourceforge-api.search-tickets\"\n          with:\n            project: \"tools.project\"\n            tracker: \"tools.tracker\"\n            q: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-project-issue\n          description: >-\n            Create a new bug report or feature request in a project tracker.\n            Use for automated issue filing from monitoring systems or CI/CD pipelines.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sourceforge-api.create-ticket\"\
  \n          with:\n            project: \"tools.project\"\n            tracker: \"tools.tracker\"\n            summary: \"tools.summary\"\n            description: \"tools.description\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-wiki-page\n          description: >-\n            Retrieve a specific wiki page from a project. Use to read project\n            documentation, installation guides, or release notes.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sourceforge-api.get-wiki-page\"\n          with:\n            project: \"tools.project\"\n            wiki: \"tools.wiki\"\n            title: \"tools.title\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-wiki-pages\n          description: >-\n            List all wiki pages for a project. Use to discover available documentation\n\
  \            and project resources.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sourceforge-api.list-wiki-pages\"\n          with:\n            project: \"tools.project\"\n            wiki: \"tools.wiki\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-project-webhooks\n          description: >-\n            List webhooks configured for a project tool. Use to audit repository\n            integrations and CI/CD pipeline connections.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sourceforge-api.list-webhooks\"\n          with:\n            project: \"tools.project\"\n            tool: \"tools.tool\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sourceforge/refs/heads/main/capabilities/project-management.yaml
tags:
- SourceForge
- Open Source
- Project Management
- Issue Tracking
- Wiki
- Collaboration
- Developer Tools
tools:
- description: Get details about a SourceForge project including its description, tools, and metadata. Use to understand a project before performing operations.
  hints:
    openWorld: true
    readOnly: true
  name: get-project-info
- description: List all issues and bug reports in a project tracker. Use for project health assessment and triage workflows.
  hints:
    openWorld: false
    readOnly: true
  name: list-project-issues
- description: Search issues in a project tracker with text queries. Use to find specific bugs, features, or tickets by keyword.
  hints:
    openWorld: false
    readOnly: true
  name: search-project-issues
- description: Create a new bug report or feature request in a project tracker. Use for automated issue filing from monitoring systems or CI/CD pipelines.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-project-issue
- description: Retrieve a specific wiki page from a project. Use to read project documentation, installation guides, or release notes.
  hints:
    openWorld: true
    readOnly: true
  name: get-wiki-page
- description: List all wiki pages for a project. Use to discover available documentation and project resources.
  hints:
    openWorld: false
    readOnly: true
  name: list-wiki-pages
- description: List webhooks configured for a project tool. Use to audit repository integrations and CI/CD pipeline connections.
  hints:
    openWorld: false
    readOnly: true
  name: list-project-webhooks
---
